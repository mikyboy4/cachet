# Cachet

Cachet client

## About Cachet

Cachet is an open source status page system written in PHP. https://github.com/CachetHQ/Cachet

## Usage

Setup

```php
$client = new Client('https://demo.cachethq.io/api/v1/', '9yMHsdioQosnyVK4iCVR');
```

### Components

Get components

```php
$components = $client->getComponents();

foreach ($components as $component) {
    echo $component->getName();
}
```

Sorting

```php
$components = $client->getComponents([
    'sort' => 'id',
    'order' => 'desc'
]);
```

Get by id

```php
$component = $client->getComponent(3);
```

Creating new component

```php
$component = new Component();
$component->setName('My new component');
$component->setDescription('Component description');
$component->setLink('https://github.com/mangati/cachet');
$component->setStatus(Component::STATUS_OPERATIONAL);

$client->addComponent($component);
```

Updating existing component

```php
$component = new Component();
$component->setId(3);
$component->setName('My new component (updated)');

$client->updateComponent($component);
```

Deleting existing component

```php
$id = 3;

$client->deleteComponent($id);
```


### Incidents

Get incidents

```php
$incidents = $client->getIncidents();

foreach ($incidents as $incident) {
    echo $incident->getName();
}
```

Sorting

```php
$components = $client->getIncidents([
    'sort' => 'id',
    'order' => 'desc'
]);
```

Get by id

```php
$incident = $client->getIncident(3);
```

Creating new incident

```php
$incident = new Incident();
$incident->setName('My new incident');
$incident->setMessage('incident message');
$incident->setStatus(Incident::STATUS_WATCHING);

$client->addIncident($$incident);
```

Updating existing incident

```php
$incident = new Incident();
$incident->setId(3);
$incident->setStatus(Incident::STATUS_FIXED);

$client->updateIncident($incident);
```

Deleting existing incident

```php
$id = 3;

$client->deleteIncident($id);
```
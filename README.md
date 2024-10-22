## About Project

Laravel over tenancyforlaravel

- [Laravel](https://laravel.com/docs/11.x#herd-on-macos).
- [Tenancy](https://tenancyforlaravel.com/docs/v3/quickstart/).

## Tenants

- [Foo](http://foo.tenancyforlaravel.test/)
- [Bar](http://bar.tenancyforlaravel.test/)


## Create tenants in Tinker

```php

$tenant1 = App\Models\Tenant::create(['id' => 'foo']);
$tenant1->domains()->create(['domain' => 'foo.tenancyforlaravel.test']);

$tenant2 = App\Models\Tenant::create(['id' => 'bar']);
$tenant2->domains()->create(['domain' => 'bar.tenancyforlaravel.test']);

App\Models\Tenant::all()->runForEach(function () {
    App\Models\User::factory()->create();
});


```

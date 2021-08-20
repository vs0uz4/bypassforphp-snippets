# Bypass for PHP Snippets

Code snippets for writing tests for PHP using [Bypass for PHP](https://bypassforphp.com/) in Visual Studio Code.

## Usage

### Writing Tests

To write a test, you first need to open the Bypass Server.

#### Opening Server
Bypass provides two fuctions for opening server `open()` and `serve()`.

Type `:bopen` + [TAB] for:

```php
Bypass::open();
```

Type `:bserv` + [TAB] for:

```php
Bypass::serve(
    //Route::
);
```

#### Get Base URL and/or Port

Type `:bburl` + [TAB] for:

```php
->getBaseUrl();
```

Type `:bport` + [TAB] for:

```php
->getPort();
```

#### Stop and Shut down

Type `:bstop` + [TAB] for:

```php
->stop();
```

Type `:bdown` + [TAB] for:

```php
->down();
```

#### Adding Routes (Standard and File) 

Bypass Server provides two types of routes: `Standard Routes` and `File Routes`. 

For standard routes the bypass provides the `addRoute()` method. This method has an alias, called `expect()`.

Type `:baro` + [TAB] for:

```php
->addRoute(method: '', uri: '', status: , body: );
```

Type `:bexp` + [TAB] for:

```php
->expect(method: '', uri: '', status: , body: );
```

For File routes:

Type `:bafr` + [TAB] for:

```php
->addFileRoute(method: '', uri: '', status: , file: );
```

#### Asserting Routes

Type `:bass` + [TAB] for:

```php
->assertRoutes();
```

### Route Helpers

When we use the `serve()` method to open a bypass server, it expects us to pass it routes. And for this, Bypass offers us the route helpers.

After opening the Bypass server by typing `:bserv`, finish adding the desired route.

Example: Type `:brok` + [TAB] produces:

```php
Bypass::serve(
    Route::ok(method: '', uri: '', body: '', times: )
    ..
);
```

Available `Route::` methods:

| Trigger         | Snippet          |
| --------------- | ---------------- |
| :brok           | Route::ok(method: '', uri: '', body: '', times: ) |
| :brbadrequest   | Route::badRequest(method: '', uri: '', body: '', times: ) |
| :brunauthorized | Route::unauthorized(method: '', uri: '', body: '$', times: ) |
| :brforbidden    | Route::forbidden(method: '', uri: '', body: '', times: ) |
| :brcreated      | Route::created(uri: '', body: '', times: ) |
| :brnotfound     | Route::notFound(method: '', uri: '', body: '', times: ) |
| :brnotallowed   | Route::notAllowed(method: '', uri: '', body: '', times: ) |
| :brtoomany      | Route::tooMany(method: '', uri: '', body: '', times: ) |
| :brservererror  | Route::serverError(method: '', uri: '', body: '', times: ) |
| :brvalidationfailed | Route::validationFailed(method: '', uri: '', body: '', times: ) |
| :brfile    | Route::file(method: '', uri: '', file: '', status: , times: ) |
| :brget     | Route::get(uri: '', body: '', status: , times: ) |
| :brgetfile | Route::getFile(uri: '', file: '', status: , times: ) |
| :brpost    | Route::post(uri: '', body: '', status: , times: ) |
| :brput     | Route::put(uri: '', body: '', status: , times: ) |
| :brdelete  | Route::delete(uri: '', body: '', status: , times: ) |
| :brpatch   | Route::patch(uri: '', body: '', status: , times: ) |

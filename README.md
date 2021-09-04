# React for PHP

React-like library for component based development in PHP.

## Usage

```php
class MyComponent extends \React\Component {
  static function render($props = []) {
    ?>
    <p>This is the message: <?= $props['msg'] ?></p>
    <?php
  }
}

class MyOtherComponent extends \React\Component {
  static function render($props = []) {
    ?>
    <div>
      <?php self::render_children($props['children']) ?>
    </div>
    <?php
  }
}

// Basic
MyComponent::render(['msg' => 'Hello World!']);

// Nested
MyOtherComponent::render([
  'children' => [
    new MyComponent(['msg' => 'First child']),
    new MyComponent(['msg' => 'Second child']),
  ]
]);
```

I recommend using [webpack](https://github.com/webpack/webpack) so you can colocate both back end and front end code of each component in the same directory.
The structure for a generic project could look like this:

```
.
└── src
    ├── MyComponent
    │   ├── Component.php
    │   ├── index.js
    │   └── style.css
    ├── MyOtherComponent
    │   ├── Component.php
    │   ├── index.js
    │   └── style.css
    └── index.js
```

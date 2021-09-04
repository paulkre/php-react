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

MyComponent::render(['msg' => 'Hello World!'])
```

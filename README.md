# Timber Snippets

![Visual Studio Marketplace Downloads](https://img.shields.io/visual-studio-marketplace/d/jdcreations.timber-snippets?color=%234D8AB3&label=VS%20Marketplace%20Downloads)
![GitHub](https://img.shields.io/github/license/Jdevx97/Timber-Snippets?color=rgb%2854%2C%20237%2C%2017%29)

Timber Snippets is a VS Code Extension built to speed up development workflow with the Timber + Twig framework, providing simple, reliable snippets for common [Timber.](https://timber.github.io/docs) methods.

All snippets are prefixed with `ts` (Timber Snippets).

## Snippets

| Snippet  | Purpose                                     |
| -------- | ------------------------------------------- |
| tsctxt   | Retrieve Timber Context                     |
| tsnew    | New Timber Instance (Post, Menu, Term)      |
| tsrender | Simple Timber Context Render.               |
| tsarndr  | Advanced Timber Context Render.             |
| tsuesc   | Universal timnber Escaping                  |
| tsext    | Extend a Timber API                         |
| tsnmenu  | Setup a Timber Menu                         |
| tsnamenu | Advanced Timber Menu Setup                  |
| tswoosup | Enable Woocommerce Theme Support for Timber |
| tsroute  | Timber Routing                              |

## Examples

### `tsctxt`

This snippet outputs a setup for retrieving the Timber Context, it allows two options

*Usage:*

`tsctxt` => `$context = Timber::context();`

`tsctxt` => `$context = Timber::get_context();`

### `tsnew`

tsnew renders output for assigning a context key to `Timber\Post()`, `Timber\Term()`, or `Timber\Menu()`.

`tsnew` => `$context['post'] = new Timber\Post();`

`tsnew` => `$context['post'] = new Timber\Term();`

`tsnew` => `$context['post'] = new Timber\Menu();`

### `tsrender`

tsrender converts to the `Timber::render` method.

`tsrender` => `Timber::render('example.twig', $context);`

### `tsarndr`

tsarndr converts to a more advanced `Timber::render` method, implementing a basis for dynamic rendering based on a components post name.

`tsarnr => Timber::render( array( 'post-' . post->post_name . '.twig', 'page.twig' ), $context );`

### `tsuesc`

tsuesc converts to the standard output for universal timber escaping.

`tsuesc => if( class_exists('Timber') ) { Timber::autoescape = 'html'; }`

### `tsext`

tsext is a basis for implementating a class that extends an instance of Timber.

`tsext => class MySitePost extends Timber\Post`

[All Extension Options](https://timber.github.io/docs/reference/)

### `tsnmenu`

Simple Timber menu output.

`tsnmenu => $context['primary-menu'] = new Timber\Menu( 'primary-menu' );`

### `tsnamenu`

Advanced Timber Menu Output. (Args printed above)

```
$args = array(
  'depth' =>
);

$context['primary-menu'] = new Timber\Menu( 'primary-menu', $args );
```

### `tswoosup`

Implements Timber support for Woocommerce.

```
function theme_add_woocommerce_support() {
  add_theme_support("woocommerce");
}

add_action('after_setup_theme','theme_add_woocommerce_support');
````
### `tsroute`

Outputs Timber Routing setup.

```
Routes::map('info/:name'), function($params) {
  $query =
  Routes::load('archive.php', null, $qry, 200);
});
```

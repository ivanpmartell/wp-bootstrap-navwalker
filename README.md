# Sage Wordpress Bootstrap Navwalker

## Installation

To install, run the following in your Sage9-based theme directory:
```bash
composer require "ivanpmartell/wp-bootstrap-navwalker"
```

In your 'header.blade.php'
```php
<header class="header">
  <nav class="navbar navbar-expand-md navbar-dark bg-dark" role="navigation">
    <div class="container">
    <!-- Brand and toggle get grouped for better mobile display -->
    <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#bs-example-navbar-collapse-1" aria-controls="bs-example-navbar-collapse-1" aria-expanded="false" aria-label="Toggle navigation">
      <i class="fas fa-bars"></i>
    </button>
    <a class="navbar-brand" href="#">brand</a>
      <?php
      wp_nav_menu( array(
        'theme_location'    => 'primary_navigation',
        'depth'             => 2,
        'container'         => 'div',
        'container_class'   => 'collapse navbar-collapse',
        'container_id'      => 'bs-example-navbar-collapse-1',
        'menu_class'        => 'nav navbar-nav',
        'fallback_cb'       => 'WP_Bootstrap_Navwalker::fallback',
        'walker'            => new WP_Bootstrap_Navwalker(),
      ) );
      ?>
    </div>
  </nav>
</header>
```

You might need to add fontawesome bars for the toggler
```bash
yarn add @fortawesome/fontawesome-free-solid
```

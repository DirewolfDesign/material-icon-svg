# Material SVG Icons

Just a quick library of some material icons in svg format. Feel free to drop them into your project!

---

## Usage

All icons can be found in the `icons` directory.

We've done our best to divide the icons up into categories to make it easier to find the icons you need and all icons come in a preset 24 x 24px `viewbox`.

How you use the files is up to you, just ***use them for good, not evil!***

---

## Examples (PHP)

### Get all icons
```
<?php

// Get the `icons` directory (relative to this file)
$dir = dirname( __FILE__ ) . '/icons';

// Get all icons
foreach( glob( "$dir/**/*.svg" ) as $filename ) :

    $iconName = basename( $filename, '.svg' );
    $iconCategory = basename( dirname( $filename ) );
    $svg = file_get_contents( $filename );

    // Do something with the icon...

endforeach;
```

### Get all icons in category
```
<?php

// Get the `icons` directory (relative to this file)
$dir = dirname( __FILE__ ) . '/icons';

// Get all icons in category
function get_category_icons( $category ) {
    foreach( glob( "$dir/$category/*.svg" ) as $filename ) :

        $iconName = basename( $filename, '.svg' );
        $iconCategory = basename( dirname( $filename ) );
        $svg = file_get_contents( $filename );

        // Do something with the icon...

    endforeach;
}

// Get all `device` icons
$categoryIcons = get_category_icons( 'device' );
```

### Get specific icon
```
<?php

// Get the `icons` directory (relative to this file)
$dir = dirname( __FILE__ ) . '/icons';

// Get specific icon in category
function get_icon( $icon, $category ) {
    $filename = "$dir/$category/$icon.svg";

    if( file_exists( $filename ) )
        return array(
            'name' => $icon,
            'category' => $category,
            'svg' => file_get_contents( $filename )
        }
}

// Get the `bluetooth` icon from the `device` category
$icon = get_icon( 'bluetooth', 'device' );
```

## Support

Like this package? Consider buying us a coffee on Ko-Fi!

<a href='https://ko-fi.com/R6R640ZDZ' target='_blank'><img height='36' style='border:0px;height:36px;' src='https://cdn.ko-fi.com/cdn/kofi4.png?v=2' border='0' alt='Buy Me a Coffee at ko-fi.com' /></a>

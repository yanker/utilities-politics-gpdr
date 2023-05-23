# Politics GPDR

Sample politics GPDR for yours projects

## Description

This project is a example of politics GPDR. This files has default text about this politics GPDR.
This sample use bootstrap for base template.

## Getting Started

### Dependencies

* Download repository only

### Installing

* Download repository
* Edit assets/plugins/politics/config for indicate data for your company
* Add in htaccess url-friends for access politics
```
<IfModule mod_rewrite.c>

  # Activar RewriteEngine
    RewriteEngine on

  # Políticas de Privacidad & Cookies
    RewriteRule ^politicas/(.+)/?$ index.php?typePolitics=$1 [NC,L]
    
</IfModule>
```
* Insert this code in page where you need politics (you can do function but it´s not necessary)
```
<!-- Insert in Page Politics Projects -->
    <?php
        switch (strtolower($_GET['typePolitics'])) {
            case 'politica-privacidad':
            case 'politica-cookies':
            case 'politica-avisolegal':
                $nameFilePolitic = strtolower($_GET['typePolitics']);
                break;
            default:
                $nameFilePolitic = '';
                break;
        }

    if (empty($nameFilePolitic)) { ?>
        <h1 class="text-body-emphasis">GPDR Politics Template</h1>
        <p class="fs-5 col-md-8">This project is a example of politics GPDR. This files has default text about this politics GPDR. This sample use bootstrap for base template.</p>
    <?php } else { ?>
        <p class="fs-5 col-md-8">
            <?php
            // Print Politics
            include('assets/plugins/politics/' . $nameFilePolitic . '.php');
            ?>
        </p>
    <?php } ?>
<!-- Insert in Page Politics Projects -->
```

## Version History

* 1.0
    * Initial Release (23/05/2023)

## References

Inspiration, code snippets, etc.
* [bootstrap](https://getbootstrap.com/)
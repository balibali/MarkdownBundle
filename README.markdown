Provide markdown conversion to your Symfony2 projects.

## INSTALLATION

Put MarkdownBundle in your `src/Bundle` dir.

Then enable it in your `config.yml`:

    markdown.parser: ~      # Enable the parser service
    markdown.helper: ~      # Enable the helper in the templates

Optionnally enable the twig markdown filter :

    twig.config: ~          # Enable Twig
    markdown.twig: ~        # Enable the markdown filter

You can also define your own Parser class :

    markdown.parser:
        class: Bundle\HelloBundle\MarkdownParser

## USAGE

    // Use the service
    $html = $this->container['markdownParser']->transform($text);

    // Use the helper
    echo $view['markdown']->transform($text);

If you have enabled the twig markdown filter, you can use the following in your twig templates:

    {{ my_data | markdown }}

## TEST

    phpunit -c myapp src/Bundle/MarkdownBundle

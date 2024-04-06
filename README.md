# Use Twig template engine with Xaraya

Xaraya has been using Blocklayout for templates since the early days. The [Twig bridge](https://github.com/xaraya/core/blob/com.xaraya.core.bermuda/html/lib/xaraya/bridge/README.md#twig-template-engine) included in Xaraya core allows you to use Twig-based templates to generate output in Xaraya if needed, with a number of Xaraya-specific extensions.

This repository contains the Twig templates converted from Blocklayout for different modules, blocks, properties and themes.

## Twig Namespaces

In general `modules` templates are mapped to their equivalent `@modname` namespace. To avoid overlap (with the themes or blocks modules), `themes`, `properties` and `blocks` templates use the singular equivalent `@theme`, `@property` and `@block` namespace.

| Component | Namespace | Templates |
|-----------|-----------|----------|
| Module | @base | html/code/modules/base |
| Module | @dynamicdata | html/code/modules/dynamicdata |
| Module | ... | ... |
| Theme | @theme | html/themes |
| Property | @property | html/code/properties |
| Block | @block | html/code/blocks |

## Xaraya Twig Extensions

Since Blocklayout allows significant PHP processing in templates and Twig deliberately does not, many of the common API calls to static core methods have been made available as Twig functions.
Similarly, most Blocklayout and Xaraya tags have their equivalent Twig functions too.

This made translation of all templates from Blocklayout to Twig feasible, but for future template development we highly recommend to prepare all needed template variables up-front in the PHP functions, and then pass them along to the template as intended.

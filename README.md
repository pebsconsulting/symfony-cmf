# Symfony Content Management Framework

## Mission Statement

The Symfony CMF project makes it easier for **developers** to add **CMS functionality** to applications built with the **Symfony2 PHP** framework. Key development principles for the provided **set of bundles** are **scalability**, **usability**, **documentation** and **testing**.


## Links

- GitHub: <https://github.com/symfony-cmf/symfony-cmf>
- Sandbox: <https://github.com/symfony-cmf/cmf-sandbox>
- Web: <http://cmf.symfony-project.org/>
- Wiki: <http://github.com/symfony-cmf/symfony-cmf/wiki>
- Issue Tracker: <http://cmf.symfony-project.org/redmine/>
- IRC: irc://freenode/#symfony-cmf
- Users mailing list: <http://groups.google.com/group/symfony-cmf-users>
- Devs mailing list: <http://groups.google.com/group/symfony-cmf-devs>


## Installation

This is the main repository containing all bundles you need for the CMF.

### Prerequisites

You need to install [Doctrine PHPCR ODM](http://github.com/doctrine/phpcr-odm) according to the install instructions.

### Setup

* Add this repository to your vendors
* Make sure to run ```git submodule update --recursive --init``` inside the symfony-cmf folder after each vendor update (we add this to the vendors script)
* Add autoloader entries ( *before* the line registering Symfony itself )

    'Symfony\\Cmf'                          => __DIR__.'/../vendor/symfony-cmf/src',
    'Symfony\\Bundle\\DoctrinePHPCRBundle'  => __DIR__.'/../vendor/symfony-cmf/src',
    'Doctrine\\ODM\\PHPCR'                  => __DIR__.'/../vendor/doctrine-phpcr-odm/lib',
    'Jackalope'                             => __DIR__.'/../vendor/doctrine-phpcr-odm/lib/vendor/jackalope/src',
    'PHPCR'                                 => __DIR__.'/../vendor/doctrine-phpcr-odm/lib/vendor/jackalope/lib/phpcr/src',

* Initialize bundles in the Kernel registerBundle method

    new Symfony\Bundle\DoctrinePHPCRBundle\DoctrinePHPCRBundle(),
    new Symfony\Cmf\Bundle\CoreBundle\SymfonyCmfCoreBundle(),
    new Symfony\Cmf\Bundle\MultilangContentBundle\SymfonyCmfMultilangContentBundle(),
    new Symfony\Cmf\Bundle\NavigationBundle\SymfonyCmfNavigationBundle(),
    new Symfony\Cmf\Bundle\ContentBundle\SymfonyCmfContentBundle(),
    new Symfony\Cmf\Bundle\PhpcrCommandsBundle\PhpcrCommandsBundle(),


### Note

Some of the bundles are additionally exported into separate repository in case
you want to use only a specific bundle. Browse https://github.com/symfony-cmf/
to see which are available. If you miss one, please contact us and explain why
it should be available stand-alone.


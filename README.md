# EoHoneypotBundle

Honeypot for Symfony2 forms.

## What is Honey pot?
> A honey pot trap involves creating a form with an extra field that is hidden to human visitors but readable by robots.
> The robot fills out the invisible field and submits the form, leaving you to simply ignore their spammy submission or blacklist their IP.
> It’s a very simple concept that can be implemented in a few minutes and it just works – add them to your contact and submission forms to help reduce spam.

## Prerequisites
This version of the bundle requires Symfony 2.1+

## Installation

### Step 1: Download EoHoneypotBundle using composer
Add EoHoneypotBundle in your composer.json:
```
{
    "require": {
        "eo/honeypot-bundle": "dev-master"
    }
}
```

Now tell composer to download the bundle by running the command:
```
$ php composer.phar update eo/honeypot-bundle
```
Composer will install the bundle to your project's vendor/eo directory.

### Step 2: Enable the bundle
Enable the bundle in the kernel:
```
<?php
// app/AppKernel.php

public function registerBundles()
{
    $bundles = array(
        // ...
        new Eo\HoneypotBundle\EoHoneypotBundle(),
    );
}
```

### There is no step 3

## Usage
Once installed and configured you can start using `honeypot` type in your forms.

### Example usage:
```
<?php

namespace Acme\DemoBundle\Form\Type;

use Symfony\Component\Form\AbstractType;
use Symfony\Component\Form\FormBuilderInterface;

class FooType extends AbstractType
{
    public function buildForm(FormBuilderInterface $builder, array $options)
    {
        $builder->add('name', 'text');
        $builder->add('email', 'text');

        // Honeypot field
        $builder->add('SOME-FAKE-NAME', 'honeypot');
    }

    public function getName()
    {
        return 'foo';
    }
}
```

## License
This bundle is under the MIT license. See the complete license in the bundle:
```
Resources/meta/LICENSE
```

## Reporting an issue or a feature request
Issues and feature requests related to this bundle are tracked in the Github issue tracker https://github.com/eymengunay/EoHoneypotBundle/issues.

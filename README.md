## Locale Extensions for Twig

### Installation

The extension is installable via composer:

`composer require anezi/locale-extension`

### Symfony service

```yaml
services:
    anezi_twig.locale_extension:
        class: Anezi\Locale\Twig\Extension\LocaleExtension
        public:    false
        arguments: ["%managed_locales%"]
        tags:
            - { name: twig.extension }

```

### Functions

#### Get locales

`{% for locale in locales() %}{{ locale }} - {% endfor %}`

shows:

**ar - en - fr -** 

### Filters

#### Get country name

`{{ "be"|country_name }}`

shows:

**Belgium**

#### Get locale name

`{{ "fr_BE"|locale_name }}`

shows:

**French (Belgium)**

#### Get locale name in that locale

`{{ "fr_BE"|origin_locale_name }}`

shows:

**français (Belgique)**

#### Get locale short name

`{{ "fr_BE"|locale_short_name }}`

shows:

**fr**

#### Get html direction

`{{ "ar"|html_dir }}`

shows:

**rtl**

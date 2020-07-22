# Intro

This is my bootstrap/setup for Drupal with all the required config and modules enabled for development.

## Installation

Use the [ddev](https://ddev.readthedocs.io/en/stable/) to install foobar.

Instructions to install ddev can be found on their official [documentation](https://ddev.readthedocs.io/en/stable/).

Clone the site. cd into the site.

1. Run

```bash
ddev config
```
(Follow the on-screen instructions)

2. Run `ddev composer install`

(If required)Sometimes ddev doesn't create an entry of the hostname, so I run this command.

```bash
sudo ddev hostname sitename.ddev.site 127.0.0.1
```

3. Install the site.

```bash
ddev exec drush site-install --account-name=admin --account-pass=admin
```

4. Let's set up the UUID for the site.

```bash
ddev exec drush cset system.site uuid d42d4143-3157-4dae-b083-ab0e1b10d644
```

5. Sync up the config and clear up the cache. Follow the Troubleshoot section if you face any issues here.

```bash
ddev exec drush cim -y && ddev exec drush cr
```

## Troubleshoot
If you get the following error, which you will surely just go to `/admin/config/user-interface/shortcut/manage/default/customize` and delete all the shortcut entries.

```bash
The import failed due to the following reasons:
  Entities exist of type <em class="placeholder">Shortcut link</em> and <em class="placeholder
  ">Shortcut set</em> <em class="placeholder">Default</em>. These entities need to be deleted
  before importing.
```

## Contributing
Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.




# heroku-php-app-buildpack
You want to run generic PHP applications on heroku? That's what this custom buildpack is for! Just add it to your project and point it to your application source ZIP file, and off we go.

## Installation
**1. Create your heroku app**

If you don't already have an heroku app, create a new one. If you do, you can of course use your existing one with this buildpack, too.

---
**2. Configure the required buildpacks**

This buildpack works in combination with the corresponding buildpack to run your application code. For example, when running an external PHP app, you could use it together with `heroku/php`. The minimal configuration would be adding the following buildpack to your application:

    https://github.com/janxb/heroku-zipped-app-buildpack.git
    
*(Hint: The order is important, always place the custom buildpack at the top)*

---
**3. Create the required environment variables**

|Property Name|Example Value|Description|
|---|---|---|
| `APP_ARCHIVE` | `https://github.com/invoiceninja/invoiceninja/archive/v4.5.9.zip` | Release ZIP-file URL, manually increment for each update |

---
**4. Updating your application**

Because heroku does not offer persistent application storage, your hosted application is not able to automatically update itself. Instead, you have to edit the `APP_ARCHIVE` property manually and then trigger a new deployment in the heroku web interface. This should take no longer than a few minutes.
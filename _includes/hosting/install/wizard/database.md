## 2.{{ include.stepNumber }}{% assign include.stepNumber = include.stepNumber | plus:1 %}. Database

Passbolt {{ page.card_title }} comes with a preinstalled mariadb database. The credentials for
this database are randomly generated on the first boot and the webinstaller autofills
those credentials for you. The autogenerated database credentials will be
available for later use by administrators in `/etc/passbolt/passbolt.php` file.

If you decide to use the autogenerated credentials you
can click the "Next" button and move to the next step on this tutorial.

{% if product == 'pro' %}
{% include articles/figure.html url="/assets/img/help/2021/02/web-installer-pro-database.png" legend="wizard - database" width="586px" %}
{% else %}
{% include articles/figure.html url="/assets/img/help/2021/02/web-installer-ce-database.png" legend="wizard - database" width="586px" %}
{% endif %}

**Optional:** in case you do not want to use the autogenerated mariadb
credentials you could connect through ssh to your instance
and use the mariadb root credentials to create a new
user, password and database for passbolt to use:

```
ssh admin@<your_domain|instance_ip>
```

You can find the root database credentials in `/root/.mysql_credentials` file:

```
sudo cat /root/.mysql_credentials
```

Once you have the root database credentials you can connect to the local mariadb
and create any database and user you want to use to install passbolt.

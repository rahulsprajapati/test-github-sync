---
ID: 104
post_title: Admin Tools
author: rahul
post_excerpt: ""
layout: post
permalink: https://rahulprajapati.me/admin-tools/
published: true
post_date: 2018-12-13 19:32:19
---
<!-- wp:paragraph --> In EasyEngine v4, we have support for following tools to help site administrators. 

<!-- /wp:paragraph -->

<!-- wp:paragraph --> These admin-tools needs to be enabled/disabled per site. By default they are disabled.  

<!-- /wp:paragraph -->

<!-- wp:paragraph --> DATA 

<!-- /wp:paragraph -->

<!-- wp:heading -->

## Usage

<!-- /wp:heading -->

<!-- wp:paragraph --> In order to use the admin-tools, you must first enable them using 

<!-- /wp:paragraph -->

<!-- wp:code -->

<pre class="wp-block-code"><code>ee admin-tools enable example.com</code></pre>

<!-- /wp:code -->

<!-- wp:paragraph --> By default, we enable auth on admin-tools. To view username/password with which you can login, run 

<!-- /wp:paragraph -->

<!-- wp:code -->

<pre class="wp-block-code"><code>ee auth list global</code></pre>

<!-- /wp:code -->

<!-- wp:paragraph --> Then navigate to 

`example.com/ee-admin/` in the browser. There you'll see a list of admin-tools. <!-- /wp:paragraph -->

<!-- wp:heading -->

## List Of Admin Tools

<!-- /wp:heading -->

<!-- wp:table -->

<table class="wp-block-table">
  <tbody>
    <tr>
      <td>
        <strong>Admin Tools</strong>
      </td>
      
      <td>
        <strong>Purpose</strong>
      </td>
      
      <td>
        <strong>URL</strong>
      </td>
    </tr>
    
    <tr>
      <td>
        <a href="https://github.com/amnuts/opcache-gui">opcache-gui</a>
      </td>
      
      <td>
        visualize PHP zend <a class="" href="http://php.net/manual/en/intro.opcache.php">opcache</a> stats
      </td>
      
      <td>
        example.com/ee-admin/opcache-gui.php
      </td>
    </tr>
    
    <tr>
      <td>
        phpinfo
      </td>
      
      <td>
        A file with just <code>&lt;?php phpinfo() ?&gt;</code> in it
      </td>
      
      <td>
        example.com/ee-admin/phpinfo.php
      </td>
    </tr>
    
    <tr>
      <td>
        <a href="https://www.phpmyadmin.net/">phpMyAdmin</a>
      </td>
      
      <td>
        Check "Database Access for PhpMyAdmin" section below for login details
      </td>
      
      <td>
        example.com/ee-admin/pma
      </td>
    </tr>
    
    <tr>
      <td>
        <a href="https://github.com/erikdubbelboer/phpRedisAdmin">phpRedisAdmin</a>
      </td>
      
      <td>
        Web interface for Redis cache
      </td>
      
      <td>
        example.com/ee-admin/pra
      </td>
    </tr>
    
    <tr>
      <td>
        <a href="https://easyengine.io/handbook/mailhog/">MailHog</a>
      </td>
      
      <td>
        Catches & displays email from your app in Web GUI
      </td>
      
      <td>
        example.com/ee-admin/mailhog
      </td>
    </tr>
    
    <tr>
      <td>
        php-fpm ping
      </td>
      
      <td>
        a response of "pong" on this URL means your site's PHP is working fine
      </td>
      
      <td>
        example.com/ee-admin/ping
      </td>
    </tr>
    
    <tr>
      <td>
        <a href="https://easyengine.io/tutorials/php/fpm-status-page/">php-fpm status</a>
      </td>
      
      <td>
        displays php fpm pool status
      </td>
      
      <td>
        example.com/ee-admin/status
      </td>
    </tr>
    
    <tr>
      <td>
        <a href="https://easyengine.io/tutorials/nginx/status-page/">nginx status</a>
      </td>
      
      <td>
        displays nginx status
      </td>
      
      <td>
        example.com/ee-admin/nginx_status.
      </td>
    </tr>
  </tbody>
</table>

<!-- /wp:table -->

<!-- wp:heading {"level":3} -->

### Database Access for PhpMyAdmin

<!-- /wp:heading -->

<!-- wp:paragraph --> You can find database access credentials for 

`example.com` by running: <!-- /wp:paragraph -->

<!-- wp:code -->

<pre class="wp-block-code"><code>$ ee site info example.com

+--------------------+--------------------------------+
| Site               | https://example.com            |
+--------------------+--------------------------------+
| Access admin-tools | https://example.com/ee-admin/  |
+--------------------+--------------------------------+
| Site Title         | example.com                    |
+--------------------+--------------------------------+
| WordPress Username | example.com-K8FzH              |
+--------------------+--------------------------------+
| WordPress Password | q27eGm5pYRe2                   |
+--------------------+--------------------------------+
| DB Host            | global-db                      |
+--------------------+--------------------------------+
| DB Name            | example_com                    |
+--------------------+--------------------------------+
| DB User            | example.com-c1O1a7             |
+--------------------+--------------------------------+
| DB Password        | dg5T9GNhr4Ah                   |
+--------------------+--------------------------------+
| E-Mail             | admin@example.com              |
+--------------------+--------------------------------+
| SSL                | Enabled                        |
+--------------------+--------------------------------+
| SSL Wildcard       | No                             |
+--------------------+--------------------------------+
| Cache              | None                           |
+--------------------+--------------------------------+</code></pre>

<!-- /wp:code -->

<!-- wp:paragraph --> So in this case: 

<!-- /wp:paragraph -->

<!-- wp:list -->

*   Server would be `global-db`.
*   Username would be `example.com-c1O1a7`.
*   Password would be `dg5T9GNhr4Ah`.

<!-- /wp:list -->

<!-- wp:paragraph --> You can access phpMyAdmin at 

`example.com/ee-admin/pma` <!-- /wp:paragraph -->
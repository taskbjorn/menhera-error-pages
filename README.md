A collection of custom error pages for common web server error codes featuring [Menhera](https://github.com/a-wing/Menhera-chan) sticker pack and cheeky but informative error descriptions.

## Installation

Clone the contents of the repo to the root folder of your favourite web server and configure it to serve error codes directly from the root.

### NGINX

```conf
error_page 400 /400.html;
error_page 401 /401.html;
error_page 403 /403.html;
error_page 404 /404.html;
error_page 418 /418.html;
error_page 500 /500.html;
error_page 502 /502.html;
```

### Traefik

Prepare a container running a webserver to serve the error pages and serve it under *your-domain.tld* or *your-ip*. Replace all relative links to resources in each .html file with their absolute counterparts including your domain or IP: this is readily achieved running a search and replace with the following settings:

| Search for | Replace with |
| --- | --- |
| href=" | href="https://your-domain.tld/ |

## Supported Error Pages

The following error codes are currently included:

* 400 Bad Request  
  ![400 Bad Request](preview/400.png)
* 401 Unauthorized  
  ![401 Unauthorized](preview/401.png)
* 403 Forbidden  
  ![403 Forbidden](preview/403.png)
* 404 Not Found  
  ![404 Not Found](preview/404.png)
* 418 I'm a teapot  
  ![418 I'm a teapot](preview/418.png)
* 500 Internal Server Error  
  ![500 Internal Server Error](preview/500.png)
* 502 Bad Gateway  
  ![502 Bad Gateway](preview/502.png)

## Dependencies

The page makes use of [ribbon.js](https://github.com/hustcc/ribbon.js) for the coloured ribbon effect in the background, [FontAwesome](https://github.com/FortAwesome/Font-Awesome) for the GitHub icon and [Google Fonts](https://github.com/google/fonts) for the [Libre Franklin](https://fonts.google.com/specimen/Libre+Franklin) font. These are included in the repo, but may be served via a CDN if necessary.

The ribbon.min.js is slightly different than the one from the official repo, having an additional parameter 'colseed' acting as a seed for the initial colour of the ribbon. This allows to have a consistent, but different ribbon colour for each error page.


## Roadmap

The following additions are planned:

* Responsive layout for mobile devices
<h1 align="center"> <img src="/site_assets/{{ page.title.split()[0].lower() }}/logo.png" alt="logo" width="30" height="30"> {{ page.title.split()[0] }}</h1>

Custom [{{ page.title.split()[0] }}](https://github.com/amir20/dozzle) CSS

<p align="center"> Organizr Dark Theme </p>

![](/site_assets/{{ page.title.split()[0].lower() }}/organizr-dark.png)

```css
https://theme-park.dev/CSS/themes/{{ page.title.split()[0].lower() }}/XXX.css
aquamarine.css
hotline.css
plex.css
dark.css
space-gray.css
organizr-dark.css
```

## 🛠️ Installation

### [Setup](/setup)

!!! warning  "CSP"
    As dozzle will block the theme with its content security policy you need to change or remove the CSP header.
    Add this in your reverse proxy to remove the headers:

```nginx
proxy_hide_header "x-webkit-csp";
proxy_hide_header "content-security-policy";
```

#### Nginx variable example

```nginx
      server {
        ...

        location / {
            proxy_pass http://<dozzle.container.ip.address>:8080;
            set $app dozzle;
            include /config/nginx/theme-park.conf;
            proxy_hide_header "x-webkit-csp";
            proxy_hide_header "content-security-policy";
        }

        location /api {
            proxy_pass http://<dozzle.container.ip.address>:8080;
            proxy_buffering off;
            proxy_cache off;
        }
    }
```

{% set addons = extra.addons %}
{% set title = page.title.split()[0].lower() %}
{% for app, addon_name in addons.items() %}
    {% if app  ==  title %}

### Addons

        {% for el in addon_name.items() %}
            {% set name =  el[0]  %}
            {% for p in el[1].items() %}
            {% set path = p[1] %}

### [{{ name }}](/{{ path }})

            {% endfor %}
        {% endfor %}
    {% endif %}
{% endfor %}

## Screenshots

<p align="center">  
<a href="/site_assets/{{ page.title.split()[0].lower() }}/dark.png">Dark Theme<img src="/site_assets/{{ page.title.split()[0].lower() }}/dark.png"></img>
</p>

<p align="center">  
<a href="/site_assets/{{ page.title.split()[0].lower() }}/space-gray.png">Space Gray Theme<img src="/site_assets/{{ page.title.split()[0].lower() }}/space-gray.png"></img>
</p>

<p align="center">  
<a href="/site_assets/{{ page.title.split()[0].lower() }}/plex.png">Plex Theme<img src="/site_assets/{{ page.title.split()[0].lower() }}/plex.png"></img>
</p>

<p align="center">
<a href="/site_assets/{{ page.title.split()[0].lower() }}/organizr-dark.png">Organizr Dark Theme<img src="/site_assets/{{ page.title.split()[0].lower() }}/organizr-dark.png"></img>
</p>

<p align="center">
<a href="/site_assets/{{ page.title.split()[0].lower() }}/hotline.png">Hotline Theme<img src="/site_assets/{{ page.title.split()[0].lower() }}/hotline.png"></img>
</p>

<p align="center">
<a href="/site_assets/{{ page.title.split()[0].lower() }}/aquamarine.png">Aquamarine Theme<img src="/site_assets/{{ page.title.split()[0].lower() }}/aquamarine.png"></img>
</p>

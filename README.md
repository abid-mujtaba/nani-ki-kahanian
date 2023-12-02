# nani-ki-kahanian

A website for promoting the book "Nani ki Kahanian".

## Deployment

The website is served on an IONOS server whose IP address is mapped to
the doman `nani-ki-kahanian.com` via [name.com](https://www.name.com).

### Access to Deployment Host

```sh
ssh nani-ki-kahanian
```

The relevant ssh config is:

```text
Host nani-ki-kahanian
    Hostname nani-ki-kahanian.com
    User abid
    IdentityFile ~/.ssh/ionos
```

## SSL certification

We will setup a free SSL using [Let's Encrypt][lets-encrypt].
As recommended there, since we have shell access we will use
the [Certbot](https://certbot.eff.org/) ACME client.

The certbot webpage asks for the software (`nginx`) and
system (`Ubuntu 18`) that is running the website.

[lets-encrypt]: https://letsencrypt.org/getting-started/

### Prerequisites

Certbot is installed using `snap`: `sudo apt install snapd`.

Follow these [instructions][certbot-install-instructions] to install certbot using snap.

[certbot-install-instructions]: https://certbot.eff.org/instructions?ws=nginx&os=ubuntubionic

### Install SSL certificates

Simply run `sudo certbot --nginx` and select the domains you want install SSL for.

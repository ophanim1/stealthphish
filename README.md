![stealthphish logo](https://raw.github.com/ophanim1/stealthphish/master/static/images/stealthfish_purple.png)

Stealthphish - A modded version of GoPhish to improve stealthyness
=======

**IMPORTANT: This is a modified version of the original [GoPhish](https://github.com/gophish/gophish) project created by Jordan Wright. This fork includes security and stealth enhancements but is not affiliated with or endorsed by the original GoPhish team.**

![Build Status](https://github.com/gophish/gophish/workflows/CI/badge.svg) [![GoDoc](https://godoc.org/github.com/gophish/gophish?status.svg)](https://godoc.org/github.com/gophish/gophish)

```
## Security Enhancements
The following modifications have been made to the original GoPhish project (Credits: https://www.sprocketsecurity.com/blog/never-had-a-bad-day-phishing-how-to-set-up-gophish-to-evade-security-controls):

    - Modified email headers sent by default to not include the word "GoPhish."
    - Modified the server name sent in browser and with emails to the value "IGNORE"
    - Changed our 404.html page to be a bit more complex and harder to fingerprint
    - Changed web server headers to appear real as opposed to the simple defaults included with GoPhish
    - Changed the tracking parameter included in phishing links to track user clicks
```

About the Original GoPhish
-------
[GoPhish](https://getgophish.com) is an open-source phishing toolkit designed for businesses and penetration testers. It provides the ability to quickly and easily setup and execute phishing engagements and security awareness training.

### Install
**Note: This version does not include already compiled GoPhish binaries.**

~~Installation of Gophish is dead-simple - just download and extract the zip containing the [release for your system](https://github.com/gophish/gophish/releases/), and run the binary. Gophish has binary releases for Windows, Mac, and Linux platforms.~~

### Building From Source
**Note: Building from source requires Go v1.10 or above!**

To build from source, run ```git clone https://github.com/ophanim1/stealthphish.git``` and ```cd``` into the project source directory. Then, run ```go build```. After this, you should have a binary called ```gophish``` in the current directory.

### Docker
**Note: This version does not have an official Docker container.**

~~You can also use Gophish via the official Docker container [here](https://hub.docker.com/r/gophish/gophish/).~~

### Setup
After running the Gophish binary, open an Internet browser to https://localhost:3333. Change this in the config.json file to https://0.0.0.0:3333 to access the web interface from other machines on the network (you are going to get an https warning, but you can ignore that). Then login with the default username and password listed in the log output.
e.g.
```
time="2020-07-29T01:24:08Z" level=info msg="Please login with the username admin and the password 4304d5255378177d"
```

Releases of Gophish prior to v0.10.1 have a default username of `admin` and password of `gophish`.

### Documentation

Documentation can be found on the  [original GoPhish site](http://getgophish.com/documentation). Find something missing? Let them know by filing an issue!

### Issues

Find a bug? Want more features? Find something missing in the documentation? Let us know! Please don't hesitate to [file an issue](https://github.com/gophish/gophish/issues/new) and we'll get right on it.

### License
```
This modified version is based on Gophish - Open-Source Phishing Framework

The MIT License (MIT)

Copyright (c) 2013 - 2020 Jordan Wright

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software ("Gophish Community Edition") and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in
all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
THE SOFTWARE.
```

### Whitelabeling
To customize the appearance of this application for your organization, you can modify the following assets:

#### Images
All images are located in `static/images/`:

- `gophish_purple.png` (994x298) - Main logo used in the login page and documentation
- `logo.png` (175x200) - Standard logo used throughout the application
- `logo_purple.png` (175x200) - Purple variant of the main logo
- `logo_small.png` (40x46) - Small version of the logo used in navigation
- `logo_inv_small.png` (35x40) - Inverted small logo for dark backgrounds
- `favicon.ico` (16x16) - Browser favicon
- `pixel.png` (1x1) - Tracking pixel for email opens

To whitelabel:
1. Replace these images with your own versions, maintaining the same dimensions
2. Update the color scheme by modifying the CSS files in `static/css/`
3. Ensure your replacement tracking pixel (`pixel.png`) remains a 1x1 transparent PNG

Note: After replacing images, you may need to clear your browser cache to see the changes.

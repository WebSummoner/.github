<div align="center">

<img src="https://websummoner.riadvice.com/img/websummoner_logo.svg" width="88" alt="WebSummoner">

# WebSummoner

**A fast Selenium hub that summons a fleet of browsers into Docker containers —
ephemeral, session-scoped environments.**

[Website](https://websummoner.riadvice.com) ·
[Documentation](https://websummoner.riadvice.com/websummoner/) ·
[Docker Hub](https://hub.docker.com/u/websummoner)

[![Release](https://img.shields.io/github/v/release/WebSummoner/websummoner?label=release)](https://github.com/WebSummoner/websummoner/releases/latest)
[![Hub pulls](https://img.shields.io/docker/pulls/websummoner/websummoner?label=hub%20pulls&logo=docker&logoColor=white)](https://hub.docker.com/r/websummoner/websummoner)
[![License](https://img.shields.io/github/license/WebSummoner/websummoner)](https://github.com/WebSummoner/websummoner/blob/master/LICENSE)

</div>

---

One container per session. The browser starts when the test starts and is gone
when it ends, so nothing leaks between runs.

```bash
docker run -d --name websummoner -p 4444:4444 \
    -v $PWD/browsers.json:/etc/websummoner/browsers.json:ro \
    -v /var/run/docker.sock:/var/run/docker.sock \
    websummoner/websummoner:latest-release
```

Point your WebDriver client at `http://localhost:4444/wd/hub` and run the tests
you already have.

## Projects

| | Repository | What it does |
| --- | --- | --- |
| 🧭 | [**websummoner**](https://github.com/WebSummoner/websummoner) | the hub — W3C WebDriver, one container per session |
| 🖥️ | [**websummoner-ui**](https://github.com/WebSummoner/websummoner-ui) | live sessions, video and logs in the browser |
| ⚖️ | [**ggr**](https://github.com/WebSummoner/ggr) | load balancer across several hubs |
| 📊 | [**ggr-ui**](https://github.com/WebSummoner/ggr-ui) | one status view over a ggr cluster |
| 🛠️ | [**cm**](https://github.com/WebSummoner/cm) | one-command install and upgrade |
| 🌐 | [**images**](https://github.com/WebSummoner/images) | the browser images and their build tooling |
| ✅ | [**websummoner-container-tests**](https://github.com/WebSummoner/websummoner-container-tests) | the suite every image must pass |

## Browsers

Seven engines, each pinned to a driver that matches the build.

| Browser | Image | Driver |
| --- | --- | --- |
| Chrome | `websummoner/chrome` | ChromeDriver |
| Firefox | `websummoner/firefox` | geckodriver |
| Edge | `websummoner/edge` | msedgedriver |
| Opera | `websummoner/opera` | OperaDriver |
| Brave | `websummoner/brave` | ChromeDriver |
| Yandex | `websummoner/yandex` | YandexDriver |
| WebKit (Safari engine) | `websummoner/safari` | WebKitWebDriver |

Video with sound, session logs, live screen and VNC come from the hub, not from
your test code.

## Coming from Selenoid?

WebSummoner is a maintained fork of [Selenoid](https://github.com/aerokube/selenoid),
archived in December 2024. Configuration and the `selenoid:options` capability
still work, so most grids move over by changing the image name.

<div align="center">

Maintained by [**RIADVICE**](https://riadvice.com)

</div>

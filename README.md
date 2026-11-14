<div align="center">

# Free Proxy List

**981,907 proxies · 9 ready-to-use lists · rebuilt every day, no signup, no API key.**

[![Proxies](https://img.shields.io/badge/proxies-981.9K-brightgreen)](https://raw.githubusercontent.com/MADEVAL/free-proxy-list/main/summary.txt)
[![Updated](https://img.shields.io/badge/updated-2026-11-14-blue)](https://raw.githubusercontent.com/MADEVAL/free-proxy-list/main/summary.txt)
[![Sources](https://img.shields.io/badge/sources-157%2F157-informational)](https://raw.githubusercontent.com/MADEVAL/free-proxy-list/main/summary.txt)
[![License](https://img.shields.io/badge/license-MIT-lightgrey)](LICENSE)
[![Stars](https://img.shields.io/github/stars/MADEVAL/free-proxy-list?style=social)](https://github.com/MADEVAL/free-proxy-list)

[English](#english) · [Русский](#русский) · [All files](https://raw.githubusercontent.com/MADEVAL/free-proxy-list/main/summary.txt) · [Security](SECURITY.md)

Maintained by [GLOBUS.studio](https://globus.studio)

</div>

---

## English

Plain-text proxy lists, deduplicated and validated, published straight from an automated pipeline.
Point your scraper at a raw URL and you are done.

- **981,907 addresses** across HTTP, HTTPS, SOCKS4, SOCKS5, mixed and anonymity tiers.
- **Updated daily.** Last build: `2026-11-14 09:58:10+00:00`.
- **Clean data.** Valid IP or hostname, valid port, no private or reserved ranges, no duplicates.
- **Two mirrors.** `raw.githubusercontent.com` and jsDelivr, so you can pick the faster one.

### Endpoints

| List | Proxies | Format | Raw | CDN |
| --- | ---: | --- | --- | --- |
| **Mixed** | 239,604 | `scheme://ip:port` | [`mix.txt`](https://raw.githubusercontent.com/MADEVAL/free-proxy-list/main/mix.txt) | [jsDelivr](https://cdn.jsdelivr.net/gh/MADEVAL/free-proxy-list@main/mix.txt) |
| **HTTP** | 185,751 | `ip:port` | [`http.txt`](https://raw.githubusercontent.com/MADEVAL/free-proxy-list/main/http.txt) | [jsDelivr](https://cdn.jsdelivr.net/gh/MADEVAL/free-proxy-list@main/http.txt) |
| **SOCKS5** | 174,200 | `ip:port` | [`socks5.txt`](https://raw.githubusercontent.com/MADEVAL/free-proxy-list/main/socks5.txt) | [jsDelivr](https://cdn.jsdelivr.net/gh/MADEVAL/free-proxy-list@main/socks5.txt) |
| **SOCKS4** | 150,456 | `ip:port` | [`socks4.txt`](https://raw.githubusercontent.com/MADEVAL/free-proxy-list/main/socks4.txt) | [jsDelivr](https://cdn.jsdelivr.net/gh/MADEVAL/free-proxy-list@main/socks4.txt) |
| **Bare addresses** | 147,357 | `ip` | [`no-ports.txt`](https://raw.githubusercontent.com/MADEVAL/free-proxy-list/main/no-ports.txt) | [jsDelivr](https://cdn.jsdelivr.net/gh/MADEVAL/free-proxy-list@main/no-ports.txt) |
| **HTTPS** | 67,142 | `ip:port` | [`https.txt`](https://raw.githubusercontent.com/MADEVAL/free-proxy-list/main/https.txt) | [jsDelivr](https://cdn.jsdelivr.net/gh/MADEVAL/free-proxy-list@main/https.txt) |
| **Elite** | 13,274 | `scheme://ip:port` | [`elite.txt`](https://raw.githubusercontent.com/MADEVAL/free-proxy-list/main/elite.txt) | [jsDelivr](https://cdn.jsdelivr.net/gh/MADEVAL/free-proxy-list@main/elite.txt) |
| **Anonymous** | 3,453 | `scheme://ip:port` | [`anonymous.txt`](https://raw.githubusercontent.com/MADEVAL/free-proxy-list/main/anonymous.txt) | [jsDelivr](https://cdn.jsdelivr.net/gh/MADEVAL/free-proxy-list@main/anonymous.txt) |
| **Transparent** | 670 | `scheme://ip:port` | [`transparent.txt`](https://raw.githubusercontent.com/MADEVAL/free-proxy-list/main/transparent.txt) | [jsDelivr](https://cdn.jsdelivr.net/gh/MADEVAL/free-proxy-list@main/transparent.txt) |

Total: **981,907** addresses built from 157 sources (0 dead at build time).

### Unique IPs only: `ips.txt`

`ips.txt` is one extra file, kept apart from the lists above: **186,288 unique IP addresses**, one per line, without schemes and without ports, deduplicated across every list in this repository.

It is a **lookup set**, not a proxy list in itself. Feed it IPs from your logs, firewall or analytics and check whether an address is known to be (or has been seen as) a proxy:

```bash
curl -sL https://raw.githubusercontent.com/MADEVAL/free-proxy-list/main/ips.txt -o ips.txt
grep -Fxf ips.txt suspicious-ips.txt
```

- Only IP addresses - hostname-based entries from the lists are not included.
- One IP appears once, no matter how many ports or protocols it was published with.
- Sorted numerically, so day-to-day diffs stay readable. For `comm` or `join`, run `sort` on the file first.

[`ips.txt`](https://raw.githubusercontent.com/MADEVAL/free-proxy-list/main/ips.txt) · [jsDelivr](https://cdn.jsdelivr.net/gh/MADEVAL/free-proxy-list@main/ips.txt)

Raw base: `https://raw.githubusercontent.com/MADEVAL/free-proxy-list/main`
jsDelivr base: `https://cdn.jsdelivr.net/gh/MADEVAL/free-proxy-list@main`

### Quick start

```bash
curl -sL https://raw.githubusercontent.com/MADEVAL/free-proxy-list/main/socks5.txt | head
```

```python
import urllib.request

url = "https://raw.githubusercontent.com/MADEVAL/free-proxy-list/main/http.txt"
proxies = urllib.request.urlopen(url, timeout=30).read().decode().split()
print(len(proxies), proxies[0])
```

```javascript
const res = await fetch("https://raw.githubusercontent.com/MADEVAL/free-proxy-list/main/socks5.txt");
const proxies = (await res.text()).trim().split("\n");
console.log(proxies.length, proxies[0]);
```

```php
$list = file_get_contents('https://raw.githubusercontent.com/MADEVAL/free-proxy-list/main/http.txt');
$proxies = preg_split('/\R/', trim($list));
echo count($proxies) . PHP_EOL;
```

```go
resp, _ := http.Get("https://raw.githubusercontent.com/MADEVAL/free-proxy-list/main/socks4.txt")
body, _ := io.ReadAll(resp.Body)
proxies := strings.Fields(string(body))
```

### How it works

1. **Collect** - 157 public proxy sources are downloaded in parallel.
2. **Parse** - `ip:port`, `scheme://ip:port`, `user:pass@ip:port`, `ip:port:user:pass`, JSON and CSV are understood.
3. **Validate** - address and port are checked, private/loopback/reserved ranges are dropped.
4. **Dedupe** - duplicates removed inside a source and across all sources.
5. **Publish** - one snapshot commit per run, so the repository stays small.

### Notes

- These are **candidate** proxies: an open port does not guarantee a working proxy. Test before use.
- Lists are rebuilt from public sources; availability varies day to day.
- The repository is generated automatically. Pull requests with data changes are not accepted.
- Use responsibly and only where you have permission. No warranty of any kind.

### Contact

Privacy, security, protection, responsible disclosure, takedown requests and any abuse reports go to **GLOBUS.studio**:

- [globus.studio](https://globus.studio)
- [hello@globus.studio](mailto:hello@globus.studio)

See [SECURITY.md](SECURITY.md) for the reporting policy. Everything else - open an issue.

---

## Русский

Готовые текстовые списки прокси: проверенные по формату, без дублей, публикуются автоматически.
Достаточно взять raw-ссылку - регистрация и API-ключ не нужны.

- **981,907 адресов** в категориях HTTP, HTTPS, SOCKS4, SOCKS5, mixed и анонимные.
- **Обновление каждый день.** Последняя сборка: `2026-11-14 09:58:10+00:00`.
- **Чистые данные.** Валидный IP или домен, валидный порт, без частных и служебных диапазонов, без дублей.
- **Два зеркала.** `raw.githubusercontent.com` и jsDelivr - бери то, что быстрее.

### Файлы

| List | Proxies | Format | Raw | CDN |
| --- | ---: | --- | --- | --- |
| **Mixed** | 239,604 | `scheme://ip:port` | [`mix.txt`](https://raw.githubusercontent.com/MADEVAL/free-proxy-list/main/mix.txt) | [jsDelivr](https://cdn.jsdelivr.net/gh/MADEVAL/free-proxy-list@main/mix.txt) |
| **HTTP** | 185,751 | `ip:port` | [`http.txt`](https://raw.githubusercontent.com/MADEVAL/free-proxy-list/main/http.txt) | [jsDelivr](https://cdn.jsdelivr.net/gh/MADEVAL/free-proxy-list@main/http.txt) |
| **SOCKS5** | 174,200 | `ip:port` | [`socks5.txt`](https://raw.githubusercontent.com/MADEVAL/free-proxy-list/main/socks5.txt) | [jsDelivr](https://cdn.jsdelivr.net/gh/MADEVAL/free-proxy-list@main/socks5.txt) |
| **SOCKS4** | 150,456 | `ip:port` | [`socks4.txt`](https://raw.githubusercontent.com/MADEVAL/free-proxy-list/main/socks4.txt) | [jsDelivr](https://cdn.jsdelivr.net/gh/MADEVAL/free-proxy-list@main/socks4.txt) |
| **Bare addresses** | 147,357 | `ip` | [`no-ports.txt`](https://raw.githubusercontent.com/MADEVAL/free-proxy-list/main/no-ports.txt) | [jsDelivr](https://cdn.jsdelivr.net/gh/MADEVAL/free-proxy-list@main/no-ports.txt) |
| **HTTPS** | 67,142 | `ip:port` | [`https.txt`](https://raw.githubusercontent.com/MADEVAL/free-proxy-list/main/https.txt) | [jsDelivr](https://cdn.jsdelivr.net/gh/MADEVAL/free-proxy-list@main/https.txt) |
| **Elite** | 13,274 | `scheme://ip:port` | [`elite.txt`](https://raw.githubusercontent.com/MADEVAL/free-proxy-list/main/elite.txt) | [jsDelivr](https://cdn.jsdelivr.net/gh/MADEVAL/free-proxy-list@main/elite.txt) |
| **Anonymous** | 3,453 | `scheme://ip:port` | [`anonymous.txt`](https://raw.githubusercontent.com/MADEVAL/free-proxy-list/main/anonymous.txt) | [jsDelivr](https://cdn.jsdelivr.net/gh/MADEVAL/free-proxy-list@main/anonymous.txt) |
| **Transparent** | 670 | `scheme://ip:port` | [`transparent.txt`](https://raw.githubusercontent.com/MADEVAL/free-proxy-list/main/transparent.txt) | [jsDelivr](https://cdn.jsdelivr.net/gh/MADEVAL/free-proxy-list@main/transparent.txt) |

Всего: **981,907** адресов из 157 источников (0 недоступны на момент сборки).

### Только уникальные IP: `ips.txt`

`ips.txt` - отдельный файл вне таблицы выше: **186,288 уникальных IP-адресов**, по одному в строке, без схем и без портов, с дедупом по всем спискам репозитория.

Это **набор для проверки**, а не список прокси. Берёшь IP из логов, файрвола или аналитики и смотришь, встречается ли адрес в датасете, то есть предлагался ли он где-то как прокси:

```bash
curl -sL https://raw.githubusercontent.com/MADEVAL/free-proxy-list/main/ips.txt -o ips.txt
grep -Fxf ips.txt suspicious-ips.txt
```

- Только IP - доменные записи из списков сюда не попадают.
- Один адрес ровно один раз, сколько бы портов и протоколов у него ни было.
- Отсортирован численно, поэтому диффы между днями читаемые. Для `comm` и `join` прогони файл через `sort`.

[`ips.txt`](https://raw.githubusercontent.com/MADEVAL/free-proxy-list/main/ips.txt) · [jsDelivr](https://cdn.jsdelivr.net/gh/MADEVAL/free-proxy-list@main/ips.txt)

База raw: `https://raw.githubusercontent.com/MADEVAL/free-proxy-list/main`
База jsDelivr: `https://cdn.jsdelivr.net/gh/MADEVAL/free-proxy-list@main`

### Быстрый старт

```bash
curl -sL https://raw.githubusercontent.com/MADEVAL/free-proxy-list/main/socks5.txt | head
```

```python
import urllib.request

url = "https://raw.githubusercontent.com/MADEVAL/free-proxy-list/main/http.txt"
proxies = urllib.request.urlopen(url, timeout=30).read().decode().split()
print(len(proxies), proxies[0])
```

```javascript
const res = await fetch("https://raw.githubusercontent.com/MADEVAL/free-proxy-list/main/socks5.txt");
const proxies = (await res.text()).trim().split("\n");
console.log(proxies.length, proxies[0]);
```

### Как это устроено

1. **Сбор** - параллельно скачиваются 157 публичных источников.
2. **Разбор** - понимаются `ip:port`, `scheme://ip:port`, `user:pass@ip:port`, `ip:port:user:pass`, JSON и CSV.
3. **Проверка** - валидные адрес и порт, частные и служебные диапазоны отбрасываются.
4. **Дедупликация** - внутри источника и между всеми источниками.
5. **Публикация** - один снапшот-коммит на запуск, репозиторий не разрастается.

### Важно

- Это **кандидаты** в прокси: открытый порт не гарантирует работоспособность. Проверяй перед использованием.
- Списки собираются из публичных источников, доступность меняется день ото дня.
- Репозиторий генерируется автоматически. Pull request с правкой данных не принимается.
- Используй ответственно и только там, где есть разрешение. Гарантий нет.

### Контакты

Вопросы приватности, безопасности, защиты, ответственного раскрытия уязвимостей, запросы на удаление и жалобы на злоупотребление - в **GLOBUS.studio**:

- [globus.studio](https://globus.studio)
- [hello@globus.studio](mailto:hello@globus.studio)

Политика раскрытия - в [SECURITY.md](SECURITY.md). Всё остальное - через issue.

---

## License

MIT. See [LICENSE](LICENSE).

[Security](SECURITY.md) · [Contributing](CONTRIBUTING.md) · [Code of Conduct](CODE_OF_CONDUCT.md)

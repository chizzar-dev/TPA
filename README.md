<div align="center">

<img src="https://capsule-render.vercel.app/api?type=rect&color=0:0b1220,100:0e7490&height=110&section=header&text=Tpa&fontSize=42&fontColor=22d3ee&fontAlignY=54&desc=Teleport%20requests%20with%20warmup&descSize=13&descColor=94a3b8&descAlignY=80" width="100%" alt="Tpa" />

<p>
<img src="https://img.shields.io/github/v/release/chizzar-dev/TPA?style=flat&label=release&color=06b6d4&labelColor=0b1220" alt="release" />
<img src="https://img.shields.io/badge/Minecraft-1.8%20%E2%80%93%201.21.11-0891b2?style=flat&labelColor=0b1220" alt="Minecraft 1.8 - 1.21.11" />
<img src="https://img.shields.io/badge/Java-8%2B-155e75?style=flat&labelColor=0b1220&logo=openjdk&logoColor=22d3ee" alt="Java 8+" />
<a href="LICENSE"><img src="https://img.shields.io/github/license/chizzar-dev/TPA?style=flat&label=license&color=0e7490&labelColor=0b1220" alt="license" /></a>
</p>

</div>

Tpa adds teleport requests between players, with a configurable warmup, on-screen countdown and cancel-on-move.

*Tpa, oyuncular arasi isinlanma istekleri ekler; ayarlanabilir bekleme suresi, ekranda geri sayim ve hareket edince iptal icerir.*

## Features · Özellikler
- Ayarlanabilir ışınlanma bekleme süresi (varsayılan 5 sn)
- Bekleme süresi ekranda **geri sayarak** gösterilir (action bar veya title)
- Hareket edince iptal (configden açılıp kapatılabilir)
- Aynı anda tek bekleyen istek — biri beklerken başkasına istek atılamaz
- İstek zaman aşımı ve isteğe bağlı bekleme (cooldown) configden
- `tpa.bypass` yetkisi olanlar anında ışınlanır

## Installation · Kurulum
1. [Releases](https://github.com/chizzar-dev/TPA/releases/latest) sayfasından `Tpa.jar` dosyasını indir ve sunucunun `plugins/` klasörüne at.
2. Sunucuyu yeniden başlat.
3. `plugins/Tpa/config.yml` dosyasından süreleri ve mesajları düzenle.

## Commands · Komutlar
| Komut | Açıklama | Yetki |
|-------|----------|-------|
| `/tpa <oyuncu>` | Oyuncunun yanına gitmek için istek gönderir | `tpa.use` |
| `/tpaccept [oyuncu]` | Gelen isteği kabul eder | `tpa.use` |
| `/tpdeny [oyuncu]` | Gelen isteği reddeder | `tpa.use` |
| `/tpacancel` | Gönderdiğin isteği iptal eder | `tpa.use` |

## Permissions · Yetkiler
| Yetki | Açıklama | Varsayılan |
|-------|----------|------------|
| `tpa.use` | Işınlanma komutlarını kullanır | herkes |
| `tpa.bypass` | Beklemeden anında ışınlanır | kapalı (verilmeli) |

> `tpa.bypass` varsayılan **kapalıdır** — OP dahil herkes bekleme süresine tabidir. Yalnızca bu
> yetki açıkça verilen oyuncular (örn. LuckPerms ile) anında ışınlanır.

## Configuration · Ayarlar
| Anahtar | Açıklama |
|---------|----------|
| `warmup` | Işınlanma bekleme süresi (saniye, 0 = anında) |
| `cancel-on-move` | Hareket edince iptal et |
| `request-timeout` | İstek kaç saniye sonra zaman aşımına uğrar |
| `cooldown` | İki istek arası bekleme (saniye, 0 = kapalı) |
| `countdown.type` | `ACTIONBAR` (küçük) veya `TITLE` (ekran ortası) |
| `countdown.message` / `title` / `subtitle` | Geri sayım metinleri (`%time%`) |
| `messages.*` | Tüm mesajlar |

## Building · Derleme
```bash
mvn clean package
```
Çıktı · Output: `target/Tpa.jar`

Her push [GitHub Actions](https://github.com/chizzar-dev/TPA/actions/workflows/build.yml) ile derlenir; `v*` etiketli sürümler jar'la birlikte [Releases](https://github.com/chizzar-dev/TPA/releases) sayfasına eklenir.
<br><sub>Every push is built by GitHub Actions; tagged `v*` releases attach the jar.</sub>

## License · Lisans
[MIT](LICENSE) — istediğin gibi kullan, değiştir, dağıt · use, modify and distribute freely

<div align="center"><sub>chizzar-dev · Minecraft plugins for 1.8 – 1.21.11</sub></div>

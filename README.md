# BedrockLoader mod deposu

BedrockLoader içindeki **Dahili modlar** ekranının mod listesi.

| Mod | DLL | Discord |
| --- | --- | --- |
| ForceCloseOreUI | [ForceCloseOreUI.dll](ForceCloseOreUI.dll) | [Discord](https://discord.gg/gBaFaMQ) |
| MinecraftForFree — Kokluk | [MinecraftForFree.dll](MinecraftForFree.dll) | — |

ForceCloseOreUI, Kokluk tarafından geliştirilmemiştir. Discord bağlantısı kaynak topluluğa kredi vermek içindir. MinecraftForFree, Kokluk tarafından sağlanmıştır.

## Yeni mod ekleme

DLL dosyasını depo köküne ekle ve `catalog.json` içindeki `mods` listesine bir kayıt ekle. Uygulamada **Yenile** seçildiğinde liste yeniden alınır.

Alanlar: `name`, `description`, `credit`, `fileName`, `downloadUrl`, `discordUrl`, `sha256`, `size` (bayt). `schemaVersion` değeri 1 olmalıdır. Her dosya adı benzersiz ve `.dll` uzantılı olmalıdır. İndirme URL'si bu deponun raw dosya bağlantısı veya Release indirme bağlantısı olmalıdır.

SHA-256 ve dosya boyutunu PowerShell ile öğrenebilirsin:

```powershell
Get-FileHash -LiteralPath .\ModAdi.dll -Algorithm SHA256
(Get-Item -LiteralPath .\ModAdi.dll).Length
```

Launcher, kullanıcı onayından sonra DLL'i indirir; boyutu, SHA-256 özetini ve Windows DLL biçimini doğrular. Doğrulanan dosya yerel mod klasörüne eklenir. DLL bu işlem sırasında çalıştırılmaz. Aynı dosya zaten varsa değiştirmek için ayrıca izin istenir.

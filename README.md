# Coopanion Discord 驗證頁面

Discord Developer Portal「驗證您的應用程式」所需的兩個公開連結頁面。
純靜態 HTML，無外部依賴，可直接放 GitHub Pages。

## 待填佔位符（共 2 處，兩個檔案都要改）

| 佔位符 | 換成 |
| --- | --- |
| `YOUR_DISCORD_HANDLE` | 你的 Discord 使用者名稱（不用加 @ 也可，頁面已有 @） |
| `YOUR_EMAIL` | 可公開的聯絡信箱 |

用編輯器全局替換即可，例如 PowerShell：

```powershell
Get-ChildItem *.html | ForEach-Object {
  (Get-Content $_ -Raw) `
    -replace 'YOUR_DISCORD_HANDLE', 'sagi' `
    -replace 'YOUR_EMAIL', 'your@mail.com' |
  Set-Content $_ -Encoding utf8
}
```

## 部署到 GitHub Pages

1. 新建一個**公開** repo，例如 `coopanion-legal`。
2. 把 `terms.html`、`privacy.html` 放進根目錄，push 上 GitHub。
3. repo → Settings → Pages → Source 選 `Deploy from a branch`，Branch 選 `main` / `/ (root)`，Save。
4. 等約一分鐘，網址會是：

```
https://<你的帳號>.github.io/coopanion-legal/terms.html
https://<你的帳號>.github.io/coopanion-legal/privacy.html
```

5. 回到 Discord Developer Portal → 你的 App → **General Information**，填進：
   - `Terms of Service URL` ← terms.html 網址
   - `Privacy Policy URL` ← privacy.html 網址

## 團隊（若日後真的要驗證）

左側 **Teams → New Team**（免費）建立團隊 → 回 App 的 General Information → **Transfer App** 轉進去。

## 注意

- 這兩個連結必須是 **https** 且無需登入即可存取。
- 目前主人在 100 個伺服器以下，**驗證非必要**，這兩個頁面先備著即可。

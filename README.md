
# All-In-One Automatic Clicker

یک کلیکر خودکار برای بات‌های (Hamster ~ TapSwap ~ CexIO ~ Blum).

## وضعیت بات‌ها

<div align="center">

| **Bot**  | **Status**  |
|:--------:|:-----------:|
| **Blum** | ✔️ فعال      |
| **Hamster** | ✔️ فعال   |
| **CexIO** | ✔️ فعال     |
| **TapSwap** | ❌ غیرفعال |

</div>

## پیش‌نیازها

- Python 3.10 یا بالاتر

## نصب

مراحل زیر را برای نصب و راه‌اندازی کلیکر خودکار در تلگرام دنبال کنید:

1. **کلون کردن مخزن**
   ```sh
   git clone https://github.com/salehpx/Clicker
   cd Clicker
   ```

2. **ایجاد و فعال‌سازی محیط مجازی**
   ```sh
   python -m venv venv
   source venv/bin/activate  # در ویندوز: `venv\Scripts\activate`
   ```

3. **نصب وابستگی‌ها**
   ```sh
   pip install -r requirements.txt
   ```

## تنظیمات

1. **پیکربندی حساب‌های تلگرام**
   - اطمینان حاصل کنید که شماره تلفن‌های هر حسابی که قرار است از کلیکر استفاده کنند را دارید.

2. **ویرایش فایل پیکربندی**
   - فایل `config.json` را باز کرده و پارامترهای لازم را ویرایش کنید.
   - نمونه `config.json`:
     ```json
     {
        "api_id": 26766605,
        "api_hash": "9d27802c38413c38b1aa12149ee50bff",
        "admin": 6057539036,
        "bot_token": "",
        "tapswap_clicker": "off",
        "hamster_clicker": "on",
        "cexio_clicker": "on",
        "blum_clicker": "on",
        "auto_upgrade": true,
        "max_days_for_return": 5,
        "max_charge_level": 5,
        "max_energy_level": 10,
        "max_tap_level": 10,
        "cexio_ref_code": "1717768426029179",
        "blum_ref_code": "Aa83Rh"
     }
     ```
   - **توجه:**
     - مقدار `admin` را با شناسه عددی ادمین جایگزین کنید. می‌توانید این شناسه را با تماس با [@chatIDrobot](https://t.me/chatIDrobot) در تلگرام دریافت کنید.
     - اگر هر یک از کلیکرها (`tapswap_clicker`, `hamster_clicker`, `cexio_clicker`, `blum_clicker`) را روی "off" تنظیم کنید، بات با آن بات خاص تعامل نخواهد داشت.
     - تنظیم `max_days_for_return` برای بات Hamster است و حداکثر تعداد روزهایی را مشخص می‌کند که باید طول بکشد تا یک کارت به سوددهی برسد.
     - تنظیمات `max_charge_level`, `max_energy_level`, و `max_tap_level` برای بات TapSwap هستند.
     - کدهای ارجاع `cexio_ref_code` و `blum_ref_code` را با کدهای خودتان جایگزین کنید.

### نکته مهم: پیکربندی توکن بات برای مدیریت چند حساب

برای مدیریت چندین حساب، نیاز به تنظیم یک توکن بات که از BotFather دریافت می‌کنید دارید. مراحل زیر را دنبال کنید:

1. **ایجاد یک بات تلگرام از طریق BotFather**
   - تلگرام را باز کنید و [@BotFather](https://t.me/BotFather) را جستجو کنید.
   - یک چت با BotFather شروع کنید و از دستور `/newbot` برای ایجاد یک بات جدید استفاده کنید.
   - دستورالعمل‌ها را برای تنظیم نام و نام کاربری بات دنبال کنید.
   - پس از ایجاد، یک توکن بات دریافت خواهید کرد. **این توکن را کپی کنید.**

2. **وارد کردن توکن بات در `config.json`**
   - فایل `config.json` را باز کنید.
   - توکن بات کپی شده را در فیلد `"bot_token"` جایگذاری کنید.
   - مثال:
     ```json
     {
        "api_id": 26766605,
        "api_hash": "9d27802c38413c38b1aa12149ee50bff",
        "admin": 6057539036,
        "bot_token": "YOUR_BOT_TOKEN_HERE",
        "tapswap_clicker": "off",
        "hamster_clicker": "on",
        "cexio_clicker": "on",
        "blum_clicker": "on",
        "auto_upgrade": true,
        "max_days_for_return": 5,
        "max_charge_level": 5,
        "max_energy_level": 10,
        "max_tap_level": 10,
        "cexio_ref_code": "1717768426029179",
        "blum_ref_code": "Aa83Rh"
     }
     ```
   - **توجه:** توکن بات فقط برای مدیریت چند حساب مورد نیاز است. اطمینان حاصل کنید که به درستی وارد شده است تا از بروز مشکلات جلوگیری شود.

## اجرای اسکریپت

1. **اجرای اسکریپت چند حساب**
   ```sh
   python multi-account.py
   ```

2. **ارسال دستور /help**
   - پس از اجرای موفقیت‌آمیز اسکریپت، دستور `/help` را به بات ارسال کنید.

3. **نظارت بر لاگ‌ها**
   - لاگ‌ها را بررسی کنید تا اطمینان حاصل کنید که بات به درستی اجرا شده و با بات‌های مشخص شده (Hamster, TapSwap, Cex IO) تعامل دارد.

## استفاده

- بات به طور خودکار اقدامات کلیک کردن را روی بات‌های تلگرام مشخص شده انجام خواهد داد.
- اطمینان حاصل کنید که محیط و تنظیمات شما صحیح هستند تا از هرگونه وقفه جلوگیری شود.

## رفع اشکال

- اطمینان حاصل کنید که نسخه Python 3.10 یا بالاتر نصب شده است.
- بررسی کنید که همه وابستگی‌ها به درستی نصب شده‌اند.
- شماره تلفن‌های خود را دوباره بررسی کنید و مطمئن شوید که به درستی وارد شده‌اند.
- فایل `config.json` را دوباره بررسی کنید و مطمئن شوید که به درستی پیکربندی شده است.

## تماس

برای دریافت کمک بیشتر، لطفاً با نگهدارنده پروژه تماس بگیرید.

---

این راهنما یک تنظیم و استفاده کامل از All-In-One Automatic Clicker را فراهم می‌کند. اطمینان حاصل کنید که هر مرحله را با دقت دنبال کنید تا ابزار به درستی کار کند.

---

## به‌روزرسانی پیکربندی

فایل پیکربندی به شرح زیر به‌روز شده است:

```json
{
    "api_id": 8086441,
    "api_hash": "2a305482a93b5a762d2acd4be90dd00f",
    "admin": 6135970338,
    "bot_token": "",
    "tapswap_clicker": "off",
    "hamster_clicker": "on",
    "cexio_clicker": "on",
    "blum_clicker": "on",
    "auto_upgrade": true,
    "max_days_for_return": 5,
    "max_charge_level": 5,
    "max_energy_level": 10,
    "max_tap_level": 10,
    "cexio_ref_code": "1716310450941700",
    "blum_ref_code": "AacKuW83Rh"
}
```

### نکته مهم

قسمت `app.py` پروژه دیگر موجود نیست.

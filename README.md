پروژه ساخت فیلترشکن شخصی با Xray
این پروژه نسخه‌ای ویرایش و شخصی‌سازی شده بر اساس پروژه اصلی sepehrpiton/argo-pass است.

با این پروژه می‌تونی خیلی راحت برای خودت یک فیلترشکن شخصی با هسته قدرتمند Xray بسازی و اون رو روی سرویس‌های ابری رایگان (که بهشون PaaS میگن مثل Heroku, Koyeb, Render و...) اجرا کنی.

قابلیت‌های اصلی پروژه
ترکیب فناوری‌های قدرتمند: این سیستم از یک ترکیب حرفه‌ای برای دور زدن فیلترینگ استفاده می‌کنه:

Argo Tunnel کلودفلر: برای مخفی کردن IP اصلی سرور و پایداری بالا.
وب‌سرور Nginx: برای مدیریت هوشمند ترافیک و ردگم‌کنی.
پروتکل‌های متنوع: پشتیبانی کامل از پروتکل‌های محبوب Vmess, Vless, Trojan و Shadowsocks روی بستر امن WebSocket و TLS.
امنیت در برابر شناسایی: کانفیگ و فایل‌های اصلی جوری تنظیم شدن که ریسک شناسایی و مسدود شدن سرور شما توسط فیلترینگ خیلی کمتر بشه.

قابلیت شخصی‌سازی کامل: شناسه (UUID) و مسیرهای ارتباطی (Path) برای همه پروتکل‌ها کاملاً قابل تغییر و شخصی‌سازی هستن. اینطوری میتونی سرور خودت رو خاص و منحصر به فرد کنی.

مانیتورینگ (اختیاری): اگه دوست داشته باشی، میتونی سیستم مانیتورینگ «Nezha» رو هم فعال کنی تا وضعیت منابع و مصرف سرورت رو همیشه زیر نظر داشته باشی.

راهکار برای دامنه‌های فیلتر شده:
نکته مهم: بعد از اینکه همه چیز رو ساختی، اگه دیدی به سرور وصل نمیشه، احتمالاً دامنه Argo Tunnel که بهت داده فیلتر شده. برای حل این مشکل خیلی راحت میتونی از یک Worker یا CDN کلودفلر استفاده کنی و به اصطلاح، یک دامنه تمیز برای خودت داشته باشی.

## deployment

* Register with any PaaS cloud service provider
* Depending on the PaaS cloud service provider, bind your own GitHub account or use the Actions provided by the project to generate a DockerHub image. It is highly recommended to use a trumpet + private library
* Variables available to the project
   | Variable name | Required | Default value | Remarks |
   | ------------ | ------ | ------ | ------ |
   | UUID | No | de04add9-5c68-8bab-950c-08cd5320df18 | Can be generated online https://www.uuidgenerator.net/ |
   | VMESS_WSPATH | No | /vmess | Starts with / |
   | VLESS_WSPATH | No | /vless | Starts with / |
   | TROJAN_WSPATH | No | /trojan | Starts with / |
   | SS_WSPATH | No | /shadowsocks | Start with / |
   | NEZHA_SERVER | No | | The IP or domain name of the Nezha probe server |
   | NEZHA_PORT | No | | The port of the Nezha probe server |
   | NEZHA_KEY | No | | Nezha Probe client dedicated Key |

* Variables used by GitHub Actions

   | Variable name | Remarks |
   | ------------- | -------------- |
   |DOCKER_USERNAME|Docker Hub username|
   |DOCKER_PASSWORD|Docker Hub password|
   |DOCKER_REPO |Docker Hub repository name|

![image](https://user-images.githubusercontent.com/116990986/211692321-34df154a-320a-448f-9abe-2efab9c53550.png)

## Acknowledgments

* ifeng's v2ray project: https://github.com/hiifeng
* fscarmen2's argo xray project: https://github.com/fscarmen2
* Translator to English (all files translated) : https://github.com/yebekhe

## Disclaimer

* This program is only for learning and understanding. For non-profit purposes, please delete it within 24 hours after downloading. It cannot be used for any commercial purposes. The text, data and pictures are copyrighted. If reproduced, the source must be indicated.
* Use of this program is subject to the deployment disclaimer. The use of this program must comply with the laws and regulations of the location where the deployment server is located, the country where the user is located, and the country where the user is located. The program author is not responsible for any improper behavior of the user.

## sponsorship

Afdian: https://afdian.net/a/Misaka-blog

![afdian-MisakaNo の Xiaopo Station](https://user-images.githubusercontent.com/122191366/211533469-351009fb-9ae8-4601-992a-abbf54665b68.jpg)

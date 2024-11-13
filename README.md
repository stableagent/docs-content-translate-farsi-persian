# اسناد-محتوا

## این Repository چیست؟

این repository محتوای وب سایت اسناد آردوینو را میزبانی می کند.  محتوا باید در Markdown نوشته شود و در طول فرآیند ساخت به طور خودکار به HTML تبدیل می شود.

در این آدرس در دسترس است:
<https://docs.arduino.cc>

## چگونه می توانم کمک کنم؟
مشارکت با ترجمه محتوا یا پیشنهاد تغییرات در محتوای موجود را می توان با ایجاد ** pull requests ** انجام داد.
(( و توجه داشته باشید به هیچ عنوان کلمات فنی را ترجمه نکنید ))

اگر دسترسی نوشتن به این repository دارید، با جدا کردن مخزن یا ایجاد یک شعبه جدید شروع می‌کنید.  یک branch جدید بر اساس main ایجاد کنید و آن را بر اساس آنچه که پیشوند با نام کاربری GitHub و یک اسلش ایجاد خواهید کرد نامگذاری کنید (به عنوان مثال `sebromero/wifi-tutorial`)
نحوه افزودن انواع مختلف محتوای جدید را در بخش زیر بخوانید.

وقتی کارتان با یک پیش نویس تمام شد، می توانید یک pull request ایجاد کنید.
این به تیم محتوا این امکان را می دهد که آن را بررسی کند و نظر بدهد یا درخواست تغییر دهد.
در طول این فرآیند بررسی، می‌توانید به فشار دادن commit‌ها به همان شعبه ادامه دهید.  آنها به طور خودکار در درخواست کشش نشان داده می شوند.

وقتی کارتان با یک پیش نویس تمام شد، می توانید یک pull request ایجاد کنید.  این به تیم محتوا این امکان را می دهد که آن را بررسی کند و نظر بدهد یا درخواست تغییر دهد.
در طول این فرآیند بررسی، می‌توانید به push commit‌ ها به همان branch ادامه دهید.برای ما به طور خودکار در pull request نشان داده می شوند.

هنگامی که pull request تأیید شد و merged شد، محتوا در سرور مستقر می شود.


## رفع اشکالات و اشتباهات تایپی

اگر اشتباهی در محتوا پیدا کردید، باید فایل مربوطه را پیدا کنید تا آن را برطرف کنید و یک pull request ایجاد کنید.  در اینجا نحوه یافتن محتوا آورده شده است.

### Products

- اگر در یک آموزش مخصوص محصول سخت افزاری مشکلی پیدا کرده اید، طبق الگوی زیر قرار گرفته اند:
  `/content/hardware/[product-family]/[product-type]/[product]/tutorials/[tutorial-name]/[content-file].md`

- اگر مشکلی در دیتاشیت محصول سخت افزاری پیدا کرده اید، طبق الگوی زیر قرار دارند:
  `/content/hardware/[product-family]/[product-type]/[product]/datasheet/datasheet.md`

- If you have found an issue in a hardware product's description they are located according to the following pattern:
  `/content/hardware/[product-family]/[product-type]/[product]/product.md`

- If you have found an issue in a hardware product's tech specs table they are located according to the following pattern:
  `/content/hardware/[product-family]/[product-type]/[product]/tech-specs.yml`

- If you have found an issue in a hardware product's features they are located according to the following pattern:
  `/content/hardware/[product-family]/[product-type]/[product]/features.md`

### Software

- If you have found an issue in a software product's tutorial they are located according to the following pattern:
  `/content/software/[product-name]/tutorials/(tutorial-subfolder)/[tutorial-name]/[content-file].md`

## Adding Content

### Referencing Content From Other Folders

The build system supports symlinks. This allows the inclusion of content in multiple places. For example, if there is a tutorial that works for different boards, it can be written once and included in different places. On Unix the `ln` command can be used for that.

به عنوان مثال، اگر ما می خواهیم آموزشی که در اینجا است را داشته باشیم
`content/tutorials/generic/basic-servo-control` برای نمایش در صفحه محصول Nano 33 BLE، می توانیم آن را به صورت زیر پیوند دهیم.  ابتدا یک پوسته باز کنید و به پوشه آموزش محصول بروید.  به عنوان مثال `cd content/hardware/03.nano/boards/nano-33-ble/tutorials/`. سپس یک Symlink با یک مسیر نسبی به آموزش ایجاد کنید.  به عنوان مثال `ln -s ../../../../../tutorials/generic/basic-servo-control basic-servo-control`. این یکبرای نمایش در صفحه محصول Nano 33 BLE، می توانیم آن را به صورت زیر پیوند دهیم.  ابتدا یک پوسته باز کنید و به پوشه آموزش محصول بروید.  به عنوان مثال

#### اضافه کردن Symlinks در ویندوز

برای ایجاد symlink با استفاده از سیستم عامل ویندوز، مراحل زیر را دنبال کنید:

- یک ترمینال (CMD) را به عنوان admin راه اندازی کنید.
- به پوشه‌ای بروید که می‌خواهید پیوندهای symlink داشته باشید.  به عنوان مثال، برای ایجاد پیوند برای برد UNO، به آن بروید
`docs.arduino.cc\content\hardware\02.hero\boards\uno-rev3\tutorials`.
- برای ایجاد یک symlink، باید دستوری شبیه به زیر را اجرا کنید:

```cmd
mklink AnalogInput "..\..\..\..\..\built-in-examples\03.analog\AnalogInput"
```

> The `..\..\` باید با محل فایل اصلی مطابقت داشته باشد.  هر کدام `..\` یک پله بالاتر از دایرکتوری است.


توجه داشته باشید که هنگام ایجاد symlink، فایلی را در کد VS نخواهید دید، اما زمانی که تغییرات را انجام دهید، شناسایی می شود.

On success, the following is printed:
در مورد موفقیت، موارد زیر چاپ می شود:
```cmd
symbolic link created for AnalogInput <<===>> ..\..\..\..\..\built-in-examples\03.analog\AnalogInput
```

### از جمله قطعه کد

تکه های کد را می توان با استفاده از سینتکس بکتیک سه گانه گنجاند. نمونه ` ```arduino`  به دنبال کد و سه بکتیک بسته.  سینتکس های زیر پشتیبانی می شوند:
```
arduino, bash, markup, clike, c, cpp, css, css-extras, javascript, jsx, js-extras, coffeescript, diff, git, go, graphql, handlebars, json, less, makefile, markdown, objectivec, ocaml, python, reason, sass, scss, sql, stylus, tsx, typescript, wasm, yaml
```

### Including Code Blocks fetching GitHub pages

CodeBlocks are custom components that can be added directly in the Markdown on docs-content.

Using this component, the code block will be fetched directly from GitHub pages.

Syntax:

` <CodeBlock url=”https://github.com/example” className="{language}"/>`

URL های شکسته یک هشدار خطا نشان می دهند.  URL باید در دامنه GitHub باشد و باید عمومی باشد.

## پیش نمایش تغییرات

هر زمان که یک درخواست Pull Request (PR) ایجاد می‌کنید و برچسب `preview` به آن اختصاص می‌یابد، یک پیش‌نمایش برای هر 'commit' ایجاد و به‌روزرسانی می‌شود.

## License

![](https://i.creativecommons.org/l/by-sa/3.0/88x31.png)

لطفاً توجه داشته باشید که مشارکت شما در اسناد آردوینو تحت مجوز Creative Commons Attribution است.

https://creativecommons.org/licenses/by-sa/4.0/

در پایان باید اشاره کنم که از هر نوع کمکی قدردانی خواهد شد بطور مثال در موارد زیر شما میتوانید به من کمک کنید:

گرامر و تصحیح املا
ترجمه فنی بهتر
تقویت منابع و مراجع
تصحیح اصلاعات ناقص و نادرست

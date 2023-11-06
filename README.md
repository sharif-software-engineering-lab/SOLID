# SOLID
Introduction to Object-Oriented Principles

<div dir="rtl">
  
## گام ۱: افزودن یک روش پرداخت دیگر

کامیت: [4ca5f69f0292c23cd8be5ee31cb67c746e875fab](https://github.com/sharif-software-engineering-lab/SOLID/commit/4ca5f69f0292c23cd8be5ee31cb67c746e875fab)
| ردیف | محل اعمال تغییرات (کلاس/واسط) | عنوان تغییر | شرحی کوتاه از تغییر |
| - | - | - | - |
| ۱ | واسط OrderService | اضافه شدن تابع phoneOrderRegister | قابلیت سفارش تلفنی به واسط اضافه شد |
| ۲ | واسط OrderService | اضافه شدن تابع phoneOrderPayment | قابلیت پرداخت سفارش تلفنی به واسط اضافه شد |
| ۳ | کلاس OnlineOrderService | اضافه شدن تابع phoneOrderRegister | چون این کلاس واسط OrderService را پیاده‌سازی می‌کند، به اجبار باید این تابع را در آن قرار دهیم |
| ۴ | کلاس OnlineOrderService | اضافه شدن تابع phoneOrderPayment | چون این کلاس واسط OrderService را پیاده‌سازی می‌کند، به اجبار باید این تابع را در آن قرار دهیم |
| ۵ | کلاس OnSiteOrderService | اضافه شدن تابع phoneOrderRegister | چون این کلاس واسط OrderService را پیاده‌سازی می‌کند، به اجبار باید این تابع را در آن قرار دهیم |
| ۶ | کلاس OnSiteOrderService | اضافه شدن تابع phoneOrderPayment | چون این کلاس واسط OrderService را پیاده‌سازی می‌کند، به اجبار باید این تابع را در آن قرار دهیم |
| ۷ | کلاس PhoneOrderService | پیاده‌سازی روش پرداخت جدید | روش پرداخت جدید از طریق تلفن با استفاده از این کلاس و واسط OrderService انجام شد |
| ۸ | کلاس Main | اضافه کردن روش پرداخت جدید | روش پرداخت جدید که در کلاس PhoneOrderService پیاده‌سازی شده بود، به این کلاس اضافه شد |

مجموع تعداد تغییرات: ۸

## گام ۲: تحلیل و وارسی برنامه از منظر تحقق و یا عدم تحقق اصول SOLID

<table dir='rtl'>
<tbody>
<tr>
<td rowspan="2" width="240">
<p>اصل 1</p>
<p>Single Responsibility</p>
</td>
<td width="95">
<p><strong>موارد تحقق</strong></p>
</td>
<td width="454">
کلاس Food، Order و پکیج PaymentService
</td></tr>
<tr>
<td>
<p><strong>موارد نقض</strong></p>
</td>
<td>
این اصل در تابع main نقض شده است
</td></tr>
<tr>
<td rowspan="2">
<p>اصل 2</p>
<p>Open-Close Principle (OCP)</p>
</td>
<td>
<p><strong>موارد تحقق</strong></p>
</td>
<td>
موارد خاص دیگری باقی نمیماند که به این اصل نیاز باشد
</td></tr>
<tr>
<td>
<p><strong>موارد نقض</strong></p>
</td>
<td>
این اصل به طور جدی در پیاده‌سازی PaymentServices نقض شده است 
</td></tr>
<tr>
<td rowspan="2">
<p>اصل 3</p>
<p>Liskov Substitution Principle</p>
</td>
<td>
<p><strong>موارد تحقق</strong></p>
</td>
<td>
این اصل در واسط OrderService تحقق یافته است
</td></tr>
<tr>
<td>
<p><strong>موارد نقض</strong></p>
</td>
<td>
مورد نقضی وجود ندارد 
</td></tr>
<tr>
<td rowspan="2">
<p>اصل 4</p>
<p>Interface Segregation Principle</p>
</td>
<td>
<p><strong>موارد تحقق</strong></p>
</td>
<td>
جای دیگر از واسط استفاده نشده
</td></tr>
<tr>
<td>
<p><strong>موارد نقض</strong></p>
</td>
<td>
در واسط OrderService به صورت جدی نقض شده است
</td></tr>
<tr>
<td rowspan="2">
<p>اصل 5</p>
<p>Dependency Inversion Principle</p>
</td>
<td>
<p><strong>موارد تحقق</strong></p>
</td>
<td>
رابطه کلاس Main و OrderService
</td></tr>
<tr>
<td>
<p><strong>موارد نقض</strong></p>
</td>
<td>
مورد نقضی وجود ندارد
</td></tr>
</tbody>
</table>



در خصوص هرکدام از موارد نقض هرکدام از اصول، یک راهکار را به منظور رفع آن مشکل ارایه داده و در جدول زیر ثبت نمایید:

| اصل مربوطه (از اصول SOLID) | علت نقض | راه حل پیشنهادی |
| - | - | - |
| تک مسئولیتی | کارهای متعددی در تابع main انجام می‌شود | باید هر کدام از این کارها در توابع جدا انجام شوند و در تابع main صدا زده شوند |
| اصل OCP | برای اضافه کردن پیاده‌سازی جدید به رابط OrderService نیاز به تغییر خود تابع هست | تابع‌های وابسطه به کلاس از اینترفیس خارج شوند |
| اصل ISP | کلاس‌هایی که رابط OrderService را پیاده‌سازی می‌کنند مجبور به پیاده‌سازی توابعی هستند که استفاده نمی‌کنند | توابع عمومی در رابط قرار گیرند |

## گام ۳: اصلاح موارد نقض
کامیت‌ها:
- [b2eb816eb21295405925397b701819138b36f417](https://github.com/sharif-software-engineering-lab/SOLID/commit/b2eb816eb21295405925397b701819138b36f417)
- [326e121078d6011c4e6b40fa5e8901c87ad0d552](https://github.com/sharif-software-engineering-lab/SOLID/commit/326e121078d6011c4e6b40fa5e8901c87ad0d552)

## گام ۴: بررسی مجدد تغییرات مورد نیاز

1. در این صورت از انجام کدام یک از تغییرات ثبت شده در جدول گام ۱ معاف خواهید شد؟
> بسیار جالب است که بدانید از تمامی تغییرات ۱ تا ۶ معاف می‌شویم و تنها دو تغییر ۷ و ۸ نیاز است. 
3. تعداد تغییرات مورد نیاز، چند تغییر خواهد شد؟
> ۲ تغییر 

## گام ۵: جمع بندی

در آخر متوجه شدیم که اگر اصول SOLID را رعایت نکنیم، نگهداری از کد و به صورت خاص اضافه کردن یک قابلیت خاص به کد بسیار سخت، پیچیده و طاقت‌فرسا می‌شود. درست است که رعایت اصول SOLID از بدو طراحی و پیاده‌سازی کد وقت گیر است و باعث کندتر شدن روند توسعه می‌شود، ولی با رعایت این اصول در بلند مدت زمان بسیار کمتری برای توسعه و نگه‌داری از کد صرف می‌شود. پس در نهایت رعایت اصول SOLID به نفع همه خواهد بود و همه برنامه‌نویس‌ها باید از آن تبعیت کنند. 

</div>

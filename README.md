# SOLID
Introduction to Object-Oriented Principles

<div dir="rtl">
  
## گام ۱: افزودن یک روش پرداخت دیگر


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
---
</td></tr>
<tr>
<td>
<p><strong>موارد نقض</strong></p>
</td>
<td>
---
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
---
</td></tr>
<tr>
<td>
<p><strong>موارد نقض</strong></p>
</td>
<td>
---
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
---
</td></tr>
<tr>
<td>
<p><strong>موارد نقض</strong></p>
</td>
<td>
---
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
---
</td></tr>
<tr>
<td>
<p><strong>موارد نقض</strong></p>
</td>
<td>
---
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
---
</td></tr>
<tr>
<td>
<p><strong>موارد نقض</strong></p>
</td>
<td>
---
</td></tr>
</tbody>
</table>



در خصوص هرکدام از موارد نقض هرکدام از اصول، یک راهکار را به منظور رفع آن مشکل ارایه داده و در جدول زیر ثبت نمایید:

| اصل مربوطه (از اصول SOLID) | علت نقض | راه حل پیشنهادی |
| - | - | - |
| ش | ش | ش |

## گام ۳: اصلاح موارد نقض

## گام ۴: بررسی مجدد تغییرات مورد نیاز

1. در این صورت از انجام کدام یک از تغییرات ثبت شده در جدول گام ۱ معاف خواهید شد؟
2. تعداد تغییرات مورد نیاز، چند تغییر خواهد شد؟

## گام ۵: جمع بندی

در آخر 

</div>

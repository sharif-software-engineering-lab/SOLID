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

</div>

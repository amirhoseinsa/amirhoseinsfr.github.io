<link href="https://fonts.googleapis.com/css?family=Changa" rel="stylesheet"> 
<link href="https://fonts.googleapis.com/css?family=Scheherazade" rel="stylesheet">


<div dir="rtl" align="center" style = " font-family: 'Changa', sans-serif; font-size:150%" >HTTPS  باعث آسیب رسیدن به کاربرانی میشود که از سرور شما دور می باشند  :    </div>

<div dir="rtl" align="center" style = "font-family: 'Scheherazade', serif;">
 <br>
 _______________________________________________________
</div>


<div dir="rtl" align="center" style = "font-family: 'Scheherazade', serif; font-size:190% ;color:black;">
<br>
خلاصه : 
</div>

<div dir="rtl" align="center" style = "font-family: 'Scheherazade', serif; font-size:150%">
<br>

برای دست دادن (شروع ارتباط یا همان درخواست برقراری ارتباط) در HTTPS، کاربر قبل از فرستادن درخواست خودش باید ابتدا کلید را از سرور بگیرد. این مساله باعث می شود که برای برقراری هر ارتباط جدید به یک سفر رفت و برگشت اضافی در مقایسه با فرستادن درخواست و دریافت مستقیم جواب نیاز داشته باشیم. پس از اینکه اولین درخواست پاسخ داده بشود و انجام شود، ارتباط تا زمانی که کاربر فعال است باز نگه داشته می شود و ارتباط قطع نمی شود. این سفر رفت و برگشت اضافی هنگامی باعث ایجاد مشکل می شود که کاربرانی که به سرور ما وصل می شود در سراسر جهان پخش شده باشند و همگی محدود به یک منطقه جغرافیایی نباشند.
</div>


<div dir="rtl" align="center" style = "font-family: 'Scheherazade', serif; font-size:150%">
<br>

برای حل این مشکل تا به حال دو راه حل پیشنهاد شده است : 
<br>
1 _ به بازدید کننده این اجازه را بدهیم که به طور مستقیم درخواست خودش را رمزگذاری کرده و برای سرور بفرستد تا هند شیکینگ را به طور کامل انجام ندهد که برای انجام اینکار نیاز است که سرور کلید را از قبل با کلاینت به اشتراک گذاشته باشد.
<br>
2 _ ایده این روش این می باشد که ارتباط را بین لبه های Cloudflare سرور و کاربر باز نگه داریم و آن را نبندیم و سپس هنگامی که خواستیم ارتباط را برقرار کنیم Cloudflare ها باعث میشوند که نیاز به ارسال داده های کمتری داشته باشیم و مقدار قابل توجهی از داده ها را میتوانیم از طریق Cloudflare  منتقل کنیم و این باعث میشود که هند شیکینگ سریع تری داشته باشیم.

</div>

<div dir="rtl" align="center" style = "font-family: 'Scheherazade', serif;">
 <br>
 _______________________________________________________
</div>


<div dir="rtl" align="center" style = "font-family: 'Scheherazade', serif; font-size:190%; color:black;">
<br>
تحلیل : 
</div>

<div dir="rtl" align="center" style = "font-family: 'Scheherazade', serif; font-size:150%">
<br>
در مواقعی که کاربرهای سرور ما کاربران محلی باشند، استفاده از HTTPS مشکلی را برای ما بوجود نمی آورد اما هنگامی که کاربران ما در سراسر جهان پخش شده باشند آنگاه استفاده از HTTPS باعث بروز مشکل می شود. هرچند که این مشکل در ابتدا مهم به نظر نمی رسد اما برای مثال یک سفر رفت و برگشت از برلین به مرکز داده AWS سیدنی حدود 345 میلی ثانیه طول می کشد که زمان زیادی می باشد ما با استفاده از HTTPS دوبار نیاز به این سفر داریم که باعث هدر رفتن زمان زیادی می شود و کاربر باید مدت زمان زیادی را منتظر باشد که این مشکلی جدی است.
</div>

<div dir="rtl" align="center" style = "font-family: 'Scheherazade', serif; font-size:150%">
<br>
راه حل های پیشنهاد شده همچنان نتوانسته اند این مشکل را حل کنند، راه حل اول هنوز کامل پیاده سازی نشده است و در دسترس نمی باشد و در پیاده سازی آن مشکلاتی از جمله مشکلات امنیتی وجود دارد، مشکل راه حل دوم هم این می باشد که برای سرور کمی پر هزینه است (مبلغی حدود 200 دلار در ماه) و در بسیاری از موارد این کار صرفه اقتصادی ندارد اما این روش از لحاظ علمی کارآمد می باشد.
</div>

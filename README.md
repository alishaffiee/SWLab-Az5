# SWLab-Az5

## توضیحات قسمت عملی

در توسعه‌ی این کد از روش TDD استفاده شده است. بدین ترتیب که در ابتدا، تست‌ها را نوشتیم و فرض کردیم که کلاس‌های Reactangle و Squera به‌طور کامل و طبق خواسته‌ی صورت تمرین وجود دارند؛ طبق اصل اول SOLID بهتر است این دو کلاس مجزا را داشته باشیم. در فایل Test.java دو تا متد تست وجود دارد که هر کدام یکی از کلاس‌ها را تست می‌کند در هد کدام از متدها هم ابتدا یک شی از آن نوع ساخته‌ایم و متدهای get مربوطه به آن کلاس را بررسی کرده‌ایم که درست باشند، سپس با کمک توابع set مقدار طول‌ها را تغییر دادیم و پس از آن دوباره توابع get را صدا زده‌ایم تا مطمئن شویم کلاس‌ها به‌طور کامل کار می‌کنند و سناریوهایی که ممکن است در برنامه پیش بیایند به‌طور کامل پوشش داده می‌شوند.

پس از آن وارد نوشتن خود کدهای پروژه شدیم. در این کد کاری کرده‌ایم تا مستطیل از مربع ارث ببرد؛ علت این تصمیم این است که مستطیل به نسبت مربع ویژگی‌های بیشتری دارد و پیچیدگی‌اش بیشتر است؛ می‌توان گفت اصل سوم SOLID به ما می‌گوید تا از این تصمیم استفاده کنیم. منطق کدها بسیار ساده هستند و نیازمندی‌ای که در قسمت تست‌ها مشخص کرده‌ایم را برطرف می‌کنند. 

## سوالات تئوری

### توضیح اصول SOLID

۱. اصل Single Responsibility Principle: این اصل به‌طور کلی می‌گوید که هر کلاس فقط باید برای انجام دادن یک مسئولیت واحد به وجود آمده باشد؛ بدین معنی که دو بخش مختلف که نیازمندی‌های مختلفی دارند، نیازمندی‌شان صرفا توسط یک کلاس برطرف نشود. رعایت این اصل کمک می‌کند تا در صورتی که یکی از نیازمندی‌های مقداری تغییر کرد و بقیه تغییری نکردند، دیگر نیاز نباشد کل کد را برای هندل کردن دیگر نیازمندی‌ها که توسط کلاس مشابه برطرف می‌شد، تغییر کند

۲. اصل Open-Closed Principle: این اصل می‌گوید که نرم‌افزار همیشه باید برای توسعه دادن باز باشد و ما امکان توسعه را در هر صورت داشته باشیم؛ اما این توسعه باید بدون تغییر کدهای اصلی باشد و به اصطلاح آن بخش‌ها بسته هستند و تغییری نمی‌کنند.

۳. اصل Liskov Substitution Principle: طبق این اصل اگر کلاس B کلاس A را اکستند می‌کند باید بتوان با کمک کلاس B هر شیئی از کلاس A را ساخت تا بتوانیم از همه‌ی قابلیت‌های جدیدی که در کلاس A نسبت به B قرار دارد استفاده کنیم. 

۴. اصل Interface Segregation Principle (ISP): یک کلاس نباید interface هایی پیاده‌سازی که به آن‌ها نیازی ندارد. در واقع در صورتی که نیاز داریم یک کلاس ویژگی‌های دیگری وابسته به نیازمندی یک کلاس دیگر داشته باشد، این اتفاق باید توسط واسط‌هایی بیفتد که بین این دو کلاس قرار می‌گیرد و در واقع چیزی به کلاس اولیه اضافه نمی‌کنیم. 

۵. اصل Dependency Inversion Principle: طبق این اصل ماژول‌ها و کلاس‌های سطح بالا نباید وابسته به ماژول‌ها و کلاس‌های سطح پایین باشند. این اصل ما را تشویق می‌کند تا بیشتر از اینترفیس‌ها استفاده کنیم و نیازمندی‌های بین ماژول‌ها را کمتر کنیم.


### استفاده از اصول SOLID در گام‌های مهندسی نرم‌افزار

از این اصول بیشتر در مراحل طراحی و پیاده‌سازی استفاده می‌شود؛ بدین شکل که در مرحله‌ی طراحی با کمک گرفتن از این اصول می‌توانیم معماری بهتری برای نرم‌افزارمان داشته باشیم تا هم توسعه‌ی آن ساده‌تر باشد و هم بتوان به شکل مناسب‌تری از آن نگهداری کرد. بعد از آن هم در مرحله‌ی پیاده‌سازی از این اصول بهره می‌گیریم تا بتوانیم مواردی که در بخش معماری فیکس کرده‌ایم را رعایت کنیم و معماری‌مان را مطابق با اصول SOLID پیاده‌سازی کنیم.
البته از اصول SOLID می‌توان در مرحله‌ی تست هم بهره گرفت بدین صورت که هر کدام از تست‌های ما باید فقط بر یک چیز تمرکز کنند و آن را بسنجند. مشابه اصل اول SOLID که هر کلاس باید فقط برای یک مسئولیت به وجود آمده باشد.


### تست‌نویسی در TDD و اختلاف آن با روش سنتی توسعه‌ی نرم‌افزار

در روش سنتی توسعه‌ی نرم‌افزار ایتدا معماری را مشخص می‌کنیم و کدها را می‌زنیم و در نهایت تست‌ها را می‌نویسیم و آن‌ها را اجرا می‌کنیم. در جفت این موارد برای ما مهم است که حتما کد ما به‌درستی تست شود و این تست‌ها قابلیت اجرا در آینده را هم داشته باشند. مزیت روش TDD این است که ما از قبل همه‌ی نیازمندی‌ها را در قالب تست‌ها مشخص می‌کنیم تا کاملا صورت مساله برایمان شفاف باشد تا بتوانیم به‌خوبی نرم‌افزار را توسعه دهیم؛ از همین رو نمی‌توان گفت که نوشتن کدها قبل از پیاده‌سازی با پیاده‌سازی بعد از آن در تناقض است چون اتفاقا کمک می‌کند تا پیاده‌سازی با شکل بهتری و با چهارچوب‌های مشخص جلو برود تا ابهام در زمان کد زدن کمتر باشد و سریع‌تر و با بازده بیشتر بتوانیم به نتیجه‌ی دلخواهمان برسیم.


### تغییرات مدل‌ها در صورت عدم نیاز به تغییر ابعاد مستطیل

باز هم طراحی مدل‌ها تغییر خاصی نمی‌کرد چون طبق اصل اول SOLID باز هم بهتر است دو کلاس متفاوت برای مستطیل و مربع داشته باشیم و کلاس‌هایمان تفاوتی نمی‌کرد. صرفا از کلاس Rectangle باید متدهای مربوط به set برداشته می‌شد.


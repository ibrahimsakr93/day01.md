1. Laravel: تسجيل الـ middleware في Laravel 11

البرومبت: "أضيف middleware مخصص في Laravel 11 إزاي؟"
الغلط المتوقع: النموذج يقولك عدّل app/Http/Kernel.php ويضيفه في $routeMiddleware.
الصح: في Laravel 11 مفيش Kernel.php. التسجيل بيتم في bootstrap/app.php جوه ->withMiddleware(function (Middleware $middleware) { ... }).
الدليل: صفحة Middleware في توثيق Laravel 11.

2. Next.js: الـ params في Next.js 15

البرومبت: "اعمل صفحة app/posts/[id]/page.tsx تجيب الـ id من الـ params".
الغلط المتوقع: const { id } = params بشكل مباشر من غير await.
الصح: في Next.js 15 الـ params وsearchParams بقوا Promise، فتكتب const { id } = await params. نفس الحكاية مع cookies() وheaders().
الدليل: صفحة الـ upgrade guide لـ Next.js 15 (Async Request APIs).

3. Flutter: APIs اتعمل لها deprecate

البرومبت: "اعمل زرار يمنع الرجوع لو الفورم فيها بيانات، ودرّج لون بشفافية 50%".
الغلط المتوقع: يستخدم WillPopScope وColor.withOpacity().
الصح: PopScope بدل WillPopScope، وwithValues(alpha: 0.5) بدل withOpacity في الإصدارات الحديثة.
الدليل: Flutter breaking changes، وتحذيرات الـ analyzer في نسختك.

4. MySQL: الـ charset

البرومبت: "عايز أخزن رسائل عربي فيها إيموجي في MySQL، أعمل الجدول إزاي؟"
الغلط المتوقع: يقولك CHARACTER SET utf8 كفاية.
الصح: utf8 في MySQL هو utf8mb3 وبيرفض الإيموجي (4 bytes)، فلازم utf8mb4.
الدليل: توثيق MySQL عن utf8mb3 مقابل utf8mb4.

5. cPanel: كرون الـ Laravel scheduler

البرومبت: "أظبط schedule:run على cPanel لمشروع Laravel بيشتغل على PHP 8.2".
الغلط المتوقع: يكتب php /home/user/app/artisan schedule:run بالـ php العادي.
الصح: الـ php في الـ CLI ممكن يكون إصدار مختلف عن اللي مختاره في MultiPHP، فالأأمن تكتب المسار الكامل، زي /opt/cpanel/ea-php82/root/usr/bin/php. اتأكد من المسار عندكم من الـ hosting.
الدليل: توثيق cPanel (MultiPHP) + php -v من الـ Terminal

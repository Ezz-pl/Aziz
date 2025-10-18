document.addEventListener('DOMContentLoaded', () => {

    // ***************************************************
    // 1. منطق تبديل اللغة (Localization Logic)
    // ***************************************************
    const langSwitchBtn = document.getElementById('lang-switch');
    const htmlElement = document.documentElement;

    // قاموس الترجمة: يجب تحديث هذا القاموس ليشمل جميع النصوص في الموقع
    const translations = {
        'ar': {
            'h1': 'عبدالعزيز',
            'h2': 'خبير في قيادة الابتكار والتوسع التكنولوجي',
            'tag-line': 'أُحوّل الاستراتيجيات الجريئة إلى نتائج رقمية ملموسة. خبرة 12 عاماً في قيادة نمو الأداء والتحول المؤسسي.',
            'switch-text': 'English | EN',
            'dir': 'rtl',
            'font-family': 'var(--font-ar)'
            // ... (يجب إضافة كل النصوص هنا)
        },
        'en': {
            'h1': 'Abdulaziz',
            'h2': 'Expert in Leading Innovation & Tech Expansion',
            'tag-line': 'I transform bold strategies into tangible digital results. 12 years experience in driving performance growth and corporate transformation.',
            'switch-text': 'العربية | AR',
            'dir': 'ltr',
            'font-family': 'var(--font-en)'
            // ... (يجب إضافة كل النصوص هنا)
        }
    };

    const applyTranslations = (lang) => {
        const data = translations[lang];
        
        // تطبيق اللغة والاتجاه والخط
        htmlElement.lang = lang;
        htmlElement.dir = data.dir;
        document.body.style.fontFamily = data['font-family'];

        // تحديث النصوص الرئيسية
        document.querySelector('.hero-content h1').textContent = data.h1;
        document.querySelector('.hero-content h2').textContent = data.h2;
        document.querySelector('.tag-line').textContent = data['tag-line'];
        langSwitchBtn.textContent = data['switch-text'];
        
        // تحديث حالة الزر
        langSwitchBtn.dataset.lang = lang === 'ar' ? 'en' : 'ar';
    };

    langSwitchBtn.addEventListener('click', () => {
        const currentLangToggle = langSwitchBtn.dataset.lang;
        applyTranslations(currentLangToggle);
    });

    // ***************************************************
    // 2. التدقيق على الروابط والأكشن (CTAs)
    // ***************************************************

    // تدقيق زر تحميل السيرة الذاتية
    const downloadBtn = document.getElementById('download-cv-btn');
    downloadBtn.addEventListener('click', (e) => {
        // تنبيه في حال لم يتم رفع الملف الفعلي على GitHub
        if (downloadBtn.getAttribute('href') === 'CV_2025.pdf') {
             // يمكن للمبرمج إزالة هذا الكود بعد رفع الملف فعلياً
             console.warn('تنبيه: تأكد من رفع ملف CV_2025.pdf في مجلد GitHub.');
        }
    });

    // تدقيق عمل نموذج التواصل (Contact Form)
    const contactForm = document.getElementById('contact-form');
    contactForm.addEventListener('submit', (e) => {
        e.preventDefault();
        
        // ** ملاحظة هامة: يجب هنا ربط النموذج بخدمة Backend (مثل Netlify Forms أو Formspree) **
        // هذا التنبيه هو مؤقت لضمان أن الزر يعمل.
        alert('شكراً لك يا عبد العزيز! تم استلام رسالتك. (تنبيه وهمي)');
        contactForm.reset();
    });
    
    // ***************************************************
    // 3. تأثيرات الإبهار (ظهور الأقسام عند التمرير)
    // ***************************************************
    const elementsToReveal = document.querySelectorAll('.reveal-on-scroll');
    const observer = new IntersectionObserver((entries, observer) => {
        entries.forEach(entry => {
            if (entry.isIntersecting) {
                entry.target.style.opacity = 1;
                entry.target.style.transform = 'translateY(0)';
                entry.target.style.transition = 'opacity 0.6s ease-out, transform 0.6s ease-out';
                observer.unobserve(entry.target);
            }
        });
    }, {
        threshold: 0.1 
    });

    elementsToReveal.forEach(el => {
        el.style.opacity = 0;
        el.style.transform = 'translateY(50px)';
        observer.observe(el);
    });
});

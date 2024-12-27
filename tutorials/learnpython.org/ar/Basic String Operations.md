Strings هي أجزاء من النص. يمكن تعريفها كأي شيء بين العلامات التنصيصية:

    astring = "Hello world!"
    astring2 = 'Hello world!'

كما ترى، أول شيء تعلمته هو طباعة جملة بسيطة. وقد خزنها Python كسلسلة نصية. ومع ذلك، بدلاً من طباعة السلاسل النصية فورًا، سنستكشف الأمور المختلفة التي يمكنك القيام بها بها.

يمكنك أيضًا استخدام علامات التنصيص الفردية لتعيين سلسلة نصية. ومع ذلك، ستواجه مشاكل إذا كانت القيمة المراد تعيينها تحتوي على علامات التنصيص الفردية نفسها. على سبيل المثال، لتعيين السلسلة النصية بين القوسين (علامات التنصيص الفردية هي ' ') يجب عليك استخدام علامات التنصيص المزدوجة فقط مثل هذا

    astring = "Hello world!"
    print("single quotes are ' '")

    print(len(astring))

الذي يطبع 12، لأن "Hello world!" مكونة من 12 حرفًا، بما في ذلك علامات الترقيم والمسافات.

    astring = "Hello world!"
    print(astring.index("o"))

الذي يطبع 4، لأن موضع أول ظهور للحرف "o" يبعد 4 أحرف عن أول حرف. لاحظ كيف يوجد في الواقع حرفين "o" في العبارة - هذه الطريقة تتعرف فقط على الأول.

لكن لماذا لم يطبع 5؟ أليس "o" هو الحرف الخامس في السلسلة؟ لتبسيط الأمور، تبدأ Python (ومعظم لغات البرمجة الأخرى) الأشياء من 0 بدلاً من 1. لذا فإن الفهرس للحرف "o" هو 4.

    astring = "Hello world!"
    print(astring.count("l"))

بالنسبة لأولئك الذين يستخدمون خطوطًا غريبة، هذا هو الحرف "l" الصغير، وليس رقم 1. هذا يحسب عدد الحروف "l" في السلسلة. لذلك، يجب أن يطبع 3.

    astring = "Hello world!"
    print(astring[3:7])

هذا يطبع جزءًا من السلسلة، بدءًا من الفهرس 3، وينتهي عند الفهرس 6. ولكن لماذا 6 وليس 7؟ مرة أخرى، تفعل معظم لغات البرمجة ذلك - يجعل ذلك القيام بالرياضيات داخل تلك الأقواس أسهل.

إذا كان لديك مجرد رقم واحد داخل الأقواس، فسوف يعطيك الحرف الوحيد في ذلك الفهرس. إذا قمت بترك الرقم الأول ولكن احتفظت بالنقطتين، فسوف يطبع لك جزءًا من البداية إلى الرقم الذي تركته. إذا قمت بترك الرقم الثاني، فسوف يطبع لك جزءًا من الرقم الأول إلى النهاية.

يمكنك حتى وضع الأرقام السلبية داخل الأقواس. إنها طريقة سهلة للبدء من نهاية السلسلة بدلاً من البداية. بهذه الطريقة، -3 تعني "الحرف الثالث من النهاية".

    astring = "Hello world!"
    print(astring[3:7:2])

هذا يطبع حروف السلسلة من 3 إلى 7 متخطياً حرفاً واحداً. هذا هو بناء الشريحة الموسع. الشكل العام هو [start:stop:step].

    astring = "Hello world!"
    print(astring[3:7])
    print(astring[3:7:1])

لاحظ أن كلاهما ينتج نفس النتيجة.

لا توجد دالة مثل strrev في لغة C لعكس سلسلة نصية. ولكن مع نوع الشريحة المذكور أعلاه يمكنك بسهولة عكس سلسلة نصية مثل هذا

    astring = "Hello world!"
    print(astring[::-1])

هذا

    astring = "Hello world!"
    print(astring.upper())
    print(astring.lower())

يؤديان إلى تكوين سلسلة جديدة مع تحويل جميع الحروف إلى الأحرف الكبيرة والصغيرة، على التوالي.

    astring = "Hello world!"
    print(astring.startswith("Hello"))
    print(astring.endswith("asdfasdfasdf"))

يستخدم هذا لتحديد ما إذا كانت السلسلة تبدأ بشيء ما أو تنتهي بشيء ما، على التوالي. الأول سيطبع True، حيث أن السلسلة تبدأ بـ"Hello". والثاني سيطبع False، حيث أن السلسلة لا تنتهي بـ"asdfasdfasdf".

    astring = "Hello world!"
    afewwords = astring.split(" ")

هذا يقسم السلسلة إلى مجموعة من السلاسل المجموعة معًا في قائمة. نظرًا لأن هذا المثال يقسم عند مسافة، سيكون أول عنصر في القائمة هو "Hello"، والثاني سيكون "world!".

Exercise
--------

حاول إصلاح الكود لطباعة المعلومات الصحيحة عن طريق تغيير السلسلة النصية.
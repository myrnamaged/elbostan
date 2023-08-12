<html>
<head>
  <title></title>
<head> 
<style>
  p { background: white;
  box-shadow:0 2px 5px rgba(0, 0, 0, 0.1);
  border-radius:15px;
  padding: 30px;
  max-height: 400px;
  width: 400px;
  font-size: 20px;
  color: gray;
  text-align: center;
  margin:auto;
  }
  h1 { background: white;
  box-shadow:0 2px 5px rgba(0, 0, 0, 0.1);
  border-radius:15px;
  padding: 30px;
  max-height:100px;
  width: 200px;
  font-size: 24px;
  color: gray;
  text-align: center;
  margin:auto;
  margin-bottom: 30;
  }
  body {font-family: Arial,Sans-Serif;
  background-image: url("https://i.ibb.co/xSmRBbG/362296943-6532817723474788-3100763377268110788-n.jpg");
  opacity:0.9;
  background-position: center;
  background-size:contain ;
  background-repeat: no-repeat;
  margin: 100px;
  padding: 20px;
  }
 
  qoute-background { max-height: 600px;
  max-width: 300px;
  text-align: center;
  opacity : 0.1;
  }
</style>
<body>
<h1>أقوال الآباء</h1>
<p id="quote"></p>
</body>
 <script>
const quotes = ["القلب المتضع كالوادى المنخفض الذى سرعان ما يمتلىء من ماء الروح - القديس أغسطينوس",
"اذا اكمل الانسان جميع الحسنات وفى قلبه حقد على اخيه فهو غريب عن الله - الانبا باخوميوس اب الشركة",
"لزمنا أن نعرف متى نصمت و متى نتكلم،و كيف نصمت و بماذا نتكلم - القديس مار اسحق السريانى",
"لا تتحدث بجميع افكارك لجميع الناس الا للذين لهم القدره في خلاص نفسك لئلا تكون عثره - الأنبا انطونيوس الكبير",
"لا تتبع كل افكارك بل اجعل فكرك في الوصايا كل حين و داوم علي فعلها - الأنبا انطونيوس الكبير", 
"تفكر في كل يوم انه اخر ما بقي لك في العالم فان ذلك ينقذك من الخطيه - الأنبا انطونيوس الكبير",
"يا ابني ان تجعل اتكالك علي المال بل اتكل علي المسيح - الأنبا انطونيوس الكبير",
"لا تكن كسلانا فتموت بأشر حال -  الأنبا انطونيوس الكبير",
"اطلب التوبه في كل لحظه و لا تدع نفسك للكسل لحظه واحده - الأنبا انطونيوس الكبير" ,
 "لا يُهذب الأب ابنه لو لم يكن يحبه، والمُعلم لا يُصلح من شأن تلميذه ما لم يرَ فيه علامات نوال الوعد. عندما ينزع الطبيب عنايته عن مريض يُحسَب هذا علامة يأسه من شفائه - القديس جيروم",
"الخدمة بدون حب المصلوب هى مجرد عمل بشرى له نهاية - لابونا بيشوى كامل",
"القلب عندما يقدم للآخرين خدمة من أجل الرب يسوع فإن صورة الرب تنطبع عليه فيستنير بنوره - لابونا بيشوى كامل",
"الكاهن والخادم المحب للظهور بذاته وبخدمته يفرح قلب الشيطان - لابونا بيشوى كامل",
"الانسان الذى يحيا حياة المسيح بدقة وأمانة يحمل صورة المسيح ورائحته وينشرها فى كل مكان - لابونا بيشوى كامل",
"الخدمة ليست إضافة جديدة للمخدومين ، بل نبش الينابيع الكامنة فيهم - لابونا بيشوى كامل",
"يجب عليك أن تكون راضياً بما لديك حتى لا تتألم وتصير غير شاكراً ، فتطلم نفسك بنفسك دون أن تدري؛ ولكن هناك طريقٌ واحدٌ ، احتقر تلك العطايا الزمنية - الأنبا انطونيوس الكبير",
"لا تتبع جميع أفكارك؛ بل اجعل فكرك في الوصايا كل حين، وداوم على فعلها. ولا تفكر في الخطايا القديمة التي فعلتها؛ لئلا تتجدد عليك. ولا تذكر لذلك الشهوات في زمان كسلك، ولا تتحدث عنها؛ لئلا تصبح لك عثرة - الأنبا انطونيوس الكبير ",
"ثق أن كل كلمة تقرأها من الكتاب (المقدس) سيكون لها تأثيرها فيك، وقوتها، وفاعليتها دون شرح ودون وعظ - البابا شنوده الثالث",
" المُلتصق بمُحب الله يستغني بأسرار الله، والمُلتصق بالجاهل والمُفتخر يبتعد من الرب، وأيضاً يُبغَض من أحبائه - الشيخ الروحاني يوحنا سابا",
"الكبرياء طردت الملائكة من السماء، والاتضاع جعل ابن الله ينزل من السماء؛ ليتجسد على الأرض. الكبرياء أخرجت آدم من الفردوس، والاتضاع أدخل اللص إليه - القديس أوغسطينوس",
"احذر أن تقول كلمة جفاء لإنسانٍ أو تصنع عملاً يوجع إنساناً - الشيخ الروحاني يوحنا سابا",
"تعلم كيف تصلي، واغصب ذاتك على الصلاة. في البداءة سيكون الأمر لديك شاقاً؛ ولكن بعدئذ كلما غصبت نفسك صار سهلاً لديك أن تصلي، كل شيء في بدايته يحتاج إلى أن يغصب الإنسان نفسه عليه - القديس الأب يوحنا كاسيان",
"حينما تأخذ مكانك على المائدة، إبدأ بالصلاة. لماذا التسرُّع؟! هل الطعام سيَفرُّ من أمامك؟! - البابا شنوده الثالث ",
"بدلاً من أن تحمل سلاحاً أو شيئاً يحميك، إحمل الصليب، واطبع صورته على أعضائك وقلبك، وارسم به ذاتك، لا بتحريك اليد فقط؛ بل ليكن برسم الذهن والفكر أيضاً، ارسمه في كل مناسبة: في دخولك وخروجك، في جلوسك وقيامك، في نومك وفي عملك، ارسمه باسم الآب والابن والروح القدس - القديس مار أفرام السرياني ",
"أيها الأخ، اعمل في حداثتك؛ لكي لا تندم في أواخرك، لا تنافس الأشرار، ولا تُباري الذين يعملون الإثم، فإنهم كالحشيش يجفون سريعاً، وكبقل الخضرة يذبلون قريباً. توكل على الرب، واعمل صلاحاً - القديس مار أفرام السرياني",
"لا تفصل قلبك عن الله. داوم معه حارساً قلبك من كل فكر يبعدك عنه بدوام ذكر الرب يسوع المسيح حتى يتأصل اسم الرب في قلبك، ولا يفكر في شيء آخر سوى تمجيد المسيح - القديس يوحنا ذهبي الفم",
"هل تظن أن الإنسان يسقط في الخطية، بسبب أن الخطية قوية، والعثرات شديدة، والشيطان كثير الحيل؟!! كلا، بل أنه يسقط بالأكثر لأن قلبه خالٍ من محبة الله  - البابا شنوده الثالث",
"بمقدار ما يعطي الإنسان نفسه لخدمة وراحة آخرين بإفراز، هكذا الله يظهره لكثيرين ويرفعه ويمجده - الشيخ الروحاني يوحنا سابا",
"كل مَنْ يُجاهد من أجل العفة، يكون له عند الله دالةٌ عظيمةٌ - القديس الأنبا دانيال",
"أرح المُتعبين، افتقد المرضى، أعن الفقراء؛ لأن هذه أيضاً صلاة - القديس الأب أفراهات",
"إذا أردت حقاً أن تغلب أفكارك، وتلبسها الخزي: قف صامتاً، وهدئ قلبك، وإبدأ بصلاة قصيرة مثل صلاة «ياربي يسوع»، إلصق بها كل حواسك. وكلما زاغ عقلك رُدَّه، ففي أيام قليلة ترى قيمة هذا العمل القديس حزقيوس الأورشليمي",
" إن كنت رئيساً لغيرك، أو من رجال الدين، أو أباً جسدياً؛ فلا تُعطِ نفسك الحق في الكلام، بلا ضابط أو بلا مُراعاة لمشاعر غيرك - البابا شنوده الثالث",
" مخافة الرب ينبوع حياة، مخافة الرب تنقي العقل، مخافة الرب صيانة للنفس، مخافة الرب تعطي المُتقي الرب نعمةً في كل تصرفاته، مخافة الرب مُديرة للنفس، خشية الرب تضيء النفس، وتبعد كل ما هو خبيث، مخافة الرب تبعد الآلام وتنمي المحبة، مخافة الرب تقطع كل شهوة ردية - القديس مار أفرآم السرياني",
"إن الإهمال في تأدية رسم الصليب أمر ربما نُدان عليه. فإن رسم الصليب اعتراف بيسوع المسيح مصلوباً، وإيمان بالآلام التي عاناها فوق الصليب. إنه اعتراف وذكرى لعمل الرب، ومكتوب في (إرميا ٤٨: ١٠) «ملعونٌ مَنْ يعمل عمل الرب برخاوة» - القديس الأب يوحنا كاسيان", 
"لا تخجل يا أخي من علامة الصليب، فهو ينبوع الشجاعة والبركات، وفيه نحيا مخلوقين خلقة جديدة في المسيح. إلبسه وافتخر به كتاجٍ  - القديس يوحنا ذهبي الفم",
"الصلاة وسيلة لفحص القلب، وإصلاح عيوبه، وإعداده لحلول السيد المسيح، وعمل النعمة - القديس الأب يوحنا كاسيان",
" ليست دعوة للحب أعظم من أن تُبادر بالحب - القديس أوغسطينوس",
"لا تُبدد طاقاتك في السلبيات، فإن الشيطان مستعد أن يقدم لك سلبيات في كل يوم؛ ليشغلك بها - البابا شنودة الثالث",
" أيها الإخوة الأعزاء، إن أعمال المحبة عظيمةٌ إلهيةٌ، هي تعزيةٌ عظيمةٌ للمؤمنين، حارسٌ نافعٌ لنجاتنا، وحصنٌ للرجاء، حمايةٌ للإيمان، وعلاجٌ للخطية - القديس كبريانوس",
"الجدير بك أن تبغض زلات الخاطئ وتتضرع لأجله؛ لتكون مُشابهاً للمسيح، لأنه اتكأ مع الآثمة - مار إسحق السرياني",
"لندرب أنفسنا على محبة الإخوة، فإن أحببت أخاك ستُعاين الله؛ لأن بمحبتك لأخيك تُعاين المحبة ذاتها التي فيها يُسكن الله - القديس أوغسطينوس",
"كل شيء يُزينه الاعتدال، الذي بدونِهِ تتحول الأمور النافعة إلى أمور مُضرة - مار إسحق السرياني",
"الذي يشتاق إلى الروحانيات، يجب عليه أن يتهاون بالجسدانيات ويرفضها بفرحٍ - مار إسحق السرياني",
"أتريد أن تبعد عن الفتور، ارفع قلبك بين الحين والحين إلى الله، ولو بجملة واحدة، أو صلاة قصيرة لا تستغرق دقيقة واحدة أو عدة ثوان -  البابا شنودة الثالث",
"أي مجدٌ لنا إن كنا لا نُؤذي مَنْ لا يُؤذينا؟! بل الفضيلة الحقة هي أن نغفر لمَنْ يُؤذينا - القديس أمبروسيوس",
"يُمكنك أن تختصر من كلمات الصلاة أو تغير كلماتها أو تستعيض عنها بالأخرى أو حتى تقف أمام الرب عقلياً بدون كلام. لأن القوة ليست في نطق الكلام؛ ولكن بوضع العقل في القلب أمام الرب بعيداً عن كل المؤثرات والأفكار - القديس الأب ثيئوفان الناسك",
"ليس شيء يثبت الحب بقوة مثل المشاركة في الفرح والألم. ليس لأنك بعيد عن المتاعب تنعزل عن مشاركة الآخرين أيضاً. فعندما يتعب قريبك، احسب الضيق خاصاً بك. شاركه دموعه؛ لكي تسند روحه المنسحقة، وشاركه فرحه ليصير الفرح فيه عميقاً متأصلاً. - القديس يوحنا ذهبي الفم",
"ليتنا في تجارينا وشدائدنا نتطلع بعيونٍ مؤمنةٍ ورجاءٍ ثابتٍ، وإيمان بلا رياء إلى الرب الساكن في الأعالي، والناظر إلى المتواضعات، ونقول: «هوذا اللهُ خلاصي؛ فاطْمئنُّ، ولا ارتَعِبُ» (إش ١٢: ٢) - مار إسحق السرياني",
 "لا تُصغِ إلى أمور العَالم، كأنه هو هدفك حتى يمكنك أن تخلص، ولا يكُن لك في هذا العَالم رجاء لئلا يبطل رجاؤك في الله. اُمقت أقاويل العَالم لكي يعاين قلبك الله - القديس الأنبا موسى الأسود",
"اضرم في قلوبنا يا رب نار حبك؛ فتلهينا عن أوجاع هذا الزمان - الشيخ الروحاني يوحنا سابا",
"ليكُن كل واحدٍ كبيراً في عينيك، ولا تَهِنْ الذين هم أقل منك معرفةً، ولا تطلب كرامةً من أحدٍ؛ لكن اتضع لكل الناس، ولا تغضب من الذي يتعظم عليك لأنه قليل المعرفة؛ لأنه من قلة المعرفة يتعظم الأخ على أخيه - القديس الأنبا يؤانس القصير",
"علِّم فمك أن يقول ما في قلبك - القديس الأنبا بيمين",
" يا ابني، إذا جعلت توكُّلك على الله؛ فإنه يصير لكَ ملجأ، ويُخلصك من جميع شدائدك. إن سلمت كل أمورك إلى الله؛ فآمن أنه قادر أن يظهر عجائبه لقديسيه - القديس الأنبا باخوميوس",
"اذكر عظم خطايا القدماء الذين سقطوا ثم تابوا، ومقدار الشرف والكرامة اللذين نالوهما من التوبة بعد ذلك؛ لكيما تتعزى في توبتك - مار إسحق السرياني",
"حتى لو لم يكن كلام الكتب المقدسة مفهوماً، فيجب استعماله ضد الشياطين؛ لأنهم يفهمونه، ويُهزَمون بقوة الكلمات الإلهية، لأنهم لا يستطيعون احتمال صوت الروح القدس الذي يتكلم في الأنبياء والرسل - القديس الأنبا أرسانيوس",
"أيها الربُّ الصالح، اقطع من قلبي محبة هذا العالم، وابدل حبِّي له بحبِّي لك. وأنا عالِم أن محبتي فيك ستلهيني عن ميلي إليه، فأنحلُّ منه بغير اغتصاب؛ لأربط بكَ إلى الأبد في حبٍّ شديدٍ ثابتٍ - القديس أوغسطينوس",
" ليكُن قلبك نحو الأفكار شجاعاً مُتجلداً حتى تخف عنك؛ أما الذي يخاف منها؛ فهي تسحقه، والذي يفزع منها؛ يشهد على نفسه أنه ليس له إيمان بالله، ومَنْ يطرح نفسه قدام يسوع سيده بكل قلبه يصير أقوى من الأفكار - القديس الأنبا موسى الأسود",
"إذا أتعبك الفكر ولم تستطع أن تنتصر عليه، اهرب منه بالحديث مع الناس. حتى إن كنت في وحدةٍ أو خلوةٍ، اترك وِحدتك، وخُلوتك، واختلط بغيرك. لأن حديثك مع الناس، يطرد الفكر الخاطئ منك، إذ لا يستطيع عقلك أن ينشغل بموضوع الفكر، والأحاديث في نفس الوقت. واعرف أن الوِحدة بمعناها الروحي هي اختلاء مع الله. فإن تحولت إلى اختلاء مع الأفكار الشريرة؛ فالخلطة أفضل منها طبعاً - البابا شنوده الثالث",
"اهتم إذاً بالعمل الداخلي، بالفضائل الرئيسية كالمحبة والإيمان والتواضع والوداعة والنقاوة والطهارة... وحينئذ ستجد صلاتك لهيب نار؛ لأنها نابعة من قلب نقي مملوء من محبة الله ومحبة الفضيلة - البابا شنودة الثالث",
"إذ يعتزلُ الجاحدون الصلاة والشكر، يحرمون أنفسهم من ثمر الفرح @القديس البابا اثناسيوس الرسولي","فليعلم كل إنسان أن عناية الله تتدفق بسخاء على الذين يتحملون من أجله كل التجارب والضيقات - مار إسحق السرياني",
"يليقُ بنا أن نضع زيتاً مرطباً على جراحات الضعفاء؛ لا مواد مُلتهبة تزيد آلامهم - القديس يوحنا ذهبي الفم",
"ليس لنا عدو إلا الشيطان، فكل البشر مهما كانوا هم أحباء لنا. أي مصباح بلا نورٍ! وأي مسيحي بلا حبٍ! - القديس يوحنا ذهبي الفم",
"الصلاة تحوِّل القلوب اللحمية إلى قلوب روحانية، والقلوب الفاترة إلى قلوب غيِّورة، والقلوب البشرية إلى قلوب سماوية - القديس يوحنا ذهبي الفم",
"لا تكن قاسي القلب على أخيك؛ لأننا جميعاً تغلبنا الأفكار السمجة - القديس الأنبا موسى الأسود",
"إن أردت أن تكون لك صورة المسيح، افعل مثله. أطلب خلاص كل أحد. افتقد سلامة إخوتك. وأولاً عليك أن تُحب كل الناس كما أحبهم المسيح، وتبذل نفسك عنهم -في حدود إمكانياتك- كما بذل المسيح. وتكون مُستعداً أن تُضحي بنفسك من أجلهم. بهذا تدخل فاعلية الميلاد في حياتك - البابا شنوده الثالث",
" تعامل مع كل إنسانٍ بنفس الطريقة التي يتعامل بها الله أيضاً معك - القديس الأنبا أمونيوس الأسقف",
"الحبُ يجعل الأمور سهلة، والروح يُعين، والرجاء يُنير، والتجارب تصقلك؛ فتجعلك مُجرَّباً، قادراً على احتمال كل شيء بشهامةٍ، يرافق هذا كله سلاحٌ عظيمٌ جداً هو الصلاة  - القديس يوحنا ذهبي الفم",
"ليكن حديثك مع محبي الله؛ لتأخذ لنفسك شبه طهارتهم - الشيخ الروحاني يوحنا سابا"]
function getRandomIndex(array) {
return Math.floor(Math.random() * array.length);
 }
const randomIndex = getRandomIndex(quotes);
const randomQuote = quotes[randomIndex];
document.getElementById("quote").textContent = randomQuote;
document.getElementById("author").textContent = randomAuthor;
const quoteAndAuthor = qoutes [0].split(" - ");
quoteElement.innerHTML = quoteAndAuthor[0];
authorElement.innerHTML = "— " + quoteAndAuthor[1];
 </script>
</html>

# Text-Analysis-on-Great-Expections
# 📚 Text Analysis & Topic Modeling on "Great Expectations"

Welcome to this comprehensive Natural Language Processing (NLP) project! In this notebook, we perform deep text analysis, sentiment tracking, and topic modeling on Charles Dickens' famous novel, **"Great Expectations"**, sourced from Project Gutenberg.

---

## 🚀 Project Overview (نظرة عامة على المشروع)
الهدف من المشروع هو استكشاف وفهم خبايا الرواية نصياً وبصرياً، من خلال تحويل الكلمات إلى أرقام وتحليل المشاعر المسيطرة على أحداث القصة، بالإضافة إلى استخراج المواضيع الأساسية (Topics) التي تدور حولها الرواية بشكل تلقائي باستخدام الذكاء الاصطناعي.

---

## 🛠️ Tech Stack & Tools (الأدوات المستخدمة)
We utilized a powerful set of Python libraries tailored for NLP:
* **`NLTK`**: For tokenization, stopword removal, lemmatization, and sentiment analysis using VADER.
* **`Gensim`**: The core engine for building the **LDA Topic Model** (Latent Dirichlet Allocation) and managing the text corpus.
* **`WordCloud`**: For generating advanced, visually engaging word distribution clouds.
* **`Pandas & NumPy`**: For structured data manipulation and cleaning.
* **`Matplotlib`**: For rendering all visualizations.

---

## 🔄 Project Workflow (خطوات العمل بالتفصيل)

### 1️⃣ Data Loading & Splitting (تحميل وتقسيم النص)
* قمنا بقراءة النص الأصلي للرواية وتجريده من المقدمات الطويلة لـ Project Gutenberg لبدء التحليل من الفصل الأول مباشرة.
* تم كتابة كود مخصص (Sentence Splitter regex) لتقسيم النص بالكامل إلى جمل منفصلة وبناء **`Pandas DataFrame`** يحتوي على أكثر من 9,900 جملة منظمة للتحليل.

### 2️⃣ Text Cleaning & Preprocessing (تنظيف وتجهيز البيانات النصية)
To make the text ready for advanced models, we performed:
* **Lowercasing & Regex Cleaning**: تحويل الحروف لـ Lowercase وحذف علامات الترقيم والأرقام غير الضرورية.
* **Tokenization**: تقسيم الجمل لكلمات مفردة (`tokens`).
* **Stopwords Removal**: التخلص من كلمات الوقف الشائعة التي لا تحمل معنى سياقي ملموس مثل (*the, is, an, or*).
* **Lemmatization**: إرجاع الكلمات المختلفة إلى جذورها اللغوية الصحيحة (مثل توحيد كلمات *play, playing, played* إلى الكلمة الأصلية *play*).

### 3️⃣ Word Frequency & Advanced Word Clouds (سحابة الكلمات المتقدمة)
* قمنا بحساب توزيع تكرار الكلمات باستخدام `nltk.FreqDist`.
* تم بناء **Advanced Word Cloud** تأخذ شكلًا مخصصًا (Mask) يعبر عن طابع الرواية الكلاسيكي (مثل شكل رجل يرتدي قبعة مخصصة `man_in_top_hat.jpeg`) لتوضيح الكلمات الأكثر شعبية وظهوراً بحجم أكبر وبصري مريح.

### 4️⃣ Sentiment Analysis (تحليل المشاعر)
* باستخدام أداة **VADER SentimentIntensityAnalyzer**، تم قياس وتحليل الحالة العاطفية لكل جملة في الرواية.
* ركزنا بشكل أساسي على الـ **Compound Score** (الذي يتراوح بين -1 و 1) لمعرفة النبرة العامة والمظهر العاطفي للقصة، وهل تميل الجمل للـ Positive، الـ Negative، أم الـ Neutral.

### 5️⃣ Topic Modeling with LDA (نمذجة المواضيع المخفية)
هنا تبدأ اللعبة الكبيرة لـ **Gensim**:
* قمنا ببناء الـ **`Dictionary`** لجمع الكلمات الفريدة المميزة بالرواية (حوالي 9,744 كلمة فريدة).
* حولنا النصوص إلى لغة الآلة من خلال الـ **`Corpus`** عبر دالة `doc2bow` (Bag of Words) لتحديد تكرار الـ IDs الخاصة بكل كلمة داخل الـ 9,978 وثيقة نصية.
* قمنا بتدريب كائن الـ **`ldamodel.LdaModel()`** لاكتشاف الـ Topics والمفاهيم الأساسية المسيطرة على أحداث الرواية بشكل تلقائي وتقسيم الكلمات بناءً عليها وعرض التوزيع الاحتمالي للكلمات في كل موضوع.

---

## 📈 Key Results & Insights (أبرز النتائج)
* **Visual Summary**: سحابة الكلمات نجحت في إبراز الشخصيات والمفردات المحورية في الرواية (مثل الكلمات المرتبطة بالبطل Pip وعائلة Havisham وجو ومفهوم الـ Time).
* **Automated Clustering**: موديل الـ LDA استطاع فصل الكلمات المرتبطة بالمشاعر والعلاقات الإنسانية في مجموعات (Topics) منفصلة تماماً عن الكلمات التي تدور حول البيئة والمكان وحقوق الملكية لـ Project Gutenberg.

---

## 🏃‍♂️ How to Run the Project (طريقة التشغيل)
1. Clone this repository:
 ```bash
 git clone [https://github.com/AbdulrahmanAhmed123/Text-Analysis-on-Great-Expections.git](https://github.com/AbdulrahmanAhmed123/Text-Analysis-on-Great-Expections.git)

Install the requirements:

Bash
pip install nltk gensim wordcloud pandas numpy matplotlib 

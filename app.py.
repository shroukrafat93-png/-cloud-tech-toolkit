import streamlit as st
import hashlib
import qrcode
from io import BytesIO
import time

# إعدادات الصفحة
st.set_page_config(
    page_title="Cloud Tech Toolkit",
    page_icon="☁️",
    layout="wide"
)

# عنوان المنصة
st.title("☁️ Cloud Tech Toolkit | منصة الأدوات التكنولوجية السحابية")
st.caption("مشروع تفاعلي لتطبيق مفاهيم المعالجة السحابية والأمن السيبراني")

st.markdown("---")

# القائمة الجانبية للتنقل
st.sidebar.header("⚙️ لوحة أدوات السحابة")
tool_choice = st.sidebar.radio(
    "اختر الأداة التفاعلية:",
    ["1. محاكي التشفير والأمن السيبراني", "2. صانع الـ QR السحابي", "3. أداة تحليل معالجة السحابة (Live Demo)"]
)

# الأداة الأولى: التشفير والأمن السيبراني
if tool_choice == "1. محاكي التشفير والأمن السيبراني":
    st.subheader("🔒 محاكي التشفير واختبار قوة البيانات")
    st.write("تقوم هذه الأداة بإرسال البيانات للسيرفر السحابي لتشفيرها واختبار أمانها فوراً.")
    
    user_input = st.text_input("أدخل النص أو كلمة السر للتشفير:", "Technology2026")
    
    if user_input:
        col1, col2 = st.columns(2)
        
        # التشفير بـ SHA-256
        hashed_val = hashlib.sha256(user_input.encode()).hexdigest()
        
        with col1:
            st.info("النص الأصلي:")
            st.code(user_input)
            
            st.success("التشفير السحابي (SHA-256):")
            st.code(hashed_val)
            
        with col2:
            st.warning("تقييم الأمان بواسطة السيرفر:")
            length = len(user_input)
            if length < 6:
                st.error("ضعيفة جداً - يمكن كسرها بسهولة")
            elif length < 10:
                st.warning("متوسطة - يُفضل زيادة الطول")
            else:
                st.success("قوية جداً - مشفرة بـ 256-bit")

# الأداة الثانية: صانع الـ QR
elif tool_choice == "2. صانع الـ QR السحابي":
    st.subheader("📲 توليد رموز QR سحابية مخصصة")
    st.write("أدخل أي رابط أو نص لتوليد كود QR ينشئه السيرفر السحابي فوراً.")
    
    qr_text = st.text_input("أدخل الرابط أو النص:", "https://streamlit.io")
    
    if qr_text:
        img = qrcode.make(qr_text)
        buf = BytesIO()
        img.save(buf, format="PNG")
        byte_im = buf.getvalue()
        
        st.image(byte_im, caption="رمز الـ QR المولد عبر السحابة", width=200)

# الأداة الثالثة: محاكي الجهد السحابي (الإبهاار الفعلي)
elif tool_choice == "3. أداة تحليل معالجة السحابة (Live Demo)":
    st.subheader("⚡ محاكي قوة المعالجة السحابية (Cloud Processing Simulator)")
    st.write("اضغطي على الزر أدناه لشحن السيرفر بعملية معالجة مكثفة ورؤية النتيجة المباشرة.")
    
    if st.button("توصيل ومحاكاة عملية سحابية ضخمة"):
        progress_bar = st.progress(0)
        status_text = st.empty()
        
        for i in range(100):
            time.sleep(0.02)
            progress_bar.progress(i + 1)
            status_text.text(f"جاري معالجة البيانات عبر الخادم السحابي... {i+1}%")
            
        st.success("✅ تمت العملية بنجاح! تم الاستفادة من سرعة السيرفر السحابي في 2 ثانية فقط.")

## Hi there 👋

import matplotlib.pyplot as plt
from PIL import Image
import numpy as np
import os

# تحميل صورة الشعار
logo_path = "/mnt/data/Picture my logo.png"  # ضع المسار الصحيح للصورة هنا
logo = Image.open(logo_path)

# تحويل الشعار إلى مصفوفة numpy
logo_np = np.array(logo)

# دالة لتغيير اللون
def change_color(image, r_shift, g_shift, b_shift):
    new_image = image.copy()
    new_image[:, :, 0] = np.clip(image[:, :, 0] + r_shift, 0, 255)  # تعديل قناة الأحمر
    new_image[:, :, 1] = np.clip(image[:, :, 1] + g_shift, 0, 255)  # تعديل قناة الأخضر
    new_image[:, :, 2] = np.clip(image[:, :, 2] + b_shift, 0, 255)  # تعديل قناة الأزرق
    return new_image

# إعداد المتغيرات
frames = 30
output_dir = "/mnt/data/animated_logo"
os.makedirs(output_dir, exist_ok=True)

# إنشاء صور متتابعة مع تغيير اللون تدريجياً
for i in range(frames):
    r_shift = int(100 * np.sin(i * np.pi / frames))
    g_shift = int(100 * np.sin((i + 10) * np.pi / frames))
    b_shift = int(100 * np.sin((i + 20) * np.pi / frames))

    new_logo_np = change_color(logo_np, r_shift, g_shift, b_shift)
    new_logo = Image.fromarray(new_logo_np)

    # حفظ الصورة
    new_logo.save(f"{output_dir}/frame_{i:02d}.png")

# عرض آخر إطار
plt.imshow(new_logo_np)
plt.axis('off')
plt.show()

print(f"تم حفظ الإطارات المتتابعة في المجلد: {output_dir}")


A Computer Science graduate 🎓 from Umm Al-Qura University, passionate about artificial intelligence, cybersecurity, and web development.

🔭 I’m currently working on AI and Web Development Projects
💬 Ask me about Python, Cybersecurity, and Web Development
📫 How to reach me:
<a href="mailto:AY.Alharbi@outlook.sa"> <img alt="link to send me an email" src="https://img.shields.io/static/v1?label&message=AY.Alharbi@outlook.sa&color=white&style=flat&logo=gmail" /> </a> <h2>:bulb: Languages & Frameworks</h2> <code><img title="Python" alt="Python" width="40px" src="https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Fs3.amazonaws.com%2Fmedia-p.slid.es%2Fuploads%2F1005350%2Fimages%2F6496607%2Fpython-logo.png&f=1&nofb=1" /></code> <code><img title="C++" alt="C++" width="40px" src="https://upload.wikimedia.org/wikipedia/commons/1/18/ISO_C%2B%2B_Logo.svg" /></code> <code><img title="Java" alt="Java" width="40px" src="https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Flogoeps.com%2Fwp-content%2Fuploads%2F2011%2F06%2Fjava-logo-vector.png&f=1&nofb=1" /></code> <code><img title="HTML" alt="HTML" width="40px" src="https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Fcdn-icons-png.flaticon.com%2F512%2F732%2F732212.png&f=1&nofb=1" /></code> <code><img title="CSS" alt="CSS" width="40px" src="https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Fcdn-icons-png.flaticon.com%2F512%2F732%2F732190.png&f=1&nofb=1" /></code> <code><img title="Figma" alt="Figma" width="40px" src="https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Fupload.wikimedia.org%2Fwikipedia%2Fcommons%2F3%2F33%2FFigma-logo.svg&f=1&nofb=1" /></code> <code><img title="MySQL" alt="MySQL" width="40px" src="https://sqlbackupandftp.com/blog/wp-content/uploads/2015/01/mysql-logo_2800x2800_pixels1.png" /></code> <code><img title="ROS" alt="ROS" width="80px" src="https://upload.wikimedia.org/wikipedia/commons/b/bb/Robot_Operating_System_-_Logo.svg" /></code>

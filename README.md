from fpdf import FPDF

# Повторная инициализация PDF с добавлением шрифта до вызова add_page
pdf = FPDF()
pdf.add_font("DejaVu", "", "/usr/share/fonts/truetype/dejavu/DejaVuSans.ttf", uni=True)
pdf.add_font("DejaVu", "B", "/usr/share/fonts/truetype/dejavu/DejaVuSans-Bold.ttf", uni=True)
pdf.set_font("DejaVu", "", 12)
pdf.add_page()

# Заголовок
pdf.set_font("DejaVu", "B", 14)
pdf.cell(0, 10, "Гайд: 3 простых фразы, с чего начать", ln=True, align="C")
pdf.ln(5)

# Введение
pdf.set_font("DejaVu", "B", 12)
intro_text = ("Если ты не блогер, но хочешь начать — начни вот с этого.\n"
              "Эти фразы легко использовать в сторис или Shorts, даже если ты боишься камеры.")
pdf.multi_cell(0, 8, intro_text)
pdf.ln()

# Фраза 1
pdf.set_font("DejaVu", "B", 12)
pdf.cell(0, 10, "Фраза 1. Привет! Я решила просто попробовать", ln=True)
pdf.set_font("DejaVu", "", 11)
pdf.multi_cell(0, 8,
    'Пример:\n"Привет! Я решила просто попробовать говорить в сторис. Если ты так же боялась — знай, ты не одна."\n\n'
    'Почему работает:\n— Искренне, по-человечески\n— Сразу вызывает доверие\n— Ты не играешь в блогера — ты делишься'
)
pdf.ln()

# Фраза 2
pdf.set_font("DejaVu", "B", 12)
pdf.cell(0, 10, "Фраза 2. Сегодня я…", ln=True)
pdf.set_font("DejaVu", "", 11)
pdf.multi_cell(0, 8,
    'Пример:\n"Сегодня я работаю из дома, и вот как это выглядит."\n\n'
    'Почему работает:\n— Легко начать\n— Показывает реальную жизнь\n— Не требует сценария или навыков'
)
pdf.ln()

# Фраза 3
pdf.set_font("DejaVu", "B", 12)
pdf.cell(0, 10, "Фраза 3. А вы тоже так делаете?", ln=True)
pdf.set_font("DejaVu", "", 11)
pdf.multi_cell(0, 8,
    'Пример:\n"Я всегда начинаю день с блокнота. А вы тоже так делаете?"\n\n'
    'Почему работает:\n— Вовлекает\n— Показывает, что ты «своя»\n— Дает контекст без давления'
)
pdf.ln()

# Заключение
pdf.set_font("DejaVu", "B", 12)
pdf.cell(0, 10, 'Пиши "СТАРТ", если хочешь получить ещё больше идей и поддержку!', ln=True)

# Сохранение файла
pdf_output_path = "/mnt/data/Gaid_3_frazy_dlya_starta.pdf"
pdf.output(pdf_output_path)

pdf_output_path

from PIL import Image, ImageDraw, ImageFont

# Create an image with white background
width, height = 800, 600
image = Image.new('RGB', (width, height), 'white')
draw = ImageDraw.Draw(image)

# Define colors
title_color = 'blue'
subtitle_color = 'orange'
text_color = 'black'
highlight_color = 'red'

# Load a font
font_path = "/usr/share/fonts/truetype/dejavu/DejaVuSans-Bold.ttf"
title_font = ImageFont.truetype(font_path, 40)
subtitle_font = ImageFont.truetype(font_path, 30)
text_font = ImageFont.truetype(font_path, 20)

# Add title
title = "300,000+ E-Kitap Paketi"
draw.text((20, 20), title, fill=title_color, font=title_font)

# Add subtitle
subtitle = "Şimdi Satın Al"
draw.text((20, 80), subtitle, fill=subtitle_color, font=subtitle_font)

# Add additional text
text = "Her bütçeye uygun, anında erişim, geniş kapsam"
draw.text((20, 140), text, fill=text_color, font=text_font)

# Simulate book covers and reading devices
cover_colors = ['blue', 'green', 'purple', 'orange', 'red']
device_colors = ['gray', 'black']
for i, color in enumerate(cover_colors):
    draw.rectangle([(20 + i * 140, 200), (120 + i * 140, 300)], fill=color)

for i, color in enumerate(device_colors):
    draw.rectangle([(20 + i * 200, 320), (220 + i * 200, 420)], fill=color)

# Add discount banner
discount_text = "Özel İndirimler ve Kampanyalar"
draw.text((20, 450), discount_text, fill=highlight_color, font=text_font)

# Save the image
image_path = "/mnt/data/ebook_package_promotion.png"
image.save(image_path)

image.show()

image_path

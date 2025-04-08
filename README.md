🖼️ Making Text Like It's 1700 Again — with Deep Learning
This project started as an exploration:
"Can we take modern digital text and make it look like it was printed in the Renaissance… without destroying readability?"

Turns out—yes, yes we can.

🎯 What’s This About?
We’re applying neural style transfer to text pages to make them look like Renaissance-era printed material—aged paper, rich brush strokes, imperfect printing—but the text is still readable.
This is achieved by blending the stylized result with the original content using some simple math and a little TensorFlow magic.
Everything runs on Google Colab. No GPUs, no fancy servers, just a laptop and the cloud.
🧩 The Pipeline
•	Here’s the full flow:

•	📝 Start with a `.docx` file - It’s converted to PDF and then split into individual page images.
•	🎨 Apply Renaissance flair - We pull in some Renaissance-style paintings and use TensorFlow Hub’s neural style transfer model to give each page a makeover.
•	🧪 Blend, don’t obliterate - We mix the stylized image with the original using an alpha factor so you get the texture and feel—without losing the text.
•	💾 Save it like it’s precious art - All stylized and blended outputs are neatly saved into folders you can download.
🔧 Tech Stack
- Python + Google Colab
- TensorFlow Hub (arbitrary-image-stylization-v1-256)
- Pillow (PIL), NumPy, pdf2image
- LibreOffice (for .docx → .pdf)
📁 Folder Structure

Untitled42.ipynb              # Main notebook (runs end-to-end)
docx.pdf                      # Converted from .docx
docx_pages/                   # PNGs of each page
renaissance_dataset/         # style images
stylized_output/             # Style-transferred results
blended_output/              # Final results with preserved text

🚀To Run It Yourself
Upload your `.docx` file, and run the notebook.

To download the results:

!zip -r results.zip renaissance_dataset docx.pdf stylized_output blended_output
from google.colab import files
files.download('results.zip')

🌱Diffusion & GAN Ideas
I also explored the idea of generating ink-bleed and degradation effects using:
- A small diffusion model trained on text degradation pairs
- Possibly CycleGAN (if more unsupervised data is available)

Too heavy for a laptop right now, but it’s all part of the vision.
🧠 Final Thoughts
This was a fun experiment in style transfer that balances aesthetics with utility.
It blends art and AI in a literal way—and there's a lot of room to grow from here.



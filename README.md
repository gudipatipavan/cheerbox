<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>CheerBox | One Stop Solutions for Gifts, Toys, Festive Needs & Decor</title>
  <link rel="icon" href="https://emojiapi.dev/api/v1/package/64.png" type="image/png">
  <style>
    body { font-family: Arial, sans-serif; margin: 0; padding: 2rem; background: #fff8f0; color: #333; }
    header { text-align: center; margin-bottom: 2rem; }
    h1 { font-size: 2rem; margin: 0; }
    .product { border: 1px solid #ccc; padding: 1rem; margin-bottom: 2rem; background: #fff; border-radius: 10px; }
    .product img { max-width: 100%; height: auto; border-radius: 8px; }
    .preview { margin-top: 1rem; max-height: 150px; }
    button { background: #4CAF50; color: white; padding: 0.5rem 1rem; border: none; border-radius: 5px; cursor: pointer; }
    #popup { display: none; position: fixed; top: 20px; right: 20px; background: #dff0d8; padding: 1rem; border: 1px solid #3c763d; border-radius: 5px; }
  </style>
</head>
<body>
  <header>
    <h1>🎁 CheerBox</h1>
    <p>One stop solutions for gifts, toys, festive needs & decor</p>
  </header>

  <div class="product">
    <h2>Sling Bag</h2>
    <img src="https://via.placeholder.com/200" alt="Sling Bag">
    <input type="file" accept="image/*" id="imageUpload">
    <img id="imagePreview" class="preview" style="display:none;">
    <br><br>
    <a id="waLink" target="_blank">
      <button onclick="orderOnWhatsApp()">Order on WhatsApp</button>
    </a>
  </div>

  <div id="popup">🎉 Thanks! We’ve received your order on WhatsApp.</div>

  <script>
    const imageUpload = document.getElementById('imageUpload');
    const imagePreview = document.getElementById('imagePreview');

    imageUpload.addEventListener('change', () => {
      const file = imageUpload.files[0];
      if (file) {
        imagePreview.src = URL.createObjectURL(file);
        imagePreview.style.display = 'block';
      }
    });

    function orderOnWhatsApp() {
      const message = `Hi CheerBox! I'd like to order a Sling Bag.`;
      const url = `https://wa.me/919999999999?text=${encodeURIComponent(message)}`;
      document.getElementById('waLink').href = url;
      showPopup();
    }

    function showPopup() {
      const popup = document.getElementById('popup');
      popup.style.display = 'block';
      setTimeout(() => { popup.style.display = 'none'; }, 3000);
    }
  </script>
</body>
</html>

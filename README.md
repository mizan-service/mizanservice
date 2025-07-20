<!DOCTYPE html>
<html lang="fa" dir="rtl">
<head>
  <meta charset="UTF-8">
  <title>میزان سرویس | خدمات تعمیرات لوازم خانگی</title>
  <link rel="icon" href="https://s6.uupload.ir/files/img_20250720_115509_704_47er.jpg">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <style>
  .slider-wrapper {
    position: relative;
    max-width: 95%;
    margin: 0 auto;
    overflow: hidden;
    border: 2px solid #00a86b;
    border-radius: 12px;
    background-color: #e6fff5;
    padding: 20px;
  }

  .slider-container {
    display: flex;
    gap: 15px;
    overflow-x: auto;
    scroll-behavior: smooth;
    padding-bottom: 10px;
  }

  .slide {
    flex: 0 0 auto;
    width: 150px;
    height: 150px;
    border-radius: 10px;
    overflow: hidden;
    box-shadow: 0 2px 6px rgba(0,0,0,0.2);
    background-color: white;
    cursor: pointer;
    transition: transform 0.3s ease;
  }

  .slide img {
    width: 100%;
    height: 100%;
    object-fit: contain;
    transition: transform 0.3s;
  }

  .slide:hover img {
    transform: scale(1.1);
  }

  .nav-button {
    position: absolute;
    top: 50%;
    transform: translateY(-50%);
    background-color: #00a86b;
    color: white;
    border: none;
    font-size: 24px;
    padding: 8px 12px;
    border-radius: 50%;
    cursor: pointer;
    z-index: 10;
  }

  .nav-left {
    right: -10px;
  }

  .nav-right {
    left: -10px;
  }

  .modal {
    display: none;
    position: fixed;
    z-index: 999;
    left: 0;
    top: 0;
    width: 100%;
    height: 100%;
    overflow: auto;
    background-color: rgba(0,0,0,0.8);
  }

  .modal-content {
    margin: 10% auto;
    display: block;
    width: 80%;
    max-width: 600px;
    border-radius: 12px;
  }

  .close {
    position: absolute;
    top: 15px;
    right: 35px;
    color: white;
    font-size: 30px;
    font-weight: bold;
    cursor: pointer;
  }

  @media (max-width: 600px) {
    .slide {
      width: 100px;
      height: 100px;
    }

    .modal-content {
      width: 95%;
    }
  }

    body {
      font-family: sans-serif;
      background-color: #e6f9f0;
      margin: 0;
      padding: 0;
      color: #333;
    }

    header {
      background-color: #00a86b;
      color: white;
      padding: 15px 20px;
      display: flex;
      justify-content: space-between;
      align-items: center;
      flex-wrap: wrap;
    }

    header img {
      height: 50px;
    }

    .buttons {
      text-align: center;
      margin: 30px 0;
    }

    .btn {
      padding: 15px 25px;
      margin: 10px;
      border: none;
      border-radius: 10px;
      background-color: #00a86b;
      color: white;
      font-size: 18px;
      cursor: pointer;
      transition: 0.3s ease;
    }

    .btn:hover {
      background-color: #007a53;
    }

    .product-list {
      display: none;
      text-align: center;
      margin-top: 20px;
    }

    .product-item {
      background-color: white;
      border: 2px solid #00a86b;
      margin: 10px auto;
      max-width: 300px;
      padding: 10px;
      border-radius: 10px;
      transition: background-color 0.3s ease;
      cursor: pointer;
    }

    .product-item:hover {
      background-color: #ccf2e6;
    }

    .brand-gallery {
      display: none;
      text-align: center;
      padding: 20px;
    }

    .brand-gallery h3 {
      margin-bottom: 15px;
    }

    .brand-images {
      display: flex;
      flex-wrap: wrap;
      justify-content: center;
      gap: 15px;
    }

    .brand-images img {
      width: 150px;
      height: 150px;
      object-fit: cover;
      border-radius: 10px;
      animation: float 3s ease-in-out infinite;
    }

    @keyframes float {
      0% { transform: translateY(0px); }
      50% { transform: translateY(-8px); }
      100% { transform: translateY(0px); }
    }

    .contact-form {
      background: white;
      border: 2px solid #00a86b;
      padding: 20px;
      max-width: 400px;
      margin: 30px auto;
      border-radius: 15px;
    }

    .contact-form h2 {
      text-align: center;
    }

    .contact-form input, .contact-form textarea {
      width: 100%;
      padding: 10px;
      margin: 10px 0;
      border-radius: 8px;
      border: 1px solid #ccc;
    }

    .contact-form button {
      background-color: #00a86b;
      color: white;
      padding: 10px 20px;
      border: none;
      border-radius: 8px;
      font-size: 16px;
      cursor: pointer;
      width: 100%;
    }

    .footer {
      margin: 50px 0;
      text-align: center;
    }

    .footer div {
      display: inline-block;
      padding: 18px 30px;
      border-radius: 50%;
      background-color: #00a86b;
      color: white;
      font-weight: bold;
      font-size: 18px;
      box-shadow: 0 4px 10px rgba(0, 0, 0, 0.25);
    }

    @media screen and (max-width: 600px) {
      .brand-images img {
        width: 100px;
        height: 100px;
      }

      .btn {
        font-size: 16px;
        padding: 10px 18px;
      }

      header {
        flex-direction: column;
      }
    }
  </style>
</head>
<body>

  <header>
    <img src="https://s6.uupload.ir/files/img_20250720_115509_704_47er.jpg" alt="لوگو تعمیر‌یار">
    <h1>میزان سرویس</h1>
  </header>

  <div class="buttons">
    <button class="btn" onclick="toggleProducts()">تعمیرات</button>
    <button class="btn" onclick="scrollToContact()">اطلاعات تماس</button>
  </div>

  <div class="product-list" id="productList">
    <div class="product-item" onclick="showBrands('لباسشویی')">لباسشویی</div>
    <div class="product-item" onclick="showBrands('ظرفشویی')">ظرفشویی</div>
    <div class="product-item" onclick="showBrands('جاروبرقی')">جاروبرقی</div>
    <div class="product-item" onclick="showBrands('مایکروویو')">مایکروویو</div>
    <div class="product-item" onclick="showBrands('یخچال')">یخچال</div>
    <div class="product-item" onclick="showBrands('گاز رومیزی')">گاز رومیزی</div>
  </div>

  <div class="brand-gallery" id="brandGallery">
    <h3 id="brandTitle"></h3>
    <div class="brand-images" id="brandImages"></div>
  </div>

  <div class="contact-form" id="contactForm">
    <h2>تماس با ما</h2>
    <input type="text" placeholder="نام شما">
    <input type="text" placeholder="شماره تماس">
    <textarea rows="4" placeholder="پیام شما"></textarea>
    <button onclick="sendToWhatsApp()">ارسال از طریق واتساپ</button>
    <p style="margin-top:10px; text-align:center;">
      شماره تماس: <strong>02133693818</strong><br>
      تلگرام: <a href="https://t.me/jade_emamu" target="_blank">ارتباط با پشتیبانی</a>
    </p>
  </div>
<section>
  <h2 style="text-align: center; color: #00a86b;">برندهای لباسشویی</h2>

  <div class="slider-wrapper">
    <button class="nav-button nav-left" onclick="scrollSlider(-1)">❮</button>

    <div class="slider-container" id="slider">
      <div class="slide"><img src="images/LG.jpeg" onclick="openModal(this.src)"></div>
      <div class="slide"><img src="images/BOSCH.jpeg" onclick="openModal(this.src)"></div>
      <div class="slide"><img src="images/SAMSUNG.jpeg" onclick="openModal(this.src)"></div>
      <div class="slide"><img src="images/DAEWOO.jpeg" onclick="openModal(this.src)"></div>
      <div class="slide"><img src="images/FERIDOLIN.jpeg" onclick="openModal(this.src)"></div>
      <div class="slide"><img src="images/PAKSHOMA.jpeg" onclick="openModal(this.src)"></div>
      <div class="slide"><img src="images/SNOWA.jpeg" onclick="openModal(this.src)"></div>
      <div class="slide"><img src="images/XVISION.jpeg" onclick="openModal(this.src)"></div>
      <!-- تصویرهای بیشتر -->
    </div>

    <button class="nav-button nav-right" onclick="scrollSlider(1)">❯</button>
  </div>
</section>
  <footer class="footer">
    <div>با مدیریت امامی</div>
  </footer>

  <script>
    const brandImages = {
      "لباسشویی": [
        "https://upload.wikimedia.org/wikipedia/commons/thumb/e/e3/LG_logo_%282015%29.svg/2560px-LG_logo_%282015%29.svg.png",
        "https://cdn.mashinchi.org/wp-content/uploads/2022/09/bosch_logo.jpg",
        "https://upload.wikimedia.org/wikipedia/commons/2/26/Samsung_Logo.svg"
      ],
      "ظرفشویی": [
        "https://logos-download.com/wp-content/uploads/2016/06/Beko_logo_logotype.png",
        "https://upload.wikimedia.org/wikipedia/commons/9/99/Whirlpool_Corporation_Logo_2016.svg",
        "https://upload.wikimedia.org/wikipedia/commons/1/11/Siemens-logo.svg"
      ],
      "جاروبرقی": [
        "https://upload.wikimedia.org/wikipedia/commons/5/56/Philips_logo_new.svg",
        "https://upload.wikimedia.org/wikipedia/commons/2/24/Miele-logo.svg"
      ],
      "مایکروویو": [
        "https://upload.wikimedia.org/wikipedia/commons/4/4d/Panasonic_logo_%282013%29.svg",
        "https://upload.wikimedia.org/wikipedia/commons/8/86/Sharp_Corporation_logo.svg"
      ],
      "یخچال": [
        "https://upload.wikimedia.org/wikipedia/commons/e/e7/General_Electric_logo.svg",
        "https://upload.wikimedia.org/wikipedia/commons/7/72/Haier_logo.svg"
      ],
      "گاز رومیزی": [
        "https://upload.wikimedia.org/wikipedia/commons/6/6f/DeLonghi_Logo.svg",
        "https://upload.wikimedia.org/wikipedia/commons/c/ce/Gorenje_logo.svg"
      ]
    };

    function toggleProducts() {
      const list = document.getElementById("productList");
      list.style.display = list.style.display === "block" ? "none" : "block";
      document.getElementById("brandGallery").style.display = "none";
    }

    function showBrands(product) {
      const gallery = document.getElementById("brandGallery");
      const title = document.getElementById("brandTitle");
      const container = document.getElementById("brandImages");

      title.innerText = `برندهای ${product}`;
      container.innerHTML = "";

      if (brandImages[product]) {
        brandImages[product].forEach(src => {
          const img = document.createElement("img");
          img.src = src;
          container.appendChild(img);
        });
        gallery.style.display = "block";
        scrollToElement("brandGallery");
      }
    }

    function sendToWhatsApp() {
      const name = document.querySelector('input[placeholder="نام شما"]').value;
      const phone = document.querySelector('input[placeholder="شماره تماس"]').value;
      const message = document.querySelector('textarea').value;

      const text = `نام: ${name}%0aتلفن: ${phone}%0aپیام: ${message}`;
      window.open(`https://wa.me/989191391650?text=${text}`, '_blank');
    }

    function scrollToContact() {
      scrollToElement("contactForm");
    }

    function scrollToElement(id) {
      document.getElementById(id).scrollIntoView({ behavior: "smooth" });
    }
  </script>
<!-- مودال برای نمایش عکس بزرگ -->
<div id="imageModal" class="modal" onclick="closeModal(event)">
  <span class="close" onclick="closeModal(event)">×</span>
  <img class="modal-content" id="modalImage" />
</div>

<script>
  const slider = document.getElementById('slider');
  function scrollSlider(direction) {
    const scrollAmount = 180;
    slider.scrollLeft += direction * scrollAmount;
  }

  function openModal(src) {
    const modal = document.getElementById("imageModal");
    const modalImg = document.getElementById("modalImage");
    modal.style.display = "block";
    modalImg.src = src;
  }

  function closeModal(e) {
    if (e.target.id === 'modalImage') return;
    document.getElementById("imageModal").style.display = "none";
  }
</script>
</body>
</html>

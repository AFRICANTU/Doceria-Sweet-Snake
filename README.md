<!DOCTYPE html>
<html lang="pt-br">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Doceria Sweet Snake - Delivery de Doces Premium</title>
  <script async src="https://pagead2.googlesyndication.com/pagead/js/adsbygoogle.js?client=ca-pub-. "
     crossorigin="anonymous"></script>
  <style>
    /* Reset e tipografia moderna */
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }
    
    body {
      font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
      background: #fff;
      color: #333;
      line-height: 1.6;
      overflow-x: hidden;
    }

    /* Header moderno */
    header {
      background: linear-gradient(rgba(0, 0, 0, 0.4), rgba(0, 0, 0, 0.4)), url('https://images.unsplash.com/photo-1578985545062-69928b1d9587?ixlib=rb-4.0.3&auto=format&fit=crop&w=1200&q=80');
      background-size: cover;
      background-position: center;
      padding: 60px 20px;
      text-align: center;
      color: #fff;
      position: relative;
      box-shadow: 0 4px 20px rgba(0, 0, 0, 0.2);
    }

    /* Login Button */
    .login-btn {
      position: absolute;
      top: 20px;
      right: 20px;
      background: rgba(255, 255, 255, 0.2);
      color: white;
      border: 2px solid white;
      padding: 10px 20px;
      border-radius: 25px;
      cursor: pointer;
      font-weight: 600;
      transition: all 0.3s ease;
      backdrop-filter: blur(10px);
    }
    
    .login-btn:hover {
      background: white;
      color: #dc2626;
      transform: translateY(-2px);
    }

    /* Cart Button */
    .cart-btn {
      position: absolute;
      top: 20px;
      right: 150px;
      background: rgba(255, 255, 255, 0.2);
      color: white;
      border: 2px solid white;
      padding: 10px 20px;
      border-radius: 25px;
      cursor: pointer;
      font-weight: 600;
      transition: all 0.3s ease;
      backdrop-filter: blur(10px);
      display: flex;
      align-items: center;
      gap: 8px;
    }
    
    .cart-btn:hover {
      background: white;
      color: #dc2626;
      transform: translateY(-2px);
    }

    .cart-count {
      background: #dc2626;
      color: white;
      border-radius: 50%;
      width: 20px;
      height: 20px;
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 0.8em;
      font-weight: bold;
    }

    /* Profile Page Styles */
    .profile-page {
      display: none;
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
      z-index: 3000;
      overflow-y: auto;
    }

    .profile-page.active {
      display: block;
      animation: slideInFromRight 0.5s ease-out;
    }

    @keyframes slideInFromRight {
      from {
        transform: translateX(100%);
      }
      to {
        transform: translateX(0);
      }
    }

    .profile-header {
      background: rgba(255, 255, 255, 0.1);
      backdrop-filter: blur(20px);
      padding: 20px;
      display: flex;
      justify-content: space-between;
      align-items: center;
      border-bottom: 1px solid rgba(255, 255, 255, 0.2);
    }

    .profile-nav {
      display: flex;
      gap: 20px;
    }

    .profile-nav-btn {
      background: rgba(255, 255, 255, 0.2);
      color: white;
      border: none;
      padding: 12px 24px;
      border-radius: 25px;
      cursor: pointer;
      font-weight: 600;
      transition: all 0.3s ease;
      backdrop-filter: blur(10px);
    }

    .profile-nav-btn:hover,
    .profile-nav-btn.active {
      background: rgba(255, 255, 255, 0.3);
      transform: translateY(-2px);
    }

    .close-profile {
      background: #dc2626;
      color: white;
      border: none;
      padding: 12px 24px;
      border-radius: 25px;
      cursor: pointer;
      font-weight: 600;
      transition: all 0.3s ease;
    }

    .close-profile:hover {
      background: #b91c1c;
      transform: translateY(-2px);
    }

    .profile-content {
      padding: 40px 20px;
      max-width: 1200px;
      margin: 0 auto;
    }

    .profile-section {
      display: none;
      background: rgba(255, 255, 255, 0.95);
      border-radius: 20px;
      padding: 40px;
      box-shadow: 0 20px 60px rgba(0, 0, 0, 0.1);
      backdrop-filter: blur(20px);
    }

    .profile-section.active {
      display: block;
      animation: fadeInUp 0.5s ease-out;
    }

    /* Image Creator Styles */
    .image-creator {
      text-align: center;
    }

    .canvas-container {
      background: white;
      border-radius: 15px;
      padding: 20px;
      margin: 30px auto;
      display: inline-block;
      box-shadow: 0 10px 30px rgba(0, 0, 0, 0.1);
    }

    #imageCanvas {
      border: 3px solid #dc2626;
      border-radius: 10px;
      cursor: crosshair;
    }

    .creator-tools {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
      gap: 30px;
      margin-top: 30px;
    }

    .tool-group {
      background: #f8f9fa;
      padding: 25px;
      border-radius: 15px;
      border: 2px solid #e2e8f0;
    }

    .tool-group h3 {
      color: #dc2626;
      margin-bottom: 20px;
      font-size: 1.3em;
      display: flex;
      align-items: center;
      gap: 10px;
    }

    .color-palette {
      display: grid;
      grid-template-columns: repeat(6, 1fr);
      gap: 10px;
      margin-bottom: 20px;
    }

    .color-btn {
      width: 40px;
      height: 40px;
      border: 3px solid transparent;
      border-radius: 50%;
      cursor: pointer;
      transition: all 0.3s ease;
    }

    .color-btn:hover,
    .color-btn.active {
      border-color: #333;
      transform: scale(1.1);
    }

    .brush-sizes {
      display: flex;
      gap: 15px;
      justify-content: center;
      margin-bottom: 20px;
    }

    .brush-btn {
      width: 50px;
      height: 50px;
      border: 2px solid #dc2626;
      border-radius: 50%;
      background: white;
      cursor: pointer;
      display: flex;
      align-items: center;
      justify-content: center;
      font-weight: bold;
      transition: all 0.3s ease;
    }

    .brush-btn:hover,
    .brush-btn.active {
      background: #dc2626;
      color: white;
      transform: scale(1.1);
    }

    .action-buttons {
      display: flex;
      gap: 15px;
      justify-content: center;
      flex-wrap: wrap;
    }

    .action-btn {
      background: linear-gradient(135deg, #dc2626, #ef4444);
      color: white;
      border: none;
      padding: 12px 24px;
      border-radius: 25px;
      cursor: pointer;
      font-weight: 600;
      transition: all 0.3s ease;
      display: flex;
      align-items: center;
      gap: 8px;
    }

    .action-btn:hover {
      transform: translateY(-2px);
      box-shadow: 0 8px 25px rgba(220, 38, 38, 0.3);
    }

    .action-btn.secondary {
      background: #6b7280;
    }

    .action-btn.secondary:hover {
      background: #4b5563;
      box-shadow: 0 8px 25px rgba(107, 114, 128, 0.3);
    }



    /* Modal Styles */
    .modal {
      display: none;
      position: fixed;
      z-index: 2000;
      left: 0;
      top: 0;
      width: 100%;
      height: 100%;
      background-color: rgba(0,0,0,0.5);
      backdrop-filter: blur(5px);
    }
    
    .modal-content {
      background-color: white;
      margin: 5% auto;
      padding: 40px;
      border-radius: 20px;
      width: 90%;
      max-width: 400px;
      position: relative;
      box-shadow: 0 20px 60px rgba(0,0,0,0.3);
      animation: modalSlideIn 0.3s ease-out;
    }
    
    @keyframes modalSlideIn {
      from {
        opacity: 0;
        transform: translateY(-50px);
      }
      to {
        opacity: 1;
        transform: translateY(0);
      }
    }
    
    .close {
      position: absolute;
      right: 20px;
      top: 15px;
      color: #aaa;
      font-size: 28px;
      font-weight: bold;
      cursor: pointer;
      transition: color 0.3s ease;
    }
    
    .close:hover {
      color: #dc2626;
    }
    
    .modal h2 {
      text-align: center;
      margin-bottom: 30px;
      color: #333;
      font-size: 1.8em;
    }
    
    .form-group {
      margin-bottom: 20px;
    }
    
    .form-group label {
      display: block;
      margin-bottom: 8px;
      font-weight: 600;
      color: #333;
    }
    
    .form-group input {
      width: 100%;
      padding: 12px 15px;
      border: 2px solid #e2e8f0;
      border-radius: 10px;
      font-size: 1em;
      transition: all 0.3s ease;
      box-sizing: border-box;
    }
    
    .form-group input:focus {
      outline: none;
      border-color: #dc2626;
      box-shadow: 0 0 0 3px rgba(220, 38, 38, 0.1);
    }
    
    .modal-btn {
      width: 100%;
      background: linear-gradient(135deg, #dc2626, #ef4444);
      color: white;
      padding: 15px;
      border: none;
      border-radius: 10px;
      font-size: 1.1em;
      font-weight: 600;
      cursor: pointer;
      transition: all 0.3s ease;
      margin-bottom: 15px;
    }
    
    .modal-btn:hover {
      transform: translateY(-2px);
      box-shadow: 0 8px 25px rgba(220, 38, 38, 0.3);
    }
    
    .privacy-link {
      text-align: center;
      margin-top: 20px;
    }
    
    .privacy-link a {
      color: #dc2626;
      text-decoration: none;
      font-weight: 600;
      transition: color 0.3s ease;
    }
    
    .privacy-link a:hover {
      color: #b91c1c;
      text-decoration: underline;
    }
    
    header h1 {
      font-size: 2.8em;
      font-weight: 700;
      margin-bottom: 5px;
      text-shadow: 2px 2px 4px rgba(0,0,0,0.3);
    }
    
    header p {
      font-size: 1.1em;
      opacity: 0.95;
    }

    /* Navegação */
    nav {
      background: rgba(34, 34, 34, 0.95);
      backdrop-filter: blur(10px);
      padding: 0;
      position: sticky;
      top: 0;
      z-index: 1000;
      box-shadow: 0 2px 20px rgba(0,0,0,0.1);
    }
    
    .nav-container {
      display: flex;
      justify-content: center;
      align-items: center;
      flex-wrap: wrap;
      max-width: 1200px;
      margin: 0 auto;
      text-align: center;
    }
    
    nav a {
      color: #fff;
      text-decoration: none;
      font-weight: 600;
      padding: 15px 25px;
      transition: all 0.3s ease;
      position: relative;
      text-transform: uppercase;
      letter-spacing: 1px;
      font-size: 0.9em;
    }
    
    nav a:hover {
      color: #dc2626;
      transform: translateY(-2px);
    }

    /* Banner Rotativo (Carrossel) */
    .carousel-container {
      position: relative;
      max-width: 100%;
      margin: 0 auto;
      overflow: hidden;
      height: 400px;
    }
    
    .carousel {
      display: flex;
      transition: transform 0.5s ease-in-out;
      height: 100%;
    }
    
    .carousel-slide {
      min-width: 100%;
      height: 100%;
      position: relative;
      display: flex;
      align-items: center;
      justify-content: center;
      background-size: cover;
      background-position: center;
    }
    
    .slide1 {
      background: linear-gradient(rgba(0, 0, 0, 0.4), rgba(0, 0, 0, 0.4)), url('https://images.unsplash.com/photo-1578985545062-69928b1d9587?ixlib=rb-4.0.3&auto=format&fit=crop&w=1200&q=80');
    }
    
    .slide2 {
      background: linear-gradient(rgba(0, 0, 0, 0.4), rgba(0, 0, 0, 0.4)), url('https://images.unsplash.com/photo-1606313564200-e75d5e30476c?ixlib=rb-4.0.3&auto=format&fit=crop&w=1200&q=80');
    }
    
    .slide3 {
      background: linear-gradient(rgba(0, 0, 0, 0.4), rgba(0, 0, 0, 0.4)), url('https://images.unsplash.com/photo-1563805042-7684c019e1cb?ixlib=rb-4.0.3&auto=format&fit=crop&w=1200&q=80');
    }
    
    .carousel-content {
      text-align: center;
      color: white;
      z-index: 2;
      max-width: 600px;
      padding: 20px;
    }
    
    .carousel-content h2 {
      font-size: 3em;
      font-weight: 700;
      margin-bottom: 15px;
      text-shadow: 2px 2px 4px rgba(0,0,0,0.8);
    }
    
    .carousel-content p {
      font-size: 1.3em;
      margin-bottom: 25px;
      text-shadow: 1px 1px 2px rgba(0,0,0,0.8);
    }
    
    .carousel-btn {
      background: linear-gradient(135deg, #dc2626, #ef4444);
      color: white;
      padding: 15px 35px;
      font-size: 1.1em;
      font-weight: 600;
      border: none;
      border-radius: 50px;
      cursor: pointer;
      transition: all 0.3s ease;
      text-transform: uppercase;
      letter-spacing: 1px;
      box-shadow: 0 8px 25px rgba(220, 38, 38, 0.3);
    }
    
    .carousel-btn:hover {
      transform: translateY(-3px);
      box-shadow: 0 12px 35px rgba(220, 38, 38, 0.4);
    }
    
    .carousel-indicators {
      position: absolute;
      bottom: 20px;
      left: 50%;
      transform: translateX(-50%);
      display: flex;
      gap: 10px;
    }
    
    .indicator {
      width: 12px;
      height: 12px;
      border-radius: 50%;
      background: rgba(255, 255, 255, 0.5);
      cursor: pointer;
      transition: all 0.3s ease;
    }
    
    .indicator.active {
      background: white;
      transform: scale(1.2);
    }

    /* Menu Interativo por Categorias */
    .menu-section {
      padding: 80px 20px;
      background: #f8f9fa;
    }
    
    .section-title {
      text-align: center;
      font-size: 2.5em;
      font-weight: 700;
      margin-bottom: 20px;
      color: #333;
    }
    
    .section-subtitle {
      text-align: center;
      font-size: 1.2em;
      color: #666;
      margin-bottom: 50px;
    }
    
    .category-tabs {
      display: flex;
      justify-content: center;
      gap: 20px;
      margin-bottom: 50px;
      flex-wrap: wrap;
    }
    
    .tab-btn {
      background: white;
      border: 2px solid #dc2626;
      color: #dc2626;
      padding: 12px 25px;
      font-size: 1em;
      font-weight: 600;
      border-radius: 25px;
      cursor: pointer;
      transition: all 0.3s ease;
      text-transform: uppercase;
      letter-spacing: 0.5px;
    }
    
    .tab-btn.active,
    .tab-btn:hover {
      background: #dc2626;
      color: white;
      transform: translateY(-2px);
      box-shadow: 0 5px 15px rgba(220, 38, 38, 0.3);
    }
    
    .products-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
      gap: 30px;
      max-width: 1200px;
      margin: 0 auto;
    }
    
    .product-card {
      background: white;
      border-radius: 15px;
      overflow: hidden;
      box-shadow: 0 8px 30px rgba(0,0,0,0.1);
      transition: all 0.3s ease;
      display: none;
      height: 100%;
    }
    
    .product-card.active {
      display: flex;
      flex-direction: column;
      animation: fadeInUp 0.5s ease-out;
    }
    
    .product-card:hover {
      transform: translateY(-5px);
      box-shadow: 0 15px 40px rgba(220, 38, 38, 0.2);
    }
    
    .product-image {
      width: 100%;
      height: 200px;
      background-size: cover;
      background-position: center;
      position: relative;
    }
    
    .product-badge {
      position: absolute;
      top: 15px;
      right: 15px;
      background: #dc2626;
      color: white;
      padding: 5px 12px;
      border-radius: 15px;
      font-size: 0.8em;
      font-weight: 600;
    }
    
    .product-info {
      padding: 25px;
      flex: 1;
      display: flex;
      flex-direction: column;
      justify-content: space-between;
    }
    
    .product-content {
      flex: 1;
    }
    
    .product-info h3 {
      font-size: 1.4em;
      font-weight: 700;
      margin-bottom: 10px;
      color: #333;
    }
    
    .product-info p {
      color: #666;
      margin-bottom: 20px;
      line-height: 1.6;
    }
    
    .product-price {
      display: flex;
      align-items: center;
      justify-content: space-between;
      margin-bottom: 20px;
    }
    
    .price-original {
      text-decoration: line-through;
      color: #999;
      font-size: 0.9em;
    }
    
    .price-current {
      font-size: 1.5em;
      font-weight: 700;
      color: #dc2626;
    }
    
    .product-btn {
      width: 100%;
      background: linear-gradient(135deg, #dc2626, #ef4444);
      color: white;
      padding: 12px;
      border: none;
      border-radius: 8px;
      font-size: 1em;
      font-weight: 600;
      cursor: pointer;
      transition: all 0.3s ease;
      text-transform: uppercase;
      letter-spacing: 0.5px;
    }
    
    .product-btn:hover {
      transform: translateY(-2px);
      box-shadow: 0 5px 15px rgba(220, 38, 38, 0.3);
    }

    /* Checkout Form Styles */
    .checkout-form {
      margin-top: 20px;
      padding: 25px;
      background: #f8f9fa;
      border-radius: 15px;
      border: 2px solid #dc2626;
      display: none;
      animation: slideDown 0.3s ease-out;
    }
    
    .checkout-form.active {
      display: block;
    }
    
    @keyframes slideDown {
      from {
        opacity: 0;
        transform: translateY(-20px);
      }
      to {
        opacity: 1;
        transform: translateY(0);
      }
    }
    
    .checkout-title {
      color: #dc2626;
      font-size: 1.3em;
      font-weight: 700;
      margin-bottom: 20px;
      text-align: center;
    }
    
    .checkout-form .form-group {
      margin-bottom: 15px;
    }
    
    .checkout-form .form-group label {
      display: block;
      margin-bottom: 5px;
      font-weight: 600;
      color: #333;
      font-size: 0.9em;
    }
    
    .checkout-form .form-group input {
      width: 100%;
      padding: 10px 12px;
      border: 2px solid #e2e8f0;
      border-radius: 8px;
      font-size: 0.9em;
      transition: all 0.3s ease;
      box-sizing: border-box;
    }
    
    .checkout-form .form-group input:focus {
      outline: none;
      border-color: #dc2626;
      box-shadow: 0 0 0 3px rgba(220, 38, 38, 0.1);
    }
    
    .checkout-buttons {
      display: flex;
      gap: 10px;
      margin-top: 20px;
    }
    
    .checkout-btn {
      flex: 1;
      padding: 12px;
      border: none;
      border-radius: 8px;
      font-size: 0.9em;
      font-weight: 600;
      cursor: pointer;
      transition: all 0.3s ease;
      text-transform: uppercase;
      letter-spacing: 0.5px;
    }
    
    .checkout-btn.confirm {
      background: linear-gradient(135deg, #10b981, #059669);
      color: white;
    }
    
    .checkout-btn.confirm:hover {
      transform: translateY(-2px);
      box-shadow: 0 5px 15px rgba(16, 185, 129, 0.3);
    }
    
    .checkout-btn.cancel {
      background: #6b7280;
      color: white;
    }
    
    .checkout-btn.cancel:hover {
      background: #4b5563;
      transform: translateY(-2px);
    }

    /* Promoções Especiais */
    .promo-section {
      padding: 80px 20px;
      background: linear-gradient(135deg, #dc2626, #ef4444);
      color: white;
      text-align: center;
    }
    
    .promo-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
      gap: 30px;
      max-width: 1000px;
      margin: 50px auto 0;
    }
    
    .promo-card {
      background: white;
      color: #333;
      padding: 30px;
      border-radius: 20px;
      box-shadow: 0 10px 30px rgba(0,0,0,0.2);
      transition: all 0.3s ease;
    }
    
    .promo-card:hover {
      transform: translateY(-5px) scale(1.02);
    }
    
    .promo-code {
      background: #ff6347;
      color: white;
      padding: 10px 20px;
      border-radius: 25px;
      font-weight: 700;
      font-size: 1.2em;
      margin-bottom: 15px;
      display: inline-block;
    }

    /* Localização */
    .location-section {
      padding: 80px 20px;
      background: #f8f9fa;
    }
    
    .map-container {
      max-width: 1000px;
      margin: 50px auto 0;
      border-radius: 15px;
      overflow: hidden;
      box-shadow: 0 10px 30px rgba(0,0,0,0.1);
    }
    
    .map-container iframe {
      width: 100%;
      height: 400px;
      border: none;
    }

    /* Avaliações */
    .reviews-section {
      padding: 80px 20px;
      background: white;
    }
    
    .reviews-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
      gap: 30px;
      max-width: 1000px;
      margin: 50px auto 0;
    }
    
    .review-card {
      background: #f8f9fa;
      padding: 30px;
      border-radius: 15px;
      text-align: center;
      box-shadow: 0 5px 20px rgba(0,0,0,0.1);
      transition: all 0.3s ease;
    }
    
    .review-card:hover {
      transform: translateY(-5px);
      box-shadow: 0 10px 30px rgba(220, 38, 38, 0.1);
    }
    
    .review-avatar {
      width: 80px;
      height: 80px;
      border-radius: 50%;
      margin: 0 auto 20px;
      background-size: cover;
      background-position: center;
      border: 4px solid #ffd700;
    }
    
    .review-stars {
      color: #ffc107;
      font-size: 1.5em;
      margin-bottom: 15px;
    }
    
    .review-text {
      font-style: italic;
      color: #666;
      margin-bottom: 15px;
      line-height: 1.6;
    }
    
    .review-author {
      font-weight: 700;
      color: #333;
    }

    /* Galeria Instagram */
    .instagram-section {
      padding: 80px 20px;
      background: linear-gradient(135deg, #833ab4, #fd1d1d, #fcb045);
      color: white;
      text-align: center;
    }
    
    .instagram-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
      gap: 20px;
      max-width: 1000px;
      margin: 50px auto 0;
    }
    
    .instagram-post {
      aspect-ratio: 1;
      border-radius: 15px;
      overflow: hidden;
      background-size: cover;
      background-position: center;
      transition: all 0.3s ease;
      cursor: pointer;
    }
    
    .instagram-post:hover {
      transform: scale(1.05);
      box-shadow: 0 10px 30px rgba(0,0,0,0.3);
    }

    /* Botão WhatsApp Flutuante */
    .whatsapp-float {
      position: fixed;
      width: 60px;
      height: 60px;
      bottom: 40px;
      right: 40px;
      background: #25d366;
      color: white;
      border-radius: 50px;
      text-align: center;
      font-size: 30px;
      box-shadow: 2px 2px 3px #999;
      z-index: 1000;
      transition: all 0.3s ease;
      display: flex;
      align-items: center;
      justify-content: center;
      text-decoration: none;
      animation: pulse 2s infinite;
    }
    
    .whatsapp-float:hover {
      transform: scale(1.1);
      box-shadow: 0 5px 20px rgba(37, 211, 102, 0.5);
    }
    
    @keyframes pulse {
      0% { box-shadow: 0 0 0 0 rgba(37, 211, 102, 0.7); }
      70% { box-shadow: 0 0 0 10px rgba(37, 211, 102, 0); }
      100% { box-shadow: 0 0 0 0 rgba(37, 211, 102, 0); }
    }

    /* Redes Sociais */
    .social-section {
      background: #333;
      color: white;
      text-align: center;
      padding: 60px 20px;
    }
    
    .social-links {
      display: flex;
      justify-content: center;
      gap: 30px;
      flex-wrap: wrap;
      margin-top: 40px;
    }
    
    .social-links a {
      display: inline-flex;
      align-items: center;
      justify-content: center;
      width: 60px;
      height: 60px;
      background: linear-gradient(135deg, #ff8c00, #ffa500);
      color: white;
      text-decoration: none;
      border-radius: 50%;
      font-size: 1.5em;
      transition: all 0.3s ease;
      box-shadow: 0 5px 20px rgba(255, 140, 0, 0.3);
    }
    
    .social-links a:hover {
      transform: translateY(-5px) scale(1.1);
      box-shadow: 0 10px 30px rgba(255, 140, 0, 0.4);
    }

    /* Footer */
    footer {
      background: #222;
      color: white;
      text-align: center;
      padding: 30px 20px;
    }

    /* Animações */
    @keyframes fadeInUp {
      from {
        opacity: 0;
        transform: translateY(30px);
      }
      to {
        opacity: 1;
        transform: translateY(0);
      }
    }

    @keyframes fadeIn {
      from { opacity: 0; }
      to { opacity: 1; }
    }

    /* Responsividade */
    @media (max-width: 768px) {
      header h1 { font-size: 2.2em; }
      .carousel-content h2 { font-size: 2.2em; }
      .section-title { font-size: 2em; }
      .category-tabs { gap: 10px; }
      .tab-btn { padding: 10px 20px; font-size: 0.9em; }
      .whatsapp-float { bottom: 20px; right: 20px; }
      .profile-nav { flex-direction: column; gap: 10px; }
      .creator-tools { grid-template-columns: 1fr; }
    }
  </style>
</head>
<body>

<header>
  <button class="login-btn" onclick="openProfilePage()">Entrar</button>
  <h1>Sweet Snake</h1>
  <p>TRAZENDO + SABOR PARA SUA VIDA.</p>
</header>

<nav>
  <div class="nav-container">
    <a href="#promocoes">Promoções</a>
    <a href="#carousel">Início</a>
    <a href="#menu">Cardápio</a>
    <a href="#avaliacoes">Avaliações</a>
    <a href="#contato">Contato</a>
  </div>
</nav>

<!-- Profile Page -->
<div id="profilePage" class="profile-page">
  <div class="profile-header">
    <div class="profile-nav">
      <button class="profile-nav-btn active" onclick="showProfileSection('dashboard')">🏠 Dashboard</button>
      <button class="profile-nav-btn" onclick="showProfileSection('imageCreator')">🎨 Criar Imagem</button>
      <button class="profile-nav-btn" onclick="showProfileSection('orders')">📦 Pedidos</button>
    </div>
    <button class="close-profile" onclick="closeProfilePage()">✕ Fechar</button>
  </div>

  <div class="profile-content">
    <!-- Dashboard Section -->
    <div id="dashboard" class="profile-section active">
      <h2 class="section-title" style="color: white; margin-bottom: 30px;">🍰 Bem-vindo ao seu Perfil Sweet Snake!</h2>
      
      <div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(300px, 1fr)); gap: 30px;">
        <div style="background: rgba(255, 255, 255, 0.1); backdrop-filter: blur(20px); padding: 30px; border-radius: 20px; text-align: center; color: white;">
          <div style="width: 100px; height: 100px; background: linear-gradient(135deg, #dc2626, #ef4444); border-radius: 50%; margin: 0 auto 20px; display: flex; align-items: center; justify-content: center; color: white; font-size: 3em; font-weight: bold;" id="dashboardAvatar"></div>
          <h3 id="dashboardName" style="margin-bottom: 10px; font-size: 1.5em;"></h3>
          <p id="dashboardEmail" style="opacity: 0.8;"></p>
        </div>
        
        <div style="background: rgba(255, 255, 255, 0.1); backdrop-filter: blur(20px); padding: 30px; border-radius: 20px; color: white;">
          <h3 style="margin-bottom: 20px; display: flex; align-items: center; gap: 10px;">
            <span style="font-size: 1.5em;">📊</span> Estatísticas
          </h3>
          <div style="display: grid; grid-template-columns: 1fr 1fr; gap: 20px; text-align: center;">
            <div>
              <div style="font-size: 2em; font-weight: bold; color: #ffd700;" id="totalOrders">0</div>
              <div style="opacity: 0.8;">Pedidos</div>
            </div>
            <div>
              <div style="font-size: 2em; font-weight: bold; color: #10b981;" id="totalSpent">R$ 0</div>
              <div style="opacity: 0.8;">Gasto Total</div>
            </div>
          </div>
        </div>
        
        <div style="background: rgba(255, 255, 255, 0.1); backdrop-filter: blur(20px); padding: 30px; border-radius: 20px; color: white;">
          <h3 style="margin-bottom: 20px; display: flex; align-items: center; gap: 10px;">
            <span style="font-size: 1.5em;">🎯</span> Ações Rápidas
          </h3>
          <div style="display: flex; flex-direction: column; gap: 15px;">
            <button class="action-btn" onclick="showProfileSection('imageCreator')">
              🎨 Criar Nova Imagem
            </button>
            <button class="action-btn secondary" onclick="closeProfilePage()">
              🛒 Fazer Pedido
            </button>
          </div>
        </div>
      </div>
    </div>

    <!-- Image Creator Section -->
    <div id="imageCreator" class="profile-section">
      <div class="image-creator">
        <h2 class="section-title" style="color: white; margin-bottom: 30px;">🎨 Criador de Imagens Personalizado</h2>
        
        <div class="canvas-container">
          <canvas id="imageCanvas" width="500" height="400"></canvas>
        </div>
        
        <div class="creator-tools">
          <div class="tool-group">
            <h3>🎨 Cores</h3>
            <div class="color-palette">
              <div class="color-btn active" style="background: #000000;" onclick="selectColor('#000000')"></div>
              <div class="color-btn" style="background: #dc2626;" onclick="selectColor('#dc2626')"></div>
              <div class="color-btn" style="background: #10b981;" onclick="selectColor('#10b981')"></div>
              <div class="color-btn" style="background: #3b82f6;" onclick="selectColor('#3b82f6')"></div>
              <div class="color-btn" style="background: #f59e0b;" onclick="selectColor('#f59e0b')"></div>
              <div class="color-btn" style="background: #8b5cf6;" onclick="selectColor('#8b5cf6')"></div>
              <div class="color-btn" style="background: #ef4444;" onclick="selectColor('#ef4444')"></div>
              <div class="color-btn" style="background: #06b6d4;" onclick="selectColor('#06b6d4')"></div>
              <div class="color-btn" style="background: #84cc16;" onclick="selectColor('#84cc16')"></div>
              <div class="color-btn" style="background: #f97316;" onclick="selectColor('#f97316')"></div>
              <div class="color-btn" style="background: #ec4899;" onclick="selectColor('#ec4899')"></div>
              <div class="color-btn" style="background: #ffffff; border: 2px solid #ccc;" onclick="selectColor('#ffffff')"></div>
            </div>
          </div>
          
          <div class="tool-group">
            <h3>🖌️ Tamanho do Pincel</h3>
            <div class="brush-sizes">
              <div class="brush-btn" onclick="selectBrushSize(2)">2</div>
              <div class="brush-btn active" onclick="selectBrushSize(5)">5</div>
              <div class="brush-btn" onclick="selectBrushSize(10)">10</div>
              <div class="brush-btn" onclick="selectBrushSize(20)">20</div>
            </div>
          </div>
          
          <div class="tool-group">
            <h3>⚡ Ações</h3>
            <div class="action-buttons">
              <button class="action-btn secondary" onclick="clearCanvas()">
                🗑️ Limpar
              </button>
              <button class="action-btn" onclick="saveImage()">
                💾 Salvar
              </button>
              <button class="action-btn" onclick="downloadImage()">
                📥 Download
              </button>
            </div>
          </div>
        </div>
      </div>
    </div>



    <!-- Orders Section -->
    <div id="orders" class="profile-section">
      <h2 class="section-title" style="color: white; margin-bottom: 30px;">📦 Meus Pedidos</h2>
      <div id="profileOrders" style="max-height: 600px; overflow-y: auto;">
        <p style="text-align: center; color: white; padding: 40px; font-size: 1.2em;">Nenhum pedido encontrado. Faça seu primeiro pedido!</p>
      </div>
    </div>
  </div>
</div>



<!-- Promoções -->
<section id="promocoes" class="promo-section">
  <h2 class="section-title" style="color: white;">Promoções da Semana</h2>
  <p class="section-subtitle" style="color: white; opacity: 0.9;">Use nossos cupons e economize ainda mais!</p>
  
  <div class="promo-grid">
    <div class="promo-card">
      <div class="promo-code">SWEET25</div>
      <h3>25% de Desconto</h3>
      <p>Em pedidos acima de R$ 50,00. Oferta limitada!</p>
    </div>
    
    <div class="promo-card">
      <div class="promo-code">FRETEGRATIS</div>
      <h3>Frete Grátis</h3>
      <p>Em todos os pedidos acima de R$ 40,00. Aproveite!</p>
    </div>
  </div>
</section>

<!-- Banner Rotativo -->
<section id="carousel">
  <div class="carousel-container">
    <div class="carousel">
      <div class="carousel-slide slide1">
        <div class="carousel-content">
          <h2>2 BROWNIES + MOUSSE</h2>
          <p>Combo especial por apenas R$ 35,99 • Frete Grátis</p>
          <button class="carousel-btn" onclick="window.open('https://www.ifood.com.br/delivery/rio-de-janeiro-rj/sweet-snake-ltda-piedade/f71e72f3-8d6b-4431-9153-2b32c355d0d0','_blank')">Peça Agora</button>
        </div>
      </div>
      <div class="carousel-slide slide2">
        <div class="carousel-content">
          <h2>BROWNIE DOCE DE LEITE</h2>
          <p>Novidade! Recheio cremoso argentino • Experimente já</p>
          <button class="carousel-btn" onclick="window.open('https://www.ifood.com.br/delivery/rio-de-janeiro-rj/sweet-snake-ltda-piedade/f71e72f3-8d6b-4431-9153-2b32c355d0d0','_blank')">Peça Agora</button>
        </div>
      </div>
      <div class="carousel-slide slide3">
        <div class="carousel-content">
          <h2>FRETE GRÁTIS + 25% OFF</h2>
          <p>Em todos os pedidos acima de R$ 40 • Válido hoje</p>
          <button class="carousel-btn" onclick="window.open('https://www.ifood.com.br/delivery/rio-de-janeiro-rj/sweet-snake-ltda-piedade/f71e72f3-8d6b-4431-9153-2b32c355d0d0','_blank')">Peça Agora</button>
        </div>
      </div>
    </div>
    <div class="carousel-indicators">
      <div class="indicator active" onclick="currentSlide(1)"></div>
      <div class="indicator" onclick="currentSlide(2)"></div>
      <div class="indicator" onclick="currentSlide(3)"></div>
    </div>
  </div>
</section>

<!-- Menu Interativo -->
<section id="menu" class="menu-section">
  <h2 class="section-title">Nosso Cardápio</h2>
  <p class="section-subtitle">Escolha sua categoria favorita e descubra sabores únicos</p>
  
  <div class="category-tabs">
    <button class="tab-btn active" onclick="showCategory('mousses')">Mousses</button>
    <button class="tab-btn" onclick="showCategory('brownies')">Brownies</button>
    <button class="tab-btn" onclick="showCategory('combos')">Combos</button>
    <button class="tab-btn" onclick="showCategory('gelados')">Gelados</button>
  </div>
  
  <div class="products-grid">
    <!-- Mousses -->
    <div class="product-card active mousses">
      <div class="product-image" style="background-image: url('https://images.unsplash.com/photo-1488477181946-6428a0291777?ixlib=rb-4.0.3&auto=format&fit=crop&w=400&q=80')">
        <div class="product-badge">Mais Vendido</div>
      </div>
      <div class="product-info">
        <div class="product-content">
          <h3>Mousse de Limão Siciliano</h3>
          <p>Refrescante e cremoso, feito com limões sicilianos selecionados e toque especial da casa.</p>
          <div class="product-price">
            <div>
              <span class="price-original">R$ 28,00</span>
              <span class="price-current">R$ 19,99</span>
            </div>
          </div>
        </div>
        <button class="product-btn" onclick="showCheckoutForm(this, 'Mousse de Limão Siciliano', 19.99)">Comprar Agora</button>
        <div class="checkout-form">
          <h4 class="checkout-title">Finalizar Compra - Mousse de Limão Siciliano</h4>
          <form onsubmit="processOrder(event, this)">
            <div class="form-group">
              <label for="fullName1">Nome Completo:</label>
              <input type="text" id="fullName1" name="fullName" required placeholder="Digite seu nome completo">
            </div>
            <div class="form-group">
              <label for="email1">E-mail:</label>
              <input type="email" id="email1" name="email" required placeholder="seu@email.com">
            </div>
            <div class="form-group">
              <label for="whatsapp1">WhatsApp:</label>
              <input type="tel" id="whatsapp1" name="whatsapp" required placeholder="(21) 99999-9999">
            </div>
            <div class="checkout-buttons">
              <button type="button" class="checkout-btn cancel" onclick="hideCheckoutForm(this)">Cancelar</button>
              <button type="submit" class="checkout-btn confirm">Confirmar Pedido</button>
            </div>
          </form>
        </div>
      </div>
    </div>
    
    <div class="product-card active mousses">
      <div class="product-image" style="background-image: url('https://images.unsplash.com/photo-1464349095431-e9a21285b5f3?ixlib=rb-4.0.3&auto=format&fit=crop&w=400&q=80')">
        <div class="product-badge">Tropical</div>
      </div>
      <div class="product-info">
        <div class="product-content">
          <h3>Mousse de Maracujá</h3>
          <p>Cremoso com sabor tropical inconfundível. Perfeito para refrescar o paladar.</p>
          <div class="product-price">
            <div>
              <span class="price-original">R$ 27,66</span>
              <span class="price-current">R$ 21,80</span>
            </div>
          </div>
        </div>
        <button class="product-btn" onclick="showCheckoutForm(this, 'Mousse de Maracujá', 21.80)">Comprar Agora</button>
        <div class="checkout-form">
          <h4 class="checkout-title">Finalizar Compra - Mousse de Maracujá</h4>
          <form onsubmit="processOrder(event, this)">
            <div class="form-group">
              <label for="fullName2">Nome Completo:</label>
              <input type="text" id="fullName2" name="fullName" required placeholder="Digite seu nome completo">
            </div>
            <div class="form-group">
              <label for="email2">E-mail:</label>
              <input type="email" id="email2" name="email" required placeholder="seu@email.com">
            </div>
            <div class="form-group">
              <label for="whatsapp2">WhatsApp:</label>
              <input type="tel" id="whatsapp2" name="whatsapp" required placeholder="(21) 99999-9999">
            </div>
            <div class="checkout-buttons">
              <button type="button" class="checkout-btn cancel" onclick="hideCheckoutForm(this)">Cancelar</button>
              <button type="submit" class="checkout-btn confirm">Confirmar Pedido</button>
            </div>
          </form>
        </div>
      </div>
    </div>
    
    <!-- Brownies -->
    <div class="product-card brownies">
      <div class="product-image" style="background-image: url('https://images.unsplash.com/photo-1606313564200-e75d5e30476c?ixlib=rb-4.0.3&auto=format&fit=crop&w=400&q=80')">
        <div class="product-badge">Novidade</div>
      </div>
      <div class="product-info">
        <div class="product-content">
          <h3>Brownie Doce de Leite</h3>
          <p>Brownie artesanal com recheio cremoso de doce de leite argentino. Explosão de sabor!</p>
          <div class="product-price">
            <div>
              <span class="price-original">R$ 22,56</span>
              <span class="price-current">R$ 17,98</span>
            </div>
          </div>
        </div>
        <button class="product-btn" onclick="showCheckoutForm(this, 'Brownie Doce de Leite', 17.98)">Comprar Agora</button>
        <div class="checkout-form">
          <h4 class="checkout-title">Finalizar Compra - Brownie Doce de Leite</h4>
          <form onsubmit="processOrder(event, this)">
            <div class="form-group">
              <label for="fullName3">Nome Completo:</label>
              <input type="text" id="fullName3" name="fullName" required placeholder="Digite seu nome completo">
            </div>
            <div class="form-group">
              <label for="email3">E-mail:</label>
              <input type="email" id="email3" name="email" required placeholder="seu@email.com">
            </div>
            <div class="form-group">
              <label for="whatsapp3">WhatsApp:</label>
              <input type="tel" id="whatsapp3" name="whatsapp" required placeholder="(21) 99999-9999">
            </div>
            <div class="checkout-buttons">
              <button type="button" class="checkout-btn cancel" onclick="hideCheckoutForm(this)">Cancelar</button>
              <button type="submit" class="checkout-btn confirm">Confirmar Pedido</button>
            </div>
          </form>
        </div>
      </div>
    </div>
    
    <div class="product-card brownies">
      <div class="product-image" style="background-image: url('https://images.unsplash.com/photo-1578985545062-69928b1d9587?ixlib=rb-4.0.3&auto=format&fit=crop&w=400&q=80')">
        <div class="product-badge">Clássico</div>
      </div>
      <div class="product-info">
        <div class="product-content">
          <h3>Brownie Tradicional</h3>
          <p>O clássico brownie com chocolate belga, crocante por fora e cremoso por dentro.</p>
          <div class="product-price">
            <div>
              <span class="price-original">R$ 20,00</span>
              <span class="price-current">R$ 15,99</span>
            </div>
          </div>
        </div>
        <button class="product-btn" onclick="showCheckoutForm(this, 'Brownie Tradicional', 15.99)">Comprar Agora</button>
        <div class="checkout-form">
          <h4 class="checkout-title">Finalizar Compra - Brownie Tradicional</h4>
          <form onsubmit="processOrder(event, this)">
            <div class="form-group">
              <label for="fullName4">Nome Completo:</label>
              <input type="text" id="fullName4" name="fullName" required placeholder="Digite seu nome completo">
            </div>
            <div class="form-group">
              <label for="email4">E-mail:</label>
              <input type="email" id="email4" name="email" required placeholder="seu@email.com">
            </div>
            <div class="form-group">
              <label for="whatsapp4">WhatsApp:</label>
              <input type="tel" id="whatsapp4" name="whatsapp" required placeholder="(21) 99999-9999">
            </div>
            <div class="checkout-buttons">
              <button type="button" class="checkout-btn cancel" onclick="hideCheckoutForm(this)">Cancelar</button>
              <button type="submit" class="checkout-btn confirm">Confirmar Pedido</button>
            </div>
          </form>
        </div>
      </div>
    </div>
    
    <!-- Combos -->
    <div class="product-card combos">
      <div class="product-image" style="background-image: url('https://images.unsplash.com/photo-1563805042-7684c019e1cb?ixlib=rb-4.0.3&auto=format&fit=crop&w=400&q=80')">
        <div class="product-badge">Oferta</div>
      </div>
      <div class="product-info">
        <div class="product-content">
          <h3>Combo Família</h3>
          <p>2 Brownies + 2 Mousses + Bolo no Pote. Perfeito para compartilhar!</p>
          <div class="product-price">
            <div>
              <span class="price-original">R$ 89,90</span>
              <span class="price-current">R$ 65,99</span>
            </div>
          </div>
        </div>
        <button class="product-btn" onclick="showCheckoutForm(this, 'Combo Família', 65.99)">Comprar Agora</button>
        <div class="checkout-form">
          <h4 class="checkout-title">Finalizar Compra - Combo Família</h4>
          <form onsubmit="processOrder(event, this)">
            <div class="form-group">
              <label for="fullName5">Nome Completo:</label>
              <input type="text" id="fullName5" name="fullName" required placeholder="Digite seu nome completo">
            </div>
            <div class="form-group">
              <label for="email5">E-mail:</label>
              <input type="email" id="email5" name="email" required placeholder="seu@email.com">
            </div>
            <div class="form-group">
              <label for="whatsapp5">WhatsApp:</label>
              <input type="tel" id="whatsapp5" name="whatsapp" required placeholder="(21) 99999-9999">
            </div>
            <div class="checkout-buttons">
              <button type="button" class="checkout-btn cancel" onclick="hideCheckoutForm(this)">Cancelar</button>
              <button type="submit" class="checkout-btn confirm">Confirmar Pedido</button>
            </div>
          </form>
        </div>
      </div>
    </div>
    
    <!-- Gelados -->
    <div class="product-card gelados">
      <div class="product-image" style="background-image: url('https://images.unsplash.com/photo-1497034825429-c343d7c6a68f?ixlib=rb-4.0.3&auto=format&fit=crop&w=400&q=80')">
        <div class="product-badge">Refrescante</div>
      </div>
      <div class="product-info">
        <div class="product-content">
          <h3>Bolo no Pote Gelado</h3>
          <p>Camadas de bolo gelado com creme especial. Irresistível em cada colherada.</p>
          <div class="product-price">
            <div>
              <span class="price-original">R$ 29,99</span>
              <span class="price-current">R$ 19,99</span>
            </div>
          </div>
        </div>
        <button class="product-btn" onclick="showCheckoutForm(this, 'Bolo no Pote Gelado', 19.99)">Comprar Agora</button>
        <div class="checkout-form">
          <h4 class="checkout-title">Finalizar Compra - Bolo no Pote Gelado</h4>
          <form onsubmit="processOrder(event, this)">
            <div class="form-group">
              <label for="fullName6">Nome Completo:</label>
              <input type="text" id="fullName6" name="fullName" required placeholder="Digite seu nome completo">
            </div>
            <div class="form-group">
              <label for="email6">E-mail:</label>
              <input type="email" id="email6" name="email" required placeholder="seu@email.com">
            </div>
            <div class="form-group">
              <label for="whatsapp6">WhatsApp:</label>
              <input type="tel" id="whatsapp6" name="whatsapp" required placeholder="(21) 99999-9999">
            </div>
            <div class="checkout-buttons">
              <button type="button" class="checkout-btn cancel" onclick="hideCheckoutForm(this)">Cancelar</button>
              <button type="submit" class="checkout-btn confirm">Confirmar Pedido</button>
            </div>
          </form>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- Avaliações -->
<section id="avaliacoes" class="reviews-section">
  <h2 class="section-title">O que nossos clientes dizem</h2>
  <p class="section-subtitle">Mais de 1000 clientes satisfeitos em todo o Rio de Janeiro</p>
  
  <div class="reviews-grid">
    <div class="review-card">
      <div class="review-avatar" style="background-image: url('https://images.unsplash.com/photo-1507003211169-0a1dd7228f2d?ixlib=rb-4.0.3&auto=format&fit=crop&w=150&q=80')"></div>
      <div class="review-stars">★★★★★</div>
      <p class="review-text">"Brownie sensacional! Chegou quentinho e o sabor é incrível. Minha família toda aprovou. Recomendo demais!"</p>
      <p class="review-author">Carlos Mendes - Piedade, RJ</p>
    </div>
    
    <div class="review-card">
      <div class="review-avatar" style="background-image: url('https://images.unsplash.com/photo-1438761681033-6461ffad8d80?ixlib=rb-4.0.3&auto=format&fit=crop&w=150&q=80')"></div>
      <div class="review-stars">★★★★★</div>
      <p class="review-text">"Qualidade excepcional! Os doces são fresquinhos e o atendimento é nota 10. Sweet Snake é referência em doces!"</p>
      <p class="review-author">Mariana Costa - Méier, RJ</p>
    </div>
  </div>
</section>

<!-- Galeria Instagram -->
<section class="instagram-section">
  <h2 class="section-title" style="color: white;">Siga @doceria_sweet_snake</h2>
  <p class="section-subtitle" style="color: white; opacity: 0.9;">Acompanhe nossas novidades e bastidores no Instagram</p>
  
  <div class="instagram-grid">
    <div class="instagram-post" style="background-image: url('https://images.unsplash.com/photo-1578985545062-69928b1d9587?ixlib=rb-4.0.3&auto=format&fit=crop&w=300&q=80')" onclick="window.open('https://www.instagram.com/doceria_sweet_snake','_blank')"></div>
    <div class="instagram-post" style="background-image: url('https://images.unsplash.com/photo-1551024506-0bccd828d307?ixlib=rb-4.0.3&auto=format&fit=crop&w=300&q=80')" onclick="window.open('https://www.instagram.com/doceria_sweet_snake','_blank')"></div>
    <div class="instagram-post" style="background-image: url('https://images.unsplash.com/photo-1606313564200-e75d5e30476c?ixlib=rb-4.0.3&auto=format&fit=crop&w=300&q=80')" onclick="window.open('https://www.instagram.com/doceria_sweet_snake','_blank')"></div>
  </div>
</section>

<!-- Modal de Login -->
<div id="loginModal" class="modal">
  <div class="modal-content">
    <span class="close" onclick="closeLoginModal()">&times;</span>
    <h2>Entrar na Sweet Snake</h2>
    <form id="loginForm" onsubmit="handleLogin(event)">
      <div class="form-group">
        <label for="email">E-mail:</label>
        <input type="email" id="email" name="email" required>
      </div>
      <div class="form-group">
        <label for="password">Senha:</label>
        <input type="password" id="password" name="password" required>
      </div>
      <button type="submit" class="modal-btn">Entrar</button>
      <button type="button" class="modal-btn" style="background: #10b981;" onclick="openRegisterModal()">Criar Nova Conta</button>
      <button type="button" class="modal-btn" style="background: #6b7280; margin-bottom: 20px;" onclick="openForgotModal()">Esqueci minha senha ou e-mail</button>
      <div class="privacy-link">
        <a href="#" onclick="openPrivacyModal()">Política de Privacidade</a>
      </div>
    </form>
  </div>
</div>

<!-- Modal de Recuperação de Senha -->
<div id="forgotModal" class="modal">
  <div class="modal-content">
    <span class="close" onclick="closeForgotModal()">&times;</span>
    <h2>Recuperar Acesso</h2>
    <p style="text-align: center; color: #666; margin-bottom: 30px;">Digite seu e-mail ou WhatsApp para recuperar sua conta</p>
    <form id="forgotForm" onsubmit="handleForgotPassword(event)">
      <div class="form-group">
        <label for="recoveryInfo">E-mail ou WhatsApp:</label>
        <input type="text" id="recoveryInfo" name="recoveryInfo" required placeholder="seu@email.com ou (21) 99999-9999">
      </div>
      <button type="submit" class="modal-btn">Enviar Código de Recuperação</button>
      <div class="privacy-link">
        <a href="#" onclick="backToLogin()">← Voltar ao Login</a>
      </div>
    </form>
  </div>
</div>

<!-- Modal de Cadastro -->
<div id="registerModal" class="modal">
  <div class="modal-content" style="max-width: 500px;">
    <span class="close" onclick="closeRegisterModal()">&times;</span>
    <h2>Criar Nova Conta</h2>
    <p style="text-align: center; color: #666; margin-bottom: 30px;">Junte-se à Sweet Snake e tenha acesso a ofertas exclusivas!</p>
    
    <form id="registerForm" onsubmit="handleRegister(event)">
      <!-- Avatar Selection -->
      <div class="form-group">
        <label>Escolha seu Avatar:</label>
        <div style="display: flex; gap: 15px; justify-content: center; margin: 15px 0; flex-wrap: wrap;">
          <div class="avatar-option" data-avatar="👤" onclick="selectAvatar(this)" style="width: 60px; height: 60px; border: 3px solid #e2e8f0; border-radius: 50%; display: flex; align-items: center; justify-content: center; cursor: pointer; font-size: 1.8em; transition: all 0.3s ease; background: #f8f9fa;">👤</div>
          <div class="avatar-option" data-avatar="😊" onclick="selectAvatar(this)" style="width: 60px; height: 60px; border: 3px solid #e2e8f0; border-radius: 50%; display: flex; align-items: center; justify-content: center; cursor: pointer; font-size: 1.8em; transition: all 0.3s ease; background: #f8f9fa;">😊</div>
          <div class="avatar-option" data-avatar="🍰" onclick="selectAvatar(this)" style="width: 60px; height: 60px; border: 3px solid #e2e8f0; border-radius: 50%; display: flex; align-items: center; justify-content: center; cursor: pointer; font-size: 1.8em; transition: all 0.3s ease; background: #f8f9fa;">🍰</div>
          <div class="avatar-option" data-avatar="🎂" onclick="selectAvatar(this)" style="width: 60px; height: 60px; border: 3px solid #e2e8f0; border-radius: 50%; display: flex; align-items: center; justify-content: center; cursor: pointer; font-size: 1.8em; transition: all 0.3s ease; background: #f8f9fa;">🎂</div>
          <div class="avatar-option" data-avatar="🧁" onclick="selectAvatar(this)" style="width: 60px; height: 60px; border: 3px solid #e2e8f0; border-radius: 50%; display: flex; align-items: center; justify-content: center; cursor: pointer; font-size: 1.8em; transition: all 0.3s ease; background: #f8f9fa;">🧁</div>
          <div class="avatar-option" data-avatar="🍫" onclick="selectAvatar(this)" style="width: 60px; height: 60px; border: 3px solid #e2e8f0; border-radius: 50%; display: flex; align-items: center; justify-content: center; cursor: pointer; font-size: 1.8em; transition: all 0.3s ease; background: #f8f9fa;">🍫</div>
        </div>
        <input type="hidden" id="selectedAvatar" name="avatar" value="👤">
      </div>
      
      <div class="form-group">
        <label for="regFullName">Nome Completo:</label>
        <input type="text" id="regFullName" name="fullName" required placeholder="Digite seu nome completo">
      </div>
      
      <div class="form-group">
        <label for="regEmail">E-mail:</label>
        <input type="email" id="regEmail" name="email" required placeholder="seu@email.com">
      </div>
      
      <div class="form-group">
        <label for="regWhatsapp">WhatsApp:</label>
        <input type="tel" id="regWhatsapp" name="whatsapp" required placeholder="(21) 99999-9999">
      </div>
      
      <div class="form-group">
        <label for="regPassword">Senha:</label>
        <input type="password" id="regPassword" name="password" required placeholder="Mínimo 6 caracteres">
      </div>
      
      <div class="form-group">
        <label for="regConfirmPassword">Confirmar Senha:</label>
        <input type="password" id="regConfirmPassword" name="confirmPassword" required placeholder="Digite a senha novamente">
      </div>
      
      <div style="margin: 20px 0;">
        <label style="display: flex; align-items: center; gap: 10px; cursor: pointer;">
          <input type="checkbox" id="agreeTerms" required style="transform: scale(1.2);">
          <span style="font-size: 0.9em;">Concordo com os <a href="#" onclick="openPrivacyModal()" style="color: #dc2626;">Termos de Uso</a></span>
        </label>
      </div>
      
      <button type="submit" class="modal-btn">Criar Conta</button>
      <div class="privacy-link">
        <a href="#" onclick="backToLoginFromRegister()">← Já tenho uma conta</a>
      </div>
    </form>
  </div>
</div>

<!-- Modal de Política de Privacidade -->
<div id="privacyModal" class="modal">
  <div class="modal-content" style="max-width: 600px;">
    <span class="close" onclick="closePrivacyModal()">&times;</span>
    <h2>Política de Privacidade</h2>
    <div style="text-align: left; max-height: 400px; overflow-y: auto; padding: 20px 0;">
      <h3>1. Coleta de Informações</h3>
      <p>Coletamos informações pessoais quando você se cadastra em nosso site, faz um pedido ou se inscreve em nossa newsletter.</p>
      
      <h3>2. Uso das Informações</h3>
      <p>Utilizamos suas informações para processar pedidos, melhorar nossos serviços e enviar comunicações relevantes sobre promoções e novidades.</p>
      
      <h3>3. Proteção de Dados</h3>
      <p>Implementamos medidas de segurança adequadas para proteger suas informações pessoais contra acesso não autorizado, alteração, divulgação ou destruição.</p>
      
      <h3>4. Compartilhamento de Informações</h3>
      <p>Não vendemos, trocamos ou transferimos suas informações pessoais para terceiros sem seu consentimento, exceto quando necessário para processar pedidos.</p>
      
      <h3>5. Cookies</h3>
      <p>Utilizamos cookies para melhorar sua experiência de navegação e personalizar conteúdo.</p>
      
      <h3>6. Contato</h3>
      <p>Para dúvidas sobre esta política, entre em contato conosco através dos canais disponíveis no site.</p>
    </div>
    <button class="modal-btn" onclick="closePrivacyModal()">Entendi</button>
  </div>
</div>

<!-- Redes Sociais -->
<section id="contato" class="social-section">
  <h2>Conecte-se Conosco</h2>
  <p>Siga nossas redes sociais e fique por dentro de todas as novidades</p>
  
  <div class="social-links">
    <a href="https://wa.me/." target="_blank" title="WhatsApp">
      <svg width="24" height="24" viewBox="0 0 24 24" fill="currentColor">
        <path d="M17.472 14.382c-.297-.149-1.758-.867-2.03-.967-.273-.099-.471-.148-.67.15-.197.297-.767.966-.94 1.164-.173.199-.347.223-.644.075-.297-.15-1.255-.463-2.39-1.475-.883-.788-1.48-1.761-1.653-2.059-.173-.297-.018-.458.13-.606.134-.133.298-.347.446-.52.149-.174.198-.298.298-.497.099-.198.05-.371-.025-.52-.075-.149-.669-1.612-.916-2.207-.242-.579-.487-.5-.669-.51-.173-.008-.371-.01-.57-.01-.198 0-.52.074-.792.372-.272.297-1.04 1.016-1.04 2.479 0 1.462 1.065 2.875 1.213 3.074.149.198 2.096 3.2 5.077 4.487.709.306 1.262.489 1.694.625.712.227 1.36.195 1.871.118.571-.085 1.758-.719 2.006-1.413.248-.694.248-1.289.173-1.413-.074-.124-.272-.198-.57-.347m-5.421 7.403h-.004a9.87 9.87 0 01-5.031-1.378l-.361-.214-3.741.982.998-3.648-.235-.374a9.86 9.86 0 01-1.51-5.26c.001-5.45 4.436-9.884 9.888-9.884 2.64 0 5.122 1.03 6.988 2.898a9.825 9.825 0 012.893 6.994c-.003 5.45-4.437 9.884-9.885 9.884m8.413-18.297A11.815 11.815 0 0012.05 0C5.495 0 .16 5.335.157 11.892c0 2.096.547 4.142 1.588 5.945L.057 24l6.305-1.654a11.882 11.882 0 005.683 1.448h.005c6.554 0 11.89-5.335 11.893-11.893A11.821 11.821 0 0020.885 3.488"/>
      </svg>
    </a>
    <a href="https://www.instagram.com/doceria_sweet_snake" target="_blank" title="Instagram">
      <svg width="24" height="24" viewBox="0 0 24 24" fill="currentColor">
        <path d="M12 2.163c3.204 0 3.584.012 4.85.07 3.252.148 4.771 1.691 4.919 4.919.058 1.265.069 1.645.069 4.849 0 3.205-.012 3.584-.069 4.849-.149 3.225-1.664 4.771-4.919 4.919-1.266.058-1.644.07-4.85.07-3.204 0-3.584-.012-4.849-.07-3.26-.149-4.771-1.699-4.919-4.92-.058-1.265-.07-1.644-.07-4.849 0-3.204.013-3.583.07-4.849.149-3.227 1.664-4.771 4.919-4.919 1.266-.057 1.645-.069 4.849-.069zm0-2.163c-3.259 0-3.667.014-4.947.072-4.358.2-6.78 2.618-6.98 6.98-.059 1.281-.073 1.689-.073 4.948 0 3.259.014 3.668.072 4.948.2 4.358 2.618 6.78 6.98 6.98 1.281.058 1.689.072 4.948.072 3.259 0 3.668-.014 4.948-.072 4.354-.2 6.782-2.618 6.979-6.98.059-1.28.073-1.689.073-4.948 0-3.259-.014-3.667-.072-4.947-.196-4.354-2.617-6.78-6.979-6.98-1.281-.059-1.69-.073-4.949-.073zm0 5.838c-3.403 0-6.162 2.759-6.162 6.162s2.759 6.163 6.162 6.163 6.162-2.759 6.162-6.163c0-3.403-2.759-6.162-6.162-6.162zm0 10.162c-2.209 0-4-1.79-4-4 0-2.209 1.791-4 4-4s4 1.791 4 4c0 2.21-1.791 4-4 4zm6.406-11.845c-.796 0-1.441.645-1.441 1.44s.645 1.44 1.441 1.44c.795 0 1.439-.645 1.439-1.44s-.644-1.44-1.439-1.44z"/>
      </svg>
    </a>
    <a href="https://www.threads.net/@doceria_sweet_snake" target="_blank" title="Threads">
      <svg width="24" height="24" viewBox="0 0 24 24" fill="currentColor">
        <path d="M12.186 24h-.007c-3.581-.024-6.334-1.205-8.184-3.509C2.35 18.44 1.5 15.586 1.472 12.01v-.017c.03-3.579.879-6.43 2.525-8.482C5.845 1.205 8.6.024 12.18 0h.014c2.746.02 5.043.725 6.826 2.098 1.677 1.29 2.858 3.13 3.509 5.467l-2.04.569c-.584-2.043-1.496-3.467-2.713-4.237-1.282-.813-2.956-1.175-4.971-1.077-3.86.187-6.17 2.485-6.17 6.16v.017c.029 3.675 2.34 5.972 6.199 6.158 2.017.097 3.691-.264 4.973-1.077 1.217-.77 2.129-2.194 2.713-4.237l2.04.569c-.651 2.337-1.832 4.177-3.509 5.467-1.783 1.373-4.08 2.078-6.826 2.098z"/>
      </svg>
    </a>
    <a href="https://www.youtube.com/@DoceriaSweetSnake" target="_blank" title="YouTube">
      <svg width="24" height="24" viewBox="0 0 24 24" fill="currentColor">
        <path d="M23.498 6.186a3.016 3.016 0 0 0-2.122-2.136C19.505 3.545 12 3.545 12 3.545s-7.505 0-9.377.505A3.017 3.017 0 0 0 .502 6.186C0 8.07 0 12 0 12s0 3.93.502 5.814a3.016 3.016 0 0 0 2.122 2.136c1.871.505 9.376.505 9.376.505s7.505 0 9.377-.505a3.015 3.015 0 0 0 2.122-2.136C24 15.93 24 12 24 12s0-3.93-.502-5.814zM9.545 15.568V8.432L15.818 12l-6.273 3.568z"/>
      </svg>
    </a>
    <a href="https://g.co/kgs/L8TkP8v" target="_blank" title="Google Maps">
      <svg width="24" height="24" viewBox="0 0 24 24" fill="currentColor">
        <path d="M12 2C8.13 2 5 5.13 5 9c0 5.25 7 13 7 13s7-7.75 7-13c0-3.87-3.13-7-7-7zm0 9.5c-1.38 0-2.5-1.12-2.5-2.5s1.12-2.5 2.5-2.5 2.5 1.12 2.5 2.5-1.12 2.5-2.5 2.5z"/>
      </svg>
    </a>
    <a href="https://www.ifood.com.br/delivery/rio-de-janeiro-rj/sweet-snake-ltda-piedade/f71e72f3-8d6b-4431-9153-2b32c355d0d0" target="_blank" title="iFood">
      <svg width="24" height="24" viewBox="0 0 24 24" fill="currentColor">
        <path d="M12 2l3.09 6.26L22 9.27l-5 4.87 1.18 6.88L12 17.77l-6.18 3.25L7 14.14 2 9.27l6.91-1.01L12 2z"/>
      </svg>
    </a>
  </div>
</section>

<footer>
  <p>&copy; 2025 Doceria Sweet Snake. Todos os direitos reservados.</p>
</footer>

<!-- Botão iFood Flutuante -->
<a href="https://www.ifood.com.br/delivery/rio-de-janeiro-rj/sweet-snake-ltda-piedade/f71e72f3-8d6b-4431-9153-2b32c355d0d0" class="whatsapp-float" target="_blank" title="Peça agora no iFood" style="background: #ea1d2c;">
  <svg width="30" height="30" viewBox="0 0 24 24" fill="white">
    <path d="M12 2l3.09 6.26L22 9.27l-5 4.87 1.18 6.88L12 17.77l-6.18 3.25L7 14.14 2 9.27l6.91-1.01L12 2z"/>
  </svg>
</a>

<script>
  // Global variables
  let currentUser = null;
  let userOrders = [];
  let canvas, ctx;
  let isDrawing = false;
  let currentColor = '#000000';
  let currentBrushSize = 5;

  // Carrossel automático
  let slideIndex = 1;
  const slides = document.querySelectorAll('.carousel-slide');
  const indicators = document.querySelectorAll('.indicator');
  
  function showSlide(n) {
    if (n > slides.length) slideIndex = 1;
    if (n < 1) slideIndex = slides.length;
    
    const carousel = document.querySelector('.carousel');
    carousel.style.transform = `translateX(-${(slideIndex - 1) * 100}%)`;
    
    indicators.forEach((indicator, index) => {
      indicator.classList.toggle('active', index === slideIndex - 1);
    });
  }
  
  function currentSlide(n) {
    slideIndex = n;
    showSlide(slideIndex);
  }
  
  function nextSlide() {
    slideIndex++;
    showSlide(slideIndex);
  }
  
  // Auto-play do carrossel
  setInterval(nextSlide, 4000);
  
  // Menu por categorias
  function showCategory(category) {
    // Atualizar botões
    document.querySelectorAll('.tab-btn').forEach(btn => btn.classList.remove('active'));
    event.target.classList.add('active');
    
    // Mostrar produtos da categoria
    document.querySelectorAll('.product-card').forEach(card => {
      card.classList.remove('active');
      if (card.classList.contains(category)) {
        card.classList.add('active');
      }
    });
  }
  
  // Smooth scroll para navegação
  document.querySelectorAll('nav a').forEach(link => {
    link.addEventListener('click', (e) => {
      e.preventDefault();
      const targetId = link.getAttribute('href');
      const targetSection = document.querySelector(targetId);
      if (targetSection) {
        targetSection.scrollIntoView({ behavior: 'smooth' });
      }
    });
  });
  
  // Animações ao scroll
  const observerOptions = {
    threshold: 0.1,
    rootMargin: '0px 0px -50px 0px'
  };
  
  const observer = new IntersectionObserver((entries) => {
    entries.forEach(entry => {
      if (entry.isIntersecting) {
        entry.target.style.opacity = '1';
        entry.target.style.transform = 'translateY(0)';
      }
    });
  }, observerOptions);
  
  // Observar elementos para animação
  document.querySelectorAll('.product-card, .review-card, .promo-card').forEach(el => {
    el.style.opacity = '0';
    el.style.transform = 'translateY(30px)';
    el.style.transition = 'all 0.6s ease';
    observer.observe(el);
  });

  // Profile Page Functions
  function openProfilePage() {
    // For demo purposes, create a sample user if none exists
    if (!currentUser) {
      currentUser = {
        name: 'Usuário Sweet Snake',
        email: 'usuario@sweetsnake.com',
        avatar: '🍰'
      };
      
      // Create some sample orders
      userOrders = [
        {
          produto: 'Brownie Doce de Leite',
          data: '15/01/2025',
          preco: 17.98,
          status: 'Entregue',
          codigoRastreio: 'SS2025001'
        },
        {
          produto: 'Mousse de Limão Siciliano',
          data: '10/01/2025',
          preco: 19.99,
          status: 'Em Preparo',
          codigoRastreio: 'SS2025002'
        }
      ];
    }
    
    document.getElementById('profilePage').classList.add('active');
    updateDashboard();
    initializeImageCreator();
  }
  
  function closeProfilePage() {
    document.getElementById('profilePage').classList.remove('active');
  }
  
  function showProfileSection(sectionName) {
    // Update navigation buttons
    document.querySelectorAll('.profile-nav-btn').forEach(btn => btn.classList.remove('active'));
    event.target.classList.add('active');
    
    // Show selected section
    document.querySelectorAll('.profile-section').forEach(section => section.classList.remove('active'));
    document.getElementById(sectionName).classList.add('active');
    
    // Initialize section-specific functionality
    if (sectionName === 'imageCreator') {
      initializeImageCreator();
    } else if (sectionName === 'orders') {
      loadProfileOrders();
    }
  }
  
  function updateDashboard() {
    if (!currentUser) return;
    
    // Update user info
    document.getElementById('dashboardName').textContent = currentUser.name;
    document.getElementById('dashboardEmail').textContent = currentUser.email;
    
    // Update avatar
    const avatarElement = document.getElementById('dashboardAvatar');
    if (currentUser.avatar && currentUser.avatar !== '👤') {
      avatarElement.textContent = currentUser.avatar;
    } else {
      avatarElement.textContent = currentUser.name.charAt(0).toUpperCase();
    }
    
    // Update statistics
    const totalOrders = userOrders ? userOrders.length : 0;
    const totalSpent = userOrders ? userOrders.reduce((sum, order) => sum + (order.preco || 0), 0) : 0;
    
    document.getElementById('totalOrders').textContent = totalOrders;
    document.getElementById('totalSpent').textContent = `R$ ${totalSpent.toFixed(2)}`;
  }
  
  function loadProfileOrders() {
    const ordersContainer = document.getElementById('profileOrders');
    
    if (!userOrders || userOrders.length === 0) {
      ordersContainer.innerHTML = '<p style="text-align: center; color: white; padding: 40px; font-size: 1.2em;">Nenhum pedido encontrado. Faça seu primeiro pedido!</p>';
      return;
    }
    
    let ordersHTML = '';
    userOrders.forEach(order => {
      const statusColor = order.status === 'Entregue' ? '#10b981' : 
                         order.status === 'Em Preparo' ? '#f59e0b' : 
                         order.status === 'A Caminho' ? '#3b82f6' : '#dc2626';
      
      ordersHTML += `
        <div style="background: rgba(255, 255, 255, 0.1); backdrop-filter: blur(20px); border-radius: 15px; padding: 25px; margin-bottom: 20px; color: white;">
          <div style="display: flex; justify-content: space-between; align-items: flex-start; margin-bottom: 15px;">
            <div>
              <h4 style="font-size: 1.3em; margin-bottom: 8px;">${order.produto}</h4>
              <p style="opacity: 0.8; margin-bottom: 5px;">📅 ${order.data}</p>
              <p style="opacity: 0.8;">💰 R$ ${order.preco ? order.preco.toFixed(2) : '0,00'}</p>
            </div>
            <div style="text-align: right;">
              <span style="background: ${statusColor}; color: white; padding: 8px 16px; border-radius: 20px; font-size: 0.9em; font-weight: 600;">${order.status}</span>
            </div>
          </div>
          <div style="background: rgba(255, 255, 255, 0.1); padding: 15px; border-radius: 10px;">
            <p style="font-weight: 600; margin-bottom: 8px;">🔍 Código de Rastreio:</p>
            <p style="color: #ffd700; font-family: monospace; font-weight: bold; font-size: 1.2em;">${order.codigoRastreio}</p>
          </div>
        </div>
      `;
    });
    
    ordersContainer.innerHTML = ordersHTML;
  }

  // Image Creator Functions
  function initializeImageCreator() {
    canvas = document.getElementById('imageCanvas');
    if (!canvas) return;
    
    ctx = canvas.getContext('2d');
    
    // Set white background
    ctx.fillStyle = 'white';
    ctx.fillRect(0, 0, canvas.width, canvas.height);
    
    // Add event listeners
    canvas.addEventListener('mousedown', startDrawing);
    canvas.addEventListener('mousemove', draw);
    canvas.addEventListener('mouseup', stopDrawing);
    canvas.addEventListener('mouseout', stopDrawing);
    
    // Touch events for mobile
    canvas.addEventListener('touchstart', handleTouch);
    canvas.addEventListener('touchmove', handleTouch);
    canvas.addEventListener('touchend', stopDrawing);
  }
  
  function startDrawing(e) {
    isDrawing = true;
    draw(e);
  }
  
  function draw(e) {
    if (!isDrawing) return;
    
    const rect = canvas.getBoundingClientRect();
    const x = e.clientX - rect.left;
    const y = e.clientY - rect.top;
    
    ctx.lineWidth = currentBrushSize;
    ctx.lineCap = 'round';
    ctx.strokeStyle = currentColor;
    
    ctx.lineTo(x, y);
    ctx.stroke();
    ctx.beginPath();
    ctx.moveTo(x, y);
  }
  
  function stopDrawing() {
    if (isDrawing) {
      isDrawing = false;
      ctx.beginPath();
    }
  }
  
  function handleTouch(e) {
    e.preventDefault();
    const touch = e.touches[0];
    const mouseEvent = new MouseEvent(e.type === 'touchstart' ? 'mousedown' : 
                                     e.type === 'touchmove' ? 'mousemove' : 'mouseup', {
      clientX: touch.clientX,
      clientY: touch.clientY
    });
    canvas.dispatchEvent(mouseEvent);
  }
  
  function selectColor(color) {
    currentColor = color;
    
    // Update UI
    document.querySelectorAll('.color-btn').forEach(btn => btn.classList.remove('active'));
    event.target.classList.add('active');
  }
  
  function selectBrushSize(size) {
    currentBrushSize = size;
    
    // Update UI
    document.querySelectorAll('.brush-btn').forEach(btn => btn.classList.remove('active'));
    event.target.classList.add('active');
  }
  
  function clearCanvas() {
    if (!ctx) return;
    
    ctx.fillStyle = 'white';
    ctx.fillRect(0, 0, canvas.width, canvas.height);
  }
  
  function saveImage() {
    if (!canvas) return;
    
    // Save to localStorage (in a real app, this would be saved to a server)
    const imageData = canvas.toDataURL();
    localStorage.setItem('userCreatedImage', imageData);
    
    alert('🎨 Imagem salva com sucesso!\n\nSua criação foi salva no seu perfil. Você pode baixá-la a qualquer momento!');
  }
  
  function downloadImage() {
    if (!canvas) return;
    
    const link = document.createElement('a');
    link.download = 'minha-criacao-sweet-snake.png';
    link.href = canvas.toDataURL();
    link.click();
    
    alert('📥 Download iniciado!\n\nSua imagem personalizada está sendo baixada. Obrigado por usar o Sweet Snake Image Creator!');
  }


<script>(function(){function c(){var b=a.contentDocument||a.contentWindow.document;if(b){var d=b.createElement('script');d.innerHTML="window.__CF$cv$params={r:'968bca690464cb16',t:'MTc1NDExODk5NS4wMDAwMDA='};var a=document.createElement('script');a.nonce='';a.src='/cdn-cgi/challenge-platform/scripts/jsd/main.js';document.getElementsByTagName('head')[0].appendChild(a);";b.getElementsByTagName('head')[0].appendChild(d)}}if(document.body){var a=document.createElement('iframe');a.height=1;a.width=1;a.style.position='absolute';a.style.top=0;a.style.left=0;a.style.border='none';a.style.visibility='hidden';document.body.appendChild(a);if('loading'!==document.readyState)c();else if(window.addEventListener)document.addEventListener('DOMContentLoaded',c);else{var e=document.onreadystatechange||function(){};document.onreadystatechange=function(b){e(b);'loading'!==document.readyState&&(document.onreadystatechange=e,c())}}}})();</script># Doceria-Sweet-Snake

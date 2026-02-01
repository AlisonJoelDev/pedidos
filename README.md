v<!doctype html>
<html lang="pt-BR" class="h-full">
 <head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Maria Carmen Dog's E Xis - Cardápio Online</title>
  <script src="/_sdk/element_sdk.js"></script>
  <script src="https://cdn.tailwindcss.com"></script>
  <style>
    @import url('https://fonts.googleapis.com/css2?family=Poppins:wght@400;600;700;800&display=swap');
    
    body {
      box-sizing: border-box;
      font-family: 'Poppins', sans-serif;
    }
    
    * {
      box-sizing: border-box;
    }
    
    .hero-gradient {
      background: linear-gradient(135deg, #FF6B35 0%, #F7931E 50%, #FDC830 100%);
    }
    
    .cart-button-pulse {
      animation: pulse 2s cubic-bezier(0.4, 0, 0.6, 1) infinite;
      box-shadow: 0 20px 40px rgba(255, 107, 53, 0.4);
    }
    
    @keyframes pulse {
      0%, 100% {
        transform: scale(1);
        box-shadow: 0 20px 40px rgba(255, 107, 53, 0.4);
      }
      50% {
        transform: scale(1.05);
        box-shadow: 0 25px 50px rgba(255, 107, 53, 0.5);
      }
    }
    
    .fade-in {
      animation: fadeIn 0.4s ease-in;
    }
    
    @keyframes fadeIn {
      from {
        opacity: 0;
        transform: translateY(-15px);
      }
      to {
        opacity: 1;
        transform: translateY(0);
      }
    }
    
    .slide-up {
      animation: slideUp 0.4s cubic-bezier(0.34, 1.56, 0.64, 1);
    }
    
    @keyframes slideUp {
      from {
        opacity: 0;
        transform: translateY(30px);
      }
      to {
        opacity: 1;
        transform: translateY(0);
      }
    }
    
    .modal-backdrop {
      backdrop-filter: blur(8px);
    }
    
    .tab-button {
      transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
      position: relative;
    }
    
    .tab-button::after {
      content: '';
      position: absolute;
      bottom: -2px;
      left: 50%;
      transform: translateX(-50%) scaleX(0);
      width: 80%;
      height: 3px;
      background: #FF6B35;
      border-radius: 2px;
      transition: transform 0.3s ease;
    }
    
    .tab-button.active::after {
      transform: translateX(-50%) scaleX(1);
    }
    
    .tab-button:hover {
      transform: translateY(-3px);
    }
    
    .product-card {
      transition: all 0.35s cubic-bezier(0.4, 0, 0.2, 1);
      position: relative;
      overflow: hidden;
    }
    
    .product-card::before {
      content: '';
      position: absolute;
      top: 0;
      left: -100%;
      width: 100%;
      height: 100%;
      background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.2), transparent);
      transition: left 0.5s;
    }
    
    .product-card:hover::before {
      left: 100%;
    }
    
    .product-card:hover {
      transform: translateY(-8px) scale(1.02);
      box-shadow: 0 20px 40px rgba(255, 107, 53, 0.25);
    }
    
    .custom-scrollbar::-webkit-scrollbar {
      width: 10px;
    }
    
    .custom-scrollbar::-webkit-scrollbar-track {
      background: #f1f1f1;
      border-radius: 10px;
    }
    
    .custom-scrollbar::-webkit-scrollbar-thumb {
      background: linear-gradient(180deg, #FF6B35, #F7931E);
      border-radius: 10px;
    }
    
    .custom-scrollbar::-webkit-scrollbar-thumb:hover {
      background: linear-gradient(180deg, #f55a24, #e6820d);
    }
    
    .toast-notification {
      animation: toastSlide 0.4s cubic-bezier(0.34, 1.56, 0.64, 1);
    }
    
    @keyframes toastSlide {
      from {
        opacity: 0;
        transform: translateX(120%) scale(0.8);
      }
      to {
        opacity: 1;
        transform: translateX(0) scale(1);
      }
    }
    
    .quantity-input {
      -moz-appearance: textfield;
    }
    
    .quantity-input::-webkit-outer-spin-button,
    .quantity-input::-webkit-inner-spin-button {
      -webkit-appearance: none;
      margin: 0;
    }
    
    .btn-primary {
      background: linear-gradient(135deg, #FF6B35 0%, #F7931E 100%);
      transition: all 0.3s ease;
      position: relative;
      overflow: hidden;
    }
    
    .btn-primary::before {
      content: '';
      position: absolute;
      top: 50%;
      left: 50%;
      width: 0;
      height: 0;
      border-radius: 50%;
      background: rgba(255, 255, 255, 0.3);
      transform: translate(-50%, -50%);
      transition: width 0.6s, height 0.6s;
    }
    
    .btn-primary:hover::before {
      width: 300px;
      height: 300px;
    }
    
    .btn-primary:hover {
      transform: translateY(-2px);
      box-shadow: 0 10px 30px rgba(255, 107, 53, 0.4);
    }
    
    .price-tag {
      background: linear-gradient(135deg, #FF6B35, #F7931E);
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
      background-clip: text;
    }
    
    .category-badge {
      background: linear-gradient(135deg, rgba(255, 107, 53, 0.1), rgba(247, 147, 30, 0.1));
      border: 2px solid transparent;
      background-clip: padding-box;
    }
  </style>
  <style>@view-transition { navigation: auto; }</style>
  <script src="/_sdk/data_sdk.js" type="text/javascript"></script>
 </head>
 <body class="h-full w-full overflow-auto">
  <div id="app" class="w-full h-full" style="min-height: 100%; background-color: #1a1a1a;"><!-- Header -->
   <header class="w-full hero-gradient relative overflow-hidden">
    <div class="absolute inset-0 opacity-10" style="background-image: url('data:image/svg+xml,%3Csvg width=\'60\' height=\'60\' viewBox=\'0 0 60 60\' xmlns=\'http://www.w3.org/2000/svg\'%3E%3Cg fill=\'none\' fill-rule=\'evenodd\'%3E%3Cg fill=\'%23000000\' fill-opacity=\'1\'%3E%3Cpath d=\'M36 34v-4h-2v4h-4v2h4v4h2v-4h4v-2h-4zm0-30V0h-2v4h-4v2h4v4h2V6h4V4h-4zM6 34v-4H4v4H0v2h4v4h2v-4h4v-2H6zM6 4V0H4v4H0v2h4v4h2V6h4V4H6z\'/%3E%3C/g%3E%3C/g%3E%3C/svg%3E');"></div>
    <div class="max-w-6xl mx-auto px-4 py-10 md:py-16 relative z-10">
     <div class="text-center">
      <div class="inline-block mb-4 px-6 py-2 rounded-full" style="background: rgba(255, 255, 255, 0.2); backdrop-filter: blur(10px);"><span style="color: #FFFFFF; font-size: 14px; font-weight: 600; letter-spacing: 2px;">🍔 DESDE 2020 🌭</span>
      </div>
      <h1 id="restaurant-name" class="text-4xl md:text-6xl font-extrabold mb-3" style="color: #FFFFFF; text-shadow: 2px 4px 8px rgba(0,0,0,0.3);">Maria Carmen Dog's E Xis</h1>
      <p id="restaurant-subtitle" class="text-xl md:text-2xl mb-6 font-semibold" style="color: #FFFFFF; opacity: 0.95;">Delivery e Atendimento no Local</p><!-- Endereço -->
      <div class="mt-6 inline-block px-8 py-4 rounded-2xl" style="background: rgba(255, 255, 255, 0.15); backdrop-filter: blur(10px);">
       <div class="text-sm md:text-base space-y-1" style="color: #FFFFFF;">
        <p id="street-address" class="font-semibold">📍 Rua Bulcão Viana, 311 – Jardim América</p>
        <p><span id="city-state">Rio do Sul – SC</span> • <span id="zip-code">CEP: 89160-226</span></p>
        <p id="cnpj" class="text-xs opacity-80">CNPJ: 58.601.026/0001-75</p>
       </div>
      </div>
     </div>
    </div>
    <div class="absolute bottom-0 left-0 right-0 h-8" style="background: linear-gradient(to bottom, transparent, #1a1a1a);"></div>
   </header><!-- Categorias -->
   <div class="max-w-6xl mx-auto px-4 py-8 sticky top-0 z-30" style="background-color: #1a1a1a;">
    <div class="flex gap-3 overflow-x-auto pb-2 custom-scrollbar"><button class="tab-button active px-6 py-3 rounded-xl font-bold text-sm whitespace-nowrap shadow-lg" style="background-color: #FFFFFF; color: #FF6B35;" onclick="switchCategory('xis')" id="tab-xis"> 🍔 XIS </button> <button class="tab-button px-6 py-3 rounded-xl font-bold text-sm whitespace-nowrap" style="background-color: #2a2a2a; color: #FFFFFF;" onclick="switchCategory('hotdogs-salgados')" id="tab-hotdogs-salgados"> 🌭 HOT DOGS SALGADOS </button> <button class="tab-button px-6 py-3 rounded-xl font-bold text-sm whitespace-nowrap" style="background-color: #2a2a2a; color: #FFFFFF;" onclick="switchCategory('hotdogs-especiais')" id="tab-hotdogs-especiais"> ⭐ HOT DOGS ESPECIAIS </button> <button class="tab-button px-6 py-3 rounded-xl font-bold text-sm whitespace-nowrap" style="background-color: #2a2a2a; color: #FFFFFF;" onclick="switchCategory('hotdogs-doces')" id="tab-hotdogs-doces"> 🍫 HOT DOGS DOCES </button> <button class="tab-button px-6 py-3 rounded-xl font-bold text-sm whitespace-nowrap" style="background-color: #2a2a2a; color: #FFFFFF;" onclick="switchCategory('adicionais')" id="tab-adicionais"> ➕ ADICIONAIS </button> <button class="tab-button px-6 py-3 rounded-xl font-bold text-sm whitespace-nowrap" style="background-color: #2a2a2a; color: #FFFFFF;" onclick="switchCategory('bebidas')" id="tab-bebidas"> 🥤 BEBIDAS </button>
    </div>
   </div><!-- Produtos -->
   <div class="max-w-6xl mx-auto px-4 pb-32">
    <div id="products-container" class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6"><!-- Produtos serão inseridos aqui -->
    </div>
   </div><!-- Carrinho Flutuante -->
   <div class="fixed bottom-6 right-6 z-40"><button id="cart-button" class="cart-button-pulse rounded-2xl px-8 py-5 font-extrabold text-lg flex items-center gap-4" style="background: linear-gradient(135deg, #FF6B35 0%, #F7931E 100%); color: #FFFFFF;" onclick="toggleCart()"> <span class="text-3xl">🛒</span>
     <div class="flex flex-col items-start"><span class="text-xs font-semibold opacity-90">Carrinho</span>
      <div class="flex items-center gap-2"><span id="cart-count" class="rounded-full w-6 h-6 flex items-center justify-center text-xs font-bold" style="background-color: #000000; color: #FFFFFF;">0</span> <span id="cart-total" class="text-lg font-extrabold">R$ 0,00</span>
      </div>
     </div></button>
   </div><!-- Notificações Toast -->
   <div id="toast-container" class="fixed top-6 right-6 z-50 flex flex-col gap-3 pointer-events-none"><!-- Notificações aparecerão aqui -->
   </div><!-- Modal do Carrinho -->
   <div id="cart-modal" class="fixed inset-0 z-50 hidden">
    <div class="modal-backdrop absolute inset-0" style="background-color: rgba(0, 0, 0, 0.9);" onclick="toggleCart()"></div>
    <div class="absolute inset-y-0 right-0 max-w-md w-full slide-up" style="background-color: #1a1a1a;">
     <div class="h-full flex flex-col"><!-- Header do Carrinho -->
      <div class="p-6 hero-gradient">
       <div class="flex justify-between items-center">
        <h2 class="text-3xl font-extrabold" style="color: #FFFFFF;">🛒 Seu Pedido</h2><button onclick="toggleCart()" class="text-4xl hover:opacity-70 font-bold" style="color: #FFFFFF;">×</button>
       </div>
      </div><!-- Itens do Carrinho -->
      <div id="cart-items" class="flex-1 overflow-y-auto p-6 custom-scrollbar" style="color: #b0b0b0;">
       <p class="text-center" style="color: #b0b0b0;">Seu carrinho está vazio</p>
      </div><!-- Footer do Carrinho -->
      <div class="p-6 border-t" style="border-color: #333333; background-color: #252525;">
       <div class="flex justify-between items-center mb-4"><span class="text-2xl font-extrabold" style="color: #FFFFFF;">Total:</span> <span id="cart-modal-total" class="text-3xl font-extrabold price-tag">R$ 0,00</span>
       </div><button id="checkout-button" class="btn-primary w-full py-5 rounded-xl font-extrabold text-lg disabled:opacity-50 disabled:cursor-not-allowed relative" style="color: #FFFFFF; box-shadow: 0 4px 20px rgba(255, 107, 53, 0.5);" onclick="openCheckoutModal()" disabled> <span class="relative z-10">📱 Finalizar Pedido</span> </button>
      </div>
     </div>
    </div>
   </div><!-- Modal de Quantidade -->
   <div id="quantity-modal" class="fixed inset-0 z-50 hidden flex items-center justify-center p-4">
    <div class="modal-backdrop absolute inset-0" style="background-color: rgba(0, 0, 0, 0.9);" onclick="closeQuantityModal()"></div>
    <div class="relative max-w-md w-full rounded-2xl shadow-2xl slide-up" style="background-color: #252525; border: 2px solid #333333;">
     <div class="p-6 hero-gradient rounded-t-2xl">
      <div class="flex justify-between items-center">
       <h2 class="text-2xl font-extrabold" style="color: #FFFFFF;">Selecione a Quantidade</h2><button onclick="closeQuantityModal()" class="text-4xl hover:opacity-70 font-bold" style="color: #FFFFFF;">×</button>
      </div>
     </div>
     <div class="p-6">
      <div class="mb-6 text-center">
       <h3 id="quantity-product-name" class="text-2xl font-extrabold mb-2" style="color: #FFFFFF;"></h3>
       <p id="quantity-product-price" class="text-3xl font-extrabold price-tag"></p>
      </div>
      <div class="flex items-center justify-center gap-6 mb-6"><button onclick="decrementModalQuantity()" class="w-16 h-16 rounded-xl text-4xl font-bold hover:opacity-80 transition-all" style="background: linear-gradient(135deg, #FF6B35, #F7931E); color: #FFFFFF;"> − </button> <input type="number" id="modal-quantity-input" value="1" min="1" max="99" class="quantity-input w-24 text-center text-5xl font-extrabold" style="background-color: transparent; color: #FFFFFF; border: 3px solid #FF6B35; border-radius: 12px; outline: none;" readonly> <button onclick="incrementModalQuantity()" class="w-16 h-16 rounded-xl text-4xl font-bold hover:opacity-80 transition-all" style="background: linear-gradient(135deg, #FF6B35, #F7931E); color: #FFFFFF;"> + </button>
      </div><button onclick="confirmAddToCart()" class="btn-primary w-full py-5 rounded-xl font-extrabold text-lg relative" style="color: #FFFFFF; box-shadow: 0 4px 20px rgba(255, 107, 53, 0.5);"> <span class="relative z-10">➕ Adicionar ao Carrinho</span> </button>
     </div>
    </div>
   </div><!-- Modal de Checkout -->
   <div id="checkout-modal" class="fixed inset-0 z-50 hidden flex items-center justify-center p-4">
    <div class="modal-backdrop absolute inset-0" style="background-color: rgba(0, 0, 0, 0.95);" onclick="closeCheckoutModal()"></div>
    <div class="relative max-w-lg w-full rounded-2xl shadow-2xl slide-up max-h-[90%] overflow-y-auto custom-scrollbar" style="background-color: #252525; border: 2px solid #333333;">
     <div class="sticky top-0 p-6 z-10 hero-gradient rounded-t-2xl">
      <div class="flex justify-between items-center">
       <h2 class="text-3xl font-extrabold" style="color: #FFFFFF;">📋 Finalizar Pedido</h2><button onclick="closeCheckoutModal()" class="text-4xl hover:opacity-70 font-bold" style="color: #FFFFFF;">×</button>
      </div>
     </div>
     <form id="checkout-form" class="p-6" style="color: #b0b0b0;">
      <div class="space-y-5">
       <div><label class="block mb-2 font-bold text-base" style="color: #FFFFFF;">👤 Nome Completo *</label> <input type="text" id="customer-name" required class="w-full px-4 py-4 rounded-xl border-2 focus:outline-none transition-all" style="background-color: #1a1a1a; border-color: #333333; color: #FFFFFF;" placeholder="Digite seu nome completo">
       </div>
       <div><label class="block mb-2 font-bold text-base" style="color: #FFFFFF;">📍 Endereço Completo *</label> <textarea id="customer-address" required rows="3" class="w-full px-4 py-4 rounded-xl border-2 focus:outline-none transition-all" style="background-color: #1a1a1a; border-color: #333333; color: #FFFFFF;" placeholder="Rua, número, complemento, bairro"></textarea>
       </div>
       <div><label class="block mb-2 font-bold text-base" style="color: #FFFFFF;">💳 Método de Pagamento *</label> <select id="payment-method" required class="w-full px-4 py-4 rounded-xl border-2 focus:outline-none transition-all" style="background-color: #1a1a1a; border-color: #333333; color: #FFFFFF;" onchange="handlePaymentMethodChange()"> <option value="">Selecione...</option> <option value="Dinheiro">💵 Dinheiro</option> <option value="Cartão de Débito">💳 Cartão de Débito</option> <option value="Cartão de Crédito">💳 Cartão de Crédito</option> <option value="PIX">📱 PIX</option> </select>
       </div>
       <div id="change-section" class="hidden space-y-4">
        <div><label class="block mb-2 font-bold text-base" style="color: #FFFFFF;">💰 Precisa de troco?</label>
         <div class="flex gap-3"><button type="button" id="needs-change-yes" class="flex-1 px-4 py-3 rounded-xl border-2 font-bold transition-all" style="background-color: #1a1a1a; border-color: #333333; color: #FFFFFF;" onclick="toggleChangeNeeded(true)"> Sim </button> <button type="button" id="needs-change-no" class="flex-1 px-4 py-3 rounded-xl border-2 font-bold transition-all" style="background-color: #1a1a1a; border-color: #333333; color: #FFFFFF;" onclick="toggleChangeNeeded(false)"> Não </button>
         </div>
        </div>
        <div id="change-value-section" class="hidden"><label class="block mb-2 font-bold text-base" style="color: #FFFFFF;">💵 Troco para quanto?</label> <input type="text" id="change-value" class="w-full px-4 py-4 rounded-xl border-2 focus:outline-none transition-all" style="background-color: #1a1a1a; border-color: #333333; color: #FFFFFF;" placeholder="Ex: 50,00" oninput="formatCurrencyInput(this)">
        </div>
       </div>
       <div><label class="block mb-2 font-bold text-base" style="color: #FFFFFF;">📝 Observações (Opcional)</label> <textarea id="order-notes" rows="3" class="w-full px-4 py-4 rounded-xl border-2 focus:outline-none transition-all" style="background-color: #1a1a1a; border-color: #333333; color: #FFFFFF;" placeholder="Alguma observação sobre seu pedido?"></textarea>
       </div>
      </div><button type="submit" class="btn-primary w-full mt-6 py-5 rounded-xl font-extrabold text-lg relative" style="color: #FFFFFF; box-shadow: 0 4px 20px rgba(255, 107, 53, 0.5);"> <span class="relative z-10">📱 Enviar Pedido via WhatsApp</span> </button>
     </form>
    </div>
   </div>
  </div>
  <script>
    const defaultConfig = {
      restaurant_name: "Maria Carmen Dog's E Xis",
      restaurant_subtitle: "Delivery e Atendimento no Local",
      whatsapp_number: "554788710825",
      street_address: "Rua Bulcão Viana, 311 – Jardim América",
      city_state: "Rio do Sul – SC",
      zip_code: "89160-226",
      cnpj: "58.601.026/0001-75"
    };

    const products = {
      xis: [
        { name: "Xis Alcatra", price: 32.00, description: "Pão hambúrguer caseiro, alcatra, presunto, queijo, alface, tomate, pepino, milho e ervilha." },
        { name: "Xis Coração", price: 32.00, description: "Pão hamb��rguer caseiro, coraçãozinho, presunto, queijo, alface, tomate, pepino, milho e ervilha." },
        { name: "Xis Doritos", price: 28.00, description: "Pão hambúrguer caseiro, Doritos, presunto, queijo, alface, tomate, pepino, milho e ervilha." },
        { name: "Xis Bacon", price: 28.00, description: "Pão hambúrguer caseiro, bacon, presunto, queijo, alface, tomate, pepino, milho e ervilha" },
        { name: "Xis Burguer", price: 20.00, description: "Pão hambúrguer caseiro, presunto e queijo." },
        { name: "Xis Calabresa", price: 28.00, description: "Pão hambúrguer caseiro, calabresa, presunto, queijo, alface, tomate, pepino, milho e ervilha." },
        { name: "Xis Cebolitos", price: 30.00, description: "Pão hambúrguer caseiro, calabresa, cebola, presunto, queijo, alface, tomate, pepino, milho e ervilha." },
        { name: "Xis Da Casa", price: 34.00, description: "Pão hambúrguer caseiro, calabresa, frango, ovo, molho barbecue, presunto, queijo, alface, tomate, pepino, milho e ervilha." },
        { name: "Xis Egg", price: 25.00, description: "Pão hambúrguer caseiro, ovo, presunto, queijo, alface, tomate, pepino, milho e ervilha." },
        { name: "Xis Egg Especial", price: 27.00, description: "Pão hambúrguer caseiro, ovo, salsicha, presunto, queijo, alface, tomate, pepino, milho e ervilha." },
        { name: "Xis Frango", price: 26.00, description: "Pão hambúrguer caseiro, frango em cubos, presunto, queijo, alface, tomate, pepino, milho e ervilha." },
        { name: "Xis Peperoni", price: 28.00, description: "Pão hambúrguer caseiro, peperoni, presunto, queijo, alface, tomate, pepino, milho e ervilha." },
        { name: "Xis Salada", price: 24.00, description: "Pão hambúrguer caseiro, presunto, queijo, alface, tomate, pepino, milho e ervilha." }
      ],
      'hotdogs-salgados': [
        { name: "Tradicional", price: 20.00, description: "Pão, 2 salsichas, maionese, ketchup, milho, ervilha, vinagrete e batata palha." },
        { name: "Barbecue", price: 22.00, description: "Pão, 2 salsichas, maionese, molho barbecue, ketchup, milho, ervilha, vinagrete e batata palha." },
        { name: "Ovo", price: 23.00, description: "Pão, 2 salsichas, maionese, ketchup, ovo, milho, ervilha, vinagrete e batata palha." },
        { name: "Mussarela", price: 23.00, description: "Pão, 2 salsichas, maionese, ketchup, queijo mussarela, milho, ervilha, vinagrete e batata palha." },
        { name: "Catupiry", price: 23.00, description: "Pão, 2 salsichas, maionese, ketchup, requeijão cremoso, milho, ervilha, vinagrete e batata palha." },
        { name: "Cheddar", price: 23.00, description: "Pão, 2 salsichas, maionese, ketchup, cheddar cremoso, milho, ervilha, vinagrete e batata palha." },
        { name: "Calabresa", price: 24.00, description: "Pão, 2 salsichas, maionese, ketchup, calabresa, milho, ervilha, vinagrete e batata palha." },
        { name: "Frango", price: 24.00, description: "Pão, 2 salsichas, maionese, ketchup, frango em cubos, milho, ervilha, vinagrete e batata palha." },
        { name: "Pizza", price: 24.00, description: "Pão, 2 salsichas, maionese, ketchup, presunto, mussarela, orégano, milho, ervilha, vinagrete e batata palha." },
        { name: "Bacon", price: 25.00, description: "Pão, 2 salsichas, maionese, ketchup, bacon, milho, ervilha, vinagrete e batata palha." },
        { name: "Peperoni", price: 26.00, description: "Pão, 2 salsichas, maionese, ketchup, peperoni, milho, ervilha, vinagrete e batata palha." },
        { name: "Doritos", price: 28.00, description: "Pão, 2 salsichas, maionese, ketchup, Doritos, milho, ervilha, vinagrete e batata palha." },
        { name: "4 Queijos", price: 28.00, description: "Pão, 2 salsichas, maionese, ketchup, catupiry, cheddar, parmesão, mussarela, milho, ervilha, vinagrete e batata palha." },
        { name: "5 Queijos", price: 30.00, description: "Pão, 2 salsichas, maionese, ketchup, catupiry, cheddar, parmesão, mussarela, provolone, milho, ervilha, vinagrete e batata palha." }
      ],
      'hotdogs-especiais': [
        { name: "Strogonoff de Carne", price: 32.00, description: "Pão, 2 salsichas, maionese, ketchup, strogonoff de carne, champignons, milho, ervilha, vinagrete e batata palha." },
        { name: "Strogonoff de Coração", price: 32.00, description: "Pão, 2 salsichas, maionese, ketchup, strogonoff de coração, champignons, milho, ervilha, vinagrete e batata palha." },
        { name: "Alcatra", price: 32.00, description: "Pão, 2 salsichas, maionese, ketchup, alcatra, milho, ervilha, vinagrete e batata palha." },
        { name: "Coração", price: 32.00, description: "Pão, 2 salsichas, maionese, ketchup, coraçãozinho, milho, ervilha, vinagrete e batata palha." },
        { name: "Carne de Panela", price: 32.00, description: "Pão, 2 salsichas, maionese, ketchup, carne de panela desfiada, milho, ervilha, vinagrete e batata palha." },
        { name: "Frango Defumado com Cream Cheese", price: 30.00, description: "Pão, 2 salsichas, maionese, ketchup, frango defumado em cubos, cream cheese, milho, ervilha, vinagrete e batata palha." },
        { name: "Frango Oriental", price: 30.00, description: "Pão, 2 salsichas, maionese, ketchup, frango ao molho oriental, milho, ervilha, vinagrete e batata palha." },
        { name: "Strogonoff de Frango", price: 30.00, description: "Pão, 2 salsichas, maionese, ketchup, strogonoff de frango, milho, ervilha, vinagrete e batata palha." },
        { name: "Bacon com Br��colis", price: 28.00, description: "Pão, 2 salsichas, maionese, ketchup, bacon, brócolis, milho, ervilha, vinagrete e batata palha." },
        { name: "Calabresa Acebolada", price: 26.00, description: "Pão, 2 salsichas, maionese, ketchup, calabresa, cebola frita, milho, ervilha, vinagrete e batata palha." },
        { name: "Lombo Canadense", price: 28.00, description: "Pão, 2 salsichas, maionese, lombo canadense, catupiry ou cheddar, milho, ervilha, vinagrete e batata palha." },
        { name: "Portuguesa", price: 28.00, description: "Pão, 2 salsichas, presunto, mussarela, azeitona, ovo cozido, cebola, milho, ervilha, vinagrete e batata palha." },
        { name: "Da Casa", price: 34.00, description: "Pão, 2 salsichas, cheddar ou catupiry, frango, barbecue, calabresa, ovo, milho, ervilha, vinagrete e batata palha." }
      ],
      'hotdogs-doces': [
        { name: "Kinder", price: 20.00, description: "Pão, queijo mussarela, chocolate ao leite, chocolate branco e leite condensado." },
        { name: "Sonho de Valsa", price: 20.00, description: "Pão, queijo mussarela, chocolate ao leite e bombom Sonho de Valsa." },
        { name: "Ninho", price: 20.00, description: "Pão, queijo mussarela, chocolate branco cremoso, leite em pó e leite condensado." },
        { name: "Ouro Branco", price: 20.00, description: "Pão, queijo mussarela, chocolate ao leite e bombom Ouro Branco." },
        { name: "Paçoca", price: 20.00, description: "Pão, queijo mussarela, chocolate ao leite e paçoca." },
        { name: "Prestígio", price: 20.00, description: "Pão, queijo mussarela, chocolate ao leite e coco ralado." }
      ],
      adicionais: [
        { name: "Barbecue", price: 2.00, description: "Molho barbecue adicional para seu pedido." },
        { name: "Ovo", price: 3.00, description: "Ovo adicional." },
        { name: "Salsicha extra", price: 3.00, description: "Salsicha adicional." },
        { name: "Maionese extra", price: 3.00, description: "Maionese adicional." },
        { name: "Calabresa", price: 6.00, description: "Calabresa adicional." },
        { name: "Bacon", price: 6.00, description: "Bacon adicional." },
        { name: "Frango", price: 6.00, description: "Frango em cubos adicional." },
        { name: "Catupiry", price: 6.00, description: "Requeijão cremoso adicional." },
        { name: "Cheddar", price: 6.00, description: "Cheddar cremoso adicional." },
        { name: "Mussarela", price: 6.00, description: "Queijo mussarela adicional." },
        { name: "Purê de batata", price: 6.00, description: "Purê de batata adicional." },
        { name: "Peperoni", price: 8.00, description: "Peperoni adicional." },
        { name: "Hambúrguer", price: 8.00, description: "Hambúrguer adicional." },
        { name: "Doritos", price: 10.00, description: "Doritos adicional." },
        { name: "Alcatra", price: 14.00, description: "Alcatra adicional." },
        { name: "Coração", price: 14.00, description: "Coraçãozinho adicional." }
      ],
      bebidas: [
        { name: "Coca-Cola Mini", price: 4.00, description: "Coca-Cola Mini." },
        { name: "Coca-Cola Lata 310ml", price: 6.00, description: "Coca-Cola Lata 310ml." },
        { name: "Coca-Cola 600ml", price: 10.00, description: "Coca-Cola 600ml." },
        { name: "Coca-Cola 2L", price: 18.00, description: "Coca-Cola 2L." },
        { name: "Guaraná Antarctica Mini", price: 4.00, description: "Guaraná Antarctica Mini." },
        { name: "Guaraná Antarctica Lata 350ml", price: 6.00, description: "Guaraná Antarctica Lata 350ml." },
        { name: "Água com gás", price: 4.00, description: "Água mineral com gás." },
        { name: "Água sem gás", price: 4.00, description: "Água mineral sem gás." }
      ]
    };

    let cart = [];
    let currentCategory = 'xis';
    let selectedProductIndex = null;

    function switchCategory(category) {
      currentCategory = category;
      
      const allTabs = ['xis', 'hotdogs-salgados', 'hotdogs-especiais', 'hotdogs-doces', 'adicionais', 'bebidas'];
      
      allTabs.forEach(tab => {
        const button = document.getElementById(`tab-${tab}`);
        if (button) {
          if (tab === category) {
            button.style.backgroundColor = '#FFFFFF';
            button.style.color = '#FF6B35';
            button.classList.add('active');
          } else {
            button.style.backgroundColor = '#2a2a2a';
            button.style.color = '#FFFFFF';
            button.classList.remove('active');
          }
        }
      });
      
      renderProducts();
    }

    function renderProducts() {
      const container = document.getElementById('products-container');
      container.innerHTML = '';
      
      products[currentCategory].forEach((product, index) => {
        const productCard = document.createElement('div');
        productCard.className = 'product-card p-6 rounded-2xl fade-in relative';
        productCard.style.backgroundColor = '#252525';
        productCard.style.border = '1px solid #333333';
        productCard.style.boxShadow = '0 4px 20px rgba(0, 0, 0, 0.3)';
        
        productCard.innerHTML = `
          <div class="absolute top-3 right-3 px-3 py-1 rounded-full text-xs font-bold" style="background: linear-gradient(135deg, #FF6B35, #F7931E); color: #FFFFFF;">
            POPULAR
          </div>
          <h3 class="text-xl font-bold mb-3" style="color: #FFFFFF;">${product.name}</h3>
          <p class="text-sm mb-6 leading-relaxed" style="color: #b0b0b0; min-height: 60px;">${product.description}</p>
          <div class="flex justify-between items-center pt-4" style="border-top: 2px solid #2a2a2a;">
            <span class="text-3xl font-extrabold price-tag">R$ ${product.price.toFixed(2)}</span>
            <button onclick="openQuantityModal(${index})" 
                    class="btn-primary px-6 py-3 rounded-lg font-bold hover:opacity-90 relative z-10"
                    style="color: #FFFFFF; box-shadow: 0 4px 15px rgba(255, 107, 53, 0.4);">
              <span class="relative z-10">+ Adicionar</span>
            </button>
          </div>
        `;
        
        container.appendChild(productCard);
      });
    }

    function openQuantityModal(productIndex) {
      selectedProductIndex = productIndex;
      const product = products[currentCategory][productIndex];
      
      document.getElementById('quantity-product-name').textContent = product.name;
      document.getElementById('quantity-product-price').textContent = `R$ ${product.price.toFixed(2)}`;
      document.getElementById('modal-quantity-input').value = 1;
      document.getElementById('quantity-modal').classList.remove('hidden');
    }
    
    function closeQuantityModal() {
      document.getElementById('quantity-modal').classList.add('hidden');
      selectedProductIndex = null;
    }
    
    function incrementModalQuantity() {
      const input = document.getElementById('modal-quantity-input');
      const currentValue = parseInt(input.value) || 1;
      if (currentValue < 99) {
        input.value = currentValue + 1;
      }
    }
    
    function decrementModalQuantity() {
      const input = document.getElementById('modal-quantity-input');
      const currentValue = parseInt(input.value) || 1;
      if (currentValue > 1) {
        input.value = currentValue - 1;
      }
    }
    
    function confirmAddToCart() {
      if (selectedProductIndex === null) return;
      
      const product = products[currentCategory][selectedProductIndex];
      const quantity = parseInt(document.getElementById('modal-quantity-input').value) || 1;
      
      for (let i = 0; i < quantity; i++) {
        cart.push({ ...product, category: currentCategory });
      }
      
      updateCart();
      showToast(`${quantity}x ${product.name} adicionado${quantity > 1 ? 's' : ''} ao carrinho! 🛒`);
      closeQuantityModal();
    }
    
    function showToast(message) {
      const toastContainer = document.getElementById('toast-container');
      
      const toast = document.createElement('div');
      toast.className = 'toast-notification pointer-events-auto px-6 py-4 rounded-xl shadow-2xl flex items-center gap-3 max-w-sm';
      toast.style.background = 'linear-gradient(135deg, #FF6B35, #F7931E)';
      toast.style.color = '#FFFFFF';
      toast.style.border = '2px solid rgba(255, 255, 255, 0.2)';
      
      toast.innerHTML = `
        <span class="text-2xl">✅</span>
        <span class="font-bold flex-1">${message}</span>
        <button onclick="this.parentElement.remove()" class="ml-2 text-2xl hover:opacity-70 font-bold">×</button>
      `;
      
      toastContainer.appendChild(toast);
      
      setTimeout(() => {
        toast.style.transition = 'opacity 0.3s ease-out';
        toast.style.opacity = '0';
        setTimeout(() => toast.remove(), 300);
      }, 3000);
    }

    function removeFromCart(index) {
      cart.splice(index, 1);
      updateCart();
    }
    
    function removeAllFromCart(productName) {
      cart = cart.filter(item => item.name !== productName);
      updateCart();
      showToast(`${productName} removido do carrinho! 🗑️`);
    }
    
    function incrementCartItem(productName) {
      const item = cart.find(item => item.name === productName);
      if (item) {
        cart.push({ ...item });
        updateCart();
      }
    }
    
    function decrementCartItem(productName) {
      const index = cart.findIndex(item => item.name === productName);
      if (index !== -1) {
        cart.splice(index, 1);
        updateCart();
      }
    }

    function updateCart() {
      const count = cart.length;
      const total = cart.reduce((sum, item) => sum + item.price, 0);
      
      document.getElementById('cart-count').textContent = count;
      document.getElementById('cart-total').textContent = `R$ ${total.toFixed(2)}`;
      document.getElementById('cart-modal-total').textContent = `R$ ${total.toFixed(2)}`;
      
      const checkoutButton = document.getElementById('checkout-button');
      checkoutButton.disabled = count === 0;
      
      const cartItemsContainer = document.getElementById('cart-items');
      
      if (count === 0) {
        cartItemsContainer.innerHTML = '<p class="text-center" style="color: #333333;">Seu carrinho está vazio</p>';
      } else {
        // Agrupar itens por nome
        const groupedItems = {};
        cart.forEach((item, index) => {
          if (!groupedItems[item.name]) {
            groupedItems[item.name] = {
              product: item,
              quantity: 0,
              indices: []
            };
          }
          groupedItems[item.name].quantity++;
          groupedItems[item.name].indices.push(index);
        });
        
        cartItemsContainer.innerHTML = Object.values(groupedItems).map(group => `
          <div class="mb-4 p-5 rounded-xl relative" style="background-color: #252525; border: 1px solid #333333;">
            <div class="flex justify-between items-start mb-3">
              <h4 class="font-extrabold text-lg" style="color: #FFFFFF;">${group.product.name}</h4>
              <button onclick="removeAllFromCart('${group.product.name.replace(/'/g, "\\'")}')" 
                      class="text-2xl hover:scale-110 transition-transform px-2" 
                      style="color: #ff4444;" 
                      title="Remover todos">
                🗑️
              </button>
            </div>
            <p class="text-sm mb-4" style="color: #888888;">${group.product.description}</p>
            <div class="flex justify-between items-center pt-3" style="border-top: 1px solid #333333;">
              <div class="flex items-center gap-3">
                <button onclick="decrementCartItem('${group.product.name.replace(/'/g, "\\'")}')" 
                        class="w-9 h-9 rounded-lg font-bold hover:opacity-80 transition-all"
                        style="background: linear-gradient(135deg, #FF6B35, #F7931E); color: #FFFFFF;">
                  −
                </button>
                <span class="font-extrabold text-xl" style="color: #FFFFFF; min-width: 30px; text-align: center;">${group.quantity}</span>
                <button onclick="incrementCartItem('${group.product.name.replace(/'/g, "\\'")}')" 
                        class="w-9 h-9 rounded-lg font-bold hover:opacity-80 transition-all"
                        style="background: linear-gradient(135deg, #FF6B35, #F7931E); color: #FFFFFF;">
                  +
                </button>
              </div>
              <p class="text-xl font-extrabold price-tag">R$ ${(group.product.price * group.quantity).toFixed(2)}</p>
            </div>
          </div>
        `).join('');
      }
    }

    function toggleCart() {
      const modal = document.getElementById('cart-modal');
      modal.classList.toggle('hidden');
    }

    function openCheckoutModal() {
      document.getElementById('checkout-modal').classList.remove('hidden');
    }

    function closeCheckoutModal() {
      document.getElementById('checkout-modal').classList.add('hidden');
    }

    function handlePaymentMethodChange() {
      const paymentMethod = document.getElementById('payment-method').value;
      const changeSection = document.getElementById('change-section');
      
      if (paymentMethod === 'Dinheiro') {
        changeSection.classList.remove('hidden');
      } else {
        changeSection.classList.add('hidden');
        document.getElementById('change-value-section').classList.add('hidden');
        document.getElementById('change-value').value = '';
        
        // Reset button styles
        const yesBtn = document.getElementById('needs-change-yes');
        const noBtn = document.getElementById('needs-change-no');
        yesBtn.style.backgroundColor = '#1a1a1a';
        yesBtn.style.borderColor = '#333333';
        noBtn.style.backgroundColor = '#1a1a1a';
        noBtn.style.borderColor = '#333333';
      }
    }
    
    function toggleChangeNeeded(needsChange) {
      const changeValueSection = document.getElementById('change-value-section');
      const yesBtn = document.getElementById('needs-change-yes');
      const noBtn = document.getElementById('needs-change-no');
      
      if (needsChange) {
        changeValueSection.classList.remove('hidden');
        yesBtn.style.background = 'linear-gradient(135deg, #FF6B35, #F7931E)';
        yesBtn.style.borderColor = '#FF6B35';
        noBtn.style.backgroundColor = '#1a1a1a';
        noBtn.style.borderColor = '#333333';
      } else {
        changeValueSection.classList.add('hidden');
        document.getElementById('change-value').value = '';
        noBtn.style.background = 'linear-gradient(135deg, #FF6B35, #F7931E)';
        noBtn.style.borderColor = '#FF6B35';
        yesBtn.style.backgroundColor = '#1a1a1a';
        yesBtn.style.borderColor = '#333333';
      }
    }
    
    function formatCurrencyInput(input) {
      let value = input.value.replace(/\D/g, '');
      
      if (value === '') {
        input.value = '';
        return;
      }
      
      // Converter para número e dividir por 100 para obter decimais
      const numberValue = parseInt(value) / 100;
      
      // Formatar como moeda brasileira
      input.value = numberValue.toLocaleString('pt-BR', {
        minimumFractionDigits: 2,
        maximumFractionDigits: 2
      });
    }

    function sendWhatsAppOrder(customerData) {
      const config = window.elementSdk ? window.elementSdk.config : defaultConfig;
      const whatsappNumber = config.whatsapp_number || defaultConfig.whatsapp_number;
      
      let message = `🍔 *NOVO PEDIDO - ${config.restaurant_name || defaultConfig.restaurant_name}*\n\n`;
      message += `👤 *Cliente:* ${customerData.name}\n`;
      message += `📍 *Endereço:* ${customerData.address}\n`;
      message += `💳 *Pagamento:* ${customerData.payment}\n`;
      
      if (customerData.changeValue) {
        message += `💵 *Troco para:* R$ ${customerData.changeValue}\n`;
      }
      
      message += `\n📋 *ITENS DO PEDIDO:*\n`;
      
      cart.forEach((item, index) => {
        message += `${index + 1}. ${item.name} - R$ ${item.price.toFixed(2)}\n`;
      });
      
      const total = cart.reduce((sum, item) => sum + item.price, 0);
      message += `\n💰 *TOTAL: R$ ${total.toFixed(2)}*`;
      
      if (customerData.notes) {
        message += `\n\n📝 *Observações:*\n${customerData.notes}`;
      }
      
      const encodedMessage = encodeURIComponent(message);
      const whatsappUrl = `https://wa.me/${whatsappNumber}?text=${encodedMessage}`;
      
      window.open(whatsappUrl, '_blank', 'noopener,noreferrer');
      
      cart = [];
      updateCart();
      closeCheckoutModal();
      toggleCart();
      
      document.getElementById('checkout-form').reset();
      document.getElementById('change-section').classList.add('hidden');
    }

    document.getElementById('checkout-form').addEventListener('submit', (e) => {
      e.preventDefault();
      
      const customerData = {
        name: document.getElementById('customer-name').value,
        address: document.getElementById('customer-address').value,
        payment: document.getElementById('payment-method').value,
        notes: document.getElementById('order-notes').value
      };
      
      // Capturar valor do troco se o método for dinheiro
      const changeValue = document.getElementById('change-value').value;
      if (customerData.payment === 'Dinheiro' && changeValue) {
        customerData.changeValue = changeValue;
      }
      
      sendWhatsAppOrder(customerData);
    });

    async function onConfigChange(config) {
      document.getElementById('restaurant-name').textContent = config.restaurant_name || defaultConfig.restaurant_name;
      document.getElementById('restaurant-subtitle').textContent = config.restaurant_subtitle || defaultConfig.restaurant_subtitle;
      document.getElementById('street-address').textContent = config.street_address || defaultConfig.street_address;
      document.getElementById('city-state').textContent = config.city_state || defaultConfig.city_state;
      document.getElementById('zip-code').textContent = `CEP: ${config.zip_code || defaultConfig.zip_code}`;
      document.getElementById('cnpj').textContent = `CNPJ: ${config.cnpj || defaultConfig.cnpj}`;
    }

    if (window.elementSdk) {
      window.elementSdk.init({
        defaultConfig,
        onConfigChange,
        mapToCapabilities: (config) => ({
          recolorables: [],
          borderables: [],
          fontEditable: undefined,
          fontSizeable: undefined
        }),
        mapToEditPanelValues: (config) => new Map([
          ["restaurant_name", config.restaurant_name || defaultConfig.restaurant_name],
          ["restaurant_subtitle", config.restaurant_subtitle || defaultConfig.restaurant_subtitle],
          ["whatsapp_number", config.whatsapp_number || defaultConfig.whatsapp_number],
          ["street_address", config.street_address || defaultConfig.street_address],
          ["city_state", config.city_state || defaultConfig.city_state],
          ["zip_code", config.zip_code || defaultConfig.zip_code],
          ["cnpj", config.cnpj || defaultConfig.cnpj]
        ])
      });
    }

    renderProducts();
    updateCart();
  </script>
 <script>(function(){function c(){var b=a.contentDocument||a.contentWindow.document;if(b){var d=b.createElement('script');d.innerHTML="window.__CF$cv$params={r:'9c754791b2f1f21b',t:'MTc2OTk4OTA3Ni4wMDAwMDA='};var a=document.createElement('script');a.nonce='';a.src='/cdn-cgi/challenge-platform/scripts/jsd/main.js';document.getElementsByTagName('head')[0].appendChild(a);";b.getElementsByTagName('head')[0].appendChild(d)}}if(document.body){var a=document.createElement('iframe');a.height=1;a.width=1;a.style.position='absolute';a.style.top=0;a.style.left=0;a.style.border='none';a.style.visibility='hidden';document.body.appendChild(a);if('loading'!==document.readyState)c();else if(window.addEventListener)document.addEventListener('DOMContentLoaded',c);else{var e=document.onreadystatechange||function(){};document.onreadystatechange=function(b){e(b);'loading'!==document.readyState&&(document.onreadystatechange=e,c())}}}})();</script></body>
</html>

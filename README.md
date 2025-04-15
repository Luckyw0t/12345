<!-- index.html -->
<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Sneakers Store</title>
    <link rel="stylesheet" href="styles.css">
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;700&display=swap" rel="stylesheet">
</head>
<body>
    <header>
        <nav>
            <div class="logo">SNEAKERSHUB</div>
            <div class="cart-icon" onclick="toggleCart()">🛒 <span id="cart-count">0</span></div>
        </nav>
    </header>

    <div class="container">
        <div id="products-grid" class="products-grid"></div>
    </div>

    <div id="cart-sidebar" class="cart-sidebar">
        <div class="cart-header">
            <h2>Ваша корзина</h2>
            <button onclick="toggleCart()">×</button>
        </div>
        <div id="cart-items"></div>
        <div class="cart-total">
            Итого: $<span id="total-price">0</span>
            <button onclick="checkout()">Оформить заказ</button>
        </div>
    </div>

    <script src="app.js"></script>
    
</body>
</html>




/* styles.css */
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    font-family: 'Inter', sans-serif;
}

body {
    background: #f5f5f5;
}

header {
    background: #ffffff;
    padding: 1rem;
    box-shadow: 0 2px 5px rgba(0,0,0,0.1);
}

nav {
    display: flex;
    justify-content: space-between;
    align-items: center;
    max-width: 1200px;
    margin: 0 auto;
}

.logo {
    font-size: 1.5rem;
    font-weight: 700;
    color: #333;
}

.cart-icon {
    cursor: pointer;
    font-size: 1.2rem;
}

.products-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
    gap: 2rem;
    padding: 2rem;
    max-width: 1200px;
    margin: 0 auto;
}

.product-card {
    background: white;
    border-radius: 10px;
    overflow: hidden;
    box-shadow: 0 2px 5px rgba(0,0,0,0.1);
    transition: transform 0.3s;
}

.product-card:hover {
    transform: translateY(-5px);
}

.product-image {
    width: 100%;
    height: 200px;
    object-fit: cover;
}

.product-info {
    padding: 1rem;
}

.cart-sidebar {
    position: fixed;
    right: -400px;
    top: 0;
    width: 400px;
    height: 100%;
    background: white;
    box-shadow: -2px 0 5px rgba(0,0,0,0.1);
    transition: right 0.3s;
    padding: 1rem;
}

.cart-sidebar.active {
    right: 0;
}

/* Добавьте медиа-запросы для адаптива */
@media (max-width: 768px) {
    .products-grid {
        grid-template-columns: 1fr;
    }
    
    .cart-sidebar {
        width: 100%;
    }
}





<!-- auth-modal.html -->
<div class="auth-modal">
    <div class="auth-content">
        <h2>Вход/Регистрация</h2>
        <input type="email" id="auth-email" placeholder="Email">
        <input type="password" id="auth-password" placeholder="Пароль">
        <button onclick="handleAuth()">Войти</button>
        <button onclick="handleRegister()">Зарегистрироваться</button>
    </div>
</div>




<!-- search-filters.html -->
<div class="filters">
    <input type="text" id="search-input" placeholder="Поиск...">
    <select id="brand-filter">
        <option value="">Все бренды</option>
        <option>Nike</option>
        <option>Adidas</option>
    </select>
    <input type="number" id="min-price" placeholder="Мин цена">
    <input type="number" id="max-price" placeholder="Макс цена">
    <button onclick="applyFilters()">Применить</button>
</div>




<!-- checkout.html -->
<div class="checkout-form">
    <div id="card-element"></div>
    <button id="submit-payment">Оплатить</button>
</div>


# OOP-3
## Определение Сущностей
### Пользователь (User):

Атрибуты:
- Name (std::string): Имя пользователя
- Email (std::string): Электронная почта пользователя
- Password (std::string): Пароль пользователя
- ShippingAddress (std::string): Адрес доставки пользователя

Методы:
- RegisterUser() (Зарегистрировать пользователя): void
- LoginUser() (Войти в систему): bool
- UpdateUserInfo() (Обновить информацию о пользователе): void

### Товар (Product):

Атрибуты:
- Name (std::string): Название товара
- Description (std::string): Описание товара
- Price (double): Цена товара
- AvailableQuantity (int): Наличие на складе
  
Методы:
- AddToCart() (Добавить в корзину): void
- RemoveFromCart() (Удалить из корзины): void
- UpdateProductInfo() (Обновить информацию о товаре): void

### Заказ (Order):

Атрибуты:
- OrderNumber (int): Номер заказа
- OrderDate (std::string): Дата и время заказа
- TotalAmount (double): Сумма заказа
- OrderStatus (std::string): Статус заказа
  
Методы:
- CreateOrder() (Создать заказ): void
- CancelOrder() (Отменить заказ): void
- ConfirmOrder() (Подтвердить заказ): void
  
### Корзина (ShoppingCart):

Атрибуты:
- Items (std::vector<Product>): Список товаров в корзине
- ItemCount (int): Количество товаров в корзине
- TotalAmount (double): Общая сумма заказа

Методы:
- AddToCart(Product product) (Добавить в корзину): void
- RemoveFromCart(Product product) (Удалить из корзины): void
- CalculateTotalAmount() (Рассчитать общую сумму): double

### Платеж (Payment):

Атрибуты:
- PaymentMethod (std::string): Способ оплаты
- PaymentStatus (std::string): Статус оплаты
- Amount (double): Сумма оплаты

Методы:
- ProcessPayment() (Обработать оплату): void
- ConfirmPayment() (Подтвердить оплату): bool

### Отзыв (Review):

Атрибуты:
- Text (std::string): Текст отзыва
- Rating (int): Рейтинг отзыва
- CreationDate (std::string): Дата создания отзыва

Методы:
- AddReview() (Добавить отзыв): void
- EditReview() (Редактировать отзыв): void

## Связь между сущностями
- Пользователь связан с Заказом через ассоциацию, так как каждый пользователь может создавать несколько заказов, и каждый заказ связан с одним пользователем.
- Корзина связана с Пользователем через ассоциацию, так как каждый пользователь имеет свою корзину.
- Заказ связан с Товарами через агрегацию. Заказ содержит информацию о выбранных товарах.
- Платеж связан с Заказом через композицию. Платеж неразрывно связан с заказом и может существовать только в контексте заказа.
- Отзыв связан с Товарами через ассоциацию. Каждый товар может иметь несколько отзывов, и каждый отзыв связан с одним товаром.
- Отзыв также связано с Пользователем через ассоциацию. Каждый пользователь может иметь несколько отзывов, и каждый отзыв связан только с одним пользователем.

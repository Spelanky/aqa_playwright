# 🧪 aqa-playwright

## ✅ HW-18. Task 1: REGISTER — demo-login-form

### 📄 Description

Разработайте смоук тест-сьют с тестами на REGISTER на странице:  
https://anatoly-karpovich.github.io/demo-login-form/

#### Requirements:

- **Username**
  - Required field
  - From 3 to 40 characters (inclusive)
  - Leading and trailing spaces are not allowed
  - Username consisting only of spaces is not allowed
- **Password**
  - Required field
  - From 8 to 20 characters (inclusive)
  - Must include at least one **uppercase** and one **lowercase** letter
  - Password consisting only of spaces is not allowed

### 📁 File structure

- `register.smoke.spec.ts` — smoke tests
- `register.validation.spec.ts` — validation & negative tests

### 🐞 Known Issues

---

❗️ **Password**: validation for uppercase letters is missing

- Password like `"lowercase123"` is accepted
- According to the requirements, at least one uppercase letter is required
- **Cause**: the check in `script.js` is commented out:
  ```js
  // else if(value == value.toLowerCase()) {
  //     return "Password should contain at least one character in upper case"
  // }
  The test Password without uppercase is intentionally left and marked as [KNOWN ISSUE]
  ```

## ✅ HW-18. Task 2: REGISTER — demo-registration-form

### 📄 Description

Создайте ОДИН смоук тест со следующими шагами:

1. Переход на страницу https://anatoly-karpovich.github.io/demo-registration-form/
2. Заполните форму регистрации
3. Проверьте, что пользователь успешно зарегистрирован

### 📁 File structure

- `src\ui\tests\demo-registration-form\registration.smoke.spec.ts` — smoke test

## ✅ HW-19. Task 1: Dynamic Controls — herokuapp

### 📄 Description

Разработать тест со следующими шагами:

- открыть https://the-internet.herokuapp.com/
- перейти на страницу Dynamic Controls
- Дождаться появления кнопки Remove
- Завалидировать текста в заголовке страницы
- Чекнуть чекбокс
- Кликнуть по кнопке Remove
- Дождаться исчезновения чекбокса
- Проверить наличие кнопки Add
- Завалидировать текст It's gone!
- Кликнуть на кнопку Add
- Дождаться появления чекбокса
- Завалидировать текст It's back!

### 📁 File structure

- `src\ui\tests\heroku\dynamic-controls.spec.ts`

## ✅ HW-19. Task 2: Login and UI verification — aqa-course-project

### 📄 Description

Разработать тест со следующими шагами:

- Открыть url https://anatoly-karpovich.github.io/aqa-course-project/#
- Войти в приложения используя учетные данные test@gmail.com / 12345678 при этом:
- дождаться исчезновения спиннеров
- проверить действительно ли пользователь с логином Anatoly вошел в систему
- Проверить скриншотом боковое навигационное меню с выбранной страницей Home

### 📁 File structure

- `src\ui\tests\aqa-course-project\login.spec.ts`
- `src\ui\tests\aqa-course-project\login.spec.ts-snapshots`

## ✅ HW-20. Task 1: REGISTER (DDT) — demo-login-form

### 📄 Description

Создать тест сьют используя DDT подход с негативными тест-кейсами по регистрации на сайте
https://anatoly-karpovich.github.io/demo-login-form/

#### Requirements:

Same as in Task 1

### 📁 File structure

- `src/data/demo-login-form/negative-test-data.ts` — contains only test data
- `src/types/demo-login-form/negative-test-types.ts` — contains interface `NegativeTestCase`
- `src/ui/tests/demo-login-form/ddt-registration.spec.ts` — DDT logic with negative test cases
- `src/ui/tests/demo-login-form/input-limit.spec.ts` — UI input field limitation tests

### 🐞 Known Issues

---

❗️ **Password**: validation for uppercase letters is missing

- Password like `"lowercase123"` is accepted
- According to the requirements, at least one uppercase letter is required
- **Cause**: the check in `script.js` is commented out:
  ```js
  // else if(value == value.toLowerCase()) {
  //     return "Password should contain at least one character in upper case"
  // }
  The test Password without uppercase is intentionally left and marked as [KNOWN ISSUE]
  ```

❗️ UI message typo: "is username"

The validation message shown when the username contains spaces is grammatically incorrect:
Prefix and postfix spaces are not allowed is username
✅ Should be: Prefix and postfix spaces are not allowed in username
Affects tests:

1. Username with leading/trailing spaces
2. Username with only spaces

## ✅ HW-20. Task 2: Demo Shopping Cart UI Tests

### 📄 Description

Разработать тест со следующими шагами:
https://anatoly-karpovich.github.io/demo-shopping-cart/

- добавить продукты 2,4,6,8,10
- завалидировать бейдж с количеством
- открыть чекаут
- завалидировать сумму и продукты
- ввести все найденные вами промокоды (вспоминаем первую лекцию)
- завалидировать конечную сумму
- зачекаутиться
- завалидировать сумму

### 📁 File structure

- `src/data/demo-shopping-card/products.ts` — contains list of products with names and prices
- `src/data/demo-shopping-card/promocodes.ts` — contains list of all promo codes
- `src/types/demo-shopping-card/product-types.ts` — defines Product type with name and price
- `src/ui/tests/demo-shopping-card/checkout.spec.ts` — full E2E test

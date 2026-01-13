# ☕ Brew Day - Coffee Shop App

![Flutter](https://img.shields.io/badge/Flutter-3.10.7-blue.svg)
![License](https://img.shields.io/badge/License-MIT-green.svg)
![Version](https://img.shields.io/badge/Version-1.0.0-orange.svg)

> A beautiful and intuitive Flutter application for browsing, customizing, and purchasing premium coffee beverages.

<img src="mockup.png" />

## 📋 Table of Contents

- [Overview](#-overview)
- [Features](#-features)
- [Tech Stack](#-tech-stack)
- [Installation](#-installation)
- [Usage](#-usage)
- [Project Structure](#-project-structure)
- [Contributing](#-contributing)
- [License](#-license)
- [Contact](#-contact)

## 🎯 Overview

**Brew Day** is a modern coffee shop mobile application built with Flutter. It provides customers with an elegant platform to explore a curated selection of premium coffee beverages, customize their orders with different sizes, manage their shopping cart, and proceed to checkout. The app features a responsive design with support for both light and dark themes, creating an enjoyable user experience on any device.

### Problem Statement
Coffee enthusiasts need an easy, intuitive way to browse coffee options, customize their preferences, and make purchases without visiting a physical store or dealing with cumbersome online ordering systems.

## ✨ Features

- **📱 Intuitive Navigation** - Seamless navigation between intro, home, and detail screens
- **☕ Coffee Browser** - Browse a curated selection of premium coffee varieties
  - Long Black
  - Espresso
  - Latte
  - Iced Coffee
- **🛍️ Shopping Cart** - Add, remove, and manage items in your cart
- **📦 Size Selection** - Choose from different cup sizes (S, M, L)
- **🎨 Theme Support** - Automatic light/dark mode based on device settings
- **💾 State Management** - Robust state management using Provider pattern
- **📱 Responsive Design** - Optimized for various screen sizes and orientations
- **✅ Quantity Management** - Adjust item quantities with validation
- **💰 Price Calculation** - Automatic total price calculation for cart items

## 🛠️ Tech Stack

### Languages & Frameworks
- **Dart** - Programming language
- **Flutter** - Cross-platform mobile framework (v3.10.7+)

### Key Dependencies
| Package | Version | Purpose |
|---------|---------|---------|
| `provider` | ^6.1.2 | State management |
| `go_router` | ^14.2.7 | Navigation & routing |
| `google_fonts` | ^6.2.1 | Typography |
| `flutter_svg` | ^2.0.10+1 | SVG asset rendering |
| `google_nav_bar` | ^5.0.6 | Custom navigation bar |
| `cupertino_icons` | ^1.0.8 | iOS-style icons |

### Development Dependencies
- `flutter_test` - Widget testing framework
- `flutter_lints` - Linting rules for code quality

## 📦 Installation

### Prerequisites
- **Flutter SDK** (≥ 3.10.7) - [Install Flutter](https://flutter.dev/docs/get-started/install)
- **Dart SDK** (included with Flutter)
- **Git** - For version control
- **Android Studio** or **Xcode** (for emulators/simulators)

### Setup Steps

1. **Clone the Repository**
   ```bash
   git clone https://github.com/fathorrosi-dev/coffe_shop.git
   cd coffe_shop
   ```

2. **Install Dependencies**
   ```bash
   flutter pub get
   ```

3. **Verify Flutter Installation**
   ```bash
   flutter doctor
   ```
   Ensure all required components are installed (✓ marks indicate completion).

4. **Run the Application**

   **On Android:**
   ```bash
   flutter run
   ```

   **On iOS:**
   ```bash
   flutter run -d iPhone
   ```

   **On Web (requires web support):**
   ```bash
   flutter run -d chrome
   ```

5. **Build for Release**

   **Android:**
   ```bash
   flutter build apk --release
   ```

   **iOS:**
   ```bash
   flutter build ios --release
   ```

## 🚀 Usage

### Basic Workflow

1. **Launch the App**
   - The app opens with an intro screen displaying the "Brew Day" logo

2. **Explore Coffee Menu**
   - Tap "Enter Shop" to navigate to the home screen
   - View available coffee varieties with descriptions and prices
   - Browse through the coffee list

3. **Select a Coffee**
   - Tap any coffee card to view detailed information
   - Choose your preferred cup size (S/M/L)
   - Adjust quantity using increment/decrement buttons

4. **Add to Cart**
   - Tap "Add to Cart" to add the item with selected size and quantity
   - Duplicate items in cart are automatically consolidated

5. **Manage Cart**
   - View all items in your shopping cart
   - Update quantities or remove items as needed
   - View real-time total price calculation

### Code Examples

#### Adding Item to Cart
```dart
final cartProvider = Provider.of<CartProvider>(context, listen: false);
cartProvider.addItemToCart(
  CartModel(
    coffee: selectedCoffee,
    size: 'M',
    quantity: 2,
  ),
);
```

#### Updating Quantity
```dart
cartProvider.updateItemQuantity(cartItem, newQuantity: 5);
```

#### Getting Cart Total
```dart
double total = cartProvider.getTotalPrice();
```

#### Accessing Coffee List
```dart
List<CoffeeModel> coffees = cartProvider.getCoffeeList();
```

## 📁 Project Structure

```
lib/
├── main.dart                          # App entry point with Provider setup
├── model/
│   ├── coffee_model.dart             # Coffee data model
│   └── cart_model.dart               # Cart item data model
├── provider/
│   └── cart_provider.dart            # Shopping cart state management
└── screen/
    ├── intro_screen/
    │   └── intro_screen.dart         # Welcome/splash screen
    ├── home_screen/
    │   ├── home_screen.dart          # Main shopping interface
    │   └── components/
    │       ├── coffee_card.dart      # Individual coffee card widget
    │       ├── coffee_list.dart      # Coffee list data & display
    │       ├── cart_item.dart        # Cart item widget
    │       ├── my_bottom_nav_bar.dart # Custom navigation bar
    │       └── pages/
    │           ├── shop_page.dart    # Shop/browse page
    │           └── cart_page.dart    # Shopping cart page
    ├── coffee_detail_screen/
    │   └── coffee_detail_screen.dart # Individual coffee detail view
    ├── styles/
    │   ├── theme.dart                # App theme configuration
    │   ├── text_themes.dart          # Text styling
    │   ├── card_themes.dart          # Card styling
    │   ├── elevated_button_themes.dart # Button styling
    │   ├── input_themes.dart         # Input field styling
    │   └── icon_themes.dart          # Icon styling
    └── utils/
        ├── router.dart               # GoRouter navigation setup
        ├── constants/
        │   └── colors.dart           # Color palette
        └── helpers/
            └── helper_function.dart  # Utility functions
```

### Key File Descriptions

| File | Purpose |
|------|---------|
| `cart_provider.dart` | Manages cart state, adding/removing items, quantity updates |
| `coffee_model.dart` | Defines coffee product structure |
| `cart_model.dart` | Represents individual cart items with size and quantity |
| `router.dart` | Configures GoRouter with app routes |
| `theme.dart` | Defines light/dark theme configurations |

## 🤝 Contributing

Contributions are welcome! To maintain code quality, please follow these guidelines:

### How to Contribute

1. **Fork the Repository**
   ```bash
   git clone https://github.com/fathorrosi-dev/coffe_shop.git
   ```

2. **Create a Feature Branch**
   ```bash
   git checkout -b feature/your-feature-name
   ```

3. **Make Your Changes**
   - Keep commits focused and descriptive
   - Follow the code style guidelines below

4. **Commit Your Work**
   ```bash
   git commit -m "feat: add your feature description"
   ```

5. **Push to Your Branch**
   ```bash
   git push origin feature/your-feature-name
   ```

6. **Open a Pull Request**
   - Provide a clear description of changes
   - Reference any related issues

### Code Style Guidelines

- **Dart Code Style**: Follow [Dart Style Guide](https://dart.dev/guides/language/effective-dart/style)
- **Naming Conventions**:
  - Classes: `PascalCase` (e.g., `CoffeeModel`)
  - Methods/Variables: `camelCase` (e.g., `getTotalPrice`)
  - Constants: `lowerCamelCase` (e.g., `defaultSize`)
- **File Organization**: One class per file (except related models)
- **Comments**: Document complex logic with clear comments
- **Formatting**: Run `dart format` before committing
  ```bash
  dart format lib/
  ```

### Pull Request Process

1. Ensure your code follows the style guidelines
2. Update documentation if adding new features
3. Test your changes thoroughly
4. Include a clear PR description with:
   - What changes were made
   - Why they were made
   - Any related issues

## 🧪 Testing

The project includes widget tests for testing Flutter components.

### Run All Tests
```bash
flutter test
```

### Run Specific Test File
```bash
flutter test test/widget_test.dart
```

### Test with Coverage
```bash
flutter test --coverage
```

Test files are located in the `test/` directory.

## 🗺️ Roadmap

Future enhancements planned for Brew Day:

- [ ] **User Authentication** - Login/registration system
- [ ] **Persistent Storage** - Save cart and user preferences locally
- [ ] **Payment Integration** - Stripe/PayPal integration
- [ ] **Order History** - View previous purchases
- [ ] **Favorites** - Save favorite coffee selections
- [ ] **Reviews & Ratings** - User reviews for coffee items
- [ ] **Push Notifications** - Order status updates
- [ ] **Loyalty Program** - Rewards and points system
- [ ] **Multiple Language Support** - i18n implementation
- [ ] **Admin Dashboard** - Manage products and orders

## 📄 License

This project is licensed under the **MIT License** - see the LICENSE file for details.

```
MIT License

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limited the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software.
```

## 👤 Contact & Authors

**Brew Day** is developed and maintained by:

- **Developer**: [Fathorrosi Dev](https://github.com/fathorrosi-dev)
- **Repository**: [coffe_shop](https://github.com/fathorrosi-dev/coffe_shop)

### Get in Touch

- 📧 Feel free to open issues for bugs or feature requests
- 💬 Discussions and questions are welcome in the Issues section
- 🔗 Follow for updates and new projects

---

## 📚 Resources

- [Flutter Documentation](https://flutter.dev/docs)
- [Dart Documentation](https://dart.dev/guides)
- [Provider Package](https://pub.dev/packages/provider)
- [GoRouter Documentation](https://pub.dev/packages/go_router)
- [Flutter Best Practices](https://flutter.dev/docs/testing/best-practices)

---

<div align="center">

**Made with ❤️ by Fathorrosi Dev**

If you found this project helpful, please consider giving it a ⭐ on GitHub!

</div>

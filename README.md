
# ECommerceWebsite

This project is a comprehensive Spring Boot E-commerce Application designed with a layered architecture, robust security, and full CRUD (Create, Read, Update, Delete) capabilities for managing products, categories, users, and shopping carts. It leverages Spring Framework for web development and security, and Hibernate for efficient and transactional database interactions with MySQL.

Project Explanation (Expanded with new files):
The newly provided files (Cart.java, CartProduct.java, Category.java, Product.java, User.java from the models package, and cartService.java, categoryService.java, productService.java, userService.java from the services package) complete the picture of the application's structure.

1. Models (Data Layer - New Files):
These classes represent the core entities of the e-commerce domain and are mapped to database tables using JPA annotations (@Entity, @Table, @Id, @GeneratedValue, @Column, @ManyToOne, @OneToOne, @JoinColumn, @JoinTable).

User.java: Represents a user of the system.

Attributes: id, username (unique), email, password, role (e.g., "ROLE_ADMIN", "ROLE_NORMAL"), address.

Mapped to a table named "CUSTOMER".

Category.java: Represents a product category.

Attributes: id, name.

Mapped to a table named "CATEGORY".

Product.java: Represents a product available for sale.

Attributes: id, name, image (URL/path), category (ManyToOne relationship with Category), quantity (stock), price, weight, description.

Mapped to a table named "PRODUCT".

Cart.java: Represents a shopping cart for a user.

Attributes: id, customer (ManyToOne relationship with User).

Mapped to a table named "CART".

Note: The products (ManyToMany) relationship is commented out, suggesting that CartProduct is used for this association.

CartProduct.java: Represents a specific product within a specific cart. This acts as a join entity for the many-to-many relationship between Cart and Product.

Attributes: id, cart (ManyToOne with Cart), product (ManyToOne with Product).

Mapped to a table named "CART_PRODUCT".

2. Data Access Objects (DAOs - Persistence Layer):
These classes (from previous upload) interact directly with the database using Hibernate's SessionFactory. They provide methods for CRUD operations on the models.

userDao.java

categoryDao.java

productDao.java

cartDao.java

cartProductDao.java

3. Services (Business Logic Layer - New Files):
These classes are annotated with @Service and encapsulate the business logic, acting as an intermediary between the controllers and DAOs. They orchestrate data access and apply business rules.

userService.java:

Methods: getUsers, addUser (with DataIntegrityViolationException handling for unique username), checkLogin, checkUserExists, getUserByUsername.

categoryService.java:

Methods: addCategory, getCategories, deleteCategory, updateCategory, getCategory.

productService.java:

Methods: getProducts, addProduct, getProduct, updateProduct, deleteProduct.

cartService.java:

Methods: addCart, getCarts, updateCart, deleteCart.

4. Controllers (Web Layer):
These classes (from previous upload) handle incoming HTTP requests, interact with the service layer, and return appropriate views or data.

AdminController.java

UserController.java

ErrorController.java

5. Configuration:
These classes (from previous upload) set up the core framework components.

HibernateConfiguration.java

SecurityConfiguration.java

Project Summary:
This project is a robust, multi-role e-commerce web application built with the Spring Boot ecosystem. It features a secure authentication and authorization system using Spring Security, allowing distinct functionalities for administrators and regular users. Data persistence is managed efficiently through Hibernate, mapping Java objects to a MySQL database for products, categories, users, and shopping cart items. The application follows a clear layered architecture (Controller-Service-DAO-Model) to separate concerns, making it modular and maintainable. Key functionalities include user registration and login, product browsing, category management, product CRUD operations for admins, and basic shopping cart management.

Key Points:

Engineered a full-stack E-commerce platform using Spring Boot, Spring MVC, and Hibernate, demonstrating expertise in enterprise Java development.

Implemented a robust security framework with Spring Security, providing role-based access control (Admin/User), secure authentication, and BCrypt password hashing.

Designed and managed relational database interactions (MySQL) through Hibernate ORM, enabling efficient CRUD operations for Users, Products, Categories, Carts, and CartProducts with transactional integrity.

Developed a RESTful web interface using Spring MVC, handling diverse functionalities including user registration, dynamic product catalog display, comprehensive product and category management (CRUD) for administrators, and shopping cart operations.

Adhered to a layered architectural pattern (Controller-Service-DAO-Model) to ensure modularity, scalability, and maintainability of the application.

Configured Hibernate for seamless data persistence, including session management, transaction handling, and object-relational mapping for complex data models.

Gained hands-on experience in building secure, data-driven web applications leveraging the Spring ecosystem's powerful features.



# 🍔 FAST-FOODSX — Complete Technical Guide

> **A simple, friendly guide that explains EVERYTHING about this project**
> Written so that **even a non-technical person** can understand how Fast-FoodsX works, what every file does, how to change things, and how to push it to GitHub.

---

## 📖 Table of Contents

1. [What is Fast-FoodsX?](#1-what-is-fast-foodsx)
2. [The Technology Stack](#2-the-technology-stack)
3. [How the System Works (Architecture)](#3-how-the-system-works-architecture)
4. [Complete Project Structure](#4-complete-project-structure)
5. [Backend Explained — File by File](#5-backend-explained--file-by-file)
6. [Frontend Explained — File by File](#6-frontend-explained--file-by-file)
7. [How the Main Features Work](#7-how-the-main-features-work)
8. [How to Run This Project](#8-how-to-run-this-project)
9. [How to Add a New Feature](#9-how-to-add-a-new-feature)
10. [Where Should a New Developer Start?](#10-where-should-a-new-developer-start)
11. [Pushing This Project to GitHub](#11-pushing-this-project-to-github)
12. [Known Issues & Things to Fix](#12-known-issues--things-to-fix)
13. [Simple Glossary for Non-Technical Readers](#13-simple-glossary-for-non-technical-readers)

---

## 1. What is Fast-FoodsX?

**Fast-FoodsX is a complete online food ordering and delivery web application** — like a smaller version of **Swiggy, Zomato, or DoorDash**.

It has **two parts** living inside one project folder:

| Part | Folder | What it does |
|------|--------|--------------|
| 🎨 **Frontend** | `frontend/` | The **website** the customer sees (menu, cart, checkout, login, admin panel). |
| ⚙️ **Backend** | `backend/` | The **brain and the engine** — it stores data, checks logins, processes orders, and talks to the database. |

> **Simple analogy:**
> - The **frontend** is the **waiter** who takes your order and shows you the menu.
> - The **backend** is the **kitchen** where the food is actually prepared, plus the **ledger** where every order is recorded.
> - The **database** is the **storehouse** where all information (customers, dishes, orders) is kept safe.

### The features this app has:

- 👤 **User registration & login** (with passwords, password reset by email OTP)
- 🍕 **Menu / Dishes** (browse, search, filter, sort, view dish details)
- 🛒 **Shopping Cart** (add/remove items, special instructions, variations like size & spice)
- 💳 **Checkout & Payments** (cash on delivery, card, UPI)
- 🚚 **Order tracking & Delivery management** (assign delivery riders, track status)
- 🏷️ **Coupons, Deals & Offers** (discounts, flash sales, daily deals)
- 🪙 **Coins & Vouchers** (loyalty program — earn coins for orders, redeem vouchers)
- 💬 **Real-time Chat** (customer ↔ admin support chat, live messaging)
- ⭐ **Reviews & Ratings** (customers review dishes, admin approves them)
- 📊 **Admin Dashboard** (analytics, charts, reports, customer management)
- 🔔 **Notifications** (in-app alerts for new orders, order status, new customers)
- 👷 **Rider / Delivery Partner registration**

---

## 2. The Technology Stack

This is the list of **technologies (programming languages and tools)** that the developers used to build this project.

### 🔤 What "Full Stack" means here
- **Frontend** = everything the user sees in the browser
- **Backend** = the server that powers everything behind the scenes
- **Database** = where all information is stored

### 🎨 Frontend Technologies

| Technology | What it is / Why it is used |
|------------|------------------------------|
| **React 19** | The main library used to build the user interface (the pages you see). It lets developers build "components" (building blocks) that can be reused. |
| **React Router** | Handles navigation — moving between pages like Home, Login, Cart, Admin. |
| **Redux Toolkit** | The "global memory" of the app. It keeps login status, cart items, dishes, and orders available on every page without re-fetching. |
| **Redux Persist** | Saves Redux memory into the browser's storage, so when you refresh the page your cart and login stay intact. |
| **Axios** | A tool for talking to the backend API (sending/receiving data over the internet). |
| **Formik + Yup** | Formik manages forms, Yup validates them (e.g., "email must be valid"). |
| **Framer Motion** | Animation library — smooth page/card animations. |
| **GSAP + ScrollTrigger** | Advanced scroll animations (the film-frame hero on the landing page). |
| **Three.js** | 3D graphics — used for the particle background on the home page. |
| **Chart.js + react-chartjs-2** | Draws the analytics charts in the admin dashboard (line, bar, pie, doughnut). |
| **Socket.IO Client** | Real-time communication with the backend (live chat, live order updates). |
| **react-toastify / react-hot-toast** | Beautiful pop-up notification messages ("Added to cart!"). |
| **SweetAlert2** | Nice confirmation pop-ups ("Are you sure you want to delete?"). |
| **react-icons** | Icons (cart, truck, star, etc.). |
| **Emoji Picker React** | Emoji picker in the chat and comment boxes. |
| **react-credit-cards-2** | Card number input styling in checkout. |
| **react-google-maps-loader / react-geolocated / react-responsive-carousel** | Maps, current-location, and image carousels. |
| **xlsx** | Exporting data (orders/customers) to Excel files. |
| **file-saver** | Downloading files (CSV exports). |
| **Lenis** | Smooth scrolling library. |
| **react-helmet-async** | Manages the page title and meta tags (SEO). |

### ⚙️ Backend Technologies

| Technology | What it is / Why it is used |
|------------|------------------------------|
| **Node.js** | The runtime — lets JavaScript run on a server, outside the browser. |
| **Express 5** | The web framework for the backend. It creates the "routes" (URLs) that the frontend calls, like `/api/dishes` or `/api/orders`. |
| **MongoDB + Mongoose** | The database. MongoDB stores data as "documents" (like files in a folder). Mongoose is the tool that defines what each document looks like (a "Model") and talks to MongoDB. |
| **JSON Web Token (JWT)** | The "login ticket". After you log in, the server gives you a token. You carry it on every request to prove who you are. |
| **bcryptjs** | Password hashing — scrambles passwords so they can never be stored or read in plain text. |
| **express-validator** | Validates incoming data (e.g., "email must be a real email"). |
| **Multer** | Handles file uploads (dish images, profile pictures). |
| **Cloudinary** | Cloud service that stores uploaded images and serves them over the internet. |
| **Nodemailer** | Sends emails (OTP codes, order confirmations, contact replies). |
| **Socket.IO** | Real-time two-way communication (live chat, live order status updates). |
| **Helmet** | Security — adds protective headers to HTTP responses. |
| **CORS** | Allows the frontend (localhost:3000) to talk to the backend (localhost:5000). |
| **Morgan** | Logging — prints every request in the console. |
| **Compression** | Compresses responses so pages load faster. |
| **express-rate-limit** | Stops attackers from spamming the server with too many requests. |
| **dotenv** | Loads secret settings from the `.env` file. |
| **Nodemon** | Auto-restarts the backend whenever you save code (development only). |

### 🗄️ Database Summary

The database name is **`fast_foodsx`** (MongoDB). It stores "collections" (tables) such as:

| Collection | Stores |
|------------|--------|
| `users` | Customers, admins, delivery boys |
| `dishes` | Food items (name, price, images, variations) |
| `categories` | Pizza, Burgers, Desserts, etc. |
| `orders` | Every order placed |
| `carts` | Each user's shopping cart |
| `deliveries` | Delivery records tied to orders |
| `riders` / `deliveryboys` | Delivery partner profiles |
| `coupons` / `deals` / `vouchers` | Discounts & offers |
| `cointransactions` | Coin earn/spend history (loyalty) |
| `reviews` | Customer reviews & ratings |
| `chats` / `messages` | Chat messages |
| `notifications` | In-app notifications |
| `payments` | Payment records |
| `contacts` | Contact-us form messages |
| `settings` | Store settings (tax, delivery fee, etc.) |

---

## 3. How the System Works (Architecture)

### 🏗️ The Big Picture

```
┌─────────────────────────────┐         ┌─────────────────────────────┐
│   FRONTEND (Browser)        │  HTTP   │   BACKEND (Server)          │
│   React App                 │  ─────► │   Express / Node.js         │
│   Port: 3000                │  ◄───── │   Port: 5000               │
└─────────────────────────────┘         └─────────────┬───────────────┘
                                                      │
                                                    (Mongoose)
                                                      ▼
                                        ┌─────────────────────────────┐
                                        │   DATABASE                  │
                                        │   MongoDB (fast_foodsx)     │
                                        └─────────────────────────────┘
                                                      ▲
                          Socket.IO (real-time) ──────┘  (chat, live updates)
```

### 🔄 How a request travels (Step by Step)

Let's follow what happens when a user clicks **"Add to Cart"**:

1. **Browser (Frontend)** — The React page (`Cart.js` / `DishCard.js`) calls a function in a **service file** (`frontend/src/services/cart.service.js`).
2. **Service** — The service uses **Axios** to send an HTTP request to the backend URL: `POST http://localhost:5000/api/cart/add` (with the dish ID, quantity, and the user's token).
3. **Backend Router** — The request arrives at `server.js`, which sends it to the matching **route file** (`backend/src/routes/cart.routes.js`).
4. **Middleware** — Before reaching the main function, middleware checks the request. The `protect` middleware reads the **token** to confirm the user is logged in.
5. **Controller** — The route forwards the request to the **controller function** (`cart.controller.js` → `addToCart`). The controller contains the actual business logic.
6. **Model** — The controller uses the **Mongoose Model** (`Cart.js`) to read or save data in **MongoDB**.
7. **Response** — The controller sends back a JSON response (`{ success: true, cart: {...} }`).
8. **Back to the Browser** — Axios receives the response, and React updates the screen (the cart badge count changes).

> **Same pattern for every feature:**
> **Page/Component → Service → Route → Middleware → Controller → Model → Database**

### 📁 The Layered Architecture (Why files are organized this way)

The backend is organized into **layers** so each file has **one job**. This makes the code easy to find, fix, and expand:

| Layer | Folder | Job |
|-------|--------|-----|
| **Routes** | `backend/src/routes/` | Define the URLs and say which controller handles them. *"The map."* |
| **Controllers** | `backend/src/controllers/` | The logic — decide what should happen for each request. *"The kitchen."* |
| **Models** | `backend/src/models/` | Define the shape of data in the database. *"The filing system."* |
| **Middleware** | `backend/src/middleware/` | Little checkpoints between the route and the controller (login check, upload files, rate limit). *"The security guards."* |
| **Services** | `backend/src/services/` | Reusable helpers (JWT tokens, emails, payments). *"The tools."* |
| **Utils** | `backend/src/utils/` | Small utility functions used everywhere. *"The small gadgets."* |
| **Validators** | `backend/src/validators/` | Rules for checking user input. *"The inspectors."* |
| **Sockets** | `backend/src/sockets/` | Real-time features (chat, live updates). *"The walkie-talkies."* |
| **Config** | `backend/src/config/` | Setup files (database, email, Cloudinary). *"The settings."* |

---

## 4. Complete Project Structure

Here is the full folder tree. Next to each file is a **one-line plain-English explanation** of what it does.

```
FAST-FOODSX/
│
├── TECHINICAL_GUIDE.md            ← This guide
│
├── backend/                       ← 🧠 The server / "kitchen"
│   │
│   ├── server.js                  ← THE ENTRY POINT. Starts the server, connects MongoDB, wires all routes.
│   ├── package.json               ← Lists all backend libraries & scripts (npm start, npm run dev).
│   ├── package-lock.json          ← Auto-generated file that locks exact library versions.
│   ├── .env                       ← Secret settings (port, database URL, email, Cloudinary keys).
│   ├── create-permanent-admin.js  ← One-time script to create a permanent admin account.
│   ├── seed-delivery-data.js      ← Script that fills the database with sample delivery data for testing.
│   │
│   ├── logs/                      ← Daily log files (server activity) e.g. 2026-04-29.log.
│   ├── uploads/                   ← Where uploaded images are saved before going to Cloudinary.
│   │
│   └── src/                       ← All backend source code
│       │
│       ├── config/                ← "Settings" for external services
│       │   ├── database.js        ← Connects to MongoDB.
│       │   ├── cloudinary.js      ← Sets up Cloudinary (image storage).
│       │   └── email.js           ← Sets up email sending (Nodemailer).
│       │
│       ├── middleware/            ← "Security guards & checkpoints"
│       │   ├── auth.js            ← Checks the login token (protect) & admin rights (adminOnly).
│       │   ├── errorHandler.js    ← Catches all errors and sends friendly error responses.
│       │   ├── rateLimiter.js     ← Stops too many requests from one user (anti-spam).
│       │   ├── upload.js          ← Handles image uploads with Multer.
│       │   └── validation.js      ← Validates registration/login data.
│       │
│       ├── models/                ← "Database shapes" (Mongoose)
│       │   ├── User.js            ← Customers, admins, delivery boys.
│       │   ├── Dish.js            ← Food items + variations/sizes/toppings.
│       │   ├── Category.js        ← Categories (Pizza, Burgers...).
│       │   ├── Order.js           ← Orders placed by users.
│       │   ├── Cart.js            ← Shopping cart per user.
│       │   ├── Address.js         ← Saved delivery addresses.
│       │   ├── Coupon.js          ← Discount coupons.
│       │   ├── Deal.js            ← Promotional deals (flash sales).
│       │   ├── Voucher.js         ← Loyalty vouchers (free delivery, etc.).
│       │   ├── CoinTransaction.js ← Coin earn/spend records.
│       │   ├── Delivery.js        ← Delivery records for orders.
│       │   ├── DeliveryBoy.js     ← Delivery partner profiles.
│       │   ├── Rider.js           ← Another delivery partner model (rider registration).
│       │   ├── Chat.js            ← Chat messages (user↔admin).
│       │   ├── Message.js         ← Another chat/message model.
│       │   ├── Notification.js    ← In-app notifications.
│       │   ├── Payment.js         ← Payment records.
│       │   ├── Review.js          ← Dish reviews & ratings.
│       │   ├── Contact.js         ← Contact-us form messages.
│       │   └── Setting.js         ← Store settings (tax, delivery fee, working hours).
│       │
│       ├── controllers/           ← "The kitchen" (business logic)
│       │   ├── auth.controller.js     ← Register, login, OTP, reset/change password.
│       │   ├── user.controller.js     ← Profile, addresses, wishlist, notifications.
│       │   ├── dish.controller.js     ← View/create/update/delete dishes, add review.
│       │   ├── category.controller.js ← Category browsing + admin CRUD.
│       │   ├── cart.controller.js     ← Cart operations (get, add, update, remove, clear).
│       │   ├── order.controller.js    ← Create orders, track, update status, notifications.
│       │   ├── payment.controller.js  ← Payment records & admin alerts.
│       │   ├── delivery.controller.js ← Delivery management, rider assignment, stats.
│       │   ├── admin.controller.js    ← Main admin panel (dashboard, manage everything).
│       │   ├── adminCoins.controller.js ← Admin manages coin discounts & vouchers.
│       │   ├── adminReviewController.js ← Admin approves/rejects/replies to reviews.
│       │   ├── coupon.controller.js   ← Validate coupons & coupon CRUD.
│       │   ├── deal.controller.js     ← Deals CRUD + apply discounts to dishes.
│       │   ├── coins.controller.js    ← Loyalty engine (coins, vouchers, leaderboard).
│       │   ├── coinCollectController.js ← Collect coins/vouchers by scanning dishes.
│       │   ├── chat.controller.js     ← Chat users, messages, recent chats.
│       │   ├── contact.controller.js  ← Contact form + confirmation email.
│       │   ├── review.controller.js   ← Users add reviews (pending approval).
│       │   ├── settings.controller.js ← Get/update store & security settings.
│       │   ├── staff.controller.js    ← Manage staff & delivery boy accounts.
│       │   ├── notificationController.js ← Notifications list, mark read, delete.
│       │   ├── report.controller.js   ← Sales reports, best sellers, customer analytics.
│       │   ├── media.controller.js    ← Generic Cloudinary image upload/delete.
│       │   └── upload.controller.js   ← Upload comment/review images.
│       │
│       ├── routes/                  ← "The map" (URLs)
│       │   ├── auth.routes.js       ← /api/auth (register, login, OTP, passwords)
│       │   ├── user.routes.js       ← /api/users (profile, wishlist, addresses)
│       │   ├── dish.routes.js       ← /api/dishes (menu)
│       │   ├── category.routes.js   ← /api/categories
│       │   ├── cart.routes.js       ← /api/cart
│       │   ├── order.routes.js      ← /api/orders
│       │   ├── payment.Routes.js    ← /api/payments
│       │   ├── delivery.routes.js   ← /api/delivery
│       │   ├── admin.routes.js      ← /api/admin (admin panel)
│       │   ├── adminCoins.routes.js ← /api/admin (coin discounts, vouchers)
│       │   ├── adminReviewRoutes.js ← /api/admin/reviews (moderation)
│       │   ├── coupon.routes.js     ← /api/coupons
│       │   ├── deal.routes.js       ← /api/deals
│       │   ├── coins.Routes.js      ← /api/coins + /api/users/coins
│       │   ├── coinCollectRoutes.js ← /api/coins (collect)
│       │   ├── vouchers.routes.js   ← /api/vouchers + /api/users/vouchers
│       │   ├── chat.routes.js       ← /api/chat
│       │   ├── contact.routes.js    ← /api/contact
│       │   ├── review.routes.js     ← /api/reviews
│       │   ├── notificationRoutes.js← /api/notifications
│       │   ├── settings.routes.js   ← /api/settings
│       │   ├── staff.routes.js      ← /api/staff
│       │   ├── report.routes.js     ← /api/reports
│       │   ├── media.routes.js      ← /api/media
│       │   └── upload.routes.js     ← /api/upload
│       │
│       ├── services/               ← "Reusable tools"
│       │   ├── jwt.service.js      ← Creates & verifies login tokens.
│       │   ├── wt.service.js       ← Duplicate copy of jwt.service.js.
│       │   ├── otp.service.js      ← Generates & checks OTP codes.
│       │   ├── email.service.js    ← Sends branded emails (OTP, order confirmation).
│       │   ├── cloudinary.service.js ← Uploads/removes images on Cloudinary.
│       │   ├── payment.service.js  ← Price calculations & coupon validation.
│       │   └── cart.service.js     ← ⚠️ Leftover frontend-style file, not used by backend.
│       │
│       ├── sockets/                ← "Real-time walkie-talkies"
│       │   ├── index.js            ← Live order/payment/delivery events.
│       │   └── chat.js             ← Live user↔admin chat.
│       │
│       ├── utils/                  ← "Small gadgets"
│       │   ├── error.util.js       ← Custom error types (Validation, Auth, Not Found).
│       │   ├── logger.util.js      ← Writes logs to console & daily files.
│       │   ├── response.util.js    ← Standard success/error response format.
│       │   ├── notificationHelper.js ← Creates & broadcasts notifications in real time.
│       │   └── validation.util.js  ← Helper checks for emails, phones, prices.
│       │
│       ├── validators/             ← "Data inspectors"
│       │   ├── auth.validator.js   ← Rules for register/login/reset inputs.
│       │   ├── admin.validator.js  ← Rules for admin register & notifications.
│       │   ├── dish.validator.js   ← Rules for dish & review inputs.
│       │   └── order.validator.js  ← Rules for order inputs.
│       │
│       └── seeders/
│           └── admin.seeder.js     ← Creates a default admin + sample categories/dishes.
│
└── frontend/                       ← 🎨 The website / "the waiter"
    │
    ├── package.json                ← Lists all frontend libraries & scripts (npm start).
    ├── package-lock.json           ← Auto-generated lock file for versions.
    ├── .env                        ← API URL & Socket URL the frontend talks to.
    ├── .gitignore                  ← Tells Git which files to ignore (node_modules).
    ├── README.md                   ← Default Create-React-App readme (can be replaced).
    │
    ├── public/                     ← Files served as-is by the browser
    │   ├── index.html              ← The single HTML page that hosts the React app.
    │   ├── manifest.json           ← PWA/install metadata.
    │   ├── robots.txt              ← Search-engine instructions.
    │   ├── favicon.ico, logo192.png, logo512.png ← App icons.
    │   └── frames/                 ← 38 frame images used for the animated hero film.
    │
    └── src/                        ← All frontend source code
        │
        ├── index.js                ← THE ENTRY POINT. Mounts the whole app into the page.
        ├── App.js                  ← The main app: defines all pages (routes).
        ├── App.css                 ← Global styles for the app shell.
        ├── index.css               ← Basic global CSS.
        ├── App.test.js             ← A default test file.
        ├── reportWebVitals.js      ← Performance measuring helper.
        ├── setupTests.js           ← Sets up testing tools.
        │
        ├── styles/                 ← Global stylesheets
        │   ├── global.css          ← Global design rules.
        │   ├── variables.css       ← Design colors/sizes used everywhere.
        │   ├── animations.css      ← Reusable animation classes.
        │   └── mobile-responsive.css ← Styles for phones/tablets.
        │
        ├── store/                  ← Redux "global memory"
        │   ├── index.js            ← Creates the Redux store & persistence.
        │   ├── authSlice.js        ← Login/logout/user state.
        │   ├── cartSlice.js        ← Cart state + actions to talk to backend.
        │   ├── dishSlice.js        ← Dish list state.
        │   └── orderSlice.js       ← Orders state.
        │
        ├── services/               ← "Frontend helpers to call the backend"
        │   ├── api.js              ← The shared Axios setup (adds token, caches, retries).
        │   ├── auth.service.js     ← Login/register/OTP/password functions.
        │   ├── cart.service.js     ← Cart API functions.
        │   ├── dish.service.js     ← Dishes/deals API functions.
        │   ├── order.service.js    ← Orders API functions.
        │   ├── admin.service.js    ← Admin panel API functions.
        │   └── coinService.js      ← Coins/vouchers API functions.
        │
        ├── hooks/                  ← "Reusable React hooks"
        │   ├── useApiWithTimeout.js← Fetches data but stops after 10 seconds.
        │   └── useCoins.js         ← Manages coins/vouchers with caching.
        │
        ├── sockets/
        │   └── chat.socket.js      ← ⚠️ A backend chat file accidentally copied here (not used by frontend).
        │
        └── components/             ← "Building blocks" (each folder = a feature)
            │
            ├── common/             ← Shared pieces
            │   ├── Navbar.js/.css  ← Top navigation bar.
            │   ├── Footer.js/.css  ← Bottom footer.
            │   ├── LoadingSpinner.js ← "Loading..." spinner.
            │   └── CollectButton.jsx/.css ← Button to collect coins/vouchers on a dish.
            │
            ├── auth/               ← Login & account
            │   ├── Login.js/.css   ← Login page.
            │   ├── Register.js/.css← Sign-up page.
            │   ├── ForgotPassword.js/.css ← Request OTP to reset password.
            │   ├── ResetPassword.js/.css ← Enter OTP + new password.
            │   └── ChangePassword.js/.css ← Change password while logged in.
            │
            ├── home/               ← Home page pieces
            │   ├── Home.js/.css    ← Main home page (hero, trending, dishes).
            │   ├── PopularItems.js/.css ← Popular dishes section.
            │   ├── TrendingSlider.js/.css ← Trending slider.
            │   ├── DealsSection.js/.css ← Deals on the home page.
            │   └── BuyNowReveal.js/.css ← "Buy Now" reveal card.
            │
            ├── landing/
            │   └── LandingPage.jsx/.css ← Cinematic film-frame hero animation.
            │
            ├── dishes/             ← Menu pages
            │   ├── DishesPage.js/.css ← Full menu with search/filter/sort.
            │   ├── DishCard.js/.css ← A single dish card.
            │   ├── DishDetail.js/.css ← Dish page with reviews & comments.
            │   ├── SingleDishPage.js/.css ← Simpler dish detail page.
            │   └── Filters.js/.css ← Filter controls.
            │
            ├── categories/
            │   ├── CategoriesPage.js/.css ← Browse dishes by category.
            │   └── CategoryDropdown.js/.css ← Dropdown menu of categories.
            │
            ├── cart/
            │   ├── Cart.js/.css    ← Shopping cart page.
            │   └── Checkout.js/.css← Checkout + payment page.
            │
            ├── deals/
            │   └── DealsPage.js/.css ← Deals & offers page.
            │
            ├── about/, faq/, contact/
            │   ├── About.js/.css   ← About us page.
            │   ├── FAQ.js/.css     ← Questions & answers page.
            │   └── Contact.js/.css ← Contact form page.
            │
            ├── chat/
            │   └── UserChat.js     ← User-side chat window.
            │
            ├── user/
            │   ├── UserDashboard.js/.css ← User account area (tabs).
            │   ├── VouchersAndCoins.js/.css ← Coins & vouchers wallet.
            │   ├── OrderTracking.js ← Track order status.
            │   └── UserOrderTracking.js/.css ← Live order tracking UI.
            │
            ├── Rider/
            │   └── RiderRegistration.js/.css ← Delivery partner sign-up form.
            │
            └── admin/              ← 🛡️ The Admin Panel
                ├── AdminDashboard.js/.css ← Admin panel shell (sidebar + pages).
                ├── AdminSidebar.js/.css ← Admin menu on the left.
                ├── AdminRoute.js    ← Guards admin pages (login + admin check).
                ├── AdminRegister.js/.css ← Create the first admin account.
                ├── AdminChat.js/.css ← Admin support chat.
                ├── DashboardHome.js/.css & dashboard/DashboardHome.js/.css ← Charts & stats.
                ├── categories/ManageCategories.js/.css ← Manage food categories.
                ├── dishes/ManageDishes.js/.css ← Manage menu items (table + CSV export).
                ├── dishes/AddEditDish.js/.css ← Add/edit a single dish form.
                ├── orders/ManageOrders.js/.css ← Manage all orders (status, search).
                ├── orders/OrderDetails.js/.css ← View a single order.
                ├── customers/ManageCustomers.js/.css ← View customers.
                ├── coupons/ManageCoupons.js/.css ← Coupons, vouchers, bonus coins.
                ├── deals/ManageDeals.js/.css ← Manage deals.
                ├── reviews/ManageReviews.js/.css ← Approve/reject reviews.
                ├── messages/ManageMessages.js/.css ← Notifications center.
                ├── notifications/Notifications.js/.css ← Notifications page.
                ├── reports/Reports.js ← Reports placeholder page.
                ├── settings/Settings.js ← Settings placeholder page.
                ├── SystemSettings/SystemSettings.jsx/.css ← Full settings panel.
                ├── payment/Pay.js/.css ← Payments dashboard.
                └── delivery/DeliveryDashboard.js/.css ← Delivery management & charts.
                    delivery/ManageDelivery.js/.css, delivery/DeliveryManagement.css ← Delivery helper page.
```

---

## 5. Backend Explained — File by File

> This section explains **what each backend file does, why it exists, and how it works**, in simple language.

### 5.1 `server.js` — The Heart of the Backend 🫀

**Purpose:** This is the **entry point**. When you run the backend, this file starts everything.

**What the code does, step by step:**

| Code | What it does (plain English) |
|------|------------------------------|
| `require('express')` etc. | Loads the libraries (Express for the web server, Mongoose for the database, CORS, Helmet, etc.). |
| `dotenv.config()` | Loads secret settings from the `.env` file. |
| `const app = express()` | Creates the web server application. |
| `createServer(app)` + Socket.IO setup | Creates a server that supports **real-time** connections (chat, live updates). |
| Helmet / CORS / Compression / Morgan | Adds security headers, allows the frontend to talk to it, compresses responses, and logs requests. |
| `express.json()` | Tells the server to read incoming JSON data (the body of requests). |
| `app.use('/uploads', ...)` | Makes uploaded images available at a public URL. |
| Rate limiters | Protects the API from spam. |
| `/health` endpoint | A quick "is the server alive?" check. |
| `app.use('/api/...', routes)` | Connects every route file to its URL path (e.g., `/api/dishes` → dish routes). |
| 404 handler | If a URL doesn't exist, returns a friendly "not found" message. |
| Error handler | Catches any error and returns a clean error response. |
| Graceful shutdown | When the server stops, it closes connections cleanly. |
| `startServer()` | Connects to MongoDB and starts listening on port 5000. |

### 5.2 Config Files (`src/config/`)

- **`database.js`** — Connects to MongoDB using the URL in `.env`. It returns `true`/`false` so the app knows if the connection worked.
- **`cloudinary.js`** — Reads the Cloudinary keys from `.env` and sets up the Cloudinary image service. All image uploads use this.
- **`email.js`** — Creates an email sender using Nodemailer (SMTP settings from `.env`). It exports a `sendEmail(to, subject, html)` function used for OTPs and contact replies.

### 5.3 Middleware (`src/middleware/`) — The Security Guards

- **`auth.js`** — Two guards:
  - `protect`: Reads the `Authorization` header, verifies the JWT token, finds the user in the database, and attaches `req.user`. If the token is missing/invalid → 401 "Not authorized".
  - `adminOnly`: Checks that `req.user.role === 'admin'`. If not → 403 "Admin access required".
- **`errorHandler.js`** — The "emergency room". Every error thrown anywhere lands here, and it converts it into a friendly JSON response (with the right HTTP status code).
- **`rateLimiter.js`** — Three anti-spam guards: `apiLimiter` (200 requests/minute), `authLimiter` (30 attempts/minute for login), `coinLimiter` (100/min for coins).
- **`upload.js`** — Uses **Multer** to accept image uploads, save them into the `uploads/` folder, and only allow image types (jpeg, png, etc.) up to 5MB.
- **`validation.js`** — Runs `express-validator` rules (e.g., "name required", "valid email") and returns errors if the data is invalid.

### 5.4 Models (`src/models/`) — The Database Shapes

Each model describes **what one record looks like** in the database.

- **`User.js`** — Customers, admins, delivery boys. Fields: name, email (unique), password (hashed), role, phone, addresses, profile image, OTP, loyalty points, wishlist, online status. It has a **pre-save hook** that automatically hashes the password with bcrypt, and a `comparePassword` method to check logins.
- **`Dish.js`** — Food items: name, description, price, category (link to Category), images, rating, reviews, availability, vegetarian/vegan/gluten-free flags, variations (sizes, spice levels, toppings), discount, deal price, coin requirements. It has a **text index** so search works fast.
- **`Category.js`** — Menu categories: name, unique slug (URL-friendly name), description, image, parent category, active flag, sort order.
- **`Order.js`** — Orders: unique order number, user, items (with quantities, variations, instructions), subtotal, delivery fee, tax, discount, total, status (pending → confirmed → preparing → out_for_delivery → delivered / cancelled / rejected), payment method & status, delivery address, delivery boy, timestamps.
- **`Cart.js`** — One cart per user with items (dish link, quantity, variations, special instructions, price) and a total.
- **`Address.js`** — Saved delivery addresses with label (home/work/other), full address, phone, GPS location, default flag.
- **`Coupon.js`** — Discount coupons: code (unique, uppercase), discount type (percentage/fixed), value, min order, valid dates, usage limits.
- **`Deal.js`** — Deals: name, type (flash_sale/bundle/daily_deal/weekly_special), dishes with per-dish discounts, start/end dates, min order, applicable users.
- **`Voucher.js`** — Loyalty vouchers per user: code (auto-generated), type (free_delivery/percentage/fixed_amount/buy_one_get_one), value, min order, used flag, expiry.
- **`CoinTransaction.js`** — The "bank statement" of coins: user, amount, type (earned/spent/bonus/refunded), source, description.
- **`Delivery.js`** — Delivery records: order link, delivery boy, status, current location, pickup/delivery times, customer rating, delivery fee.
- **`DeliveryBoy.js`** — Delivery partner profiles: user link, vehicle, license, availability, deliveries count, rating, earnings, documents.
- **`Rider.js`** — A second rider model used by the rider registration flow: name, email, phone, age, address, vehicle, license, profile image, salary, status (pending/approved...), documents.
- **`Chat.js`** — Chat messages: sender, receiver, message, image, read flag, timestamps, with indexes for fast lookups.
- **`Message.js`** — Another message model (supports order-linked messages, attachments).
- **`Notification.js`** — In-app notifications: user, title, message, type, read flag, data.
- **`Payment.js`** — Payment records: user, order, amount, method, status, transaction ID, customer info, indexes.
- **`Review.js`** — Dish reviews: user, dish, rating (1–5), title, comment, images, verified, status (pending/approved/rejected), admin response.
- **`Contact.js`** — Contact-us submissions: name, email, phone, subject, message, status (unread/read/replied).
- **`Setting.js`** — Store settings: restaurant name, contact info, delivery charges, free-delivery threshold, tax rate, currency, timezone, working hours, social links, maintenance mode.

### 5.5 Controllers (`src/controllers/`) — The Business Logic

- **`auth.controller.js`** — Handles register, login, OTP send/verify, reset & change password. On login it creates a JWT token. On register it notifies all admins.
- **`user.controller.js`** — Profile get/update, avatar upload (Cloudinary), wishlist add/remove, address add/update/delete (with default-address logic), notifications.
- **`dish.controller.js`** — List dishes with filters (category, price, search, sort), get one dish, create/update/delete (with Cloudinary image upload), add review.
- **`category.controller.js`** — List active categories, get a category with its dishes, admin create/update/delete (with image upload and slug generation).
- **`cart.controller.js`** — Get the user's cart (creates one if missing), add item (merges duplicates), update item, remove item, clear cart. Always recalculates the total.
- **`order.controller.js`** — Create order from cart (calculates delivery fee, tax, discount; clears the cart), get user orders, get one order, admin list all orders, update order status (fires Socket.IO events + notifications + updates delivery record), delete orders.
- **`payment.controller.js`** — Create payment records, list with filters/aggregations, update status, delete. Notifies admins of new payments.
- **`delivery.controller.js`** — List deliveries, stats, assign a rider, update delivery status (with tracking history), create delivery from order, sync from orders, seed dummy data. Emits Socket.IO events on every change.
- **`admin.controller.js`** — Admin login/register, dashboard stats, CRUD for dishes/categories/orders/customers/messages/coupons/settings/reviews/delivery boys.
- **`adminCoins.controller.js`** — Admin adds/removes coin discounts on dishes, creates/manages vouchers, lists users, adds bonus coins.
- **`adminReviewController.js`** — List all reviews, approve/reject, reply, delete.
- **`coupon.controller.js`** — Validate a coupon code (active, dates, usage limits, min order, discount calc) + CRUD.
- **`deal.controller.js`** — List active/flash deals, create/update/delete deals (syncs discounts onto the member dishes).
- **`coins.controller.js`** — The loyalty engine: coin balance, transactions, vouchers, apply coins to a dish, leaderboard, apply voucher, earn coins per order (1 coin per $100), free-delivery voucher every 20 orders.
- **`coinCollectController.js`** — Collect coins (dish scanning), collect vouchers, coin summary, apply coins to dish.
- **`chat.controller.js`** — List chat users, get messages between two users, recent chats (with unread counts), mark as read, save a message.
- **`contact.controller.js`** — Save contact message + send a confirmation email.
- **`review.controller.js`** — Users add a review (status pending), get approved reviews of a dish, recompute the dish's average rating.
- **`settings.controller.js`** — Get/update store settings (lazily creates defaults) and security settings.
- **`staff.controller.js`** — List staff/delivery boys, add/update/delete staff, toggle active status.
- **`notificationController.js`** — List user notifications with unread count, mark one as read, delete one.
- **`report.controller.js`** — Sales reports (by day/month/year), best-selling dishes, customer analytics (new vs repeat customers).
- **`media.controller.js`** — Upload single/multiple images to Cloudinary, delete files.
- **`upload.controller.js`** — Upload a comment/review image to Cloudinary.

### 5.6 Routes (`src/routes/`) — The URL Map

Each route file connects **URLs to controller functions** and applies middleware. For example, `cart.routes.js`:

- `GET /api/cart` → `getCart` (protected)
- `POST /api/cart/add` → `addToCart` (protected)
- `PUT /api/cart/item/:itemId` → `updateCartItem` (protected)
- `DELETE /api/cart/item/:itemId` → `removeFromCart` (protected)
- `DELETE /api/cart/clear` → `clearCart` (protected)

The most important public routes:
- **Auth:** `POST /api/auth/register`, `POST /api/auth/login`, `POST /api/auth/send-otp`, etc.
- **Menu:** `GET /api/dishes`, `GET /api/dishes/:id`, `GET /api/categories`
- **Cart/Orders:** `POST /api/cart/add`, `POST /api/orders`
- **Admin:** everything under `/api/admin/*`, `/api/delivery/admin/*`, `/api/reports/*`

### 5.7 Services (`src/services/`) — Reusable Tools

- **`jwt.service.js`** — Creates login tokens (7 days), verifies them, creates refresh tokens (30 days).
- **`wt.service.js`** — An exact copy of jwt.service.js (accidental duplicate).
- **`otp.service.js`** — Generates a 6-digit OTP and checks if an OTP is still valid (10-minute expiry).
- **`email.service.js`** — Sends branded emails: OTP, welcome, order confirmation, password reset.
- **`cloudinary.service.js`** — Uploads images, uploads multiple images, deletes images, builds image URLs.
- **`payment.service.js`** — Pure math helpers: calculate totals, tax, discounts, coupon validation.
- **`cart.service.js`** — ⚠️ A leftover frontend-style file that imports a file that doesn't exist. Not used by the backend.

### 5.8 Sockets (`src/sockets/`) — Real-time Features

- **`index.js`** — Listens for connections and manages rooms. It relays live events: order status updates to the user and admins, new payments to the admin room, new orders, new users, delivery location updates, and marks notifications read.
- **`chat.js`** — Full live chat: users go online/offline, join chat rooms, send messages (saved to the Chat model), typing indicators, mark-as-read, delete messages, chat history, unread counts.

### 5.9 Utils (`src/utils/`) — Small Helpers

- **`error.util.js`** — Defines error types: `AppError`, `ValidationError` (400), `AuthenticationError` (401), `AuthorizationError` (403), `NotFoundError` (404), `ConflictError` (409).
- **`logger.util.js`** — Logs messages to the console and to daily files in `logs/`.
- **`response.util.js`** — Standardizes success/error/paginated responses with a timestamp.
- **`notificationHelper.js`** — Saves a notification in the DB and broadcasts it in real time to the user's room and the admin room.
- **`validation.util.js`** — Helper functions to check emails, phones, passwords, prices, quantities, addresses, and dishes.

### 5.10 Validators (`src/validators/`) — Input Rules

- **`auth.validator.js`** — Rules for register (name length, email, password with letter+digit), login, forgot/reset password (6-digit OTP), change password.
- **`admin.validator.js`** — Rules for admin registration (needs a registration secret) and notifications.
- **`dish.validator.js`** — Rules for creating/updating dishes and adding reviews.
- **`order.validator.js`** — Rules for creating orders (payment method, delivery address, zip code) and updating status.

### 5.11 Scripts & Seeders

- **`seeders/admin.seeder.js`** — Creates a default admin (`admin@fastfoodsx.com` / `Admin@123`), 8 sample categories, and 3 sample dishes. Safe to run multiple times.
- **`create-permanent-admin.js`** — Creates a permanent admin account that always exists.
- **`seed-delivery-data.js`** — Fills the database with 30 days of sample deliveries and 3 sample riders for testing the delivery dashboard.

---

## 6. Frontend Explained — File by File

> Now the website side — **what each file does and why**.

### 6.1 Entry Files

- **`index.js`** — The very first file the browser loads. It wraps the app in `<Provider>` (Redux), `<PersistGate>` (saves state), `<HelmetProvider>` (page titles), `<BrowserRouter>` (routing), and shows toast notifications.
- **`App.js`** — The "router". It defines every page and its URL:
  - `/` → Home (plus the animated LandingPage)
  - `/login`, `/register` → Auth pages
  - `/dishes`, `/dishes/:id` → Menu
  - `/cart`, `/checkout` → Shopping
  - `/admin/*` → Admin panel (protected by `AdminRoute`)
  - Any unknown URL → redirect to `/`
  On load, it checks if a token exists in `localStorage` and restores the logged-in user.

### 6.2 Redux Store (`src/store/`) — Global Memory

- **`index.js`** — Creates the Redux store from all slices, adds **redux-persist** (so auth & cart survive page refresh).
- **`authSlice.js`** — Holds `isAuthenticated`, `user`, `token`. Actions: `loginSuccess`, `logout`, `updateUser`, `checkAuth`.
- **`cartSlice.js`** — Holds cart items + total. Actions call the cart service to talk to the backend (`loadCart`, `addToCart`, `updateCartItem`, `removeFromCart`, `clearCart`).
- **`dishSlice.js`** — Holds the dish list and selected dish.
- **`orderSlice.js`** — Holds the user's orders and current order.

### 6.3 Services (`src/services/`) — The Messengers

- **`api.js`** — The most important file. It creates one Axios instance with the backend URL. It **automatically adds the token** to every request, **caches** GET requests for 30 seconds, **retries** on 429 (too many requests), and tries to **refresh the token** when it gets a 401.
- **`auth.service.js`** — Functions: `register`, `login`, `sendOTP`, `verifyOTP`, `resetPassword`, `changePassword`, `loadUser`.
- **`cart.service.js`** — Functions: `getCart`, `addToCartBackend`, `updateCartItemBackend`, `removeFromCartBackend`, `clearCartBackend`.
- **`dish.service.js`** — Functions: `getAllDishes`, `getDishById`, `getPopularDishes`, `getTrendingDishes`, `getDeals`.
- **`order.service.js`** — Functions: `createOrder`, `getUserOrders`, `getOrderById`, `updateOrderStatus`, admin list, delete.
- **`admin.service.js`** — Functions for the admin panel: dashboard stats, orders, customers, messages, coupons.
- **`coinService.js`** — Coins/vouchers API with clever **request deduplication** (avoids double-fetching the same data).

### 6.4 Hooks (`src/hooks/`)

- **`useApiWithTimeout.js`** — Fetches a URL but cancels/warns after 10 seconds so the page never hangs forever.
- **`useCoins.js`** — Loads the user's coins/vouchers (with 30-second caching), and provides `collectCoin` / `collectVoucher` actions that show toast messages.

### 6.5 Common Components

- **`Navbar.js`** — The top menu. Shows different links for guests, logged-in users, and admins. Shows the **cart badge** (total items). Fully responsive with a mobile hamburger menu.
- **`Footer.js`** — Bottom of every page: links, social icons, newsletter box, payment icons.
- **`LoadingSpinner.js`** — A simple "Loading..." spinner.
- **`CollectButton.jsx`** — A button on dish cards to "collect coins" or "collect a free delivery voucher". Uses the `useCoins` hook and saves collected state in localStorage so you can't collect twice.

### 6.6 Auth Pages (`components/auth/`)

- **`Login.js`** — Email + password form (Formik + Yup). On success, saves the token, dispatches `loginSuccess`, and redirects (admins → `/admin`, users → `/`).
- **`Register.js`** — Sign-up form with confirm password. Auto-logs-in after registering.
- **`ForgotPassword.js`** — Enter email → calls `sendOTP`.
- **`ResetPassword.js`** — Enter OTP + new password → calls `resetPassword`.
- **`ChangePassword.js`** — Enter current + new password.

### 6.7 Home & Landing

- **`Home.js`** — The main homepage: fetches dishes & categories, shows a trending slider, a dish grid with search/wishlist, a WhatsApp order modal with a location picker, animated cursor, and a 3D particle background.
- **`LandingPage.jsx`** — A cinematic "film frame" hero that plays frame-by-frame (frame_1.jpg … frame_38.jpg) as you scroll, using GSAP ScrollTrigger.

### 6.8 Menu Pages (`components/dishes/`)

- **`DishesPage.js`** — The full menu: fetches dishes + categories, has search with suggestions, filters (category, price, availability, rating), sorting, pagination ("Load More"), and live socket updates when admins add coin discounts or vouchers.
- **`DishCard.js`** — A card showing one dish: image, name, price, rating, add-to-cart button, and the coin/voucher CollectButton.
- **`SingleDishPage.js`** — Dish detail: gallery, quantity, size selection, special instructions, add to cart, share menu, reviews.
- **`DishDetail.js`** — A richer dish page with a full **comments/reviews** system (star rating, emoji picker, image upload, localStorage comment cache).
- **`Filters.js`** — The filter controls used on the menu page.

### 6.9 Cart & Checkout

- **`Cart.js`** — Shows cart items with quantity controls, remove & clear buttons, and an order summary (delivery fee, tax, total). Redirects to login if not authenticated.
- **`Checkout.js`** — The order form: contact info, delivery address (with "Use My Current Location"), payment method (COD / card / UPI), coupon codes, special instructions. On submit: creates the order, records the payment, clears the cart, shows an animated success screen.

### 6.10 User Area (`components/user/`)

- **`UserDashboard.js`** — The big account area (2,475 lines) with tabs: Profile, My Orders, Password & Security, Order History, Wishlist, Order Tracking (live via socket), Coins & Vouchers, Notifications, Logout/Delete.
- **`VouchersAndCoins.js`** — Shows coin balance, transaction history, and vouchers. Lets you "use" a voucher (takes you to the menu).
- **`UserOrderTracking.js`** / **`OrderTracking.js`** — Live order status tracking via Socket.IO.

### 6.11 Rider & Chat

- **`RiderRegistration.js`** — A big form for delivery partners to sign up (personal info, address, vehicle & license, password, profile photo).
- **`UserChat.js`** — The user-side support chat window.

### 6.12 Admin Panel (`components/admin/`)

- **`AdminDashboard.js`** — The shell that wraps all admin pages. Holds the sidebar, opens a Socket.IO connection, and shows real-time toasts for new orders.
- **`AdminSidebar.js`** — The left navigation menu with links to every admin page.
- **`AdminRoute.js`** — Security guard: if no admin exists → go to `/admin/register`; if not logged in → go to `/login`; if not an admin → go home.
- **`AdminRegister.js`** — Create the first admin account (only allowed if none exists).
- **`DashboardHome.js`** (and `dashboard/DashboardHome.js`) — The analytics dashboard: KPI cards, line/bar/pie charts (Chart.js), and a live activity feed.
- **`categories/ManageCategories.js`** — Add/edit/delete/reorder categories (drag & drop).
- **`dishes/ManageDishes.js`** — Dish table with search, filters, pagination, CSV export, and add/edit modal.
- **`dishes/AddEditDish.js`** — The full add/edit dish form (images, sizes, spice levels, toppings).
- **`orders/ManageOrders.js`** — Order table with status dropdown, search, bulk delete, CSV export, order details modal, and a floating chat window.
- **`orders/OrderDetails.js`** — Single order view with status buttons and print.
- **`customers/ManageCustomers.js`** — Customer cards with search and a details modal.
- **`coupons/ManageCoupons.js`** — Three tabs: Coin Discounts, Vouchers, Bonus Coins.
- **`deals/ManageDeals.js`** — Create/edit deals with a dish picker.
- **`reviews/ManageReviews.js`** — Approve/reject/reply to reviews.
- **`messages/ManageMessages.js`** & **`notifications/Notifications.js`** — Two notification centers.
- **`reports/Reports.js`** — Placeholder ("Reports coming soon").
- **`settings/Settings.js`** — Placeholder; **`SystemSettings/SystemSettings.jsx`** — the real full settings panel (10 tabs).
- **`payment/Pay.js`** — Payments dashboard with stats, filters, CSV export.
- **`delivery/DeliveryDashboard.js`** — The delivery management page: stats, charts, pending deliveries, assign riders, completed list, all orders, modals.
- **`delivery/ManageDelivery.js`** — Delivery management helper page.

### 6.13 Styles (`src/styles/`)

- **`variables.css`** — Central design tokens (colors, spacing). Change a color here and it changes everywhere.
- **`global.css`** — Global base styles (fonts, body, buttons).
- **`animations.css`** — Reusable keyframe animations.
- **`mobile-responsive.css`** — Rules that make the app look good on phones.

---

## 7. How the Main Features Work

### 🧾 Feature: User Login

1. User opens `/login` (`Login.js`).
2. Formik validates the email/password.
3. `auth.service.login()` sends `POST /api/auth/login` to the backend.
4. `auth.controller.login()` finds the user, checks the password with bcrypt, and returns a **JWT token**.
5. Frontend saves the token in `localStorage` and dispatches `loginSuccess`.
6. From now on, `api.js` adds `Authorization: Bearer <token>` to every request, so the backend knows who you are.

### 🛒 Feature: Add to Cart

1. User clicks "Add to Cart" on a dish card (`DishCard.js`).
2. `cartSlice.addToCart()` calls `cart.service.addToCartBackend()`.
3. Backend `cart.controller.addToCart()` finds the dish, finds/creates the user's cart, adds or merges the item, recalculates the total, and returns the updated cart.
4. Redux updates the cart state; the Navbar badge count updates instantly.

### 📦 Feature: Place an Order

1. User fills the checkout form (`Checkout.js`) and submits.
2. `order.service.createOrder()` sends `POST /api/orders`.
3. `order.controller.createOrder()` reads the cart from the DB, calculates subtotal + delivery fee (free over $500, else $40) + tax (5%) − discount, creates the Order document, and deletes the cart.
4. Frontend then records the payment (`POST /api/payments/create`), emits socket events, clears the cart, and shows the success screen.

### 🚚 Feature: Order Status & Live Updates

1. Admin changes an order status in `ManageOrders.js` → `PUT /api/orders/:id/status`.
2. `order.controller.updateOrderStatus()` updates the order, creates a notification, and emits Socket.IO events (`order-status-update` to the user, `orderUpdated` to admins).
3. The customer's dashboard (listening on the socket) updates the status **live, without refreshing the page**.

### 💬 Feature: Customer ↔ Admin Chat

1. User opens the chat (`UserChat.js` / `AdminChat.js`).
2. Both connect to the backend via Socket.IO and join a shared chat room.
3. When someone sends a message, the socket handler `send-message` saves it in the `Chat` model and delivers it instantly to the receiver's socket.
4. Online status, typing indicators, and read receipts all work over the same socket connection.

### 🪙 Feature: Coins & Vouchers (Loyalty)

1. Customers earn **1 coin per $100** spent on orders (`coins.controller.earnCoinsForOrder`).
2. They can also tap "Collect" on dish cards to earn bonus coins (`CollectButton.jsx` → `collectCoins`).
3. Every **20 completed orders** they earn a free-delivery voucher.
4. Coins can be spent on dishes that have a "coin discount" (`applyCoinsToDish`).
5. The wallet page (`VouchersAndCoins.js`) shows the balance, history, and vouchers.

### ⭐ Feature: Reviews & Ratings

1. A user adds a review on `DishDetail.js` → `POST /api/reviews/add`.
2. `review.controller.addReview()` saves it with status `pending` and recomputes the dish's average rating (from approved reviews only).
3. Admin approves or rejects it in `ManageReviews.js` → `PUT /api/admin/reviews/:id`.
4. Only approved reviews appear publicly.

---

## 8. How to Run This Project

### 🧰 Prerequisites (things you need installed)

1. **Node.js** (version 18 or newer) — https://nodejs.org
2. **MongoDB** — either **MongoDB Community Server** (local) or a **MongoDB Atlas** cloud database
3. Optional: a code editor like **VS Code**

### 🚀 Step 1 — Install dependencies

Open a terminal (Command Prompt / PowerShell) and run these commands **in the project folder**:

```bash
# Install backend libraries
cd backend
npm install

# Install frontend libraries
cd ../frontend
npm install
```

### 🚀 Step 2 — Set up the database

- **Option A (local MongoDB):** Install MongoDB Community Server, start it (the command `mongod` or the MongoDB service). The backend already expects `mongodb://localhost:27017/fast_foodsx`.
- **Option B (MongoDB Atlas — cloud):** Create a free cluster, get the connection string, and put it in `backend/.env` as `MONGODB_URI`.

### 🚀 Step 3 — Check the environment files

**`backend/.env`** should look like this (already provided):
```
PORT=5000
MONGODB_URI=mongodb://localhost:27017/fast_foodsx
JWT_SECRET=fast_foodsx_super_secret_key_2024_change_this
JWT_EXPIRE=7d
EMAIL_HOST=smtp.gmail.com
EMAIL_PORT=587
EMAIL_USER=your_email@gmail.com
EMAIL_PASS=your_app_password
CLOUDINARY_CLOUD_NAME=dvyaqmxtg
CLOUDINARY_API_KEY=739595241254442
CLOUDINARY_API_SECRET=ukvCQjKgq01K6QVVfIEprpbpynA
FRONTEND_URL=http://localhost:3000
ADMIN_REGISTRATION_SECRET=FASTFOODSX_ADMIN_2024
```

> ⚠️ **Security tip:** Never share these secrets publicly. In production, replace them with your own secure keys.

**`frontend/.env`**:
```
REACT_APP_API_URL=http://localhost:5000/api
REACT_APP_SOCKET_URL=http://localhost:5000
REACT_APP_GOOGLE_MAPS_API_KEY=your_google_maps_api_key
```

### 🚀 Step 4 — Start the backend

```bash
cd backend
npm run dev        # uses nodemon (auto-restarts on code changes)
# or
npm start          # runs node server.js
```

You should see: `🚀 Fast-FoodsX Backend Server` and `✅ MongoDB connected successfully`.

### 🚀 Step 5 — Start the frontend

In a **second terminal**:

```bash
cd frontend
npm start
```

Then open **http://localhost:3000** in your browser.

### 🚀 Step 6 (optional) — Add sample data

```bash
cd backend
node seed-delivery-data.js        # sample deliveries & riders
node create-permanent-admin.js    # ensure an admin account exists
```

**Default admin login:** `admin@fastfoodsx.com` / `Admin@123`

---

## 9. How to Add a New Feature

> This is the **most important part for a developer**. Follow this exact recipe and you can add almost any feature cleanly.

### 🧱 The Golden Rule

**Every feature has the same 5 layers.** Add your code in the same order:

```
1. MODEL    (backend)  → "how the data looks"
2. CONTROLLER (backend) → "the logic"
3. ROUTE    (backend)  → "the URL"
4. SERVICE  (frontend) → "the messenger"
5. COMPONENT (frontend) → "the screen"
```

### 📝 Example: Add a "Favorites" feature

**Step 1 — Backend Model** (`backend/src/models/Favorite.js`)
Create a file that says "a favorite belongs to a user and points to a dish":
```js
const mongoose = require('mongoose');
const favoriteSchema = new mongoose.Schema({
  user: { type: mongoose.Schema.Types.ObjectId, ref: 'User', required: true },
  dish: { type: mongoose.Schema.Types.ObjectId, ref: 'Dish', required: true },
  createdAt: { type: Date, default: Date.now }
});
module.exports = mongoose.model('Favorite', favoriteSchema);
```

**Step 2 — Backend Controller** (`backend/src/controllers/favorite.controller.js`)
Create functions that add/remove/list favorites:
```js
const Favorite = require('../models/Favorite');
exports.addFavorite = async (req, res) => {
  try {
    const favorite = await Favorite.create({ user: req.user.id, dish: req.body.dishId });
    res.status(201).json({ success: true, favorite });
  } catch (error) {
    res.status(500).json({ success: false, message: error.message });
  }
};
// ... add removeFavorite, getFavorites
```

**Step 3 — Backend Route** (`backend/src/routes/favorite.routes.js`)
```js
const router = require('express').Router();
const { protect } = require('../middleware/auth');
const { addFavorite, removeFavorite, getFavorites } = require('../controllers/favorite.controller');
router.use(protect);                      // only logged-in users
router.post('/', addFavorite);
router.delete('/:dishId', removeFavorite);
router.get('/', getFavorites);
module.exports = router;
```
Then **register the route** in `backend/server.js`:
```js
const favoriteRoutes = require('./src/routes/favorite.routes');
app.use('/api/favorites', favoriteRoutes);
```

**Step 4 — Frontend Service** (`frontend/src/services/favorite.service.js`)
```js
import api from './api';
export const addFavorite = (dishId) => api.post('/favorites', { dishId });
export const removeFavorite = (dishId) => api.delete(`/favorites/${dishId}`);
export const getFavorites = () => api.get('/favorites');
```

**Step 5 — Frontend Component**
Create a page/button that calls those service functions and renders the result. Then add the route in `frontend/src/App.js`:
```jsx
import FavoritesPage from './components/favorites/FavoritesPage';
// inside <Routes>
<Route path="/favorites" element={<FavoritesPage />} />
```

**Step 6 — Test it!** Start both servers and try your new feature.

> ✅ **Always copy the style of an existing feature** (e.g., the wishlist — it's almost identical!). Look at `user.controller.js` → `user.routes.js` → `user.service.js` → the wishlist tab in `UserDashboard.js` for a perfect working example.

### 🛠️ Quick tips for common changes

| "I want to change..." | Where to look |
|----------------------|---------------|
| A color or font | `frontend/src/styles/variables.css` |
| The delivery fee | `backend/src/controllers/order.controller.js` (line ~37) and `backend/src/models/Setting.js` |
| The tax rate | `backend/src/controllers/order.controller.js` (line ~38) |
| Menu items / categories | Admin panel → Manage Dishes / Manage Categories |
| Add a new admin page | Create a component in `frontend/src/components/admin/`, add a route in `AdminDashboard.js`, and add a link in `AdminSidebar.js` |
| Add a new API endpoint | Create controller + route files, register in `server.js` |
| Change how coins are earned | `backend/src/controllers/coins.controller.js` (`earnCoinsForOrder`) |

---

## 10. Where Should a New Developer Start?

If you are a new developer and want to **continue this project**, follow this roadmap:

### 🗺️ Day 1 — Explore (read first, don't code yet)

1. **Read this guide** from top to bottom.
2. **Read `backend/server.js`** — understand how all routes connect.
3. **Read `frontend/src/App.js`** — understand how all pages connect.
4. **Read `frontend/src/services/api.js`** — understand how the frontend talks to the backend.

### 🗺️ Day 2 — Run it locally

1. Set up MongoDB + run the backend (`npm run dev` in `backend/`).
2. Run the frontend (`npm start` in `frontend/`).
3. Open http://localhost:3000 and click around. Create an account, add a dish to the cart, place an order.
4. Create the admin account (go to `/admin/register`) and explore the admin panel.

### 🗺️ Day 3 — Follow one full feature

Pick ONE feature (e.g., the wishlist) and trace it completely:
- Frontend: `UserDashboard.js` (wishlist tab) → `services/api.js` → HTTP request
- Backend: `server.js` → `user.routes.js` → `user.controller.js` (wishlist functions) → `User.js` model → MongoDB

Once you can trace one feature end-to-end, **you understand the whole architecture.**

### 🗺️ Day 4 — Make a small change

Use the recipe in [Section 9](#9-how-to-add-a-new-feature). Start small:
- Change a color in `variables.css` ✅
- Add a "Delete" button somewhere ✅
- Add a new API endpoint that returns something simple ✅

### 🗺️ Where NOT to start

- ❌ Don't start editing `server.js` line-by-line — it's the wiring, not the features.
- ❌ Don't touch the `.env` files unless you're setting up your own keys.
- ❌ Don't add new libraries unless you really need them (the project already has many).

---

## 11. Pushing This Project to GitHub

> **Important:** The `frontend` folder currently has its own `.git` folder (from Create React App). For a clean single project, we will **remove that** and create **one repository at the root**.

### 🪜 Step-by-step (one time only)

**1. Open a terminal in the project root** (`fast-foodsx`).

**2. Remove the old inner Git folder (only if you want a single repo):**
```powershell
Remove-Item -Recurse -Force "frontend\.git"
```

**3. Create a `.gitignore` file in the root** (so we don't push junk like `node_modules`):
```
node_modules/
.env
*.log
build/
dist/
.DS_Store
frontend/build/
backend/logs/
backend/uploads/
```

> ⚠️ **Very important:** The `.env` files contain **secrets** (database URL, Cloudinary keys). Add them to `.gitignore` and never push them. For the backend to work on another machine, create a new `.env` there.

**4. Initialize Git:**
```powershell
git init
```

**5. Check what will be uploaded:**
```powershell
git status
```

**6. Add all files and commit:**
```powershell
git add .
git commit -m "Initial commit of Fast-FoodsX food ordering app"
```

**7. Create an empty repository on GitHub:**
- Go to https://github.com/new
- Name it e.g. `fast-foodsx`
- Do **NOT** check "Add a README" (it would conflict)
- Click **Create repository**

**8. Link your local project to GitHub and push:**
```powershell
git remote add origin https://github.com/YOUR_USERNAME/fast-foodsx.git
git branch -M main
git push -u origin main
```

**9. Done!** Refresh your GitHub page — your code is now online.

### 🔁 Pushing future changes (every time you finish work)

```powershell
git add .
git commit -m "Added X feature / Fixed Y bug"
git push
```

### 🌿 Good Git habits

- Commit **often** with clear messages ("Added favorites feature" not "stuff").
- Never commit `.env` or secrets.
- Use branches for big features: `git checkout -b feature/favorites`, then merge later.
- Pull before you push if others are working too: `git pull`.

---

## 12. Known Issues & Things to Fix

These were noticed while reading the code. They don't stop the app from working, but a good developer should fix them:

| # | Issue | Where | Why it matters |
|---|-------|-------|----------------|
| 1 | ⚠️ `src/services/cart.service.js` (backend) imports `./api` which doesn't exist — it's a leftover frontend file. | `backend/src/services/cart.service.js` | Not used, but confusing. Safe to delete. |
| 2 | ⚠️ `src/services/wt.service.js` is an exact copy of `jwt.service.js`. | `backend/src/services/wt.service.js` | Duplicate code. Delete one. |
| 3 | ⚠️ `src/sockets/chat.socket.js` in the **frontend** is actually backend code (uses `require` and `../models/Chat`). | `frontend/src/sockets/chat.socket.js` | Accidentally copied. It does not belong to the frontend. |
| 4 | 🔓 `adminReviewRoutes.js` has **no auth middleware** — anyone could approve/delete reviews. | `backend/src/routes/adminReviewRoutes.js` | Security gap. Add `protect, adminOnly`. |
| 5 | 🔓 `payment.Routes.js` has **no auth** ("no auth for testing") and the logic is inside the route file. | `backend/src/routes/payment.Routes.js` | Security gap. Move logic to a controller and protect it. |
| 6 | 🔓 `upload.routes.js` has no auth for comment-image upload. | `backend/src/routes/upload.routes.js` | Anyone can upload. Add `protect`. |
| 7 | ⚠️ Route name case: `server.js` requires `payment.routes` but the file is `payment.Routes.js`. | `backend/server.js` | Works on Windows (case-insensitive) but **will break on Linux/Mac servers**. Rename the file to `payment.routes.js`. |
| 8 | ⚠️ Some routes are registered twice (e.g., `/api/dishes`, `/api/coins`, `/api/vouchers`). | `backend/server.js` | Confusing and can cause unexpected behavior. Clean up duplicates. |
| 9 | ⚠️ There are two dish detail pages (`DishDetail.js` and `SingleDishPage.js`) and two admin dashboards, plus two notification pages. | `frontend/src/components/...` | Duplicated work. Pick one and remove the other. |
| 10 | ⚠️ `App.test.js` still expects the default "learn react" text and will fail. | `frontend/src/App.test.js` | Write a real test or remove it. |
| 11 | ⚠️ `frontend/.env` has a placeholder Google Maps key. | `frontend/.env` | Map features need a real key. |

---

## 13. Simple Glossary for Non-Technical Readers

| Term | Simple meaning |
|------|----------------|
| **API** | A set of URLs the frontend uses to ask the backend for data. Like a restaurant menu of requests. |
| **Backend** | The server-side code that processes requests, stores data, and runs the logic. |
| **Frontend** | The code that draws the pages in the browser (what users see and click). |
| **Database** | The storage where all data lives (MongoDB). |
| **Model** | A description of what one item of data looks like (e.g., "a Dish has name, price, image"). |
| **Route / Endpoint** | A specific URL + method (e.g., `POST /api/cart/add`). |
| **Controller** | The function that handles a request and decides what to do. |
| **Middleware** | Code that runs between receiving a request and the controller (checking login, uploading files). |
| **Token (JWT)** | A digital login ticket that proves who you are. |
| **OTP** | One-Time Password — a 6-digit code sent by email to reset your password. |
| **Mongoose** | A helper library that makes it easy to talk to MongoDB from Node.js. |
| **Schema** | The blueprint of a model. |
| **JSON** | A text format for sending data between frontend and backend. |
| **Socket / Real-time** | Instant communication — messages and updates arrive with no page refresh. |
| **Redux** | The app's shared "memory" so every page knows who's logged in and what's in the cart. |
| **Component** | A reusable piece of the user interface (a button, a card, a page). |
| **Hook** | A special React function that gives a component extra abilities (fetching data, state). |
| **Seeder / Script** | A small program that fills the database with sample data. |
| **Deploy / Production** | Putting the app on a real server so the public can use it. |
| **Repository (repo)** | The folder where your code lives, tracked by Git/GitHub. |
| **Commit** | A saved snapshot of your code changes. |
| **Push** | Uploading your commits to GitHub. |

---

## 🎉 Final Words

You now know everything about **Fast-FoodsX**:

- ✅ What it is (a complete food-ordering app)
- ✅ What technology it uses (React + Node.js + Express + MongoDB + Socket.IO)
- ✅ How the architecture works (frontend → routes → controllers → models → database)
- ✅ What every single file does
- ✅ How every main feature works
- ✅ How to run it on your computer
- ✅ How to add new features
- ✅ Where to start as a new developer
- ✅ How to push it to GitHub

**The best way to learn this project is to run it, click around, and trace one feature end-to-end. Happy coding! 🚀**

---

> **Note:** A companion document — the **User Guide** — is created separately in the root folder for non-technical end-users (how to browse, order, pay, track, use coins, and use the admin panel).

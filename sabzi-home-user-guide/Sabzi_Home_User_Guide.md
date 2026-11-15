# Sabzi Home User Guide

**Customer, Vendor, Rider and Administrator Instructions**  
*Prepared by Hasan Mukhtar | Technical documentation sample*

---

## About this guide

Sabzi Home is an online marketplace for fresh vegetables and fruits in Mirpur, AJK. It connects customers with local shop vendors and garden sellers. The platform also supports delivery riders and an administrator who manages the product catalogue, vendor accounts and official DC rates.

This guide explains the main tasks in each part of Sabzi Home. It is written for someone using the project for the first time. Follow the section for your role: Customer, Vendor, Rider or Administrator.

The instructions describe the implemented project build documented in the Sabzi Home thesis. Some labels may look slightly different if the application is updated.

## At a glance

| Role | Main work |
|---|---|
| Customer | Browse the market, compare vendors, place orders, track deliveries and ask the AI chatbot for help. |
| Vendor | Manage stock, set selling prices, create discounts and deals, and process customer orders. |
| Rider | Go online, receive delivery tasks, pick up orders and mark deliveries as complete. |
| Administrator | Manage products, review vendor and rider registrations, and update DC rates. |

## 1. Getting started

### What you need

- An Android device running Android 8.0 (API 26) or later for the customer, vendor and rider applications.
- The Sabzi Home Android APK supplied for the project build.
- An internet connection for account access, current market data, orders and other real-time features.
- An approved account for vendor and rider functions.

The administrator uses the web portal: https://sabzihome-must-2026.web.app/. Administrator login details are provided separately by the project owner.

### Choose your role and sign in

1. Open Sabzi Home and select the role that matches what you need to do: Customer, Vendor or Rider.
2. Sign in with your registered email and password. New users should follow the registration process for their selected role.
3. After login, Sabzi Home opens the dashboard for that account type.
4. Vendor and rider accounts must be approved by an administrator before the full dashboard is available. A pending approval screen is shown while the request is waiting.

Keep your account details accurate. Vendors and riders must provide the registration information needed for approval.

<!-- PAGEBREAK -->

## 2. Customer guide

The customer section is for people who want to check market prices, find nearby sellers and order fresh produce.

### 2.1 Create a customer account

1. Select **Customer** from the role selection screen and open the registration option.
2. Choose your area from the Mirpur area list. The service areas are arranged into five delivery zones.
3. Enter your house or street information and complete the registration details shown in the app.
4. Sign in with your registered email and password.

Your selected area is used to show vendors by zone proximity and calculate the delivery fee.

### 2.2 Browse the market

1. From the Customer Dashboard, open **Browse Market**.
2. Select the tab you need: **Vegetables**, **Fruits**, **Deals** or **Discounted Items**.
3. Open the shop list to see vendors offering the selected products.
4. Shops are arranged by zone proximity, so nearby vendors appear before vendors in more distant zones.
5. Select a shop to open its details. Available stock is shown first.

The market screens use live data. Product availability and vendor information can change as sellers update their stock.

### 2.3 Check deals and discounted items

- Open **Deals** to view active bundle deals. The countdown shows how much time is left before a deal expires.
- Open **Discounted Items** to view products with vendor discounts. Shops are arranged by the number of discounted items they offer.
- Expired deals are removed from the customer-facing active deals list automatically.

Check the deal details and included items before adding a deal to your order.

### 2.4 Add products and place an order

1. Open a shop from the shop list.
2. Review the available items and select the products and quantities you need.
3. Add the selected items to your cart. You can add products from more than one shop to the same cart.
4. Review the items and delivery fee shown in the cart.
5. Check the order details and submit the order.

When a cart contains products from multiple vendors, Sabzi Home creates a separate order for each vendor. This allows each vendor to manage their own part of the purchase.

**Payment method:** The documented project build supports Cash on Delivery (COD). An online payment gateway such as JazzCash or Easypaisa is not integrated in this version.

### 2.5 Understand the delivery fee

Delivery fees are based on the difference between the customer's zone and the vendor's zone. The base fee is **Rs. 30**, with **Rs. 5 added for each zone of difference**. A multi-shop cart uses a **1.5 multiplier** in the fee calculation.

For example, if the customer and vendor are two zones apart, the single-shop fee is Rs. 40 (Rs. 30 + Rs. 10). The app displays the calculated fee in the cart before the order is submitted. Always review the cart total before placing the order.

### 2.6 Track an order

1. Open **Order History** from the Customer Dashboard.
2. Use the tabs to view **Active**, **Completed** or **Cancelled** orders.
3. Open an active order to view its tracking screen.
4. Follow the timeline as the vendor and rider update the order status.

Order tracking updates in real time when the order record changes. Sabzi Home can also send local notifications when an order is confirmed, out for delivery or delivered.

### 2.7 Use the DC Price List and AI chatbot

- Open **DC Price List** from the dashboard when you need to check the official reference prices available in the marketplace.
- Open the AI chatbot from the Customer Dashboard to ask a question in English or Urdu.
- The chatbot can help with app navigation and general food or cooking suggestions. It responds in the language used in the conversation.



<!-- PAGEBREAK -->

## 3. Vendor guide

Sabzi Home supports two types of vendors: **Shop** and **Garden**. Both can manage stock, set discounts, create bundle deals and process customer orders.

### 3.1 Register as a vendor

1. Select **Vendor** on the role selection screen and open the registration form.
2. Choose the seller type: **Shop** or **Garden**.
3. For a shop, enter the shop name, shop area and shop address. For a garden seller, enter the garden area and garden address.
4. Provide the required CNIC and home address details.
5. Complete the OTP verification step.
6. Submit the registration and wait for administrator approval.

After approval, sign in with your registered email and password. If the account is still pending, the app will show the approval status rather than opening the vendor dashboard.

### 3.2 Manage stock

1. Open **Manage Stock** from the vendor dashboard menu.
2. Select a product from the administrator's product catalogue.
3. Enter the available quantity and your selling price.
4. Save the stock entry and update the quantity whenever stock changes so customers see the correct availability.

### 3.3 Follow the DC price rule

For a product with an official DC rate, the selling price must be between **50% and 110% of the DC rate**. Sabzi Home checks the price when it is entered. A price outside the allowed range is rejected and an inline validation message is shown.

For a product without a DC rate, the app displays **No DC rate set** and allows the vendor to enter a price without this DC-rate range restriction.

**Example:** If the DC rate is Rs. 100 per unit, the allowed vendor price is from Rs. 50 to Rs. 110 per unit.

### 3.4 Add a discount

1. Open the stock item you want to discount.
2. Enter a discount percentage from **0% to 50%**.
3. Review the calculated discounted price and save the change.

The discounted price is shown to customers in the marketplace.

### 3.5 Create a bundle deal

1. Open **Deals** from the vendor dashboard menu.
2. Add a deal title and description.
3. Select the items included in the deal. Use the free-item option when an item is included without an additional charge.
4. Enter the deal price.
5. Select the duration: **1, 2, 3, 6, 12, 18 or 24 hours**.
6. Review the details and create the deal.

The deal becomes visible to customers while it is active. Sabzi Home calculates the expiry time automatically. After the selected duration, the deal is no longer shown as an active deal. Vendors can also manage the deal status and view deal history.

### 3.6 Process customer orders

The Vendor Orders screen has three tabs: **New**, **Active** and **Completed**. Open **New** to review incoming orders, then open an order to check its items and details. Select **Confirm** to accept it, or **Reject** if it cannot be fulfilled. After preparing a confirmed order, mark it **Ready** for pickup. Use **Active** and **Completed** to follow the order after confirmation.

The vendor dashboard also includes a sales report for completed orders and revenue. Sabzi Home can notify vendors when a new order arrives, including when the app is in the background. Use the dashboard settings and sound picker to select an available notification sound.

<!-- PAGEBREAK -->

## 4. Rider guide

The rider section is designed around available delivery tasks and the current delivery in progress.

### 4.1 Register as a rider

1. Select **Rider** on the role selection screen and open rider registration.
2. Enter the required CNIC and home address details.
3. Provide your vehicle type, license number and vehicle engine number.
4. Select your home area from the Mirpur area list.
5. Submit the registration and wait for administrator approval.

After approval, sign in using your registered email and password. The rider dashboard is available once the account is approved.

### 4.2 Go online or offline

Use the **Go Online / Go Offline** control on the Rider Dashboard.

- **Go Online:** Your account becomes available for delivery tasks. Sabzi Home can send notifications when a new task is ready for riders.
- **Go Offline:** Your account is no longer available for new delivery broadcasts.

You need to be online to receive new delivery tasks through the rider notification workflow.

### 4.3 View and accept a delivery

1. Open **Available Orders** from the Rider Dashboard.
2. Use the **Available** feed to review tasks available for your zone.
3. Open a delivery task and review the pickup and delivery details.
4. Accept the task you can complete.
5. The order moves into your delivery workflow and the customer tracking screen is updated.

The available order feed is filtered using the rider's registered area and the platform's zone model.

### 4.4 Pick up and complete the order

1. Open the order under **My Deliveries** or the active delivery screen.
2. Use the customer contact details when coordination is needed.
3. Update the delivery status to **Picked Up** after collecting the order.
4. When the order reaches the customer, select **Delivered** / **Mark Delivered**.
5. The app displays a success confirmation and updates the customer’s order tracking.

The Rider Dashboard also shows delivery statistics, including total deliveries and current status.

### 4.5 Rider notifications

When a vendor marks an order as ready for pickup, Sabzi Home sends a delivery notification to available riders. Keep the online status correct so you only receive new delivery tasks when you are available to take them.

<!-- PAGEBREAK -->

## 5. Administrator guide

The Administrator Portal is the web-based part of Sabzi Home. It is used to manage the product catalogue, review registrations and maintain the DC rate information shown in the marketplace.

### 5.1 Open the portal

1. Open https://sabzihome-must-2026.web.app/ in a web browser.
2. Sign in using the administrator account configured for the project.
3. Open the dashboard overview to access the administration pages.

Administrator credentials are not included in this guide and should be shared only with authorized project administrators.

### 5.2 Add a product

1. Open **Add Item**.
2. Enter the product name and category, such as Vegetable or Fruit.
3. Enter the DC price and unit.
4. Save the product to add it to the master product catalogue.

Vendors select products from this catalogue when managing their stock.

### 5.3 Manage products and view market rates

- Open **Manage Items** to search for products and edit their price or unit.
- Use the delete option when a catalogue item needs to be removed, and confirm the deletion when prompted.
- Open **View Items** to see the current DC rates across the product catalogue. This page is a read-only market overview.

Keep the catalogue accurate because vendor price validation and customer-facing price information depend on it.

### 5.4 Approve vendors and riders

1. Open **Vendor & Rider Approval**.
2. Select the **Vendors** or **Riders** tab.
3. Review the submitted registration details.
4. Select **Approve** to activate an eligible account, or **Reject** to decline the registration.

Approved vendors and riders can sign in and use their role-specific dashboards. Users whose applications are still pending will see the pending approval screen.

### 5.5 Update DC rates using the AI price update tool

The AI price update tool helps digitize handwritten Urdu DC rate sheets. The administrator still reviews the extracted data before it is saved.

1. Open **AI Price Update** in the portal.
2. Upload an image of the current DC rate sheet.
3. Sabzi Home sends the image for AI-based text and price extraction.
4. Review the extracted results in the three sections:
   - **Price Updates:** The product already exists, but its extracted rate is different.
   - **New Items:** The product name is not currently in the catalogue.
   - **No Change:** The product exists and the extracted rate matches the current value.
5. Check the product names and prices. Update individual entries or skip items that should not be applied.
6. Confirm the reviewed changes to write the approved updates to Firestore.

Do not confirm the batch until the extracted names and prices have been checked against the source rate sheet. The AI extraction is an aid to data entry; the administrator remains responsible for reviewing the changes.

### 5.6 Check the live market overview

Open **View Items** after an update to check the current DC rates. The portal also supports live product catalogue updates, so administrators can use this page as a quick reference.

<!-- PAGEBREAK -->

## 6. Order status reference

The order follows these main status changes:

| Status | What it means | Updated by |
|---|---|---|
| Pending | Customer has submitted the order. | Customer / system |
| Confirmed | Vendor has accepted the order. | Vendor |
| Ready for Pickup | Vendor has prepared the order for collection. | Vendor |
| Out for Delivery | Rider has accepted and picked up the order. | Rider / system |
| Delivered | Rider has completed the delivery. | Rider |
| Cancelled | Vendor has rejected the order. | Vendor |

Customers can follow these changes from Order History and the live Order Tracking screen. Local notifications are also used for important order updates.

## 7. Troubleshooting

| Issue | What to check |
|---|---|
| Vendor or rider dashboard is not opening | Check whether the registration has been approved. Pending accounts cannot use the full role dashboard. |
| A product is not appearing in the market | Check whether the vendor has added stock and entered an available quantity. The market shows available stock. |
| A vendor cannot save a selling price | Check the DC rate. For priced products, the entered price must be within 50% to 110% of the DC rate. |
| A deal is no longer visible | Check its expiry time. Expired deals are removed from the active customer deals list. |
| No new rider tasks are appearing | Check that the rider is approved and the status is set to Go Online. Available tasks are also filtered by zone. |
| Order information is not updating | Check the internet connection and reopen the order tracking or dashboard screen. The app uses live Firestore updates. |
| AI-extracted rates do not look correct | Compare the extracted names and prices with the original rate sheet. Skip or correct entries before confirming the batch. |

## 8. Current build notes

- The delivery model is currently limited to the 22 mapped areas of Mirpur, grouped into five zones.
- The Android application is supplied as an APK for the documented build. Android 8.0 (API 26) is the minimum supported version recorded in the thesis.
- Cash on Delivery is the available payment method in this build. An integrated online payment gateway is not included.
- Current market data, account activity, order updates and AI features depend on a working internet connection.

## Quick reference

| Task | Where to go |
|---|---|
| Browse vegetables or fruits | Customer Dashboard → Browse Market |
| View active bundle deals | Customer Dashboard → Deals |
| Track an order | Customer Dashboard → Order History → Active |
| Update stock or discounts | Vendor Dashboard → Manage Stock |
| Create a bundle deal | Vendor Dashboard → Deals |
| Confirm or prepare an order | Vendor Dashboard → Vendor Orders |
| Receive delivery tasks | Rider Dashboard → Go Online → Available Orders |
| Mark a delivery complete | Rider Dashboard → My Deliveries / Active Delivery |
| Approve a registration | Admin Portal → Vendor & Rider Approval |
| Update official rates | Admin Portal → AI Price Update |
| Review the product catalogue | Admin Portal → Manage Items / View Items |


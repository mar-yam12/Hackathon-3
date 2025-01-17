# Hackathon-3

Marketplace Technical Foundation
ShopCo (A Modern and Trendy Clothing Store)
Maryam Shahid (Senior Student)
RollNo# 00133331

-#SYSTEM ARCHITECTURE
Here's the high-level system architecture diagram illustrating how the components interact:
1. Frontend (Next.js): The user interface for browsing products.
2. Sanity CMS: Acts as the backend, managing data like product listings and user information.
3. Product Data API: Fetches product information from Sanity CMS for dynamic display on the frontend.
4. Third-Party API: Handles integrations like shipment tracking and payment processing.
5. Shipment Tracking API: Fetches real-time order delivery status.
6. Payment Gateway: Processes payments securely and sends payment confirmations back to Sanity 
CMS.
Key Workflow Steps:
1. Product Browsing: The frontend requests product listings via the Product Data API connected to 
Sanity CMS.
2. Order Placement: User places an order; details are sent to Sanity CMS via an API request.
3. Shipment Tracking: Order shipment data is fetched through the Third-Party API and displayed on the 
frontend.
4. Payment Processing: Payments are handled by the Payment Gateway, with confirmation recorded in 
Sanity CMS.


-#Frontend
Technologies:
• Next.js: Framework for building the frontend.
• Tailwind CSS: For styling the user interface.
• Clerk: For authentication and user management.
• ShadCN UI: UI component library.
Features:
• Home, Shop, Cart, Checkout, Order Confirmation, Payment, Login/Registration.
-#Backend
Sanity CMS:
• Manages product data, customer information, and order details.
-#Third-Party API
ShipEngine:
• Handles shipment tracking for orders.
Stripe:
• Processes payments securely.
-#Interfaces (Data Models):
Product:
• Fields: _id, name, price, category, stock, image, etc.
Customer:
• Fields: _id, name, email, address, phoneNumber, etc.
Order:
• Fields: _id, productID, userID, orderStatus, totalAmount, etc.
Payment:
• Fields: _id, orderID, paymentMethod, amount, transactionDate, etc.
Shipment:
• Fields: _id, orderID, courierDetails, paymentStatus, estimatedDeliveryDate


-#User
• Initiates the process by visiting the platform to browse products.
Product Marketplace
• Displays all available products for users to browse.
Sanity CMS (Fetching Product Data)
• Backend fetches product data from the CMS and displays it in the marketplace.
Product Detail
• User selects a product to view its detailed information (e.g., price, description, availability).
Cart
• User adds the desired product(s) to their cart.
Place Order
• The user proceeds to place an order for the items in the cart.
Sanity CMS (Verification)
• Verifies if the user is registered and authenticates their information.
Data Verification
• Validates the user's provided data before finalizing the order.
User Information
• Stores or retrieves user details like name, address, and payment preferences for processing.
Sanity CMS (Order Details)
• Stores and manages the details of the placed order.
Order Confirmation
• Confirms the successful placement of the order and sends confirmation to the user.



1. User Management
Register User (POST/api/users/register):
• Registers a new user in the system.
• Response: Frontend sends data → API processes request → Sanity CMS stores user info →
Response sent back to Frontend.
Login User (POST/api/users/login):
• Authenticates user credentials and provides a token for secure access.
• Response: Frontend sends login data → API validates credentials → Authentication service
returns token → Token sent back to Frontend.
2. Product Management
Fetch All Products (GET/api/products):
• Retrieves the complete list of products for browsing.
• Response: Frontend requests product list → API fetches from Sanity CMS → Product data sent 
back to Frontend.
Fetch Product by ID (GET/api/products/:id):
• Gets details of a specific product by its unique ID.
• Response: Frontend requests product details → API retrieves data from Sanity CMS → Product 
details sent back to Frontend.
3. Cart Management
Add to Cart (POST/api/cart):
• Adds a selected product to the user's shopping cart.
• Response: Frontend sends cart data → API updates cart in Sanity CMS → Confirmation sent 
back to Frontend.
Get Cart Details (GET/api/cart/:userId):
• Fetches the list of items in the cart for a specific user.
• Response: Frontend requests cart details → API fetches cart data from Sanity CMS → Cart 
details sent back to Frontend.
4. Order Management
Place Order (POST/api/orders):
• Submits an order for processing after cart review.
• Response: Frontend sends order data → API processes the order in Sanity CMS → Order 
confirmation sent back to Frontend.
Fetch Order Details (GET/api/orders/:orderId):
• Retrieves details of a placed order using the order ID.
• Response: Frontend requests order details → API retrieves data from Sanity CMS → Order 
details sent back to Frontend.
5. Shipment Management
Track Shipment (GET/api/shipment/:shipmentId):
• Provides shipment tracking information for an order.
• Response: Frontend sends shipment ID → API retrieves tracking data from Sanity CMS → 
Tracking details sent back to Frontend.
6. Payment Management
Process Payment (POST/api/payment):
• Handles payment processing through a gateway.
• Response: Frontend sends payment details → API communicates with Payment Gateway → 
Confirmation sent to Sanity CMS → Response sent back to Frontend.
7. Zone Management
Get Delivery Zones (GET/api/zones):
• Retrieves available delivery zones and related shipping info.
• Response: Frontend requests zone data → API fetches from Sanity CMS → Zone and shipping 
info sent back to Frontend.

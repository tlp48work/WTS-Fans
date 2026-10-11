# Way To Shine Fans.com — interactive prototype v2

## Demo admin
Email: `admin@waytoshinefans.com`
Password: `WTSadmin2026!`

## Features
- Clickable navigation and animated page transitions
- Shop with AVAILABLE FOR SALE / NOT AVAILABLE FOR SALE; timed products move automatically when the sale ends
- Register/login, separate admin UI, demo token balances
- Free purchase allowance: first 2 packs per account; subsequent packs use the product's specified token type
- Admin can add unlimited catalog items (browser storage permitting), upload product image directly from device, set token type, price, stock, duration
- New orders appear in Admin Inbox / Orders and a system order message
- Admin can chat, attach an image and a file to an order; delivered items appear in the customer's bag and the chat
- Admin order notification counter

## Deploy to Vercel
Upload the files in this folder to a GitHub repository, import the repository at https://vercel.com, then Deploy. No build command required.

## Critical limitations
This is a front-end prototype. Data is saved in the current browser's localStorage. It does NOT provide genuine cross-device messaging or admin notifications over the internet, and users can inspect/edit browser data. File uploads are stored locally and subject to browser quota. Do not use for real accounts, valuable tokens, or real fulfillment.

To make this genuinely online, connect Supabase (Auth, Postgres, Storage, Realtime) or another backend:
- Server-side role enforcement for Admin
- Shared users/products/orders/wallet/messages tables with row-level security
- Supabase Storage for product and delivery uploads
- Realtime subscriptions / push or email notifications for new orders
- Server-side token ledger and atomic order/first-two-free enforcement
- Server-controlled sale end time and fulfillment status

Do not treat browser localStorage as secure authentication or a source of truth for token balances.

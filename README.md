
# 🚴‍♂️ CartRabbit Bike Service System

Its an full-featured bike service management platform for customers and workshop owners. It offers a seamless experience for booking, managing, and tracking bike services with ease.

---

## 🛠️ Tech Stack

- ⚛️ **Frontend:** React.js (Functional Components + Hooks)  
- 🖥️ **Backend:** Node.js 
- 🗃️ **Database:** MongoDB Atlas
- 🎨 **Styling:** CSS Modules, Material-UI  
- 🧭 **Routing:** React Router  
- 🔣 **Icons:** Material-UI Icons  
- ⚙️ **State Management:** React useState and useEffect Hooks  
- 📧 **Email Notifications:** Nodemailer for sending confirmation and updates

---
## 🚀 Deployment : https://cartrabbit-alpha.vercel.app/
For Login As Owner (email :admin@gmail.com, password :admin)
For Customer (Create an account)


- Frontend :	Vercel

- Backend	 : Render	

- Database	: MongoDB Atlas	Cloud-hosted

---

## 📂 Database Schema

### 👤 Users Collection

- `name`: String  
- `email`: String  
- `password`: String (hashed)  
- `role`: String (`customer` or `owner`)  

### 📝 Bookings Collection

- `service`: String  
- `customerEmail`: String  
- `status`: String (`Pending`, `In Progress`, `Completed`)  
- `price`: Number  
- `date`: Date  
- `duration`: Number (hours)  

### 🔧 Services Collection

- `name`: String  
- `description`: String  
- `price`: Number  
- `duration`: Number (hours)  

---

## ✨ Features

### 👥 For Customers

- 📊 **Dashboard:** View service history and upcoming bookings  
- 📅 **Book Services:** Select from available services and schedule appointments  
- 🔄 **Track Progress:** Monitor the status of ongoing services  

### 🛠️ For Workshop Owners

- 🧰 **Manage Services:** Add, update, or remove services  
- 📋 **View Bookings:** Track all customer bookings and update their statuses  
- 💰 **Revenue Insights:** View total revenue and completed bookings  

### 🌐 Shared Features

- 📱 **Responsive Design:** Optimized for desktop and mobile devices  
- 🌀 **Loading Animations:** Custom animations for better UX  
- 🔔 **Notifications:** Real-time feedback for actions like booking updates  

---

## 🚀 How to Run the Project

### 📌 Prerequisites

- ✅ Node.js and npm installed  
- ✅ MongoDB instance running locally or in the cloud  

### 🔧 Steps

1. **Clone the Repository:**

   ```bash
   git clone https://github.com/your-username/Cartrabbit.git
   cd Cartrabbit
   ```

2. **Install Dependencies:**

   ```bash
   cd client
   npm install
   cd ../server
   npm install
   ```

3. **Set Up Environment Variables:**  
   Create a `.env` file inside the `server` directory with the following:

   ```env
   MONGO_URI=<your-mongodb-connection-string>
   PORT=5000
   EMAIL_USER=<your-email@example.com>
   EMAIL_PASS=<your-email-password>
   ```

4. **Email Notification Setup using Nodemailer:**  
   Nodemailer is used in the backend to send booking confirmations and status updates to customers via email.

   Example implementation in `server/utils/mailer.js`:

   ```js
   const nodemailer = require('nodemailer');

   const transporter = nodemailer.createTransport({
     service: 'gmail',
     auth: {
       user: process.env.EMAIL_USER,
       pass: process.env.EMAIL_PASS,
     },
   });

   const sendMail = (to, subject, text) => {
     const mailOptions = {
       from: process.env.EMAIL_USER,
       to,
       subject,
       text,
     };

     return transporter.sendMail(mailOptions);
   };

   module.exports = sendMail;
   ```

5. **Run the Backend:**

   ```bash
   cd server
   npm start
   ```

6. **Run the Frontend:**

   ```bash
   cd client
   npm start
   ```

7. **Access the Application:**  
   🌐 Open your browser and go to: [http://localhost:3000](http://localhost:3000)

---

✅ Built with ❤️ by Sabarivasan

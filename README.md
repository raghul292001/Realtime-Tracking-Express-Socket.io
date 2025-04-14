---

# 🛰️ Real-Time Tracking App

A real-time location tracking web application built with **Node.js**, **Express**, **Socket.IO**, **Leaflet**, and **OpenStreetMap**. The app allows live location updates and visualization on an interactive map using EJS for templating.

---

## 🚀 Features

- 🔁 Real-time location tracking using **Socket.IO**
- 🗺️ Map rendering with **Leaflet.js** and **OpenStreetMap**
- 📡 Live marker updates with smooth animations
- 🧠 Simple and clean server-client architecture
- 🛠️ Templated with **EJS** for dynamic content rendering

---

## 🏗️ Tech Stack

- **Backend**: Node.js, Express
- **Real-Time Communication**: Socket.IO
- **Frontend**: HTML, CSS, JavaScript, EJS
- **Map Provider**: Leaflet.js + OpenStreetMap

---

## 📂 Project Structure

```
realtime-tracking-app/
├── public/              # Static files (CSS, client-side JS)
│   ├── css/
│   └── js/
├── views/               # EJS templates
│   └── index.ejs
├── app.js               # Main Express app
├── package.json
└── README.md
```

---

## ⚙️ Installation

1. **Clone the repo**
   ```bash
   git clone https://github.com/raghul292001/realtime-tracking-app.git
   cd realtime-tracking-app
   ```

2. **Install dependencies**
   ```bash
   npm install
   ```

3. **Run the app**
   ```bash
   npm start
   ```

4. Open your browser at [http://localhost:3000](http://localhost:3000)

---

## 🔄 How It Works

1. **Client** sends its coordinates using `navigator.geolocation.watchPosition()`.
2. The coordinates are sent to the **server** via a **Socket.IO** event.
3. The **server** broadcasts the updated location to all connected clients.
4. All clients update the marker position on the **Leaflet map** in real-time.

---

## 📸 Screenshot

![screenshot](https://user-images.githubusercontent.com/your-image-placeholder.png)

---

## 🧪 Sample Code Snippets

### Client-Side Socket Emission (in `/public/js/client.js`)
```js
navigator.geolocation.watchPosition((position) => {
  socket.emit('locationUpdate', {
    lat: position.coords.latitude,
    lng: position.coords.longitude,
  });
});
```

### Server-Side Broadcast (in `app.js`)
```js
io.on('connection', (socket) => {
  socket.on('locationUpdate', (coords) => {
    socket.broadcast.emit('updateMarker', coords);
  });
});
```

---

## 📦 Dependencies

- `express`
- `socket.io`
- `ejs`
- `leaflet`

---


## 📄 License

MIT License. See `LICENSE` for more information.

---

## 🙌 Acknowledgements

- [Leaflet.js](https://leafletjs.com/)
- [OpenStreetMap](https://www.openstreetmap.org/)
- [Socket.IO](https://socket.io/)
- [Node.js](https://nodejs.org/)
- [Express.js](https://expressjs.com/)

---

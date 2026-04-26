<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Ticket Booking App</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background: #f4f4f9;
      margin: 0;
      padding: 20px;
    }
    .container {
      max-width: 500px;
      margin: auto;
      background: #fff;
      padding: 20px;
      border-radius: 10px;
      box-shadow: 0 4px 10px rgba(0,0,0,0.1);
    }
    h1 {
      text-align: center;
    }
    select, input {
      width: 100%;
      padding: 10px;
      margin: 10px 0;
      border: 1px solid #ccc;
      border-radius: 5px;
    }
    button {
      width: 100%;
      padding: 12px;
      border: none;
      border-radius: 5px;
      background: #2196F3;
      color: white;
      cursor: pointer;
      font-size: 16px;
    }
    button:hover {
      background: #1976D2;
    }
    .summary {
      margin-top: 20px;
      font-weight: bold;
      text-align: center;
    }
  </style>
</head>
<body>
  <div class="container">
    <h1>Ticket Booking</h1>
    <label for="event">Choose Event:</label>
    <select id="event">
      <option value="Concert" data-price="500">Concert - ₹500</option>
      <option value="Movie" data-price="300">Movie - ₹300</option>
      <option value="Play" data-price="400">Play - ₹400</option>
    </select>

    <label for="tickets">Number of Tickets:</label>
    <input type="number" id="tickets" min="1" value="1">

    <button onclick="bookTickets()">Book Tickets</button>

    <div class="summary" id="summary"></div>
  </div>

  <script>
    function bookTickets() {
      const eventSelect = document.getElementById("event");
      const tickets = parseInt(document.getElementById("tickets").value);
      const eventName = eventSelect.value;
      const price = parseInt(eventSelect.options[eventSelect.selectedIndex].dataset.price);

      if (tickets > 0) {
        const total = tickets * price;
        document.getElementById("summary").textContent =
          `You booked ${tickets} ticket(s) for ${eventName}. Total: ₹${total}`;
      } else {
        document.getElementById("summary").textContent = "Please select at least 1 ticket.";
      }
    }
  </script>
</body>
</html>

# Punitmartfeedback
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Punitmart Customer Feedback</title>
  <script src="https://cdn.tailwindcss.com"></script>
  <link
    rel="stylesheet"
    href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.15.3/css/all.min.css"
  />
  <link
    href="https://fonts.googleapis.com/css2?family=Poppins:wght@400;600&display=swap"
    rel="stylesheet"
  />
  <style>
    body {
      font-family: 'Poppins', sans-serif;
    }
  </style>
</head>
<body class="min-h-screen bg-gradient-to-r from-pink-400 via-purple-500 to-indigo-600 flex flex-col">
  <header class="p-6 text-center text-white">
    <h1 class="text-4xl font-extrabold mb-2">Welcome to Punimart</h1>
    <p class="text-lg font-semibold">We value your feedback after shopping with us!</p>
  </header>

  <main class="flex-grow flex items-center justify-center px-4">
    <form
      class="bg-white bg-opacity-90 rounded-xl shadow-lg max-w-lg w-full p-8"
      id="feedbackForm"
      novalidate
    >
      <h2 class="text-2xl font-bold mb-6 text-center text-indigo-700">
        Customer Feedback Form
      </h2>

      <div class="mb-5">
        <label for="name" class="block text-gray-700 font-semibold mb-2"
          >Full Name <span class="text-red-600">*</span></label
        >
        <input
          type="text"
          id="name"
          name="name"
          placeholder="Your full name"
          required
          class="w-full px-4 py-3 border border-gray-300 rounded-md focus:outline-none focus:ring-2 focus:ring-indigo-500"
        />
      </div>

      <div class="mb-5">
        <label for="email" class="block text-gray-700 font-semibold mb-2"
          >Email Address <span class="text-red-600">*</span></label
        >
        <input
          type="email"
          id="email"
          name="email"
          placeholder="you@example.com"
          required
          class="w-full px-4 py-3 border border-gray-300 rounded-md focus:outline-none focus:ring-2 focus:ring-indigo-500"
        />
      </div>

      <div class="mb-5">
        <label for="phone" class="block text-gray-700 font-semibold mb-2"
          >Phone Number <span class="text-red-600">*</span></label
        >
        <input
          type="tel"
          id="phone"
          name="phone"
          placeholder="9967370160"
          pattern="[0-9]{10}"
          required
          class="w-full px-4 py-3 border border-gray-300 rounded-md focus:outline-none focus:ring-2 focus:ring-indigo-500"
        />
        <p class="text-sm text-gray-500 mt-1">Enter 10 digit phone number</p>
      </div>

      <div class="mb-5">
        <label for="shoppingDate" class="block text-gray-700 font-semibold mb-2"
          >Date of Shopping <span class="text-red-600">*</span></label
        >
        <input
          type="date"
          id="shoppingDate"
          name="shoppingDate"
          required
          class="w-full px-4 py-3 border border-gray-300 rounded-md focus:outline-none focus:ring-2 focus:ring-indigo-500"
          max=""
        />
      </div>

      <div class="mb-5">
        <label for="rating" class="block text-gray-700 font-semibold mb-2"
          >How would you rate your shopping experience? <span class="text-red-600">*</span></label
        >
        <select
          id="rating"
          name="rating"
          required
          class="w-full px-4 py-3 border border-gray-300 rounded-md focus:outline-none focus:ring-2 focus:ring-indigo-500"
        >
          <option value="" disabled selected>Select rating</option>
          <option value="5">Excellent - 5 Stars</option>
          <option value="4">Very Good - 4 Stars</option>
          <option value="3">Good - 3 Stars</option>
          <option value="2">Fair - 2 Stars</option>
          <option value="1">Poor - 1 Star</option>
        </select>
      </div>

      <div class="mb-5">
        <label for="feedback" class="block text-gray-700 font-semibold mb-2"
          >Your Feedback</label
        >
        <textarea
          id="feedback"
          name="feedback"
          rows="4"
          placeholder="Write your comments or suggestions here..."
          class="w-full px-4 py-3 border border-gray-300 rounded-md focus:outline-none focus:ring-2 focus:ring-indigo-500 resize-none"
        ></textarea>
      </div>

      <button
        type="submit"
        class="w-full bg-indigo-600 hover:bg-indigo-700 text-white font-bold py-3 rounded-md transition-colors duration-300 flex items-center justify-center"
      >
        <i class="fas fa-paper-plane mr-2"></i> Submit Feedback
      </button>

      <p id="formMessage" class="mt-4 text-center font-semibold"></p>
    </form>
  </main>

  <footer class="bg-indigo-900 text-white p-6 text-center">
    <p class="text-lg font-semibold mb-2">Contact Us</p>
    <p>
      <i class="fas fa-envelope mr-2"></i>
      <a href="mailto:thakurpunit987@gmail.com" class="underline hover:text-pink-400"
        >thakurpunit987@gmail.com</a
      >
    </p>
    <p class="mt-2">
      <i class="fas fa-phone-alt mr-2"></i>
      <a href="tel:+919967370160" class="underline hover:text-pink-400">9967370160</a>
    </p>
    <p class="mt-2 font-semibold">Punit Thakur</p>
  </footer>

  <script>
    // Set max date for shopping date input to today
    const shoppingDateInput = document.getElementById('shoppingDate');
    const today = new Date().toISOString().split('T')[0];
    shoppingDateInput.setAttribute('max', today);

    const form = document.getElementById('feedbackForm');
    const formMessage = document.getElementById('formMessage');

    form.addEventListener('submit', (e) => {
      e.preventDefault();

      if (!form.checkValidity()) {
        formMessage.textContent = 'Please fill out all required fields correctly.';
        formMessage.classList.remove('text-green-600');
        formMessage.classList.add('text-red-600');
        return;
      }

      // Simulate form submission
      formMessage.textContent = 'Thank you for your feedback! We appreciate your time.';
      formMessage.classList.remove('text-red-600');
      formMessage.classList.add('text-green-600');

      form.reset();
    });
  </script>
</body>
</html>

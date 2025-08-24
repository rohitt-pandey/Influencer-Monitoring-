# Influencer-Monitoring
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Influencer Monitoring</title>
  <style>
    /* Minimal background */
    body {
      font-family: "Poppins", sans-serif;
      background: #000;
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
      margin: 0;
      overflow: hidden;
      color: #fff;
      perspective: 1000px;
    }
    .container {
      background: rgba(20, 20, 20, 0.9);
      border-radius: 20px;
      padding: 40px;
      width: 420px;
      text-align: center;
      box-shadow: 0 15px 40px rgba(255, 255, 255, 0.1),
                  inset 0 0 20px rgba(255,255,255,0.05);
      border: 1px solid rgba(255,255,255,0.15);
      transform-style: preserve-3d;
      animation: floatCard 6s ease-in-out infinite;
    }
  h1 {
      font-size: 2rem;
      margin-bottom: 20px;
      color: #fff;
      text-shadow: 0 0 15px #fff, 0 0 30px #aaa;
      animation: glow 2s infinite alternate;
    }
  label {
      font-size: 1rem;
      display: block;
      margin: 15px 0 8px;
      text-align: left;
      color: #ddd;
      opacity: 0;
      animation: fadeSlide 1s ease forwards;
    }
  input[type="text"],
    input[type="email"] {
      width: 100%;
      padding: 12px;
      border: 2px solid #555;
      border-radius: 12px;
      outline: none;
      font-size: 1rem;
      background: #111;
      color: #fff;
      transition: 0.3s;
      opacity: 0;
      animation: fadeSlide 1s ease forwards;
      box-shadow: 0 0 8px rgba(255, 255, 255, 0.1);
    }
  input[type="text"]:focus,
    input[type="email"]:focus {
      border-color: #fff;
      box-shadow: 0 0 15px #fff, 0 0 25px #aaa;
    }
  .social {
      display: flex;
      justify-content: space-between;
      margin: 20px 0;
      flex-wrap: wrap;
    }
.social label {
      display: flex;
      align-items: center;
      font-size: 0.9rem;
      cursor: pointer;
      transform: scale(0);
      animation: popIn 0.6s ease forwards;
      color: #fff;
      text-shadow: 0 0 8px #fff;
    }
 input[type="checkbox"] {
      margin-right: 6px;
      accent-color: #fff;
      transform: scale(1.3);
      transition: transform 0.3s;
      filter: drop-shadow(0 0 5px #fff);
    }
 input[type="checkbox"]:hover {
      transform: scale(1.6) rotate(8deg);
    }
  .note {
      font-size: 0.8rem;
      color: #aaa;
      margin-top: 10px;
      animation: fadeIn 1s ease 1.5s forwards;
      opacity: 0;
      text-shadow: 0 0 5px #fff;
    }
 button {
      margin-top: 20px;
      padding: 12px 30px;
      border: none;
      border-radius: 30px;
      font-size: 1rem;
      background: #000;
      color: #fff;
      cursor: pointer;
      animation: pulse 2s infinite;
      box-shadow: 0 0 12px #fff, inset 0 0 12px #fff;
      transition: 0.3s;
      border: 1px solid #fff;
    }
 button:hover {
      transform: translateY(-3px) scale(1.1);
      box-shadow: 0 0 20px #fff, inset 0 0 20px #fff;
    }
  .success {
      position: fixed;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -50%) scale(0);
      background: #111;
      padding: 30px 40px;
      border-radius: 20px;
      box-shadow: 0 0 30px #fff, inset 0 0 30px #999;
      text-align: center;
      font-size: 1.2rem;
      color: #fff;
      animation: popIn 0.6s ease forwards;
      display: none;
      border: 1px solid #fff;
      text-shadow: 0 0 12px #fff;
    }
  @keyframes fadeSlide {
      from { transform: translateY(20px); opacity: 0; }
      to { transform: translateY(0); opacity: 1; }
    }
    @keyframes fadeIn {
      from { opacity: 0; }
      to { opacity: 1; }
    }
@keyframes glow {
      from { text-shadow: 0 0 10px #fff, 0 0 20px #aaa; }
      to { text-shadow: 0 0 25px #fff, 0 0 40px #ddd; }
    }
@keyframes popIn {
      from { transform: scale(0); opacity: 0; }
      to { transform: scale(1); opacity: 1; }
    }
 @keyframes pulse {
      0%, 100% { transform: scale(1); box-shadow: 0 0 12px #fff, inset 0 0 12px #fff; }
      50% { transform: scale(1.08); box-shadow: 0 0 25px #fff, inset 0 0 25px #fff; }
    }
 @keyframes floatCard {
      0%, 100% { transform: translateY(0) rotateY(0); }
      50% { transform: translateY(-12px) rotateY(3deg); }
    }
  </style>
</head>
<body>
  <div class="container">
    <h1> INFLUENCER MONITORING </h1>
<form id="influencerForm">
      <label for="influencer" style="animation-delay:0.2s">Add New Influencer</label>
      <input type="text" id="influencer" placeholder="Enter influencer name" style="animation-delay:0.3s" required />
<label style="animation-delay:0.5s">Social Media Handle:</label>
      <div class="social">
        <label style="animation-delay:1s"><input type="checkbox"/> YouTube</label>
        <label style="animation-delay:1s"><input type="checkbox" /> Instagram</label>
        <label style="animation-delay:1s"><input type="checkbox" /> LinkedIn</label>
        <label style="animation-delay:1.2s"><input type="checkbox" /> TikTok</label>
      </div>

 <label for="email" style="animation-delay:1.4s">Your Email</label>
      <input type="email" id="email" placeholder="Enter your email" style="animation-delay:1.5s" required />

  <p class="note">*48 hour report will be sent to your email.</p>

  <button type="submit">SUBMIT</button>
    </form>
  </div>

  <div class="success" id="successPopup">
    ✅ Submitted Successfully!<br>
    You will receive your report soon.
  </div>

  <script>
    const form = document.getElementById("influencerForm");
    const popup = document.getElementById("successPopup");

    form.addEventListener("submit", function (e) {
      e.preventDefault();
      popup.style.display = "block";
      popup.style.animation = "popIn 0.6s ease forwards";
      setTimeout(() => {
        popup.style.display = "none";
      }, 2500);
      form.reset();
    });
  </script>
</body>
</html>

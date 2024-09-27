<template>
  <div id="app">
    <header>
      <nav>
        <ul>
          <li><a href="#home">Home</a></li>
          <li><a href="#features">Features</a></li>
          <li><a href="#demo">Demo</a></li>
          <li><a href="#screenshots">Screenshots</a></li>
          <li><a href="#contact">Contact</a></li>
          <li><a href="#privacy-policy">Privacy policy</a></li>
        </ul>
      </nav>
    </header>

    <section id="home" class="hero">
      <h1>Welcome to the Mood-Based Music App</h1>
      <p>Discover music based on your emotions</p>
      <a href="#demo" class="cta-button">Watch Demo</a>
    </section>

    <section id="features">
      <h2>Some of the features. More to come :)</h2>
      <br>
      <div class="features-grid">
        <div class="feature-item">
          <h3>Emotion Recognition</h3>
          <p>Our AI recognizes your mood and plays the perfect song.</p>
        </div>
        <div class="feature-item">
          <h3>Custom Playlists</h3>
          <p>Automatically generate playlists based on how you're feeling.</p>
        </div>
        <div class="feature-item">
          <h3>Instant Song Suggestions</h3>
          <p>Get song suggestions that match your mood instantly.</p>
        </div>
        <div class="feature-item">
          <h3>Generate beats</h3>
          <p>Get cool short beats with mood of your choice.</p>
        </div>
        <div class="feature-item">
          <h3>Track emotions</h3>
          <p>Track your emotions with the help of visualization plot.</p>
        </div>
      </div>
    </section>


    <section id="demo" class="video-section">
      <h2>Watch the Demo</h2>
      <br>
      <div class="video-wrapper">
        <iframe src="https://www.youtube.com/embed/MnDuzW7SAbI?si=t0c5jHaFooN2ay3D" frameborder="0" allowfullscreen></iframe>
      </div>
    </section>

    <section id="support">
  <h2>Support Our Kickstarter Campaign (yet to be announced)</h2>
  <br>
  <a href="#" class="support-button" target="_blank">Join Our Campaign</a>
</section>

<section id="screenshots">
  <h2>Screenshots</h2>
  <div class="screenshot-grid">
    <img v-for="(image, index) in images" :src="image" :alt="'App Screenshot ' + (index + 1)" @click="openModal(image)" />
  </div>

  <!-- Image Modal -->
  <div v-if="isModalOpen" class="modal-overlay" @click="closeModal">
    <div class="modal-content">
      <span class="close-button" @click="closeModal">&times;</span>
      <img :src="modalImage" class="modal-image" />
    </div>
  </div>
</section>

<section id="privacy-policy">
  <h2>Privacy Policy</h2>
  <p>Your privacy is important to us. This privacy policy explains how we collect, use, and share information.</p>
  <p> We don't. None of your private info will ever be shared with this app. </p>
  <!-- Add detailed privacy policy content as necessary -->
</section>


    <footer id="contact">
      <h2>Contact Us</h2>
      <p>Email: amstudio237@gmail.com </p>
      <p>Address: Zagreb, Hrvatska/Croatia<p>
    </footer>
  </div>
</template>

<script>
import Screen1 from '@/assets/Screen1.png';
import Screen2 from '@/assets/Screen2.png';
import Screen3 from '@/assets/Screen3.png';
import Screen4 from '@/assets/Screen4.png';
import Screen5 from '@/assets/Screen5.png';
import Screen6 from '@/assets/Screen6.png';


export default {
  name: 'App',
  data() {
    return {
      images: [Screen1, Screen2, Screen3, Screen4, Screen5, Screen6],
      isModalOpen: false,
      modalImage: null,
    };
  },
  methods: {
    openModal(image) {
      this.modalImage = image;
      this.isModalOpen = true;
    },
    closeModal() {
      this.isModalOpen = false;
      this.modalImage = null;
    },
  },
};

</script>

<style scoped>
/* Global Styles */
body {
  font-family: 'Arial', sans-serif;
  margin: 0;
  padding: 0;
  background-color: #f4f4f9;
  color: #333;
}

a {
  color: #007bff;
  text-decoration: none;
}

h1, h2, h3, h4 {
  margin: 0;
  padding: 0;
  text-align: center;
}

ul {
  list-style: none;
  padding: 0;
}

/* Header & Nav */
header {
  background-color: #333;
  padding: 20px;
}

nav ul {
  display: flex;
  justify-content: center;
  gap: 20px;
}

nav ul li {
  margin: 0;
}

nav ul li a {
  color: white;
  font-weight: bold;
  font-size: 16px;
}

nav ul li a:hover {
  color: #ffcc00;
}

/* Hero Section */
.hero {
  background-image: url('@/assets/R.jpg');
  background-size: cover;
  background-position: center;
  padding: 100px 20px;
  text-align: center;
  color: white;
}

.hero h1 {
  font-size: 3rem;
  margin-bottom: 20px;
}

.hero p {
  font-size: 1.5rem;
  margin-bottom: 30px;
}

.cta-button {
  background-color: #007bff;
  color: white;
  padding: 15px 30px;
  border: none;
  cursor: pointer;
  font-size: 1.2rem;
  border-radius: 5px;
}

.cta-button:hover {
  background-color: #0056b3;
}

/* Features Section */
#features {
  padding: 60px 20px;
  background-color: #fff;
}

.features-grid {
  display: flex;
  justify-content: center;
  gap: 40px;
}

.feature-item {
  background-color: #f9f9f9;
  padding: 20px;
  border-radius: 10px;
  box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
  width: 250px;
  text-align: center;
}

.feature-item h3 {
  font-size: 1.5rem;
  margin-bottom: 10px;
}

/* Video Section */
/* Video Section */
.video-section {
  padding: 60px 20px;
  background-color: #333;
  color: white;
}

.video-wrapper {
  max-width: 640px; /* Reduced from 800px */
  margin: 0 auto;
  position: relative;
  padding-bottom: 56.25%; /* 16:9 Aspect Ratio */
  height: 0;
}

.video-wrapper iframe {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
}

/* Screenshots Section */
.screenshot-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 20px;
  padding: 60px 20px;
}

.screenshot-grid img {
  width: 100%;
  border-radius: 10px;
  box-shadow: 0 2px 10px rgba(0, 0, 0, 0.2);
}

/* Footer */
footer {
  padding: 40px 20px;
  background-color: #222;
  color: white;
  text-align: center;
}

#support {
  padding: 60px 20px;
  background-color: #007bff;
  color: white;
  text-align: center;
}

.support-button {
  display: inline-block;
  background-color: #ffcc00;
  color: #333;
  padding: 15px 30px;
  border: none;
  cursor: pointer;
  font-size: 1.2rem;
  border-radius: 5px;
  text-decoration: none;
}

.support-button:hover {
  background-color: #ffd700;
  color: #000;
}

/* Modal Styles */
.modal-overlay {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, 0.8);
  display: flex;
  justify-content: center;
  align-items: center;
}

.modal-content {
  position: relative;
}

.modal-image {
  max-width: 90%;
  max-height: 80vh;
  border-radius: 10px;
}

.close-button {
  position: absolute;
  top: 10px;
  right: 20px;
  font-size: 2rem;
  color: white;
  cursor: pointer;
}


#privacy-policy {
  padding: 60px 20px;
  background-color: #f9f9f9;
  text-align: center;
}

#privacy-policy h2 {
  font-size: 2rem;
  margin-bottom: 20px;
}

#privacy-policy p {
  font-size: 1rem;
  color: #555;
  max-width: 800px;
  margin: 0 auto;
}

</style>

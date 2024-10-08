<template>
  <div id="app">
    <!-- Header and Navigation -->
    <header>
      <nav>
        <ul>
          <li><a href="#home">Home</a></li>
          <li><a href="#features">Features</a></li>
          <li><a href="#demo">Demo</a></li>
          <li><a href="#screenshots">Screenshots</a></li>
          <li><a href="#download">Download</a></li>
          <li><a href="#support">Support</a></li>
          <li><a href="#contact">Contact</a></li>
          <li><a href="#privacy-policy">Privacy Policy</a></li>
        </ul>
      </nav>
    </header>

    <!-- Hero Section -->
    <section id="home" class="hero">
      <h1>Welcome to FeelTrak</h1>
      <p>Discover music that matches your mood</p>
      <a href="#demo" class="cta-button">Watch Demo</a>
    </section>

    <!-- Features Section -->
    <section id="features">
      <h2>Awesome Features</h2>
      <div class="features-grid">
        <div class="feature-item">
          <h3>🎭 Emotion Recognition</h3>
          <p>AI recognizes your mood and plays the perfect song for you.</p>
        </div>
        <div class="feature-item">
          <h3>📚 Custom Playlists</h3>
          <p>Automatically generate playlists based on your emotions.</p>
        </div>
        <div class="feature-item">
          <h3>💡 Instant Song Suggestions</h3>
          <p>Get the perfect song suggestions instantly.</p>
        </div>
        <div class="feature-item">
          <h3>🎶 Generate Beats</h3>
          <p>Quickly create beats that match your mood.</p>
        </div>
        <div class="feature-item">
          <h3>📊 Track Emotions</h3>
          <p>Visualize your emotions over time with our tracker.</p>
        </div>
      </div>
    </section>

    <!-- Demo Section -->
    <section id="demo" class="video-section">
      <h2>Watch the Demo</h2>
      <div class="video-wrapper">
        <iframe
          width="640"
          height="360"
          src="https://www.youtube.com/embed/PBwGtrGUmC8?si=WkwGiPF2aUrlw28e"
          title="YouTube video player"
          frameborder="0"
          allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
          referrerpolicy="strict-origin-when-cross-origin"
          allowfullscreen
        ></iframe>
      </div>
    </section>

    <!-- Download Section -->
    <section id="download" class="download-section">
      <h2>Download FeelTrak BETA</h2>
      <p>Get the latest version now!</p>
      <a
        href="https://onedrive.live.com/?id=144DED0DF3B8FB69%21s1569103524ca415abf24f4e3feadc66e&cid=144DED0DF3B8FB69"
        download
        class="download-button"
      >
        Download FeelTrak BETA
      </a>
    </section>

    <!-- Support Section -->
    <section id="support">
  <h2>Support us on Patreon</h2>
  <p>Join our mission to make the world happier through music.</p>
  <a href="https://www.patreon.com/FeelTuneStudio404" class="support-button" target="_blank">Join Now</a>
</section>


    <!-- Screenshots Section -->
    <section id="screenshots">
      <h2>Screenshots</h2>
      <div class="screenshot-grid">
        <img
          v-for="(image, index) in images"
          :src="image"
          :alt="'App Screenshot ' + (index + 1)"
          @click="openModal(image)"
        />
      </div>

      <!-- Modal -->
      <div v-if="isModalOpen" class="modal-overlay" @click="closeModal">
        <div class="modal-content">
          <span class="close-button" @click="closeModal">&times;</span>
          <img :src="modalImage" class="modal-image" />
        </div>
      </div>
    </section>

    <!-- Privacy Policy Section -->
    <section id="privacy-policy">
      <h2>Privacy Policy</h2>
      <p>Your privacy matters to us. We don't collect or share your personal information.</p>
    </section>

    <!-- Footer and Contact -->
    <footer id="contact">
      <h2>Contact Us</h2>
      <p>Email: <a href="mailto:amstudio237@gmail.com">amstudio237@gmail.com</a></p>
      <p>Location: Zagreb, Hrvatska/Croatia</p>
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
  font-family: 'Poppins', sans-serif;
  margin: 0;
  padding: 0;
  background-color: #f5f8fb;
  color: #333;
}

a {
  color: #ff6600;
  text-decoration: none;
  transition: color 0.3s ease;
}

a:hover {
  color: #ff4500;
}

h1,
h2,
h3,
h4 {
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
  background-color: #1a1a1d;
  padding: 20px;
}

nav ul {
  display: flex;
  justify-content: center;
  gap: 30px;
}

nav ul li a {
  color: white;
  font-weight: 600;
  font-size: 18px;
  transition: color 0.3s ease;
}

nav ul li a:hover {
  color: #ffcc00;
}

/* Hero Section */
.hero {
  background: linear-gradient(135deg, #72edf2 10%, #5151e5 100%);
  padding: 100px 20px;
  text-align: center;
  color: white;
  border-radius: 0 0 50px 50px;
}

.hero h1 {
  font-size: 4rem;
  margin-bottom: 20px;
}

.hero p {
  font-size: 1.5rem;
  margin-bottom: 30px;
}

.cta-button {
  background: linear-gradient(45deg, #ff6600, #ff4500);
  color: white;
  padding: 15px 40px;
  border: none;
  cursor: pointer;
  font-size: 1.2rem;
  border-radius: 8px;
  transition: background 0.3s ease;
}

.cta-button:hover {
  background: linear-gradient(45deg, #ff4500, #ff6600);
}

/* Features Section */
#features {
  padding: 80px 20px;
  background-color: #f0f0f0;
  border-radius: 20px;
}

.features-grid {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  gap: 40px;
}

.feature-item {
  background-color: #fff;
  padding: 30px;
  border-radius: 10px;
  box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
  width: 300px;
  text-align: center;
  transition: transform 0.3s ease, box-shadow 0.3s ease;
}

.feature-item:hover {
  transform: translateY(-5px);
  box-shadow: 0 6px 15px rgba(0, 0, 0, 0.2);
}

.feature-item h3 {
  font-size: 1.7rem;
  margin-bottom: 15px;
}

.feature-item p {
  font-size: 1rem;
  line-height: 1.5;
}

/* Video Section */
.video-section {
  padding: 80px 20px;
}

.video-wrapper {
  display: flex;
  justify-content: center;
}

/* Download Section */
.download-section {
  padding: 80px 20px;
  text-align: center;
  background-color: #1a1a1d;
  color: white;
  border-radius: 20px;
}

.download-button {
  background: linear-gradient(45deg, #ff6600, #ff4500);
  color: white;
  padding: 15px 40px;
  border: none;
  cursor: pointer;
  font-size: 1.2rem;
  border-radius: 8px;
  transition: background 0.3s ease;
}

.download-button:hover {
  background: linear-gradient(45deg, #ff4500, #ff6600);
}

/* Support Section */
.support-button {
  background-color: #28a745;
  color: white;
  padding: 15px 40px;
  border: none;
  cursor: pointer;
  font-size: 1.2rem;
  border-radius: 8px;
  transition: background 0.3s ease;
}

.support-button:hover {
  background-color: #218838;
}

/* Screenshots Section */
.screenshot-grid {
  display: flex;
  justify-content: center;
  flex-wrap: wrap;
  gap: 20px;
}

.screenshot-grid img {
  width: 300px;
  height: auto;
  border-radius: 10px;
  cursor: pointer;
  transition: transform 0.3s ease;
}

.screenshot-grid img:hover {
  transform: scale(1.05);
}

/* Modal */
.modal-overlay {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background-color: rgba(0, 0, 0, 0.8);
  display: flex;
  justify-content: center;
  align-items: center;
  z-index: 1000;
}

.modal-content {
  position: relative;
}

.modal-image {
  max-width: 90vw;
  max-height: 90vh;
  border-radius: 10px;
}

.close-button {
  position: absolute;
  top: 10px;
  right: 15px;
  font-size: 30px;
  color: white;
  cursor: pointer;
}

/* Footer */
footer {
  background-color: #1a1a1d;
  color: white;
  text-align: center;
  padding: 20px;
  margin-top: 40px;
}

@media only screen and (max-width: 768px) {
  .hero h1 {
    font-size: 2.5rem;
  }

  .hero p {
    font-size: 1.2rem;
  }

  .features-grid {
    display: block;
  }

  .feature-item {
    margin-bottom: 20px;
    width: 100%;
  }

  .cta-button, .download-button, .support-button {
    padding: 10px 20px;
    font-size: 1rem;
  }

  nav ul {
    flex-direction: column;
    gap: 15px;
  }

  .screenshot-grid img {
    width: 100%;
  }
}
</style>

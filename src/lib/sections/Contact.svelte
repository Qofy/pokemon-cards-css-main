



<section class="contact-section">
  <h2>Contact Us</h2>
  <form class="contact-form" action="#" method="post">
    <div class="form-group">
      <label for="name">Name:</label>
      <input id="name" name="name" type="text" placeholder="Your Full Name" required>
    </div>
    <div class="form-group">
      <label for="email">Email:</label>
      <input id="email" name="email" type="email" placeholder="Your Email" required>
    </div>
    <div class="form-group">
      <label for="subject">Subject:</label>
      <input id="subject" name="subject" type="text" placeholder="Message Subject" required>
    </div>
    <div class="form-group">
      <label for="message">Message:</label>
      <textarea id="message" name="message" placeholder="Your Message" rows="5" required></textarea>
    </div>
    <button type="submit" class="submit-btn">Send Message</button>
  </form>
</section>

<style>
.contact-section {
  /* max-width: 500px; */
  margin: 2rem auto;
  background: #171717;
  padding: 2rem 2.5rem;
  border-radius: 1rem;
 		box-shadow: 0 4px 24px 0 #a0bd35, 0 1.5px 6px 0 #87a909;
}
.contact-section h2 {
  text-align: center;
  margin-bottom: 1.5rem;
  /* color: #ffd700; */
  font-size: 2.2rem;
}
.contact-form {
  display: flex;
  flex-direction: column;
  gap: 1.2rem;
}
.form-group {
  display: flex;
  flex-direction: column;
}
.form-group label {
  margin-bottom: 0.5rem;
  /* color: #fff; */
  font-weight: 500;
}
.form-group input,
.form-group textarea {
  padding: 0.7rem 1rem;
  border-radius: 0.5rem;
  border: none;
  background: #333;
  color: #fff;
  /* color: #ffd700; */
  font-size: 1rem;
  outline: none;
  transition: background 0.2s;
}
.form-group input:focus,
.form-group textarea:focus {
  background: #444;
}
.submit-btn {
  background: linear-gradient(90deg, #a0bd35 0%, #87a909 100%);
  /* color: #222; */
  font-weight: bold;
  padding: 0.9rem 0;
  border: none;
  border-radius: 0.5rem;
  font-size: 1.1rem;
  cursor: pointer;
  margin-top: 1rem;
  box-shadow: 0 2px 8px rgba(18, 232, 57, 0.15);
  transition: background 0.2s, color 0.2s;
}
.submit-btn:hover {
  background: linear-gradient(90deg, #87a909 0%, #a0bd35 100%);
  color: #fff;
}
</style>
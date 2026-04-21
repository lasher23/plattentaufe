---
title: "Kontakt"
layout: "page"
---

Schreib uns eine Nachricht – wir freuen uns über Post!

<form class="contact-form" name="kontakt" method="POST" netlify>
  <label for="name">Name *</label>
  <input type="text" id="name" name="name" required>

  <label for="email">E-Mail *</label>
  <input type="email" id="email" name="email" required>

  <label for="message">Deine Nachricht *</label>
  <textarea id="message" name="message" rows="6" required></textarea>

  <button type="submit">Absenden</button>
</form>

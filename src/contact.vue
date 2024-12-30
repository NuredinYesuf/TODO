<template>
    <div class="contact-page">
      <h1>Contact Us</h1>
      <p>If you have any questions or inquiries, feel free to reach out to us using the form below:</p>
  
      <form @submit.prevent="submitForm">
        <div class="form-group">
          <label for="name">Name</label>
          <input 
            type="text" 
            id="name" 
            v-model="form.name" 
            required 
            placeholder="Your Full Name"
          />
        </div>
  
        <div class="form-group">
          <label for="email">Email</label>
          <input 
            type="email" 
            id="email" 
            v-model="form.email" 
            required 
            placeholder="Your Email Address"
          />
        </div>
  
        <div class="form-group">
          <label for="message">Message</label>
          <textarea 
            id="message" 
            v-model="form.message" 
            required 
            placeholder="Your Message"
          ></textarea>
        </div>
  
        <button type="submit" :disabled="isSubmitting">
          {{ isSubmitting ? 'Sending...' : 'Submit' }}
        </button>
      </form>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        form: {
          name: '',
          email: '',
          message: ''
        },
        isSubmitting: false
      };
    },
    methods: {
      async submitForm() {
        if (!this.form.name || !this.form.email || !this.form.message) {
          alert('Please fill out all fields.');
          return;
        }
  
        this.isSubmitting = true;
  
        try {
          // Simulate an API call
          await new Promise(resolve => setTimeout(resolve, 2000));
          alert('Thank you for your message! We will get back to you shortly.');
          this.form = { name: '', email: '', message: '' }; // Reset the form
        } catch (error) {
          alert('There was an error submitting your form. Please try again.');
        } finally {
          this.isSubmitting = false;
        }
      }
    }
  };
  </script>
  
  <style scoped>
  .contact-page {
    max-width: 600px;
    margin: 0 auto;
    padding: 20px;
    font-family: Arial, sans-serif;
    background-color: #f9f9f9;
    border: 1px solid #ddd;
    border-radius: 8px;
  }
  
  .contact-page h1 {
    margin-bottom: 20px;
    font-size: 24px;
    text-align: center;
  }
  
  .contact-page .form-group {
    margin-bottom: 15px;
  }
  
  .contact-page label {
    display: block;
    margin-bottom: 5px;
    font-weight: bold;
  }
  
  .contact-page input,
  .contact-page textarea {
    width: 100%;
    padding: 10px;
    border: 1px solid #ccc;
    border-radius: 4px;
    font-size: 16px;
  }
  
  .contact-page textarea {
    resize: vertical;
    height: 100px;
  }
  
  .contact-page button {
    display: block;
    width: 100%;
    padding: 10px;
    font-size: 16px;
    background-color: #007BFF;
    color: white;
    border: none;
    border-radius: 4px;
    cursor: pointer;
  }
  
  .contact-page button:disabled {
    background-color: #ccc;
    cursor: not-allowed;
  }
  </style>
  
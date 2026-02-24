<template>
  <section id="contact" class="w-full py-24">
    <div class="max-w-7xl mx-auto px-6">
      <!-- Header -->
      <div class="text-center mb-16">
        <p
          class="text-sm font-semibold text-purple-800 uppercase tracking-widest"
        >
          Get in touch
        </p>
        <h2 class="text-4xl font-bold text-white mt-2">Contact Me</h2>
      </div>

      <div class="grid grid-cols-1 lg:grid-cols-3 gap-12">
        <!-- Info -->
        <div class="space-y-8">
          <div class="space-y-3">
            <div class="flex items-center gap-3">
              <span
                class="h-10 w-10 rounded-full bg-purple-400 flex items-center justify-center"
              >
                <img src="@/assets/icons/callicon.png" class="h-5" />
              </span>
              <h3 class="font-semibold text-white">Call me</h3>
            </div>
            <p class="text-gray-300 text-sm">I am available 24/7.</p>
            <p class="text-gray-300 text-sm font-medium">
              Phone: +2347032563015
            </p>
          </div>

          <hr />

          <div class="space-y-3">
            <div class="flex items-center gap-3">
              <span
                class="h-10 w-10 rounded-full bg-purple-400 flex items-center justify-center"
              >
                <img src="@/assets/icons/email.png" class="h-5" />
              </span>
              <h3 class="font-semibold text-white">Write To Me</h3>
            </div>
            <p class="text-gray-300 text-sm">
              Fill out the form and I will reply within 24 hours.
            </p>
            <p class="text-gray-300 text-sm">Email: josephword22@gmail.com</p>
          </div>
        </div>

        <!-- Form -->
        <div class="lg:col-span-2">
          <form
            @submit.prevent="sendEmail"
            class="space-y-6 bg-gray-50 p-6 md:p-8 rounded-lg"
          >
            <div class="grid grid-cols-1 md:grid-cols-3 gap-6">
              <input
                v-model="form.name"
                type="text"
                placeholder="Your Name *"
                class="input"
              />
              <input
                v-model="form.email"
                type="email"
                placeholder="Your Email *"
                class="input"
              />
              <input
                v-model="form.phone"
                type="text"
                placeholder="Your Phone"
                class="input"
              />
            </div>

            <textarea
              v-model="form.message"
              rows="6"
              placeholder="Your Message *"
              class="input resize-none"
            ></textarea>

            <p v-if="error" class="text-red-500 text-sm">{{ error }}</p>
            <p v-if="success" class="text-green-600 text-sm">Message sent!</p>

            <div class="flex justify-end">
              <button
                type="submit"
                class="bg-purple-400 hover:bg-purple-900 text-white px-8 py-3 rounded transition"
              >
                {{ loading ? "Sending..." : "Send Message" }}
              </button>
            </div>
          </form>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
import emailjs from "@emailjs/browser";

export default {
  name: "ContactSection",
  data() {
    return {
      form: {
        name: "",
        email: "",
        phone: "",
        message: "",
      },
      loading: false,
      error: "",
      success: false,
    };
  },
  methods: {
    async sendEmail() {
      console.log("sendEmail fired");
      this.error = "";
      this.success = false;

      if (!this.form.name || !this.form.email || !this.form.message) {
        this.error = "Please fill in all required fields.";
        return;
      }

      this.loading = true;

      try {
        await emailjs.send(
          import.meta.env.VITE_EMAILJS_SERVICE_ID,
          import.meta.env.VITE_EMAILJS_TEMPLATE_ID,
          {
            from_name: this.form.name,
            from_email: this.form.email,
            phone: this.form.phone,
            message: this.form.message,
          },
          import.meta.env.VITE_EMAILJS_PUBLIC_KEY,
        );
        this.success = true;
        this.form = { name: "", email: "", phone: "", message: "" };
      } catch (err) {
        this.error = "Failed to send message. Please try again.";
      } finally {
        this.loading = false;
      }
    },
  },
};
</script>

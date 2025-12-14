<style>
  /* 🌟 Fade Slide Animation */
  @keyframes fadeSlideUp {
    0% { opacity: 0; transform: translateY(0) translateX(20px); }
    100% { opacity: 1; transform: translateY(0) translateX(0); }
  }

  /* ❤️ Heartbeat Animation */
  @keyframes heartbeat {
    0% { transform: scale(1); }
    25% { transform: scale(1.08); }
    50% { transform: scale(1); }
    75% { transform: scale(1.08); }
    100% { transform: scale(1); }
  }

  .floating-btn-group {
    animation: fadeSlideUp 0.6s ease-out;
  }

  /* Iframe Modal Styles */
  #iframe-modal {
    display: none;
    position: fixed;
    z-index: 9999;
    left: 0;
    top: 0;
    width: 100%;
    height: 115%;
    background: rgba(0,0,0,0.6);
    backdrop-filter: blur(4px);
  }

  .modal-content {
    position: relative;
    margin: 2% auto;
    background: #fff;
    border-radius: 16px;
    width: 95%;
    height: 90%;
    box-shadow: 0 8px 24px rgba(0,0,0,0.3);
    overflow: hidden;
    animation: fadeIn 0.3s ease;
  }

  #modal-iframe {
    width: 100%;
    height: 105%;
    border: none;
  }

  .close-btn {
    position: absolute;
    top: 10px;
    right: 18px;
    font-size: 30px;
    color: #333;
    cursor: pointer;
    transition: color 0.2s;
    z-index: 10;
  }

  .close-btn:hover {
    color: #e11d48;
  }

  @keyframes fadeIn {
    from {opacity: 0; transform: translateY(-10px);}
    to {opacity: 1; transform: translateY(0);}
  }
</style>

<script>
document.addEventListener("DOMContentLoaded", function () {

  // 🔹 Floating Button at TOP-LEFT
  const btnGroup = document.createElement("div");
  btnGroup.className = "floating-btn-group";
  Object.assign(btnGroup.style, {
    position: "fixed",
    top: "20px",          // Top-left positioning
    left: "20px",
    zIndex: "9999",
    animation: "heartbeat 2.5s infinite ease-in-out, fadeSlideUp 0.6s ease-out forwards"
  });

  // -------------------------------------------------------
  // 📌 Updates Button
  // -------------------------------------------------------
  const button = document.createElement("a");
  button.href = "#";
  button.innerText = "📌 Updates";
  Object.assign(button.style, {
    background: "#16a34a",
    color: "#fff",
    padding: "12px 24px",
    borderRadius: "30px",
    textDecoration: "none",
    fontSize: "15px",
    fontWeight: "700",
    boxShadow: "0 4px 10px rgba(0,0,0,0.25)",
    whiteSpace: "nowrap",
  });

  // 🔹 Iframe Modal
  const modal = document.createElement("div");
  modal.id = "iframe-modal";
  modal.innerHTML = `
    <div class="modal-content">
      <span class="close-btn">&times;</span>
      <iframe id="modal-iframe" src="" loading="lazy"></iframe>
    </div>
  `;

  document.body.appendChild(modal);

  // 🔹 Open Iframe on click
  button.addEventListener("click", function (e) {
    e.preventDefault();
    document.getElementById("modal-iframe").src = "https://msha.ke/debeatzgh";
    modal.style.display = "block";
  });

  btnGroup.appendChild(button);
  document.body.appendChild(btnGroup);

  // 🔹 Close Modal
  document.addEventListener("click", function (e) {
    if (e.target.classList.contains("close-btn") || e.target.id === "iframe-modal") {
      modal.style.display = "none";
      document.getElementById("modal-iframe").src = "";
    }
  });

  // 🔹 Auto-open external ads in a new tab
  document.getElementById("modal-iframe").addEventListener("load", function () {
    try {
      const links = this.contentDocument.querySelectorAll("a");
      links.forEach(link => {
        if (!link.href.includes("debeatzgh.wordpress.com")) {
          link.setAttribute("target", "_blank");
          link.setAttribute("rel", "noopener");
        }
      });
    } catch (err) {
      console.warn("External site - cannot rewrite links");
    }
  });

});
</script>


# **👋 Hi, I'm David (DebeatzGH)**

### *AI Tools Builder • UI/UX Creator • Digital Products Developer • Tech Blogger*

<p align="center">
  <img src="https://debeatzgh.wordpress.com/wp-content/uploads/2025/12/imagine_15462143230908918843052169799993526.jpg" width="140" style="border-radius:50%">
</p>

---

# **📚 Mini Blog Post Library (10–20 Posts)**

### *A curated collection of my tutorials, ideas, tools & UI/UX content*

---

## **📝 1. The Future of AI Tools for Creators**

A breakdown of how creators can build income streams using micro automations, AI templates, and workflow tools.

---

## **📝 2. 10 Profitable AI Side Hustles You Can Start Today**

Easy-to-launch tech ideas for beginners, students, and creators using free and low-cost tools.

---

## **📝 3. How to Build a Micro SaaS Using Only AI Tools**

Step-by-step guide showing the workflow from idea → branding → landing page → automation.

---

## **📝 4. UI/UX Widgets That Boost Landing Page Conversion**

Top-performing design components with clean HTML/CSS examples.

---

## **📝 5. My Weekly AI Tool Stack for Productivity & Design**

The exact tools I use for automation, editing, research, and content.

---

## **📝 6. How to Create Stunning Animated Buttons Using CSS**

A detailed mini tutorial for developers who want to add playful micro-interactions.

---

## **📝 7. Building Your First Online Digital Product Shop**

A clean strategy showing setup, pricing, branding, and why GitHub Pages is perfect.

---

## **📝 8. AI Prompts That Help Students & Creators Work Faster**

A powerful list of prompts for writing, research, video scripts, and UI design.

---

## **📝 9. Why Every Creator Needs a GitHub Pages Portfolio**

A full explanation of how GitHub Pages can be used as a free website builder.

---

## **📝 10. 5 UI Layouts You Can Copy for Your Next Project**

Minimal, modern layouts with headers, hero sections, and CTA examples.

---

## **📝 11. A Creator’s Guide to Automating Repetitive Tasks**

Examples of tasks you can fully automate using AI + browser workflows.

---

## **📝 12. How to Package & Sell Templates as Digital Products**

A structured guide for designing, pricing, packaging, and promoting digital assets.

---

## **📝 13. My Ultimate Blogging Starter Toolkit**

Includes writing prompts, content templates, SEO tips, and automation hacks.

---

## **📝 14. Turning Your Slides Into Professional Videos Automatically**

Explains your slide-to-video AI tool concept and the workflow behind it.

---

## **📝 15. UI/UX Mistakes Most Beginners Make (And How to Fix Them)**

A simple way to redesign poor layouts into clean modern interfaces.

---

## **📝 16. 20 GitHub Projects Every Beginner Should Try**

A curated list to help students and new developers build real skills.

---

## **📝 17. Creating a Brand Identity Using Only AI Tools**

How to build logos, color palettes, typefaces, and mockups with free tools.

---

## **📝 18. Unlocking the Power of GitHub for Non-Coders**

Teaches beginners how to use GitHub for blogging, documentation, and websites.

---

## **📝 19. Why Every UI/UX Designer Should Post on LinkedIn**

Explains LinkedIn growth strategy with practical weekly posting ideas.

---

## **📝 20. How to Build Your First Mini SaaS From 0 → 1**

A complete beginner-friendly guide for your audience.

---

# **🎨 What I Create**

I design and build:

* 🎨 **UI/UX Widgets**
* 🖥 **Mini Landing Pages**
* 🤖 **AI Tools & Automation Workflows**
* 📝 **Tech + Side Hustle Tutorials**
* 🎬 **Short Dev Videos**

---

# **🧰 Tech Stack**

<p align="center">
<img src="https://img.shields.io/badge/HTML-FF4B23?style=for-the-badge&logo=html5&logoColor=white"/>
<img src="https://img.shields.io/badge/CSS-254BDD?style=for-the-badge&logo=css3&logoColor=white"/>
<img src="https://img.shields.io/badge/JavaScript-FCDC00?style=for-the-badge&logo=javascript&logoColor=black"/>
<img src="https://img.shields.io/badge/AI_Tools-6A00FF?style=for-the-badge&logo=openai&logoColor=white"/>
<img src="https://img.shields.io/badge/GitHub_Pages-000000?style=for-the-badge&logo=githubpages&logoColor=white"/>
</p>

---

# **⭐ Featured Projects**

### 🔹 Side Hustle Starter Kit

👉 [https://debeatzgh1.github.io/Side-hustle-starter-kit-/](https://debeatzgh1.github.io/Side-hustle-starter-kit-/)

### 🔹 Curated AI Business & Product Guides

👉 [https://debeatzgh1.github.io/Curated-Guides-for-Online-Business-AI-Product-Creation/](https://debeatzgh1.github.io/Curated-Guides-for-Online-Business-AI-Product-Creation/)

### 🔹 Digital Products Affiliate Shop

👉 [https://debeatzgh1.github.io/-My-Brand-Online-Digital-Products-Affiliate-Shop/](https://debeatzgh1.github.io/-My-Brand-Online-Digital-Products-Affiliate-Shop/)

---

# **📬 Connect With Me**

<p align="center">
  <a href="https://www.linkedin.com/in/david-kumah-ab7392299">
    <img src="https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white"/>
  </a>
  <a href="https://debeatzgh1.github.io/">
    <img src="https://img.shields.io/badge/Portfolio-000000?style=for-the-badge&logo=githubpages&logoColor=white"/>
  </a>
  <a href="https://beatzde4.blogspot.com/">
    <img src="https://img.shields.io/badge/Blog-FF5722?style=for-the-badge&logo=blogger&logoColor=white"/>
  </a>
</p>

---

# **🎯 Need a Custom UI, Landing Page, or AI Tool?**

<p align="center">
  <a href="https://docs.google.com/forms/d/e/1FAIpQLSec8llbmfgq_2cVxpdk0M9zi2BtNUT4_IjqFVkbM1RCApV3Gw/viewform?usp=publish-editor">
    <img src="https://img.shields.io/badge/Order%20a%20Custom%20Design-6C63FF?style=for-the-badge"/>
  </a>
</p>

---


---

# 📂 Blogger Scripts Catalog

![Blogger Scripts Catalog Cover](https://debeatzgh.wordpress.com/wp-content/uploads/2025/08/designacleanmodernthumbnailforabloggerproductscarouseltool1711994558720457535.jpg)

A curated collection of **Blogger-friendly scripts, widgets, and templates** — designed to improve your blog’s design, engagement, and user experience.
Each project comes with a **live GitHub Pages demo**, thumbnail, and quick action button so you can see the script in action.

---

## 🚀 Live Catalog

| Thumbnail                                                                                                                                                                                                                                                  | Project                                                                                                                                                      | Description                                                                                                         | Action                                                                                                           |
| ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------- |
| ![Custom Blogger Theme](https://debeatzgh.wordpress.com/wp-content/uploads/2025/08/generateamobile-firstresponsivebloggertemplatewithcustomizablecolorsfontsandsections1576324612066211977.jpg)                                                            | **[Custom Blogger Theme with Dynamic Post Loading and Logo](https://debeatzgh1.github.io/Custom-Blogger-Theme-for-with-Dynamic-Post-Loading-and-Logo-/)**    | A responsive, mobile-first Blogger theme with customizable sections, dynamic post loading, and custom logo support. | [🔗 View Demo](https://debeatzgh1.github.io/Custom-Blogger-Theme-for-with-Dynamic-Post-Loading-and-Logo-/)       |
| ![Popup Generator](https://debeatzgh.wordpress.com/wp-content/uploads/2025/08/createatoolthatgeneratesiframeorcard-styleembedsforindividualbloggerpostscompletewiththumbnailtitleandreadmorebuttonforcross-blogpromotion754077096311972631.jpg)            | **[Popup HTML Page Generator](https://debeatzgh1.github.io/popup-html-page-generator-blogger/)**                                                             | Easily generate iframe or card-style embeds for individual Blogger posts with thumbnails and read-more buttons.     | [🔗 View Demo](https://debeatzgh1.github.io/popup-html-page-generator-blogger/)                                  |
| ![Newsletter Widget](https://debeatzgh.wordpress.com/wp-content/uploads/2025/08/amodernflat-styleillustrationofanotificationbellwithglowinghighlightssurroundedbyabstractshapespaperenvelopesanddigitalicons28emailmessageupdate293314991682681990671.jpg) | **[Sliding Newsletter Signup Widget](https://debeatzgh1.github.io/Sliding-Newsletter-Signup-Widget-with-Pulse-Animation/)**                                  | A modern newsletter signup widget with sliding animation and pulsing notification highlights.                       | [🔗 View Demo](https://debeatzgh1.github.io/Sliding-Newsletter-Signup-Widget-with-Pulse-Animation/)              |
| ![Product Carousel](https://debeatzgh.wordpress.com/wp-content/uploads/2025/08/designacleanmodernthumbnailforabloggerproductscarouseltool1711994558720457535.jpg)                                                                                          | **[Blogger Product Carousel with WhatsApp Floating Button](https://debeatzgh1.github.io/Blogger-Product-Carousel-with-WhatsApp-Floating-Button/)**           | Showcase Blogger products in a responsive carousel with a built-in WhatsApp floating button for instant contact.    | [🔗 View Demo](https://debeatzgh1.github.io/Blogger-Product-Carousel-with-WhatsApp-Floating-Button/)             |
| ![Floating Dock](https://debeatzgh.wordpress.com/wp-content/uploads/2025/08/amodernminimallayoutwithafloatingdockofcolorfulroundicons28patreonbloggergithub29ontherightsideofacleanwebpagemockup6676994054500999142.jpg)                                   | **[Floating Dock Smart Iframe Modal](https://debeatzgh1.github.io/-Floating-Dock-Smart-Iframe-Modal/)**                                                      | A modern floating dock with colorful round icons and iframe modal integration.                                      | [🔗 View Demo](https://debeatzgh1.github.io/-Floating-Dock-Smart-Iframe-Modal/)                                  |
| ![Tailwind Homepage](https://debeatzgh.wordpress.com/wp-content/uploads/2025/08/createamodernandcleanthumbnailforawebdevelopmentproducttitledmodernhomepagestylingtemplatewithtailwindcss3420170625469385526.jpg)                                          | **[Modern Homepage Styling with TailwindCSS](https://debeatzgh1.github.io/Modern-homepage-styling-with-TailwindCSS-/)**                                      | A clean and modern homepage layout template styled with TailwindCSS.                                                | [🔗 View Demo](https://debeatzgh1.github.io/Modern-homepage-styling-with-TailwindCSS-/)                          |
| ![TechAdapt Solutions](https://debeatzgh.wordpress.com/wp-content/uploads/2025/08/wp-17550417188267308669484942620808.jpg)                                                                                                                                 | **[TechAdapt Solutions – Strategies for Modern Startups](https://debeatzgh1.github.io/TechAdapt-Solutions-Strategies-for-Modern-Startups-and-Individuals/)** | Practical strategies, resources, and tools for startups and individuals adapting to the modern digital world.       | [🔗 View Demo](https://debeatzgh1.github.io/TechAdapt-Solutions-Strategies-for-Modern-Startups-and-Individuals/) |

---

## 🛠️ Features

* ✅ Fully responsive designs
* ✅ Blogger-friendly & easy to embed
* ✅ Lightweight, no heavy dependencies
* ✅ Includes floating buttons, modals, and animations
* ✅ Perfect for enhancing engagement & monetization

---

## 📌 Explore More Scripts

👉 Check out the full curated collection here:
[**Firebase Curated Front-End Components**](https://github.com/debeatzgh1/firebase-front-end-components)

---

## 💡 Contribution

Want to suggest improvements or add your own scripts?

* Open an **issue**
* Submit a **pull request**
* Share your ideas in the discussions

---

## 📜 License

This project is released under the **MIT License** – free to use, modify, and share with attribution.

---

✨ Designed for creators, bloggers, and developers who want to level up their Blogger sites with modern UI components.

---


# 🌐 Personal Portfolio Website

A simple and responsive personal portfolio website built with **HTML, CSS, and JavaScript**.  
This project is perfect for showcasing your skills, projects, and contact information.  

Live Demo 👉 [View Portfolio](https://debeatzgh.github.io/portfolio-site/)

---

## ✨ Features
- Responsive design (works on mobile & desktop)  
- Navigation bar with smooth scrolling  
- Hero section with intro & call-to-action button  
- About section with bio details  
- Projects section with cards  
- Contact section with email & social links  
- **Dark mode toggle** 🌙☀️  

---

## 🛠️ Technologies Used
- **HTML5** – Structure  
- **CSS3** – Styling & Responsive design  
- **JavaScript (Vanilla)** – Interactivity (dark mode toggle)  
- **GitHub Pages** – Free hosting & deployment  

---

## 🚀 Getting Started
To run this project locally:  

1. Clone the repository:
   ```bash
   git clone https://github.com/debeatzgh1/portfolio-site.git

# 🚀 DeBeatzGH – AI Tools & Side Hustle Hub  

![DeBeatzGH Thumbnail](https://debeatzgh.wordpress.com/wp-content/uploads/2025/08/designamodernminimalisticdesignfeaturinganai-themedicon28likeabraincircuitorrobot29overlaidwithdebeatzghoraitoolshustles6089986211026037047.jpg)  

## 🌟 About  
Welcome to **[DeBeatzGH](https://debeatzgh.wordpress.com/)** — your go-to hub for **AI tools, side hustle strategies, blogging resources, and digital growth guides**.  

Our platform is built to help **students, creators, startups, and professionals** unlock the power of AI, monetize their skills, and thrive in today’s digital economy.  

### ✨ What You’ll Find  
- 💡 Explore **AI prompts, tools, and hacks**  
- 📈 Discover **side hustle strategies & online income ideas**  
- ✍️ Access **blogging & digital business guides**  
- 🚀 Stay ahead with **regular updates and fresh insights**  

---

## 👉 Get Started  
🔥 **Start your journey today → [Visit DeBeatzGH]([https://debeatzgh.wordpress.com/](https://www.patreon.com/debeatzgh/collections))**  

---


<!-- README: DebeatzGH Digital Store (HTML-friendly for GitHub) -->
<div align="center">
  <a href="https://www.socialcreator.com/debeatzgh" target="_blank" rel="noopener">
    <img
      src="https://debeatzgh.wordpress.com/wp-content/uploads/2025/08/designadigitalproductse-commerceonlinedeals3545265155247625100.jpg"
      alt="DebeatzGH Digital Store"
      style="max-width:100%; border-radius:16px;"
    />
  </a>

  <h1 style="margin-top: 14px;">DebeatzGH Digital Store</h1>
  <p style="max-width:780px;">
    Your hub for AI insights, tech tutorials, side-hustle playbooks, and productivity tools.
    Learn, build, and launch digital projects faster.
  </p>

  <!-- CTAs -->
  <p>
    <a href="https://www.socialcreator.com/debeatzgh" target="_blank" rel="noopener"
       style="display:inline-block; padding:10px 16px; margin:4px; border-radius:999px; text-decoration:none; font-weight:600; border:1px solid #2563eb;">
      🚀 View Live App
    </a>
    <a href="https://github.com/debeatzgh1/Personal-Portfolio-site-" target="_blank" rel="noopener"
       style="display:inline-block; padding:10px 16px; margin:4px; border-radius:999px; text-decoration:none; font-weight:600; border:1px solid #111827;">
      ⭐ Star this Repo
    </a>
  </p>
</div>

<hr/>

<h2>Overview</h2>
<p>
  <strong>DebeatzGH</strong> helps beginners and creators build profitable digital assets:
  blogs, affiliate funnels, AI-assisted content, and more. Explore tutorials, tools, and
  ready-to-use components to speed up your workflow.
</p>

<h2>Features</h2>
<ul>
  <li><strong>AI & Tech Learning:</strong> Bite-sized guides for modern tools and workflows.</li>
  <li><strong>Side-Hustle Playbooks:</strong> Practical steps to validate and launch ideas.</li>
  <li><strong>Productivity Toolkit:</strong> Reusable widgets, templates, and scripts.</li>
  <li><strong>Beginner-Friendly:</strong> Clear explanations, curated resources, and examples.</li>
</ul>

<h2>Quick Start</h2>
<ol>
  <li>Clone:
    <pre><code>git clone https://github.com/debeatzgh1/Personal-Portfolio-site-</code></pre>
  </li>
  <li>Enter folder:
    <pre><code>cd debeatzgh</code></pre>
  </li>
  <li>Install deps (adjust to your stack):
    <pre><code># Node
npm install
npm run dev

# or Python
pip install -r requirements.txt
python app.py</code></pre>
  </li>
  <li>Open in browser:
    <pre><code>http://localhost:3000</code></pre>
  </li>
</ol>

<h2>Project Links</h2>
<ul>
  <li>🌐 Live App: <a href="https://www.socialcreator.com/debeatzgh" target="_blank" rel="noopener">socialcreator.com/debeatzgh</a></li>
  <li>🖼️ Thumbnail: <a href="https://debeatzgh.wordpress.com/wp-content/uploads/2025/08/designadigitalproductse-commerceonlinedeals3545265155247625100.jpg" target="_blank" rel="noopener">View image</a></li>
</ul>

<h2>Contributing</h2>
<p>
  Contributions are welcome! Open an issue for bugs or ideas. For changes, fork the repo,
  create a feature branch, and submit a pull request.
</p>

<h2>License</h2>
<p>
  Released under the <a href="./LICENSE">MIT License</a>.
</p>

<hr/>

<div align="center">
  <p><em>If this project helps you, consider giving it a star. It really helps! ⭐</em></p>
  <p>
    <a href="https://www.socialcreator.com/debeatzgh/?s=314768" target="_blank" rel="noopener"
       style="display:inline-block; padding:10px 16px; margin-top:6px; border-radius:10px; text-decoration:none; font-weight:600; border:1px solid #2563eb;">
      PRODUCTS →
    </a>
  </p>
</div>

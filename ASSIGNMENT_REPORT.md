# COLLEGE ASSIGNMENT SUBMISSION
## UNIT – II: HTML & HTML5
**Student Name:** Safi Nasir Zaidi  
**Course:** Bachelor of Computer Applications (BCA) / B.Tech Computer Science  
**Subject:** Web Technologies / Internet Concepts & Web Design  
**Unit Focus:** HTML Structure, Forms, Tables, Images, Accessibility, Navigation, Metadata, Character Entities, Frames vs CSS Layout, and HTML5 Semantics.  

---

## TABLE OF CONTENTS
1. [Question 1: Personal Profile Webpage](#question-1-personal-profile-webpage)
2. [Question 2: University Timetable (Table with Rowspan & Colspan)](#question-2-university-timetable)
3. [Question 3: Online Student Registration Form (HTML5 Controls)](#question-3-online-student-registration-form)
4. [Question 4: Image Gallery with Accessible Descriptions](#question-4-image-gallery-with-accessible-descriptions)
5. [Question 5: Department Navigation Page (Internal vs External Links)](#question-5-department-navigation-page)
6. [Question 6: HTML5 Semantic Department Webpage](#question-6-html5-semantic-department-webpage)
7. [Question 7: Character Entity Challenge](#question-7-character-entity-challenge)
8. [Question 8: Framesets: Old Approach vs Modern CSS Layout](#question-8-framesets-old-approach-vs-modern-css-layout)
9. [Viva-Voce / Oral Exam Preparation Questions & Answers](#viva-voce-preparation)

---

### QUESTION 1: Personal Profile Webpage
**Question Statement:**  
*Design a complete HTML profile page for a student. It should contain a heading hierarchy, introduction, education details, skills, hobbies, an image, hyperlinks and a footer. Use meaningful HTML structure and explain the purpose of the major elements.*  
*Task type: Practical + HTML*

#### 1. Code Implementation (`q1_profile.html`)
The webpage uses a clean structural outline:
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Student Personal Profile</title>
</head>
<body>
    <header>
        <img src="avatar.svg" alt="Portrait photo of Safi Nasir Zaidi" width="140" height="140">
        <h1>Safi Nasir Zaidi</h1>
        <p>BCA Student | Aspiring Full Stack Web Developer</p>
    </header>

    <main>
        <section id="about">
            <h2>1. About Me</h2>
            <p>I am Safi Nasir Zaidi, a passionate computer applications student...</p>
        </section>

        <section id="education">
            <h2>2. Educational Qualifications</h2>
            <table>
                <thead>
                    <tr><th>Course</th><th>Institution</th><th>Year</th><th>Score</th></tr>
                </thead>
                <tbody>
                    <tr><td>BCA</td><td>ABC University</td><td>2024-2027</td><td>8.8 CGPA</td></tr>
                </tbody>
            </table>
        </section>

        <section id="skills">
            <h2>3. Technical Skills</h2>
            <h3>Web Technologies</h3>
            <ul><li>HTML5</li><li>CSS3</li><li>JavaScript</li></ul>
        </section>

        <section id="hobbies">
            <h2>4. Interests & Hobbies</h2>
            <ol>
                <li>Competitive Programming</li>
                <li>Open-Source Web Development</li>
            </ol>
        </section>

        <section id="contact">
            <h2>5. Connect With Me</h2>
            <a href="https://github.com" target="_blank" rel="noopener noreferrer">GitHub</a>
            <a href="mailto:safi.zaidi@example.edu">Send Email</a>
        </section>
    </main>

    <footer>
        <p>&copy; 2026 Safi Nasir Zaidi. Built with semantic HTML5.</p>
    </footer>
</body>
</html>
```

#### 2. Explanation of Major HTML Elements Used
* **`<!DOCTYPE html>`:** Declares the document type and tells modern web browsers to render the page adhering strictly to the HTML5 specification (standard mode) rather than quirks mode.
* **`<html lang="en">`:** Root element wrapping all HTML code. The `lang="en"` attribute specifies English as the primary natural language, allowing screen readers to apply proper pronunciation rules and search engines to index language properly.
* **`<head>`:** Contains non-visual metadata, title, character encoding (`UTF-8`), and mobile responsive viewport settings (`<meta name="viewport" content="width=device-width, initial-scale=1.0">`).
* **`<h1>` to `<h3>`:** Heading hierarchy. `<h1>` represents the single most important page subject (the student's name); `<h2>` denotes major sections (Education, Skills); `<h3>` represents sub-categories. This hierarchy forms the document outline for screen readers and SEO spiders.
* **`<main>`:** Identifies the unique central body content of the webpage, distinct from repetitive headers or footers.
* **`<table>`:** Represents structured tabular data (education record) with headers (`<th>`) and rows (`<tr>`).
* **`<ul>` and `<ol>`:** Unordered (`<ul>`) lists items where sequence does not matter (Skills); Ordered (`<ol>`) lists sequential or numbered rankings (Hobbies/Steps).
* **`<a>` (Anchor):** Establishes hyperlinks. Supports external URLs, anchors within the document, email clients (`mailto:`), and telephone dialers (`tel:`).
* **`<footer>`:** The concluding structural container holding copyright notices, author credits, and back links.

---

### QUESTION 2: University Timetable
**Question Statement:**  
*Create an HTML timetable for a BCA class using table elements. Include days, periods, subjects, faculty/lab information and suitable use of rowspan/colspan where required. Explain why tables are appropriate for this data.*  
*Task type: Practical + Table*

#### 1. Code Implementation (`q2_timetable.html`)
Key structure utilizing `rowspan` and `colspan`:
```html
<table border="1">
    <caption>Weekly Master Timetable (Section BCA-3A)</caption>
    <thead>
        <tr>
            <th scope="col">Day / Time</th>
            <th scope="col">Period 1<br>(9-10)</th>
            <th scope="col">Period 2<br>(10-11)</th>
            <th scope="col">Period 3<br>(11-12)</th>
            <th scope="col">Period 4<br>(12-1)</th>
            <th scope="col">Lunch<br>(1-1:45)</th>
            <th scope="col">Period 5<br>(1:45-2:45)</th>
            <th scope="col">Period 6<br>(2:45-3:45)</th>
            <th scope="col">Period 7<br>(3:45-4:45)</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <th scope="row">Monday</th>
            <td>Data Structures</td>
            <td>DBMS</td>
            <td>Web Tech</td>
            <td>Discrete Math</td>
            <!-- Vertical span across 6 days -->
            <td rowspan="6" class="lunch">LUNCH BREAK</td>
            <!-- Horizontal span across 2 consecutive lab hours -->
            <td colspan="2">Web Technology Lab (HTML5/CSS3)</td>
            <td>Digital Electronics</td>
        </tr>
        <!-- Tuesday through Saturday rows follow similar structure -->
    </tbody>
    <tfoot>
        <tr>
            <td colspan="9">Note: Minimum 75% attendance mandatory.</td>
        </tr>
    </tfoot>
</table>
```

#### 2. Why Tables are Appropriate for This Data
1. **True Two-Dimensional Matrix Relationship:** A timetable is inherently tabular. Every schedule slot exists at the intersection of a **Row coordinate** (Day of the Week: Monday–Saturday) and a **Column coordinate** (Time Slot: 9:00 AM – 4:45 PM). The `<table>` element is explicitly designed to establish this two-dimensional relationship in the browser's Document Object Model.
2. **Accessibility for Visually Impaired Users:** Assistive tools (screen readers like NVDA/JAWS) use `<th>` elements with `scope="row"` and `scope="col"` to announce context dynamically. When a user navigates to a cell, the screen reader automatically announces: *"Monday, Period 5, Web Technology Lab"*. This level of accessibility cannot be achieved with generic unsemantic layout boxes.
3. **Natural Multi-Cell Spanning with `rowspan` and `colspan`:**
   * **`rowspan="6"`:** Merges the Lunch Break cell vertically across all six working days, avoiding redundant duplicate columns and accurately modeling real-world campus scheduling.
   * **`colspan="2"` or `colspan="3"`:** Merges consecutive periods into a single continuous block for Practical Laboratory and Project sessions.
4. **Data vs. Layout Principle:** While using `<table>` for overall page layout (navbars, columns) is considered an anti-pattern, `<table>` remains the standard for genuine datasets (schedules, timetables, grade cards, and financial matrices).

---

### QUESTION 3: Online Student Registration Form
**Question Statement:**  
*Design an HTML student registration form containing name, email, password, gender, course, date of birth, hobbies, address, file upload and submit/reset controls. Use labels and suitable HTML5 input types.*  
*Task type: Practical + Form*

#### 1. Code Implementation (`q3_registration.html`)
```html
<form action="/submit-registration" method="POST" enctype="multipart/form-data">
    <fieldset>
        <legend>Student Registration Form</legend>

        <!-- Name -->
        <label for="fullname">Full Name:</label>
        <input type="text" id="fullname" name="fullname" required minlength="3" placeholder="Safi Nasir Zaidi">

        <!-- Email -->
        <label for="email">Email Address:</label>
        <input type="email" id="email" name="email" required placeholder="safi.zaidi@example.edu">

        <!-- Password -->
        <label for="password">Password:</label>
        <input type="password" id="password" name="password" required minlength="8">

        <!-- Gender Radio -->
        <p>Gender:</p>
        <input type="radio" id="gender-m" name="gender" value="male" required>
        <label for="gender-m">Male</label>
        <input type="radio" id="gender-f" name="gender" value="female">
        <label for="gender-f">Female</label>

        <!-- Course Dropdown -->
        <label for="course">Course Applied:</label>
        <select id="course" name="course" required>
            <option value="">-- Choose Program --</option>
            <option value="bca">Bachelor of Computer Applications (BCA)</option>
            <option value="mca">Master of Computer Applications (MCA)</option>
        </select>

        <!-- Date of Birth -->
        <label for="dob">Date of Birth:</label>
        <input type="date" id="dob" name="dob" min="1995-01-01" max="2012-12-31" required>

        <!-- Hobbies Checkboxes -->
        <p>Hobbies:</p>
        <input type="checkbox" id="h-coding" name="hobbies" value="coding">
        <label for="h-coding">Coding</label>
        <input type="checkbox" id="h-sports" name="hobbies" value="sports">
        <label for="h-sports">Sports</label>

        <!-- Address Textarea -->
        <label for="address">Residential Address:</label>
        <textarea id="address" name="address" rows="3" required></textarea>

        <!-- File Upload -->
        <label for="photo">Upload Student Photo / Certificate:</label>
        <input type="file" id="photo" name="photo" accept=".jpg,.png,.pdf" required>

        <!-- Controls -->
        <button type="submit">Submit Registration</button>
        <button type="reset">Reset Form</button>
    </fieldset>
</form>
```

#### 2. Key Concepts & Explanation
* **`<label for="id">`:** The `for` attribute binds a label directly to its input's `id`. This expands the clickable touch zone (crucial for checkboxes/radio buttons on mobile) and ensures screen readers announce the input prompt when focusing.
* **HTML5 Specific Types:**
  * `type="email"`: Validates syntax according to RFC email standards and evokes an `@`-optimized mobile keyboard.
  * `type="password"`: Obfuscates input characters to protect against shoulder surfing.
  * `type="date"`: Invokes the operating system's native calendar picker widget.
  * `type="file"`: Spawns the system file dialog to choose documents.
* **`enctype="multipart/form-data"`:** Required when a form includes file inputs (`<input type="file">`). Without this attribute, the browser transmits only the filename rather than the binary file bytes.
* **Client-Side Validation:** Attributes such as `required`, `minlength`, `maxlength`, `min`, `max`, and `pattern` validate user data before network transmission, reducing unnecessary server round-trips.

---

### QUESTION 4: Image Gallery with Accessible Descriptions
**Question Statement:**  
*Create a small HTML image gallery for a college event. Each image must have meaningful alternative text and a caption where appropriate. Explain how image size and accessibility affect user experience.*  
*Task type: Practical + Accessibility*

#### 1. Code Implementation (`q4_gallery.html`)
```html
<div class="gallery-grid">
    <figure>
        <img src="hackathon.jpg" alt="Undergraduate students collaborating intensely on laptops during the 24-hour CodeSprint Hackathon" width="400" height="250" loading="lazy">
        <figcaption>
            <strong>24-Hour CodeSprint Hackathon:</strong> Students developing AI solutions for healthcare and smart farming.
        </figcaption>
    </figure>
    <figure>
        <img src="robowars.jpg" alt="Two metal combat robots clashing in the center of the reinforced steel battle ring" width="400" height="250" loading="lazy">
        <figcaption>
            <strong>RoboWars Quarterfinals:</strong> Autonomous and remote-controlled bots clashing in the arena.
        </figcaption>
    </figure>
</div>
```

#### 2. How Image Size & Accessibility Affect User Experience
1. **Accessibility Impact:**
   * **Assistive Screen Readers:** Visually impaired individuals navigate web interfaces through audible descriptions. A well-written `alt` attribute communicates the mood, subject, and action within the image. Missing `alt` tags cause screen readers to read incomprehensible filenames (e.g., `IMG_49201.jpg`), destroying the user experience.
   * **Graceful Degradation / Broken Connections:** If images fail to load due to 404 errors or weak 2G/3G mobile connectivity, the browser displays the `alt` text in place of the image, ensuring no core information is lost.
   * **Semantic Figure Association:** `<figure>` and `<figcaption>` programmatically bind the image and its explanatory caption together in the browser's accessibility tree.
2. **Image Sizing & Performance Impact:**
   * **Core Web Vitals & Largest Contentful Paint (LCP):** Heavy, uncompressed images are the leading cause of slow page loading. A delay in LCP directly triggers visitor bounce rates.
   * **Cumulative Layout Shift (CLS):** Omitting `width` and `height` attributes causes surrounding text to unexpectedly jump when images finish downloading. Specifying dimensions reserves space immediately.
   * **Bandwidth Optimization:** Using modern responsive attributes (`srcset`, `<picture>`, and `loading="lazy"`) saves mobile data by deferring off-screen images until scrolled into view.

---

### QUESTION 5: Department Navigation Page
**Question Statement:**  
*Create an HTML page containing a professional navigation menu for Home, About, Courses, Faculty, Labs, Assignments, Notices, Gallery and Contact. Use appropriate hyperlinks and explain internal vs external links.*  
*Task type: Practical + Navigation*

#### 1. Code Implementation (`q5_navigation.html`)
```html
<!-- Sticky Main Nav -->
<nav class="main-nav">
    <ul>
        <li><a href="#home">Home</a></li>
        <li><a href="#about">About</a></li>
        <li><a href="#courses">Courses</a></li>
        <li><a href="#faculty">Faculty</a></li>
        <li><a href="#labs">Labs</a></li>
        <li><a href="#assignments">Assignments</a></li>
        <li><a href="#notices">Notices</a></li>
        <li><a href="#gallery">Gallery</a></li>
        <li><a href="#contact">Contact</a></li>
        <!-- External Hyperlinks -->
        <li><a href="https://www.w3.org" target="_blank" rel="noopener noreferrer">University Portal &nearr;</a></li>
    </ul>
</nav>

<!-- Content Sections with matching IDs -->
<section id="courses">
    <h2>Courses Offered</h2>
    <p>BCA, MCA, and Research Programs.</p>
    <a href="#top">&uarr; Back to Top</a>
</section>
```

#### 2. Internal vs. External Links Comparison
| Parameter | Internal Links (Bookmarks / Relative) | External Links (Absolute URLs) |
|---|---|---|
| **Definition** | Navigates within the current document (fragment identifier) or to another page on the same domain. | Navigates to a foreign domain or external web server. |
| **Syntax** | `href="#section-id"` or `href="about.html"` | `href="https://example.edu/path"` |
| **Target Behavior** | Typically `target="_self"` (replaces view in current tab). | Typically `target="_blank"` (opens a new browsing tab). |
| **Security Risk** | None; inherits the same origin security context. | **Tabnabbing risk:** Must use `rel="noopener noreferrer"` to prevent malicious pages from hijacking `window.opener`. |
| **Offline Portability** | Functions seamlessly in local offline folders and staging environments. | Requires active internet connection and DNS resolution. |

---

### QUESTION 6: HTML5 Semantic Department Page
**Question Statement:**  
*Design the structure of a department webpage using header, nav, main, section, article, aside and footer. Explain the purpose of each semantic element and why semantic structure is better than using generic containers everywhere.*  
*Task type: Practical + HTML5*

#### 1. Code Implementation (`q6_semantic_dept.html`)
```html
<header>
    <h1>School of Computing Sciences</h1>
    <p>Department of Computer Applications</p>
</header>

<nav aria-label="Department Navigation">
    <ul>
        <li><a href="#overview">Overview</a></li>
        <li><a href="#news">Newsroom</a></li>
    </ul>
</nav>

<main>
    <section id="overview">
        <h2>Department Overview</h2>
        <p>Committed to providing high-quality computer education...</p>
    </section>

    <section id="news">
        <h2>Department Newsroom</h2>
        <article>
            <h3>BCA Students Win Smart India Hackathon</h3>
            <time datetime="2026-10-28">October 28, 2026</time>
            <p>Our student team secured 1st prize in the national AI track...</p>
        </article>
    </section>

    <aside>
        <h3>Notice Board</h3>
        <p>Assignment submission deadline: Nov 12, 2026.</p>
    </aside>
</main>

<footer>
    <p>&copy; 2026 Department of Computer Applications. All Rights Reserved.</p>
</footer>
```

#### 2. Purpose of Each Semantic Element
* **`<header>`:** Houses introductory branding, headings, department logos, and site-wide search bars.
* **`<nav>`:** Encapsulates the primary collection of navigation hyperlinks.
* **`<main>`:** Wraps the unique central substance of the document. Only one non-hidden `<main>` is allowed per webpage.
* **`<section>`:** Defines a thematic standalone grouping of content, typically beginning with a heading.
* **`<article>`:** Represents a completely independent, reusable, and syndicatable item of content (e.g. news story, technical blog post, announcement).
* **`<aside>`:** Encloses auxiliary information tangentially related to surrounding content (sidebars, notices, callouts).
* **`<footer>`:** Contains legal credits, copyright notices, author contact details, and institutional disclosures.

#### 3. Why Semantic HTML Trumps Generic Containers (`<div>` and `<span>`)
1. **Screen Reader Landmark Navigation:** Semantic elements create landmark regions. Visually impaired users can hit a key to skip straight to `<main>`, avoiding having to tab through 50 navigation links repeatedly.
2. **Search Engine Optimization (SEO):** Web search engines assign higher semantic weight to keywords within `<main>`, `<h1>`, and `<article>` than to boilerplate headers or sidebars.
3. **Eliminating "Div Soup":** Codebases dominated by nested generic `<div>` tags are notoriously difficult to read and debug. Semantic tags clearly communicate intent.
4. **Browser Reader Modes:** Safari, Chrome, and Firefox reader views look specifically for the `<article>` tag to generate clean, distraction-free reading formats.

---

### QUESTION 7: Character Entity Challenge
**Question Statement:**  
*Create an HTML page that displays mathematical symbols, copyright information, quotation marks, angle brackets and other special characters correctly. Identify the character references used and explain why they are useful.*  
*Task type: Practical + HTML*

#### 1. Code Implementation (`q7_entities.html`)
```html
<p><strong>Math Formula:</strong> Area = &pi; &times; r&sup2;</p>
<p><strong>Quadratic Roots:</strong> x = (-b &plusmn; &radic;(b&sup2; - 4ac)) &divide; 2a</p>
<p><strong>Safe Code Display:</strong> &lt;script&gt;alert(&quot;Safe!&quot;)&lt;/script&gt;</p>
<p><strong>Copyright & Quotes:</strong> &ldquo;Code is poetry.&rdquo; &mdash; &copy; 2026 TechCorp&reg;</p>
<p><strong>Currency:</strong> Total: &#8377; 4,999 (Indian Rupee) | &euro; 55</p>
```

#### 2. Master Entity Reference Table
| Category | Rendered Symbol | Named Entity | Numeric Entity | Description |
|---|---|---|---|---|
| **Reserved** | `<` | `&lt;` | `&#60;` | Less than (Angle bracket open) |
| **Reserved** | `>` | `&gt;` | `&#62;` | Greater than (Angle bracket close) |
| **Reserved** | `&` | `&amp;` | `&#38;` | Ampersand |
| **Reserved** | `"` | `&quot;` | `&#34;` | Double quotation mark |
| **Reserved** | `'` | `&apos;` | `&#39;` | Single quote / Apostrophe |
| **Math** | `±` | `&plusmn;` | `&#177;` | Plus-minus sign |
| **Math** | `×` | `&times;` | `&#215;` | Multiplication sign |
| **Math** | `÷` | `&divide;` | `&#247;` | Division sign |
| **Math** | `√` | `&radic;` | `&#8730;` | Square root (Radical) |
| **Math** | `∞` | `&infin;` | `&#8734;` | Infinity symbol |
| **Math** | `π` | `&pi;` | `&#960;` | Greek letter Pi |
| **Legal** | `©` | `&copy;` | `&#169;` | Copyright symbol |
| **Legal** | `®` | `&reg;` | `&#174;` | Registered trademark symbol |
| **Legal** | `™` | `&trade;` | `&#8482;` | Trademark symbol |
| **Quotes** | `“` | `&ldquo;` | `&#8220;` | Left curly double quote |
| **Quotes** | `”` | `&rdquo;` | `&#8221;` | Right curly double quote |
| **Quotes** | `—` | `&mdash;` | `&#8212;` | Em dash |
| **Currency**| `₹` | &mdash; | `&#8377;` | Indian Rupee symbol |
| **Currency**| `€` | `&euro;` | `&#8364;` | Euro symbol |

#### 3. Why Character References are Useful
1. **Avoiding Parser Collisions:** If `<script>` or `<p>` is typed directly, the browser parses it as code. Writing `&lt;script&gt;` displays the code as literal text.
2. **Accessing Non-Keyboard Characters:** Standard physical keyboards do not have buttons for mathematical signs (√, ∞, π) or intellectual property symbols (©, ®, ™).
3. **Preventing Encoding Corruption (Mojibake):** If files are transferred between servers with mismatched character encodings (e.g. ASCII vs UTF-8), raw special characters can corrupt into symbols like `Â©`. Character entities use standard ASCII characters, guaranteeing universal rendering across all platforms.

---

### QUESTION 8: Framesets: Old Approach vs Modern CSS Layout
**Question Statement:**  
*Explain how traditional frames/framesets were used to divide a webpage and discuss their limitations. Then design a modern page structure using semantic HTML and CSS-based layout instead.*  
*Task type: Concept + Comparison*

#### 1. Legacy HTML 4.01 Frameset Architecture
In the 1990s, HTML allowed splitting the browser screen into separate physical HTML files loaded simultaneously using `<frameset>`:
```html
<!-- Deprecated HTML 4.01 Frameset -->
<!DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 4.01 Frameset//EN">
<html>
  <frameset rows="20%, 80%">
    <frame src="header.html" name="topFrame">
    <frameset cols="25%, 75%">
      <frame src="navigation.html" name="menuFrame">
      <frame src="content.html" name="mainFrame">
    </frameset>
  </frameset>
</html>
```

#### 2. Seven Fatal Limitations of Traditional Framesets
1. **Broken URLs and Bookmarking:** The address bar permanently showed `index.html`. Users could not bookmark, refresh, or copy a URL to a specific subpage.
2. **Broken Browser Back/Forward Buttons:** Clicking "Back" often backed out of the entire site or flipped an unintended frame.
3. **Search Engine Optimization (SEO) Failure:** Crawlers indexed individual subpages in isolation. A visitor arriving from Google would land on an orphan frame devoid of top headers or menus.
4. **Poor Accessibility:** Screen readers struggled to manage multiple simultaneous window documents and frame contexts.
5. **Mobile Unfriendliness:** Frames were rigid and did not reflow gracefully on modern mobile screens.
6. **Printing Nightmares:** Browsers typically printed only whichever sub-frame had active focus, cutting off content.
7. **Official Deprecation:** W3C and WHATWG officially obsoleted `<frameset>`, `<frame>`, and `<noframes>` in HTML5.

#### 3. Modern CSS Grid & Semantic HTML5 Equivalent (`q8_frames_vs_modern.html`)
Modern layouts unify all structural sections within a single DOM, styled flexibly using CSS Grid:
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <style>
        .layout-grid {
            display: grid;
            grid-template-areas:
                "header header"
                "sidebar main"
                "footer footer";
            grid-template-columns: 250px 1fr;
            min-height: 100vh;
            gap: 15px;
        }
        @media (max-width: 768px) {
            .layout-grid {
                grid-template-areas: "header" "sidebar" "main" "footer";
                grid-template-columns: 1fr;
            }
        }
        header { grid-area: header; }
        aside  { grid-area: sidebar; }
        main   { grid-area: main; }
        footer { grid-area: footer; }
    </style>
</head>
<body class="layout-grid">
    <header>Department Portal Banner</header>
    <aside>Navigation Sidebar</aside>
    <main>Central Content</main>
    <footer>Copyright & Disclosures</footer>
</body>
</html>
```

---

### VIVA-VOCE PREPARATION
*(Frequently asked viva questions for Unit-II: HTML & HTML5)*

* **Q1: What is the primary difference between HTML and HTML5?**  
  *Answer:* HTML5 introduces native semantic elements (`<header>`, `<nav>`, `<main>`, `<article>`, `<aside>`, `<footer>`), built-in multimedia support (`<video>`, `<audio>`), powerful form input types (`email`, `date`, `color`), Canvas/SVG graphics, and deprecates outdated elements like `<frameset>`, `<center>`, and `<font>`.

* **Q2: Why must forms have `enctype="multipart/form-data"` for file uploads?**  
  *Answer:* The default encoding `application/x-www-form-urlencoded` encodes form data as URL key-value text pairs, which cannot handle binary file streams. `multipart/form-data` splits the transmission into multiple MIME parts, allowing binary file uploads alongside textual form fields.

* **Q3: What is the difference between `rowspan` and `colspan`?**  
  *Answer:* `colspan` merges two or more adjacent table cells horizontally across multiple columns. `rowspan` merges cells vertically across multiple rows.

* **Q4: Why is `alt` attribute mandatory on `<img>` tags?**  
  *Answer:* For accessibility (enabling screen readers to describe images to visually impaired users), network resilience (displaying fallback text if the image link breaks), and SEO indexing. For purely decorative images, `alt=""` (empty) is used to tell screen readers to skip it.

* **Q5: What is the significance of `rel="noopener noreferrer"` on links with `target="_blank"`?**  
  *Answer:* It closes a critical security vulnerability known as reverse tabnabbing, preventing the opened page from manipulating the original window via `window.opener.location`.

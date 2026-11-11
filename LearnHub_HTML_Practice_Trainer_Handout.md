# LearnHub HTML Practice Pages

This folder contains two plain HTML pages with no CSS styling.

- `index.html`: Main Learning Management Portal page with examples of common HTML tags.
- `registration-info.html`: A second page demonstrating page-to-page navigation and a simple enquiry form.

Open `index.html` in a browser. The `images/` and `media/` paths are illustrative placeholders; add your own files if you want those examples to display/play.

## Trainer notes
- This is a teaching example, not a production-ready registration system.
- The demo button uses inline JavaScript only to demonstrate a button action; it can be removed if teaching HTML-only markup strictly.
- For a Django POST form, add `{% csrf_token %}` inside the form in a Django template. That syntax is a Django template tag, not HTML.
- For a file upload handled by Django, use `method="post"`, `enctype="multipart/form-data"`, and read the uploaded file from `request.FILES` after validating it on the server.

## Page 1: index.html

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>LearnHub - Learning Management Portal</title>
    <meta name="description" content="Explore courses, view lessons and manage your learning journey with LearnHub.">
</head>
<body>

    <!-- PAGE HEADER -->
    <header>
        <h1>LearnHub</h1>
        <p>Your learning journey starts here.</p>

        <nav aria-label="Main navigation">
            <a href="#home">Home</a> |
            <a href="#courses">Courses</a> |
            <a href="#schedule">Schedule</a> |
            <a href="#register">Register</a> |
            <a href="#contact">Contact</a>
        </nav>
        <hr>
    </header>

    <!-- MAIN PAGE CONTENT -->
    <main id="home">

        <section>
            <h2>Welcome to LearnHub</h2>
            <p>
                LearnHub is a <strong>Learning Management Portal</strong>
                where students can explore courses and learn new skills.
            </p>
            <p>
                Our goal is to help students become
                <em>industry-ready developers</em>.
            </p>
            <p>
                <mark>Admissions are open!</mark>
                <small>Limited seats are available for the next batch.</small>
            </p>

            <figure>
                <img src="images/classroom.jpg"
                     alt="Students attending a web development class"
                     width="500"
                     height="250">
                <figcaption>Students learning web development.</figcaption>
            </figure>

            <p>
                Course fee: <del>₹20,000</del> <strong>₹15,000</strong>
            </p>
            <p>
                Example of text formatting:
                H<sub>2</sub>O and 2<sup>3</sup> = 8.
            </p>
        </section>

        <hr>

        <!-- COURSE LIST -->
        <section id="courses">
            <h2>Available Courses</h2>

            <article>
                <h3>Python Django Development</h3>
                <p>
                    Learn Python, MySQL, Django and Django REST Framework.
                    <abbr title="Django REST Framework">DRF</abbr> is used
                    to build REST APIs.
                </p>

                <h4>Technologies covered</h4>
                <ul>
                    <li>Python</li>
                    <li>MySQL</li>
                    <li>Django</li>
                    <li>Django REST Framework</li>
                </ul>

                <h4>Learning stages</h4>
                <ol>
                    <li>Python programming</li>
                    <li>Database fundamentals</li>
                    <li>Django development</li>
                    <li>REST API development</li>
                </ol>

                <p>
                    <a href="#register">Enrol in this course</a>
                </p>
            </article>

            <article>
                <h3>Data Analytics</h3>
                <p>Learn to collect, process and understand data.</p>
                <a href="#register">Enquire about this course</a>
            </article>

            <aside>
                <h3>Did you know?</h3>
                <p>Students can learn at their own pace and track lesson progress.</p>
            </aside>
        </section>

        <hr>

        <!-- DESCRIPTION LIST -->
        <section>
            <h2>Common Terms</h2>
            <dl>
                <dt><dfn>HTML</dfn></dt>
                <dd>HyperText Markup Language, used to structure web pages.</dd>

                <dt>API</dt>
                <dd>Application Programming Interface.</dd>

                <dt>Frontend</dt>
                <dd>The part of an application users interact with.</dd>
            </dl>
        </section>

        <hr>

        <!-- COURSE SCHEDULE TABLE -->
        <section id="schedule">
            <h2>Upcoming Batch Schedule</h2>

            <table>
                <caption>Course batch details</caption>
                <thead>
                    <tr>
                        <th scope="col">Course</th>
                        <th scope="col">Batch</th>
                        <th scope="col">Start Date</th>
                        <th scope="col">Status</th>
                    </tr>
                </thead>
                <tbody>
                    <tr>
                        <th scope="row">Python Django</th>
                        <td>Morning</td>
                        <td><time datetime="2026-12-01">1 December 2026</time></td>
                        <td>Open</td>
                    </tr>
                    <tr>
                        <th scope="row">Data Analytics</th>
                        <td>Evening</td>
                        <td><time datetime="2026-12-05">5 December 2026</time></td>
                        <td>Open</td>
                    </tr>
                </tbody>
                <tfoot>
                    <tr>
                        <td colspan="4">Contact the institute for more details.</td>
                    </tr>
                </tfoot>
            </table>
        </section>

        <hr>

        <!-- REGISTRATION FORM -->
        <section id="register">
            <h2>Student Registration</h2>
            <p>Fill in the form to register your interest.</p>

            <form action="/register/" method="post">
                <!-- In a Django template, place {% csrf_token %} here. -->

                <fieldset>
                    <legend>Personal Details</legend>

                    <p>
                        <label for="full_name">Full name:</label>
                        <input type="text"
                               id="full_name"
                               name="full_name"
                               placeholder="Enter your name"
                               minlength="3"
                               maxlength="100"
                               autocomplete="name"
                               required>
                    </p>

                    <p>
                        <label for="email">Email:</label>
                        <input type="email"
                               id="email"
                               name="email"
                               placeholder="name@example.com"
                               autocomplete="email"
                               required>
                    </p>

                    <p>
                        <label for="phone">Phone:</label>
                        <input type="tel"
                               id="phone"
                               name="phone"
                               minlength="10"
                               maxlength="15"
                               autocomplete="tel"
                               required>
                    </p>

                    <p>
                        <label for="password">Create password:</label>
                        <input type="password"
                               id="password"
                               name="password"
                               minlength="8"
                               required>
                    </p>

                    <p>
                        <label for="date_of_birth">Date of birth:</label>
                        <input type="date"
                               id="date_of_birth"
                               name="date_of_birth">
                    </p>

                    <p>
                        <label for="preferred_time">Preferred contact time:</label>
                        <input type="time"
                               id="preferred_time"
                               name="preferred_time">
                    </p>

                    <p>
                        <label for="preferred_meeting">Preferred counselling date and time:</label>
                        <input type="datetime-local"
                               id="preferred_meeting"
                               name="preferred_meeting">
                    </p>

                    <p>
                        <label for="age">Age:</label>
                        <input type="number"
                               id="age"
                               name="age"
                               min="16"
                               max="70"
                               step="1">
                    </p>

                    <p>
                        <label for="website">Portfolio website:</label>
                        <input type="url"
                               id="website"
                               name="website"
                               placeholder="https://example.com">
                    </p>

                    <p>
                        <label for="search_course">Search a course:</label>
                        <input type="search"
                               id="search_course"
                               name="search_course">
                    </p>

                    <p>
                        <label for="course_suggestion">Course suggestion:</label>
                        <input list="course_options"
                               id="course_suggestion"
                               name="course_suggestion">
                        <datalist id="course_options">
                            <option value="Python Django">
                            <option value="Data Analytics">
                            <option value="MERN Stack">
                        </datalist>
                    </p>
                </fieldset>

                <fieldset>
                    <legend>Course Preferences</legend>

                    <p>Select your course:</p>
                    <p>
                        <label for="course">Course:</label>
                        <select id="course" name="course" required>
                            <option value="">Select a course</option>
                            <optgroup label="Development">
                                <option value="django">Python Django</option>
                                <option value="mern">MERN Stack</option>
                            </optgroup>
                            <optgroup label="Analytics">
                                <option value="analytics">Data Analytics</option>
                            </optgroup>
                        </select>
                    </p>

                    <p>Preferred batch:</p>
                    <input type="radio" id="morning" name="batch" value="morning">
                    <label for="morning">Morning</label>

                    <input type="radio" id="evening" name="batch" value="evening">
                    <label for="evening">Evening</label>

                    <p>Skills you already know:</p>
                    <input type="checkbox" id="python" name="skills" value="python">
                    <label for="python">Python</label>

                    <input type="checkbox" id="html" name="skills" value="html">
                    <label for="html">HTML</label>

                    <input type="checkbox" id="mysql" name="skills" value="mysql">
                    <label for="mysql">MySQL</label>

                    <p>
                        <label for="message">Why do you want to join?</label>
                        <textarea id="message"
                                  name="message"
                                  rows="4"
                                  cols="40"
                                  maxlength="500"
                                  placeholder="Write a short message"></textarea>
                    </p>

                    <p>
                        <label for="resume">Upload your resume:</label>
                        <input type="file"
                               id="resume"
                               name="resume"
                               accept=".pdf,.doc,.docx">
                    </p>

                    <p>
                        <label for="profile_color">Choose a profile colour:</label>
                        <input type="color" id="profile_color" name="profile_color">
                    </p>

                    <p>
                        <label for="confidence">Your current confidence in programming:</label>
                        <input type="range"
                               id="confidence"
                               name="confidence"
                               min="0"
                               max="10"
                               value="5">
                    </p>

                    <p>
                        <label for="progress">Registration preparation progress:</label>
                        <progress id="progress" value="60" max="100">60%</progress>
                    </p>

                    <p>
                        <label for="skill_level">Sample skill level indicator:</label>
                        <meter id="skill_level" min="0" max="10" value="7">7 out of 10</meter>
                    </p>

                    <input type="hidden" name="source" value="website">
                </fieldset>

                <p>
                    <input type="checkbox" id="terms" name="terms" value="accepted" required>
                    <label for="terms">I agree to be contacted about this course.</label>
                </p>

                <button type="submit">Submit Registration</button>
                <button type="reset">Clear Form</button>
                <button type="button" onclick="alert('This is a demonstration button.')">
                    Demo Button
                </button>
            </form>
        </section>

        <hr>

        <!-- DETAILS AND SUMMARY -->
        <section>
            <h2>Frequently Asked Questions</h2>

            <details>
                <summary>Do I need programming experience?</summary>
                <p>No. Beginners can start with the fundamentals.</p>
            </details>

            <details>
                <summary>Can I access lessons later?</summary>
                <p>Lesson access depends on the course arrangement.</p>
            </details>
        </section>

        <hr>

        <!-- MEDIA EXAMPLES -->
        <section>
            <h2>Course Introduction</h2>

            <h3>Video lesson</h3>
            <video controls width="400" poster="images/video-poster.jpg">
                <source src="media/course-introduction.mp4" type="video/mp4">
                <track src="media/captions-en.vtt"
                       kind="captions"
                       srclang="en"
                       label="English captions">
                Your browser does not support the video element.
            </video>

            <h3>Audio lesson</h3>
            <audio controls>
                <source src="media/course-introduction.mp3" type="audio/mpeg">
                Your browser does not support the audio element.
            </audio>
        </section>

        <hr>

        <!-- CODE AND PREFORMATTED TEXT -->
        <section>
            <h2>Learn HTML</h2>
            <p>Use the <code>&lt;h1&gt;</code> element for a main heading.</p>

            <pre><code>&lt;h1&gt;Hello Students&lt;/h1&gt;
&lt;p&gt;Welcome to HTML learning.&lt;/p&gt;</code></pre>

            <blockquote cite="https://developer.mozilla.org/">
                Good markup gives web content a meaningful structure.
            </blockquote>

            <p>
                For more information, visit
                <cite><a href="https://developer.mozilla.org/en-US/docs/Web/HTML"
                         target="_blank"
                         rel="noopener">MDN HTML documentation</a></cite>.
            </p>
        </section>

        <hr>

        <!-- CONTACT INFORMATION -->
        <section id="contact">
            <h2>Contact Us</h2>
            <address>
                LearnHub Training Centre<br>
                Thrissur, Kerala, India<br>
                Email: <a href="mailto:info@example.com">info@example.com</a><br>
                Phone: <a href="tel:+910000000000">+91 00000 00000</a>
            </address>
        </section>

    </main>

    <!-- PAGE FOOTER -->
    <footer>
        <hr>
        <p><small>&copy; 2026 LearnHub. All rights reserved.</small></p>
        <a href="#home">Back to top</a>
    </footer>

    <!-- A native dialog example. The open attribute displays it immediately. -->
    <dialog open>
        <p>This is an example of the HTML dialog element.</p>
        <p><small>In a real application, JavaScript can control when a dialog opens and closes.</small></p>
    </dialog>

</body>
</html>

```

## Page 2: registration-info.html

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>LearnHub - Registration Confirmation</title>
    <meta name="description" content="Registration information for LearnHub students.">
</head>
<body>
    <header>
        <h1>LearnHub</h1>
        <nav aria-label="Main navigation">
            <a href="index.html">Home</a>
            <a href="index.html#courses">Courses</a>
            <a href="index.html#register">Register</a>
        </nav>
    </header>

    <main>
        <article>
            <h2>Registration Information</h2>
            <p>
                Thank you for your interest in LearnHub.
                Please review the details below before submitting your enquiry.
            </p>

            <section>
                <h3>What happens next?</h3>
                <ol>
                    <li>Our team reviews your enquiry.</li>
                    <li>A counsellor contacts you.</li>
                    <li>You receive the batch and course details.</li>
                </ol>
            </section>

            <section>
                <h3>Course enquiry form</h3>
                <form action="/enquiry/" method="get">
                    <p>
                        <label for="enquiry_email">Email address:</label>
                        <input type="email"
                               id="enquiry_email"
                               name="email"
                               autocomplete="email"
                               required>
                    </p>
                    <p>
                        <label for="enquiry_course">Course:</label>
                        <select id="enquiry_course" name="course">
                            <option value="django">Python Django</option>
                            <option value="analytics">Data Analytics</option>
                        </select>
                    </p>
                    <button type="submit">Find course information</button>
                </form>
            </section>

            <section>
                <h3>Useful information</h3>
                <p>
                    The course content is updated on
                    <time datetime="2026-11-11">11 November 2026</time>.
                </p>
                <p>For additional information, visit the <a href="index.html">main portal</a>.</p>
            </section>
        </article>
    </main>

    <footer>
        <p><small>LearnHub Student Portal</small></p>
    </footer>
</body>
</html>

```

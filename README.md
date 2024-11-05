# portfolio

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>My Portfolio Website</title>
    <link rel="stylesheet" href="style.css">
    <script src="https://kit.fontawesome.com/84f7706ae3.js" crossorigin="anonymous"></script>
    <link rel="stylesheet" href="https://fonts.googleapis.com/css2?family=Poppins:wght@400;500;600;700&display=swap">
</head>
<body>
    <div id="header">
        <div class="container">
            <nav>
                <img src="images/logoo.png" class="logo">
                <ul id="sidemenu">
                    <li><a href="#header">Home</a></li>
                    <li><a href="#about">About</a></li>
                    <li><a href="#portfolio">Projects</a></li>
                    <li><a href="#contact">Contact</a></li>
                    <i class="fa-sharp fa-solid fa-circle-xmark" onclick="closemenu()" style="font-size: 30px;"></i> 
                  <!-- Adjusted font size here -->
                </ul>
                <i class="fa-solid fa-bars" onclick="openmenu()"></i>
            </nav>
           <div class="header-text">
                <img src="port.jpg" class="profile-pic">
              
  <h1>Hi,I'm Ananya Soorthila</h1>
            </div>
        </div>
    </div>
    <!-----------------about---------- -->
    <div id="about">
        <div class="container">
            <div class="row">
                <div class="about-col-1">
                    <img src="lofi-study-beats-focus-vibe-illustration_863013-147891.avif">
                </div>
                <div class="about-col-2">
                    <h1 class="sub-title">About Me</h1>
                    <br>
                    <div class="tab-titles">
                        <p class="tab-links active-link" onclick="opentab('skills')">Skills</p>
                        <p class="tab-links" onclick="opentab('education')">Education</p>
                    </div>
                    <div class="tab-contents active-tab" id="skills">
                        <ul>
                            <li><span>Technical Skills</span><br>python,c++,machinelearning,C, Java<br>Basics of HTML, CSS<br></li>
                            <li><br><span>Soft Skills</span><br>Communication<br>Problem solving<br>Team Work<br>Decision Making</li>
                        </ul>
                    </div>
                    <div class="tab-contents" id="education">
                        <ul>
                            <li><span>2019-2021<br></span>PUC at Nehru memorial pu college sullia</li>
                            <li><span><br>2021-2025<br></span>BE at KVG College of Engineering Sullia</li>
                        </ul>
                    </div>
                </div>
            </div>
        </div>
    </div>
    <!---------portfolio---------- -->
    <div id="portfolio">
        <div class="container">
            <h1 class="sub-title">My Projects</h1>
            <div class="work-list">
                <div class="work">
                    <img src="work 1.jpg">
                    <div class="layer">
                        <h3>Registration Form</h3><br>
                        <p>Designing and creating a user-friendly registration form using HTML,<br><br> allowing users to input personal details and submit information.</p>

</div>
                </div>
                <div class="work">
                    <img src="work 2.jpg">
                    <div class="layer">
                        <h3>Date and time</h3>
                        <p>The project incorporates JavaScript for dynamic calculations and validation, ensuring accurate user input. This project simplifies event scheduling, registration forms, and date range selections, showcasing HTML's capabilities in handling date and time data.</p>
                </div>
            </div>
        </div>
    </div>
    <!---------- contact----->
    <div id="contact">
        <div class="container">
            <div class="row">
                <div class="contact-left">
                    <h1 class="sub-title">Contact Me</h1>
                    <p><i class="fa-sharp fa-solid fa-paper-plane"></i> <a href="12ananyas@gmail.com">12ananyas@gmail.com</a></p><br>
                    <p><i class="fa-solid fa-phone"></i> <a href="tel:+916362403219">6362403219</a></p>
                    <div class="social-icons">
                        <a href="https://www.linkedin.com/in/ananya-s-16995328a/"><i class="fa-brands fa-linkedin"></i></a>
                        <a href="https://wa.me/9611905745"><i class="fa-brands fa-whatsapp"></i></a>
                    </div>
                    <a href="file:///C:/Users/THOSHIBA/Downloads/ATS%20Resume.pdf" download class="btn2">Download Resume</a>
                </div>
                <div class="contact-right">
                    <form id="contact-form" name="submit-to-google-sheet">
                        <input type="text" name="name" placeholder="Your Name" required>
                        <input type="email" name="email" placeholder="Your Email" required>
                        <textarea name="message" rows="6" placeholder="Your Message"></textarea>
                        <button type="submit" class="btn2">Submit</button>
                 
   </form>
                    <span id="msg"></span>
                </div>
            </div>
        </div>
        <div class="copyright">
            <p>&copy; 2024 My Portfolio Website. All rights reserved. Developed by Ananya Soorthila</p>
        </div>
    </div>
    <script>
        var tablinks = document.getElementsByClassName("tab-links");
        var tabcontents = document.getElementsByClassName("tab-contents");
        function opentab(tabname) {
            for (tablink of tablinks) {
                tablink.classList.remove("active-link"); 
            }
            for (tabcontent of tabcontents) {
                tabcontent.classList.remove("active-tab");
            }
            event.currentTarget.classList.add("active-link");
            document.getElementById(tabname).classList.add("active-tab");
        }
    </script>
    <script> 
        var sidemenu=document.getElementById("sidemenu"); 
        function openmenu(){
            sidemenu.style.right="0";
        }
        function closemenu(){
            sidemenu.style.right="-200px";
        }
    </script>
    <script>
        const scriptURL = 'https://script.google.com/macros/s/AKfycbzj9rmhE4PQCSzxcP2FHsMnE_o5TT6BBLXsz0LlGK7fof8durMU710xUCAUIwArsS-GwQ/exec'
        const form = document.forms['submit-to-google-sheet']
        const msg=document.getElementById("msg")
        form.addEventListener('submit', e => {
          e.preventDefault()
          fetch(scriptURL, { method: 'POST', body: new FormData(form)})
            .then(response => {
                msg.innerHTML="Message sent successfully"
            setTimeout(function(){
                msg.innerHTML=""
            },5000)
            form.reset()
            })
            .catch(error => console.error('Error!', error.message))
        })
      </script>
    <!-- EmailJS integration -->
    <script type="text/javascript" src="https://cdn.jsdelivr.net/npm/emailjs-com@2.4.1/dist/email.min.js"></script>
    <script type="text/javascript">
        (function(){
            emailjs.init("RH4kG9vZCa6LRnkL1");
        })();
 document.getElementById('contact-form').addEventListener('submit', function(event) {
            event.preventDefault();
            emailjs.sendForm('service_i5pajiu', 'template_xfhykha', this)
                .then(function() {
                    document.getElementById('msg').innerHTML = "Message sent successfully";
                    setTimeout(function(){
                        document.getElementById('msg').innerHTML = "";
                    }, 5000);
                    form.reset();
                }, function(error) {
                    console.error('Error!', error.message);
                });
        });
    </script>
</body>
</html>

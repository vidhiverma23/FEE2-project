# FEE2-project
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>PROHEALTH - Hospital Management</title>
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@100;200;300;400;500;600;700&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.15.4/css/all.min.css">

    <style>
        :root {
            --main-color: #2ecc71; /* Vibrant green */
            --dark-color: #34495e; /* Dark gray */
            --light-color: #95a5a6; /* Light gray */
            --background-color: #ecf0f1; /* Light background */
            --white: #ffffff; /* White */
            --box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
        }

        * {
            font-family: 'Poppins', sans-serif;
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            outline: none;
        }

        body {
            line-height: 1.6;
            color: var(--dark-color);
            background-color: var(--background-color);
        }

        .header {
            padding: 1rem 5%;
            position: fixed;
            top: 0;
            left: 0;
            right: 0;
            z-index: 1000;
            box-shadow: var(--box-shadow);
            display: flex;
            align-items: center;
            justify-content: space-between;
            background: var(--white);
            transition: background 0.3s;
        }

        .header.scrolled {
            background: var(--white);
        }

        .header .logo {
            color: var(--main-color);
            font-size: 2.5rem;
            font-weight: 600;
        }

        .header .navbar {
            display: flex;
            align-items: center;
        }

        .header .navbar a {
            font-size: 1.5rem;
            color: var(--light-color);
            margin-left: 2rem;
            text-decoration: none;
            transition: color 0.3s;
        }

        .header .navbar a:hover {
            color: var(--main-color);
        }

        #menu-btn {
            font-size: 2.5rem;
            border-radius: 0.5rem;
            background: #eee;
            color: var(--main-color);
            padding: 1rem;
            cursor: pointer;
            display: none;
        }

        .home {
            padding: 10rem 5%;
            text-align: center;
            background: url('https://assets.onecompiler.app/42kgty9md/42vrn3b48/page%20pic.webp') no-repeat center center/cover;
            color: var(--white);
            height: 100vh;
            display: flex;
            flex-direction: column;
            justify-content: center;
        }

        .home h1 {
            font-size: 4rem;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.3);
        }

        .home p {
            font-size: 1.8rem;
            margin: 1rem 0;
        }

        .home .btn {
            padding: 1rem 2rem;
            background: var(--main-color);
            color: var(--white);
            text-decoration: none;
            border-radius: 0.5rem;
            transition: background 0.3s;
        }

        .home .btn:hover {
            background: #27ae60; /* Darker green */
        }

        .section-header {
            text-align: center;
            margin: 3rem 0;
            background-color: var(--main-color);
            color: var(--white);
            padding: 1rem;
            border-radius: 0.5rem;
            box-shadow: var(--box-shadow);
        }

        .services, .about, .doctors, .appointment {
            padding: 5rem 5%;
            background-color: var(--white);
            box-shadow: var(--box-shadow);
            margin: 2rem 0;
            border-radius: 0.5rem;
        }

        .service-container, .doctor-container {
            display: flex;
            flex-wrap: wrap;
            justify-content: space-between;
            gap: 2rem;
        }

        .service, .doctor-card {
            flex: 1 1 calc(30% - 2rem);
            text-align: center;
            padding: 2rem;
            box-shadow: var(--box-shadow);
            border-radius: 0.5rem;
            transition: transform 0.3s, box-shadow 0.3s;
            background-color: #f9f9f9;
        }

        .service:hover, .doctor-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 0 1rem rgba(0, 0, 0, 0.2);
        }

        .service i, .doctor-card i {
            font-size: 3rem;
            color: var(--main-color);
        }

        .service h3, .doctor-card h3 {
            font-size: 1.8rem;
            margin: 1rem 0;
        }

        .service p, .doctor-card p {
            font-size: 1.2rem;
            color: var(--light-color);
        }

        .doctor-image {
            width: 150px; /* Set a fixed width */
            height: 150px; /* Set a fixed height */
            overflow: hidden; /* Hide overflow to maintain aspect ratio */
            border-radius: 50%; /* Optional: make images circular */
            display: flex; /* Center the image */
            align-items: center; /* Center vertically */
            justify-content: center; /* Center horizontally */
            margin: 0 auto; /* Center the card */
        }

        .doctor-image img {
            width: 100%; /* Make the image responsive */
            height: auto; /* Maintain aspect ratio */
            max-height: 100%; /* Limit the height to the container */
        }

        .appointment form {
            max-width: 600px;
            margin: 0 auto;
            display: flex;
            flex-direction: column;
        }

        .appointment input, .appointment select {
            margin-bottom: 1rem;
            padding: 1rem;
            border: 2px solid var(--main-color);
            border-radius: 0.5rem;
            transition: border 0.3s;
        }

        .appointment input:focus, .appointment select:focus {
            border-color: var(--dark-color);
        }

        .appointment button {
            padding: 1rem;
            background: var(--main-color);
            color: var(--white);
            border: none;
            cursor: pointer;
            border-radius: 0.5rem;
            transition: background 0.3s;
        }

        .appointment button:hover {
            background: #27ae60; /* Darker green */
        }

        .footer {
            text-align: center;
            padding: 2rem 0;
            background-color: var(--main-color);
            color: var(--white);
        }

        #scrollToTopBtn {
            display: none;
            position: fixed;
            bottom: 30px;
            right: 30px;
            z-index: 100;
            font-size: 2rem;
            background: var(--main-color);
            color: white;
            padding: 1rem;
            border: none;
            border-radius: 0.5rem;
            cursor: pointer;
            transition: background 0.3s;
        }

        #scrollToTopBtn:hover {
            background: #27ae60; /* Darker green */
        }

        @media (max-width: 768px) {
            .header .navbar a {
                font-size: 1.3rem;
            }

            .home h1 {
                font-size: 3rem;
            }

            .home p {
                font-size: 1.5rem;
            }

            .service, .doctor-card {
                flex: 1 1 calc(100% - 2rem);
            }
        }
    </style>
</head>

<body>
    <header class="header">
        <a href="#" class="logo"><i class="fas fa-heartbeat"></i> PROHEALTH</a>
        <nav class="navbar">
            <a href="#home">Home</a>
            <a href="#services">Services</a>
            <a href="#about">About</a>
            <a href="#doctors">Doctors</a>
            <a href="#appointment">Book Appointment</a>
        </nav>
        <div id="menu-btn" class="fas fa-bars"></div>
    </header>

    <section id="home" class="home">
        <h1>Welcome to PROHEALTH</h1>
        <p>Your health is our priority. We provide top-notch healthcare services to meet all your medical needs.</p>
        <a href="#services" class="btn">Explore Services</a>
    </section>

    <section id="services" class="services">
        <div class="section-header">
            <h2>Our Services</h2>
        </div>
        <div class="service-container">
            <div class="service">
                <i class="fas fa-stethoscope"></i>
                <h3>General Checkup</h3>
                <p>Regular health checkups to keep your well-being in check.</p>
            </div>
            <div class="service">
                <i class="fas fa-syringe"></i>
                <h3>Vaccinations</h3>
                <p>We offer a wide range of vaccinations to protect your health.</p>
            </div>
            <div class="service">
                <i class="fas fa-heartbeat"></i>
                <h3>Cardiology</h3>
                <p>Expert care for your heart health with advanced treatment options.</p>
            </div>
            <div class="service">
                <i class="fas fa-ambulance"></i>
                <h3>Ambulance Facility</h3>
                <p>Fast and reliable ambulance services available 24/7.</p>
            </div>
            <div class="service">
                <i class="fas fa-pills"></i>
                <h3>Pharmacy</h3>
                <p>Get your prescribed medications quickly at our in-house pharmacy.</p>
            </div>
            <div class="service">
                <i class="fas fa-x-ray"></i>
                <h3>Radiology</h3>
                <p>Advanced imaging services including X-rays and MRI scans.</p>
            </div>
        </div>
    </section>

    <section id="about" class="about">
        <div class="section-header">
            <h2>About Us</h2>
        </div>
        <p>PROHEALTH is committed to delivering comprehensive medical services. Our team of experienced professionals is here to ensure you receive the best care.</p>
        <p>Since our founding in 2005, PROHEALTH has grown into a leading healthcare provider known for innovation and excellence. Our mission is to provide compassionate and patient-centered care while maintaining the highest standards in medical services. We are proud to serve our community and constantly strive to improve the health and well-being of our patients.</p>
        <p>Our hospital is equipped with state-of-the-art facilities, including cutting-edge diagnostic and surgical technologies, specialized departments, and modern infrastructure designed to provide comfort and safety for all patients. We are accredited by [Accreditation Body], reflecting our commitment to excellence in healthcare.</p>
        <p>We actively engage with our local community through health awareness programs, vaccination drives, and partnerships with local organizations. Our focus on education and research ensures that we remain at the forefront of medical innovation.</p>
    </section>

    <section id="doctors" class="doctors">
        <div class="section-header">
            <h2>Our Doctors</h2>
        </div>
        <div class="doctor-container">
            <div class="doctor-card">
                <div class="doctor-image">
                    <img src="https://assets.onecompiler.app/42kgty9md/42vrjqu3v/john%20doe.jpeg" alt="Dr. John Doe">
                </div>
                <h3>Dr. John Doe</h3>
                <p>Cardiologist</p>
            </div>
            <div class="doctor-card">
                <div class="doctor-image">
                    <img src="https://assets.onecompiler.app/42kgty9md/42vrjqu3v/jane%20smith.webp" alt="Dr. Jane Smith">
                </div>
                <h3>Dr. Jane Smith</h3>
                <p>Pediatrician</p>
            </div>
            <div class="doctor-card">
                <div class="doctor-image">
                    <img src="https://assets.onecompiler.app/42kgty9md/42vrjqu3v/sarah%20ahmed.webp" alt="Dr. Sarah Ahmed">
                </div>
                <h3>Dr. Sarah Ahmed</h3>
                <p>General Physician</p>
            </div>
            <div class="doctor-card">
                <div class="doctor-image">
                    <img src="https://assets.onecompiler.app/42kgty9md/42vrjqu3v/michael%20lee.jpg" alt="Dr. Michael Lee">
                </div>
                <h3>Dr. Michael Lee</h3>
                <p>Orthopedic Surgeon</p>
            </div>
            <div class="doctor-card">
                <div class="doctor-image">
                    <img src="https://assets.onecompiler.app/42kgty9md/42vrjqu3v/emily%20brown.jpg" alt="Dr. Emily Brown">
                </div>
                <h3>Dr. Emily Brown</h3>
                <p>Dermatologist</p>
            </div>
            <div class="doctor-card">
                <div class="doctor-image">
                    <img src="https://assets.onecompiler.app/42kgty9md/42vrjqu3v/daniel%20turner.webp" alt="Dr. Daniel Turner">
                </div>
                <h3>Dr. Daniel Turner</h3>
                <p>Neurologist</p>
            </div>
        </div>
    </section>

    <section id="appointment" class="appointment">
        <div class="section-header">
            <h2>Book an Appointment</h2>
        </div>
        <form onsubmit="return confirmAppointment();">
            <input type="text" placeholder="Your Name" required>
            <input type="email" placeholder="Your Email" required>
            <input type="date" required>
            <select required>
                <option value="" disabled selected>Select Doctor</option>
                <option value="Dr. John Doe">Dr. John Doe</option>
                <option value="Dr. Jane Smith">Dr. Jane Smith</option>
                <option value="Dr. Sarah Ahmed">Dr. Sarah Ahmed</option>
                <option value="Dr. Michael Lee">Dr. Michael Lee</option>
                <option value="Dr. Emily Brown">Dr. Emily Brown</option>
                <option value="Dr. Daniel Turner">Dr. Daniel Turner</option>
                <option value="Dr. Aisha Patel">Dr. Aisha Patel</option>
                <option value="Dr. William Roberts">Dr. William Roberts</option>
                <option value="Dr. Priya Desai">Dr. Priya Desai</option>
                <option value="Dr. Jacob Martin">Dr. Jacob Martin</option>
                <option value="Dr. Hannah Green">Dr. Hannah Green</option>
                <option value="Dr. Rajiv Singh">Dr. Rajiv Singh</option>
            </select>
            <button type="submit" class="btn">Book Now</button>
        </form>
    </section>

    <footer class="footer">
        <p>&copy; 2024 PROHEALTH. All Rights Reserved.</p>
    </footer>

    <button id="scrollToTopBtn" title="Go to top">↑</button>

    <script>
        // Scroll to Top Button
        const scrollToTopBtn = document.getElementById('scrollToTopBtn');
        window.onscroll = function () {
            if (document.body.scrollTop > 200 || document.documentElement.scrollTop > 200) {
                scrollToTopBtn.style.display = "block";
            } else {
                scrollToTopBtn.style.display = "none";
            }
        };
        scrollToTopBtn.onclick = function () {
            window.scrollTo({ top: 0, behavior: 'smooth' });
        };

        // Change header background on scroll
        window.onscroll = function () {
            const header = document.querySelector('.header');
            if (window.scrollY > 50) {
                header.classList.add('scrolled');
            } else {
                header.classList.remove('scrolled');
            }
        };

        // Confirm Appointment Function
        function confirmAppointment() {
            alert("Your appointment is confirmed!");
            return false; // Prevent form submission for demo purposes
        }
    </script>
</body>

</html>

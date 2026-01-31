
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Nails By Lupita | Pretty Things Done Right</title>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Playfair+Display+SC:wght@500;600&family=Allura&family=Poppins:wght@300;400;500&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        :root {
            /* Color Palette */
            --cream: #FAF6F1;
            --brown: #6B4E3D;
            --light-brown: #B89A84;
            --espresso: #2F1E16;
            --beige: #E7DCD2;
            --text-dark: #3A2A23;
            --text-muted: #7A5C4B;
            --text-light: #FAF6F1;
            
            /* Fonts */
            --heading-font: 'Playfair Display SC', serif;
            --accent-font: 'Allura', cursive;
            --body-font: 'Poppins', sans-serif;
            
            /* Spacing */
            --header-height-desktop: 85px;
            --header-height-mobile: 70px;
        }
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        body {
            font-family: var(--body-font);
            background-color: var(--cream);
            color: var(--text-dark);
            line-height: 1.6;
            overflow-x: hidden;
        }
        
        a {
            text-decoration: none;
            color: inherit;
        }
        
        img {
            max-width: 100%;
            display: block;
        }
        
        .container {
            width: 100%;
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }
        
        .btn {
            display: inline-block;
            background-color: var(--brown);
            color: var(--text-light);
            font-family: var(--body-font);
            font-weight: 500;
            padding: 12px 28px;
            border-radius: 20px;
            transition: all 0.3s ease;
            border: none;
            cursor: pointer;
            font-size: 16px;
        }
        
        .btn:hover {
            background-color: #5A3F32;
            transform: scale(1.03);
        }
        
        .section-title {
            font-family: var(--accent-font);
            font-weight: 400;
            color: var(--brown);
            font-size: 3rem;
            text-align: center;
            margin-bottom: 2rem;
            position: relative;
        }
        
        .section-title:after {
            content: '';
            position: absolute;
            width: 80px;
            height: 2px;
            background-color: var(--light-brown);
            bottom: -10px;
            left: 50%;
            transform: translateX(-50%);
        }
        
        /* PAGE TRANSITION */
        .page {
            display: none;
            animation: fadeIn 0.5s ease;
        }
        
        .page.active {
            display: block;
        }
        
        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }
        
        /* HEADER STYLES */
        header {
            position: sticky;
            top: 0;
            z-index: 1000;
            background-color: var(--cream);
            height: var(--header-height-desktop);
            border-bottom: 1px solid var(--light-brown);
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.04);
            transition: all 0.4s ease;
        }
        
        .header-transparent {
            background-color: transparent !important;
            border-bottom: 1px solid rgba(255, 255, 255, 0.1);
            box-shadow: none;
        }
        
        .header-transparent .logo,
        .header-transparent .nav-links a,
        .header-transparent .hamburger span {
            color: var(--text-light) !important;
        }
        
        .header-container {
            display: flex;
            justify-content: space-between;
            align-items: center;
            height: 100%;
            padding: 0 30px;
        }
        
        /* Logo - NOW IN CURSIVE */
        .logo {
            font-family: var(--accent-font); /* Changed to cursive */
            font-weight: 400;
            font-size: 2.5rem;
            color: var(--brown);
            transition: opacity 0.3s ease;
            cursor: pointer;
        }
        
        .logo:hover {
            opacity: 0.85;
        }
        
        /* Desktop Navigation */
        .nav-desktop {
            display: flex;
            align-items: center;
            gap: 30px;
        }
        
        .nav-center {
            display: flex;
            align-items: center;
            gap: 30px;
        }
        
        .divider {
            width: 1px;
            height: 20px;
            background-color: var(--beige);
        }
        
        .nav-links {
            display: flex;
            gap: 30px;
            list-style: none;
        }
        
        .nav-links a {
            font-family: var(--body-font);
            font-weight: 400;
            color: var(--text-dark);
            position: relative;
            transition: color 0.3s ease;
            cursor: pointer;
        }
        
        .nav-links a.active-page {
            color: var(--brown);
            font-weight: 500;
        }
        
        .nav-links a:hover {
            color: var(--brown);
        }
        
        .nav-links a:after {
            content: '';
            position: absolute;
            width: 0;
            height: 1px;
            bottom: -4px;
            left: 0;
            background-color: var(--brown);
            border-radius: 2px;
            transition: width 0.3s ease;
        }
        
        .nav-links a:hover:after,
        .nav-links a.active-page:after {
            width: 100%;
        }
        
        /* Mobile Navigation */
        .hamburger {
            display: none;
            flex-direction: column;
            gap: 5px;
            background: none;
            border: none;
            cursor: pointer;
            padding: 5px;
        }
        
        .hamburger span {
            display: block;
            width: 25px;
            height: 2px;
            background-color: var(--brown);
            transition: all 0.3s ease;
        }
        
        .mobile-menu {
            position: fixed;
            top: var(--header-height-mobile);
            left: 0;
            width: 100%;
            height: calc(100vh - var(--header-height-mobile));
            background-color: var(--cream);
            transform: translateY(-100%);
            opacity: 0;
            transition: all 0.4s ease;
            display: flex;
            flex-direction: column;
            justify-content: space-between;
            z-index: 999;
            pointer-events: none;
        }
        
        .mobile-menu.active {
            transform: translateY(0);
            opacity: 1;
            pointer-events: all;
        }
        
        .mobile-links {
            list-style: none;
            padding: 40px 20px;
            display: flex;
            flex-direction: column;
            gap: 25px;
            text-align: center;
        }
        
        .mobile-links a {
            font-family: var(--body-font);
            font-size: 1.5rem;
            color: var(--text-dark);
            display: block;
            padding: 10px 0;
            transition: color 0.3s ease;
            cursor: pointer;
        }
        
        .mobile-links a.active-page {
            color: var(--brown);
            font-weight: 500;
        }
        
        .mobile-links a:hover {
            color: var(--brown);
        }
        
        .mobile-menu-btn {
            padding: 30px 20px;
            text-align: center;
            border-top: 1px solid var(--beige);
        }
        
        /* HOME PAGE STYLES */
        /* HERO SECTION - UPDATED IMAGE */
        .hero {
            height: 100vh;
            min-height: 700px;
            background-image: url('https://www.dropbox.com/scl/fi/l7eft5nqlibyb4lkz0g7l/Nails-By-Lupita.png?rlkey=l9wsfdy6v5qyd875gsv2r9wfv&st=ygzn6arz&raw=1');
            background-size: cover;
            background-position: center;
            background-attachment: fixed;
            display: flex;
            align-items: center;
            justify-content: center;
            position: relative;
            margin-top: calc(-1 * var(--header-height-desktop));
        }
        
        .hero-overlay {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(47, 30, 22, 0.3); /* Lighter overlay to show image */
        }
        
        .hero-content {
            position: relative;
            z-index: 1;
            text-align: center;
            color: var(--text-light);
            max-width: 800px;
            padding: 0 20px;
            margin-top: 150px; /* MOVED BUTTON DOWN */
        }
        
        /* ONLY BOOK APPOINTMENT BUTTON - NO TEXT - MOVED DOWN */
        .hero-btn {
            font-size: 1.8rem;
            padding: 20px 50px;
            margin-top: 60px; /* Increased margin to move button down */
            font-family: var(--accent-font);
            background-color: transparent;
            border: 2px solid var(--cream);
            border-radius: 30px;
            color: var(--cream);
            transition: all 0.3s ease;
            display: inline-block;
        }
        
        .hero-btn:hover {
            background-color: var(--cream);
            color: var(--espresso);
            transform: scale(1.05);
        }
        
        /* ABOUT SECTION */
        .about {
            padding: 100px 0;
            background-color: var(--beige);
        }
        
        .about-container {
            display: flex;
            align-items: center;
            gap: 60px;
        }
        
        .about-text {
            flex: 1;
        }
        
        .about-title {
            font-family: var(--accent-font);
            font-weight: 400;
            color: var(--brown);
            font-size: 3.5rem;
            margin-bottom: 20px;
        }
        
        .about-description {
            font-size: 1.1rem;
            line-height: 1.8;
            color: var(--text-dark);
            margin-bottom: 30px;
        }
        
        .about-image {
            flex: 1;
            border-radius: 20px;
            overflow: hidden;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.08);
        }
        
        .about-image img {
            width: 100%;
            height: 400px;
            object-fit: cover;
            display: block;
        }
        
        /* SERVICES SECTION */
        .services {
            padding: 100px 0;
        }
        
        .services-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 30px;
            margin-top: 50px;
        }
        
        .service-card {
            background-color: var(--cream);
            border: 1px solid var(--light-brown);
            border-radius: 16px;
            padding: 30px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.05);
            transition: transform 0.3s ease, box-shadow 0.3s ease;
            text-align: center;
        }
        
        .service-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 30px rgba(0, 0, 0, 0.08);
        }
        
        .service-icon {
            font-size: 2.5rem;
            color: var(--brown);
            margin-bottom: 20px;
        }
        
        .service-title {
            font-family: var(--accent-font);
            font-weight: 400;
            font-size: 2.2rem;
            margin-bottom: 15px;
            color: var(--brown);
        }
        
        .service-description {
            color: var(--text-muted);
            font-size: 0.95rem;
        }
        
        /* GALLERY PREVIEW */
        .gallery-preview {
            padding: 100px 0;
            background: linear-gradient(to bottom, var(--cream), var(--beige));
        }
        
        .gallery-slider-container {
            position: relative;
            width: 100%;
            overflow: hidden;
            margin-top: 50px;
        }
        
        .gallery-slider {
            display: flex;
            gap: 20px;
            animation: scroll 40s linear infinite;
        }
        
        .gallery-slider:hover {
            animation-play-state: paused;
        }
        
        .gallery-slide {
            flex: 0 0 auto;
            width: 300px;
            height: 300px;
            border-radius: 16px;
            overflow: hidden;
            box-shadow: 0 10px 20px rgba(0, 0, 0, 0.1);
            position: relative;
        }
        
        .gallery-slide img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: transform 0.5s ease;
        }
        
        .gallery-slide:hover img {
            transform: scale(1.05);
        }
        
        .gallery-link {
            display: block;
            text-align: center;
            margin-top: 40px;
            font-family: var(--accent-font);
            font-size: 2.5rem;
            color: var(--brown);
            transition: color 0.3s ease;
            cursor: pointer;
        }
        
        .gallery-link:hover {
            color: var(--text-dark);
        }
        
        @keyframes scroll {
            0% {
                transform: translateX(0);
            }
            100% {
                transform: translateX(calc(-300px * 8));
            }
        }
        
        /* POLICIES SECTION */
        .policies {
            padding: 100px 0;
            background: linear-gradient(to right, var(--cream), var(--beige));
        }
        
        .policies-container {
            max-width: 800px;
            margin: 0 auto;
        }
        
        .policy-item {
            background-color: rgba(255, 255, 255, 0.7);
            border-radius: 16px;
            padding: 25px;
            margin-bottom: 25px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.05);
        }
        
        .policy-title {
            font-family: var(--accent-font);
            font-weight: 400;
            color: var(--brown);
            font-size: 1.8rem;
            margin-bottom: 10px;
            display: flex;
            align-items: center;
            gap: 10px;
        }
        
        .policy-title i {
            font-size: 1.5rem;
        }
        
        .policy-text {
            color: var(--text-dark);
            font-size: 0.95rem;
        }
        
        /* INSTAGRAM PROMO */
        .instagram-promo {
            padding: 80px 0;
            background-color: var(--light-brown);
            text-align: center;
        }
        
        .instagram-text {
            font-family: var(--accent-font);
            font-size: 3rem;
            color: var(--cream);
            margin-bottom: 20px;
        }
        
        .instagram-handle {
            font-family: var(--accent-font);
            font-weight: 400;
            font-size: 2.2rem;
            color: var(--cream);
        }
        
        /* GALLERY PAGE STYLES */
        .gallery-hero {
            padding: 140px 0 60px;
            text-align: center;
            background: linear-gradient(to bottom, var(--cream), var(--beige));
        }
        
        .gallery-title {
            font-family: var(--accent-font);
            font-weight: 400;
            font-size: 4.5rem;
            color: var(--brown);
            margin-bottom: 10px;
        }
        
        .gallery-subtitle {
            font-family: var(--accent-font);
            font-size: 2.5rem;
            color: var(--light-brown);
        }
        
        .gallery-grid {
            padding: 60px 0 100px;
        }
        
        .grid-container {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 25px;
        }
        
        .gallery-item {
            border-radius: 16px;
            overflow: hidden;
            box-shadow: 0 10px 20px rgba(0, 0, 0, 0.08);
            transition: transform 0.4s ease, box-shadow 0.4s ease;
            position: relative;
            height: 300px;
        }
        
        .gallery-item:hover {
            transform: scale(1.03);
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.15);
        }
        
        .gallery-item img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: transform 0.5s ease;
        }
        
        .gallery-item:hover img {
            transform: scale(1.1);
        }
        
        /* BOOKING PAGE STYLES - FIXED */
        .booking-hero {
            height: auto;
            min-height: 100vh;
            background-image: url('https://www.dropbox.com/scl/fi/j50osv4b9nguxs13e2b7k/Screenshot-2026-01-30-181100.png?rlkey=xb9d1b4hmy331rjy3scro3a7f&st=ib4nu21g&raw=1');
            background-size: cover;
            background-position: center;
            display: flex;
            align-items: center;
            justify-content: center;
            position: relative;
            margin-top: calc(-1 * var(--header-height-desktop));
            padding: 120px 0 80px;
        }
        
        .booking-overlay {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(47, 30, 22, 0.85);
            backdrop-filter: blur(5px);
        }
        
        .booking-content {
            position: relative;
            z-index: 1;
            text-align: center;
            color: var(--text-light);
            max-width: 900px;
            padding: 0 20px;
            width: 100%;
        }
        
        .booking-title {
            font-family: var(--accent-font);
            font-weight: 400;
            font-size: 4rem;
            margin-bottom: 40px;
            color: var(--cream);
        }
        
        /* BOOKING FORM STYLES - IMPROVED */
        .booking-form-container {
            background-color: rgba(255, 255, 255, 0.1);
            border-radius: 20px;
            padding: 50px;
            margin-top: 20px;
            backdrop-filter: blur(10px);
            text-align: left;
            border: 1px solid rgba(255, 255, 255, 0.2);
        }
        
        .form-group {
            margin-bottom: 25px;
        }
        
        .form-label {
            display: block;
            font-family: var(--body-font);
            font-weight: 500;
            color: var(--beige);
            margin-bottom: 8px;
            font-size: 1rem;
        }
        
        .form-control {
            width: 100%;
            padding: 14px 18px;
            border: 1px solid rgba(255, 255, 255, 0.3);
            border-radius: 10px;
            background-color: rgba(255, 255, 255, 0.1);
            color: var(--text-light);
            font-family: var(--body-font);
            font-size: 1rem;
            transition: all 0.3s ease;
        }
        
        .form-control:focus {
            outline: none;
            border-color: var(--light-brown);
            background-color: rgba(255, 255, 255, 0.15);
            box-shadow: 0 0 0 2px rgba(184, 154, 132, 0.2);
        }
        
        .form-control::placeholder {
            color: rgba(255, 255, 255, 0.6);
        }
        
        select.form-control {
            appearance: none;
            background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='16' height='16' fill='%23FAF6F1' viewBox='0 0 16 16'%3E%3Cpath d='M7.247 11.14 2.451 5.658C1.885 5.013 2.345 4 3.204 4h9.592a1 1 0 0 1 .753 1.659l-4.796 5.48a1 1 0 0 1-1.506 0z'/%3E%3C/svg%3E");
            background-repeat: no-repeat;
            background-position: right 15px center;
            background-size: 16px;
            padding-right: 45px;
        }
        
        .form-row {
            display: flex;
            gap: 20px;
        }
        
        .form-row .form-group {
            flex: 1;
        }
        
        .form-submit {
            text-align: center;
            margin-top: 40px;
        }
        
        .submit-btn {
            background-color: var(--cream);
            color: var(--espresso);
            font-family: var(--accent-font);
            font-size: 1.8rem;
            padding: 15px 50px;
            border-radius: 30px;
            border: none;
            cursor: pointer;
            transition: all 0.3s ease;
        }
        
        .submit-btn:hover {
            background-color: var(--light-brown);
            transform: scale(1.05);
        }
        
        .booking-instructions {
            margin-top: 40px;
            padding-top: 30px;
            border-top: 1px solid rgba(255, 255, 255, 0.2);
            color: var(--beige);
            font-size: 1rem;
            text-align: center;
            line-height: 1.6;
        }
        
        .booking-instructions p {
            margin-bottom: 15px;
        }
        
        .booking-contact-info {
            display: flex;
            justify-content: center;
            gap: 30px;
            margin-top: 20px;
            flex-wrap: wrap;
        }
        
        .contact-method {
            display: flex;
            align-items: center;
            gap: 10px;
            padding: 10px 20px;
            background-color: rgba(255, 255, 255, 0.1);
            border-radius: 10px;
        }
        
        .contact-method i {
            color: var(--beige);
            font-size: 1.2rem;
        }
        
        .contact-method span {
            font-family: var(--body-font);
            font-size: 0.95rem;
        }
        
        /* FOOTER */
        footer {
            background-color: var(--espresso);
            color: var(--text-light);
            padding: 60px 0 30px;
        }
        
        .footer-container {
            display: flex;
            justify-content: space-between;
            align-items: flex-start;
            flex-wrap: wrap;
            gap: 40px;
        }
        
        .footer-brand {
            flex: 1;
            min-width: 250px;
        }
        
        .footer-logo {
            font-family: var(--accent-font);
            font-weight: 400;
            font-size: 2.8rem;
            margin-bottom: 20px;
            color: var(--text-light);
        }
        
        .footer-contact {
            flex: 1;
            min-width: 250px;
        }
        
        .footer-contact h3 {
            font-family: var(--accent-font);
            font-weight: 400;
            font-size: 1.8rem;
            margin-bottom: 20px;
            color: var(--beige);
        }
        
        .contact-info {
            list-style: none;
            display: flex;
            flex-direction: column;
            gap: 15px;
        }
        
        .contact-info li {
            display: flex;
            align-items: center;
            gap: 10px;
            font-family: var(--body-font);
        }
        
        .contact-info i {
            color: var(--light-brown);
            font-size: 1.1rem;
        }
        
        .footer-social {
            flex: 1;
            min-width: 250px;
        }
        
        .footer-social h3 {
            font-family: var(--accent-font);
            font-weight: 400;
            font-size: 1.8rem;
            margin-bottom: 20px;
            color: var(--beige);
        }
        
        .social-icons {
            display: flex;
            gap: 20px;
            margin-bottom: 30px;
        }
        
        .social-icons a {
            display: flex;
            align-items: center;
            justify-content: center;
            width: 45px;
            height: 45px;
            background-color: rgba(255, 255, 255, 0.1);
            border-radius: 50%;
            transition: all 0.3s ease;
        }
        
        .social-icons a:hover {
            background-color: var(--light-brown);
            transform: translateY(-3px);
        }
        
        .footer-image {
            flex: 1;
            min-width: 250px;
            display: flex;
            justify-content: flex-end;
        }
        
        .footer-image img {
            width: 150px;
            height: 200px;
            border-radius: 16px;
            box-shadow: 0 10px 20px rgba(0, 0, 0, 0.2);
            object-fit: cover;
        }
        
        .copyright {
            width: 100%;
            text-align: center;
            margin-top: 50px;
            padding-top: 20px;
            border-top: 1px solid rgba(255, 255, 255, 0.1);
            font-size: 0.9rem;
            color: var(--beige);
            font-family: var(--body-font);
        }
        
        /* RESPONSIVE DESIGN */
        @media (max-width: 1024px) {
            .grid-container {
                grid-template-columns: repeat(2, 1fr);
            }
            
            .about-container {
                flex-direction: column;
                text-align: center;
            }
            
            .about-image {
                order: -1;
            }
            
            .footer-image {
                justify-content: center;
            }
            
            .form-row {
                flex-direction: column;
                gap: 0;
            }
            
            .booking-form-container {
                padding: 40px 30px;
            }
            
            .booking-contact-info {
                flex-direction: column;
                align-items: center;
                gap: 15px;
            }
        }
        
        @media (max-width: 768px) {
            header {
                height: var(--header-height-mobile);
            }
            
            .header-container {
                padding: 0 15px;
            }
            
            .nav-desktop {
                display: none;
            }
            
            .hamburger {
                display: flex;
            }
            
            .hero, .booking-hero {
                min-height: 600px;
                margin-top: calc(-1 * var(--header-height-mobile));
            }
            
            .hero-content {
                margin-top: 100px; /* Adjusted for mobile */
            }
            
            .logo {
                font-size: 2rem;
            }
            
            .booking-title {
                font-size: 3rem;
            }
            
            .about-title, .service-title, .policy-title {
                font-size: 2.5rem;
            }
            
            .about, .services, .gallery-preview, .policies, .instagram-promo, .gallery-grid {
                padding: 70px 0;
            }
            
            .footer-container {
                flex-direction: column;
                gap: 30px;
            }
            
            .grid-container {
                grid-template-columns: 1fr;
            }
            
            .gallery-title {
                font-size: 3.5rem;
            }
            
            .booking-form-container {
                padding: 30px 20px;
            }
            
            .instagram-text {
                font-size: 2.2rem;
            }
            
            .instagram-handle {
                font-size: 1.8rem;
            }
            
            .hero-btn {
                font-size: 1.5rem;
                padding: 15px 40px;
                margin-top: 40px; /* Adjusted for mobile */
            }
            
            .submit-btn {
                font-size: 1.5rem;
                padding: 12px 40px;
            }
        }
        
        @media (max-width: 480px) {
            .logo {
                font-size: 1.8rem;
            }
            
            .gallery-title, .booking-title {
                font-size: 2.8rem;
            }
            
            .about-title, .service-title, .policy-title {
                font-size: 2rem;
            }
            
            .about-image img {
                height: 300px;
            }
            
            .hero-btn {
                font-size: 1.3rem;
                padding: 12px 35px;
                margin-top: 30px; /* Adjusted for mobile */
            }
            
            .submit-btn {
                font-size: 1.5rem;
                padding: 12px 40px;
            }
            
            .hero-content {
                margin-top: 80px; /* Adjusted for mobile */
            }
            
            .booking-hero {
                padding: 100px 0 60px;
            }
        }
    </style>
</head>
<body>
    <!-- HEADER -->
    <header id="main-header">
        <div class="header-container">
            <!-- Logo - NOW IN CURSIVE -->
            <div class="logo" data-page="home">Nails By Lupita</div>
            
            <!-- Desktop Navigation -->
            <div class="nav-desktop">
                <div class="nav-center">
                    <nav>
                        <ul class="nav-links">
                            <li><a href="#" class="nav-link active-page" data-page="home">Home</a></li>
                            <li><a href="#" class="nav-link" data-page="gallery">Gallery</a></li>
                            <li><a href="#" class="nav-link" data-page="booking">Booking</a></li>
                        </ul>
                    </nav>
                    <div class="divider"></div>
                    <a href="#" class="btn" data-page="booking">Book Now</a>
                </div>
            </div>
            
            <!-- Mobile Hamburger Menu -->
            <button class="hamburger" id="hamburger">
                <span></span>
                <span></span>
                <span></span>
            </button>
        </div>
        
        <!-- Mobile Menu -->
        <div class="mobile-menu" id="mobile-menu">
            <ul class="mobile-links">
                <li><a href="#" class="nav-link active-page" data-page="home">Home</a></li>
                <li><a href="#" class="nav-link" data-page="gallery">Gallery</a></li>
                <li><a href="#" class="nav-link" data-page="booking">Booking</a></li>
            </ul>
            <div class="mobile-menu-btn">
                <a href="#" class="btn" data-page="booking">Book Now</a>
            </div>
        </div>
    </header>

    <!-- HOME PAGE -->
    <div class="page active" id="home-page">
        <!-- HERO SECTION - UPDATED WITH NEW IMAGE -->
        <section class="hero" id="home">
            <div class="hero-overlay"></div>
            <div class="hero-content">
                <!-- ONLY THE BOOK APPOINTMENT BUTTON - NO TEXT - MOVED DOWN -->
                <a href="#" class="btn hero-btn" data-page="booking">Book Appointment</a>
            </div>
        </section>

        <!-- ABOUT SECTION -->
        <section class="about" id="about">
            <div class="container about-container">
                <div class="about-text">
                    <h2 class="about-title">About Lupita</h2>
                    <p class="about-description">
                        Welcome to Nails By Lupita, where pretty things are done right. I'm Lupita, a dedicated nail technician based in Georgia with a passion for creating luxurious, clean, and "baddie" nail sets that make you feel confident and beautiful.
                    </p>
                    <p class="about-description">
                        With meticulous attention to detail and a commitment to quality, I specialize in custom acrylic sets, intricate nail art, and providing a relaxing, professional experience for every client.
                    </p>
                    <p class="about-description">
                        Your nails are my canvas, and I'm dedicated to creating artwork you'll love showing off. Book your appointment today and experience the difference of personalized, luxury nail care.
                    </p>
                </div>
                <div class="about-image">
                    <img src="https://www.dropbox.com/scl/fi/10n9ygb3ofv3nln6g5m0c/Screenshot-2026-01-30-200200.png?rlkey=bcnpy534ra4gnxds03dzzw9hq&st=ra1eewxv&raw=1" alt="Nails By Lupita aesthetic">
                </div>
            </div>
        </section>

        <!-- SERVICES SECTION -->
        <section class="services" id="services">
            <div class="container">
                <h2 class="section-title">My Services</h2>
                <div class="services-grid">
                    <div class="service-card">
                        <div class="service-icon">
                            <i class="fas fa-gem"></i>
                        </div>
                        <h3 class="service-title">Short Acrylic Sets</h3>
                        <p class="service-description">Beautiful, durable acrylic sets perfect for everyday wear. Custom shapes and lengths available.</p>
                    </div>
                    
                    <div class="service-card">
                        <div class="service-icon">
                            <i class="fas fa-crown"></i>
                        </div>
                        <h3 class="service-title">Long Acrylic Sets</h3>
                        <p class="service-description">Stunning long-length acrylic sets for maximum impact. Perfect for special occasions or making a statement.</p>
                    </div>
                    
                    <div class="service-card">
                        <div class="service-icon">
                            <i class="fas fa-paint-brush"></i>
                        </div>
                        <h3 class="service-title">Custom Nail Art</h3>
                        <p class="service-description">Intricate designs, hand-painted artwork, gems, foils, and more. Bring your vision to life.</p>
                    </div>
                    
                    <div class="service-card">
                        <div class="service-icon">
                            <i class="fas fa-bolt"></i>
                        </div>
                        <h3 class="service-title">Sneeze-Ins</h3>
                        <p class="service-description">Need an appointment last minute? Sneeze-in appointments available with additional fee.</p>
                    </div>
                </div>
            </div>
        </section>

        <!-- GALLERY PREVIEW -->
        <section class="gallery-preview" id="gallery-preview">
            <div class="container">
                <h2 class="section-title">Recent Work</h2>
                <div class="gallery-slider-container">
                    <div class="gallery-slider" id="gallery-slider">
                        <!-- Gallery images will be dynamically loaded -->
                    </div>
                </div>
                <div class="gallery-link" data-page="gallery">View Full Gallery →</div>
            </div>
        </section>

        <!-- POLICIES SECTION -->
        <section class="policies" id="policies">
            <div class="container policies-container">
                <h2 class="section-title">Booking Policies</h2>
                
                <div class="policy-item">
                    <h3 class="policy-title"><i class="fas fa-calendar-check"></i> Booking Requirements</h3>
                    <p class="policy-text">A deposit is required to secure your appointment. No deposit means no appointment will be scheduled.</p>
                </div>
                
                <div class="policy-item">
                    <h3 class="policy-title"><i class="fas fa-clock"></i> Arrival Time</h3>
                    <p class="policy-text">Please arrive on time for your appointment. There is a 10-minute grace period. After 10 minutes, a $10 late fee will apply.</p>
                </div>
                
                <div class="policy-item">
                    <h3 class="policy-title"><i class="fas fa-calendar-plus"></i> Sneeze-In Appointments</h3>
                    <p class="policy-text">Sneeze-in appointments (marked in black on the calendar) are available with an additional $15 fee.</p>
                </div>
                
                <div class="policy-item">
                    <h3 class="policy-title"><i class="fas fa-ban"></i> Deposit Policy</h3>
                    <p class="policy-text">Deposits are non-refundable unless I am unable to take you as a client. Rescheduling requires 24-hour notice.</p>
                </div>
            </div>
        </section>

        <!-- INSTAGRAM PROMO -->
        <section class="instagram-promo">
            <div class="container">
                <p class="instagram-text">Post your nails & tag @nailssbygloxn</p>
                <p class="instagram-handle">Get $5 off your next set!</p>
            </div>
        </section>
    </div>

    <!-- GALLERY PAGE -->
    <div class="page" id="gallery-page">
        <section class="gallery-hero">
            <div class="container">
                <h1 class="gallery-title">Baddie Sets by Lupita</h1>
                <p class="gallery-subtitle">Luxury Nail Art Gallery</p>
            </div>
        </section>

        <section class="gallery-grid">
            <div class="container">
                <div class="grid-container" id="full-gallery">
                    <!-- Full gallery images will be loaded here -->
                </div>
            </div>
        </section>
    </div>

    <!-- BOOKING PAGE - FIXED -->
    <div class="page" id="booking-page">
        <section class="booking-hero">
            <div class="booking-overlay"></div>
            <div class="booking-content">
                <h1 class="booking-title">Book Your Appointment</h1>
                
                <div class="booking-form-container">
                    <form id="bookingForm">
                        <div class="form-row">
                            <div class="form-group">
                                <label for="firstName" class="form-label">First Name</label>
                                <input type="text" id="firstName" class="form-control" placeholder="Your first name" required>
                            </div>
                            <div class="form-group">
                                <label for="lastName" class="form-label">Last Name</label>
                                <input type="text" id="lastName" class="form-control" placeholder="Your last name" required>
                            </div>
                        </div>
                        
                        <div class="form-row">
                            <div class="form-group">
                                <label for="phone" class="form-label">Phone Number</label>
                                <input type="tel" id="phone" class="form-control" placeholder="912-401-3684" required>
                            </div>
                            <div class="form-group">
                                <label for="email" class="form-label">Email Address</label>
                                <input type="email" id="email" class="form-control" placeholder="cluptiaskyla@gmail.com" required>
                            </div>
                        </div>
                        
                        <div class="form-group">
                            <label for="service" class="form-label">Select Service</label>
                            <select id="service" class="form-control" required>
                                <option value="" disabled selected>Choose a service</option>
                                <option value="short-acrylic">Short Acrylic Set</option>
                                <option value="long-acrylic">Long Acrylic Set</option>
                                <option value="custom-art">Custom Nail Art</option>
                                <option value="sneeze-in">Sneeze-In Appointment (+$15)</option>
                                <option value="fill">Acrylic Fill</option>
                                <option value="removal">Acrylic Removal</option>
                                <option value="other">Other/Consultation</option>
                            </select>
                        </div>
                        
                        <div class="form-row">
                            <div class="form-group">
                                <label for="date" class="form-label">Preferred Date</label>
                                <input type="date" id="date" class="form-control" required>
                            </div>
                            <div class="form-group">
                                <label for="time" class="form-label">Preferred Time</label>
                                <select id="time" class="form-control" required>
                                    <option value="" disabled selected>Select time</option>
                                    <option value="9am">9:00 AM</option>
                                    <option value="10am">10:00 AM</option>
                                    <option value="11am">11:00 AM</option>
                                    <option value="12pm">12:00 PM</option>
                                    <option value="1pm">1:00 PM</option>
                                    <option value="2pm">2:00 PM</option>
                                    <option value="3pm">3:00 PM</option>
                                    <option value="4pm">4:00 PM</option>
                                    <option value="5pm">5:00 PM</option>
                                </select>
                            </div>
                        </div>
                        
                        <div class="form-group">
                            <label for="notes" class="form-label">Additional Notes or Inspiration</label>
                            <textarea id="notes" class="form-control" rows="4" placeholder="Any specific designs, colors, or details you'd like to share..."></textarea>
                        </div>
                        
                        <div class="form-submit">
                            <button type="submit" class="submit-btn">Submit Booking Request</button>
                        </div>
                    </form>
                    
                    <div class="booking-instructions">
                        <p><strong>Important Information:</strong></p>
                        <p>After submitting your booking request, you will receive a confirmation text or email within 24 hours. A deposit is required to secure your appointment time.</p>
                        <p>Please review our booking policies on the home page before submitting your request.</p>
                        
                        <div class="booking-contact-info">
                            <div class="contact-method">
                                <i class="fab fa-instagram"></i>
                                <span>@nailssbygloxn</span>
                            </div>
                            <div class="contact-method">
                                <i class="fas fa-phone"></i>
                                <span>912-401-3684</span>
                            </div>
                            <div class="contact-method">
                                <i class="fas fa-envelope"></i>
                                <span>cluptiaskyla@gmail.com</span>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </section>
    </div>

    <!-- FOOTER -->
    <footer id="contact">
        <div class="container">
            <div class="footer-container">
                <div class="footer-brand">
                    <div class="footer-logo">Nails By Lupita</div>
                    <p>Luxury nail services in Georgia. Pretty things done right.</p>
                </div>
                
                <div class="footer-contact">
                    <h3>Contact Info</h3>
                    <ul class="contact-info">
                        <li><i class="fas fa-phone"></i> 912-401-3684</li>
                        <li><i class="fas fa-envelope"></i> cluptiaskyla@gmail.com</li>
                        <li><i class="fas fa-map-marker-alt"></i> Local GA Nail Tech</li>
                    </ul>
                </div>
                
                <div class="footer-social">
                    <h3>Follow Me</h3>
                    <div class="social-icons">
                        <a href="https://instagram.com/nailssbygloxn" target="_blank" aria-label="Instagram">
                            <i class="fab fa-instagram"></i>
                        </a>
                        <a href="mailto:cluptiaskyla@gmail.com" aria-label="Email">
                            <i class="fas fa-envelope"></i>
                        </a>
                        <a href="tel:9124013684" aria-label="Phone">
                            <i class="fas fa-phone"></i>
                        </a>
                    </div>
                </div>
                
                <div class="footer-image">
                    <img src="https://www.dropbox.com/scl/fi/10n9ygb3ofv3nln6g5m0c/Screenshot-2026-01-30-200200.png?rlkey=bcnpy534ra4gnxds03dzzw9hq&st=ra1eewxv&raw=1" alt="Nails By Lupita aesthetic">
                </div>
            </div>
            
            <div class="copyright">
                &copy; 2023 Nails By Lupita. All rights reserved.
            </div>
        </div>
    </footer>

    <script>
        // Page navigation system
        const pages = {
            'home': document.getElementById('home-page'),
            'gallery': document.getElementById('gallery-page'),
            'booking': document.getElementById('booking-page')
        };
        
        const navLinks = document.querySelectorAll('.nav-link');
        const logo = document.querySelector('.logo');
        const header = document.getElementById('main-header');
        const heroSection = document.querySelector('.hero');
        const bookingHero = document.querySelector('.booking-hero');
        
        // Gallery image URLs from your Dropbox links - EXACT LINKS
        const galleryImageUrls = [
            'https://www.dropbox.com/scl/fi/n64trbmy2hq3ixtdx6aip/Screenshot-2026-01-30-231319.png?raw=1',
            'https://www.dropbox.com/scl/fi/t53uzull26j359vv451tb/Screenshot-2026-01-30-231249.png?raw=1',
            'https://www.dropbox.com/scl/fi/e70vh0gezu2lz7fgci2yo/Screenshot-2026-01-30-231306.png?raw=1',
            'https://www.dropbox.com/scl/fi/33xvo7nbp9l0myj5znmje/Screenshot-2026-01-30-231241.png?raw=1',
            'https://www.dropbox.com/scl/fi/7k0ubc8xba1czdfbjc9xq/Screenshot-2026-01-30-231230.png?raw=1',
            'https://www.dropbox.com/scl/fi/twwnjund1f85jfhmmtm1s/Screenshot-2026-01-30-231224.png?raw=1',
            'https://www.dropbox.com/scl/fi/jl8gdlwvgcb1lenpmlerx/Screenshot-2026-01-30-231210.png?raw=1',
            'https://www.dropbox.com/scl/fi/l327ocjzznqzspd0wia0w/Screenshot-2026-01-30-231200.png?raw=1',
            'https://www.dropbox.com/scl/fi/yee8v1cwxlhljnu4z9dc6/Screenshot-2026-01-30-231146.png?raw=1',
            'https://www.dropbox.com/scl/fi/61gi3k1hwqu90fe5rjph9/Screenshot-2026-01-30-231134.png?raw=1',
            'https://www.dropbox.com/scl/fi/ze1k6bl2azjct5ado3kh6/Screenshot-2026-01-30-231110.png?raw=1',
            'https://www.dropbox.com/scl/fi/4gj9t82jeafj57fz5ba57/Screenshot-2026-01-30-231058.png?raw=1',
            'https://www.dropbox.com/scl/fi/i9bpxuz8g1ncc7412fym0/Screenshot-2026-01-30-231038.png?raw=1',
            'https://www.dropbox.com/scl/fi/tag0osj2bpxjqon51c853/Screenshot-2026-01-30-231020.png?raw=1',
            'https://www.dropbox.com/scl/fi/jdk81mlb3ubrss3k84anx/Screenshot-2026-01-30-230948.png?raw=1',
            'https://www.dropbox.com/scl/fi/evxa1yyr47qz4cwxeiepf/Screenshot-2026-01-30-231010.png?raw=1'
        ];
        
        // Function to switch pages
        function switchPage(pageId) {
            // Hide all pages
            Object.values(pages).forEach(page => {
                page.classList.remove('active');
            });
            
            // Show selected page
            pages[pageId].classList.add('active');
            
            // Update active nav link
            navLinks.forEach(link => {
                if (link.dataset.page === pageId) {
                    link.classList.add('active-page');
                } else {
                    link.classList.remove('active-page');
                }
            });
            
            // Update header transparency based on page
            updateHeaderTransparency();
            
            // Scroll to top
            window.scrollTo(0, 0);
            
            // Load gallery images if on gallery page
            if (pageId === 'gallery') {
                loadFullGallery();
            }
            
            // Load preview slider if on home page
            if (pageId === 'home') {
                loadGallerySlider();
            }
            
            // Set minimum date for booking form to today
            if (pageId === 'booking') {
                const today = new Date().toISOString().split('T')[0];
                document.getElementById('date').min = today;
            }
        }
        
        // Load gallery slider on home page
        function loadGallerySlider() {
            const slider = document.getElementById('gallery-slider');
            if (!slider) return;
            
            slider.innerHTML = '';
            
            // Create 8 slides for smooth scrolling (use first 8 images)
            for (let i = 0; i < 8; i++) {
                const imgIndex = i % 8; // Use first 8 images only for slider
                const slide = document.createElement('div');
                slide.className = 'gallery-slide';
                
                // Create image element with error handling
                const img = document.createElement('img');
                img.src = galleryImageUrls[imgIndex];
                img.alt = `Nail design ${i+1}`;
                img.onerror = function() {
                    console.log(`Failed to load image: ${galleryImageUrls[imgIndex]}`);
                };
                
                slide.appendChild(img);
                slider.appendChild(slide);
            }
        }
        
        // Load full gallery on gallery page
        function loadFullGallery() {
            const galleryGrid = document.getElementById('full-gallery');
            if (!galleryGrid) return;
            
            galleryGrid.innerHTML = '';
            
            // Create all 16 gallery items
            for (let i = 0; i < galleryImageUrls.length; i++) {
                const item = document.createElement('div');
                item.className = 'gallery-item';
                
                // Create image element with error handling
                const img = document.createElement('img');
                img.src = galleryImageUrls[i];
                img.alt = `Nail design ${i+1}`;
                img.onerror = function() {
                    console.log(`Failed to load gallery image: ${galleryImageUrls[i]}`);
                };
                
                item.appendChild(img);
                galleryGrid.appendChild(item);
            }
        }
        
        // Update header transparency based on scroll position
        function updateHeaderTransparency() {
            const currentPage = Object.keys(pages).find(key => pages[key].classList.contains('active'));
            
            if (currentPage === 'home') {
                if (window.scrollY < heroSection.offsetHeight - 100) {
                    header.classList.add('header-transparent');
                } else {
                    header.classList.remove('header-transparent');
                }
            } else if (currentPage === 'booking') {
                if (window.scrollY < bookingHero.offsetHeight - 100) {
                    header.classList.add('header-transparent');
                } else {
                    header.classList.remove('header-transparent');
                }
            } else {
                header.classList.remove('header-transparent');
            }
        }
        
        // Initialize page navigation
        navLinks.forEach(link => {
            link.addEventListener('click', (e) => {
                e.preventDefault();
                switchPage(link.dataset.page);
                
                // Close mobile menu if open
                mobileMenu.classList.remove('active');
                hamburger.classList.remove('active');
            });
        });
        
        // Logo click goes to home
        logo.addEventListener('click', (e) => {
            e.preventDefault();
            switchPage('home');
        });
        
        // Book Now buttons
        document.querySelectorAll('.btn[data-page], .gallery-link').forEach(btn => {
            btn.addEventListener('click', (e) => {
                e.preventDefault();
                switchPage(btn.dataset.page);
                
                // Close mobile menu if open
                mobileMenu.classList.remove('active');
                hamburger.classList.remove('active');
            });
        });
        
        // Mobile menu toggle
        const hamburger = document.getElementById('hamburger');
        const mobileMenu = document.getElementById('mobile-menu');
        
        hamburger.addEventListener('click', () => {
            mobileMenu.classList.toggle('active');
            hamburger.classList.toggle('active');
        });
        
        // Close mobile menu when clicking a link
        const mobileLinks = document.querySelectorAll('.mobile-links a, .mobile-menu-btn a');
        mobileLinks.forEach(link => {
            link.addEventListener('click', () => {
                mobileMenu.classList.remove('active');
                hamburger.classList.remove('active');
            });
        });
        
        // Booking form submission
        document.getElementById('bookingForm').addEventListener('submit', function(e) {
            e.preventDefault();
            
            // Get form values
            const firstName = document.getElementById('firstName').value;
            const lastName = document.getElementById('lastName').value;
            const phone = document.getElementById('phone').value;
            const email = document.getElementById('email').value;
            const service = document.getElementById('service').value;
            const date = document.getElementById('date').value;
            const time = document.getElementById('time').value;
            const notes = document.getElementById('notes').value;
            
            // Format date for display
            const dateObj = new Date(date);
            const formattedDate = dateObj.toLocaleDateString('en-US', { 
                weekday: 'long', 
                year: 'numeric', 
                month: 'long', 
                day: 'numeric' 
            });
            
            // Format time for display
            const timeDisplay = {
                '9am': '9:00 AM',
                '10am': '10:00 AM', 
                '11am': '11:00 AM',
                '12pm': '12:00 PM',
                '1pm': '1:00 PM',
                '2pm': '2:00 PM',
                '3pm': '3:00 PM',
                '4pm': '4:00 PM',
                '5pm': '5:00 PM'
            }[time];
            
            // Service display names
            const serviceDisplay = {
                'short-acrylic': 'Short Acrylic Set',
                'long-acrylic': 'Long Acrylic Set',
                'custom-art': 'Custom Nail Art',
                'sneeze-in': 'Sneeze-In Appointment (+$15)',
                'fill': 'Acrylic Fill',
                'removal': 'Acrylic Removal',
                'other': 'Other/Consultation'
            }[service];
            
            // Create confirmation message
            const confirmationMessage = `
                Thank you, ${firstName} ${lastName}!
                
                ✅ Your booking request has been received.
                
                📋 Appointment Details:
                • Service: ${serviceDisplay}
                • Date: ${formattedDate}
                • Time: ${timeDisplay}
                • Contact: ${phone}, ${email}
                
                📝 Notes: ${notes || 'None provided'}
                
                You will receive a confirmation text/email within 24 hours. A deposit is required to secure your appointment.
                
                📍 Location: Local GA Nail Tech
                📱 Phone: 912-401-3684
                📧 Email: cluptiaskyla@gmail.com
                📸 Instagram: @nailssbygloxn
            `;
            
            // Show confirmation alert
            alert(confirmationMessage);
            
            // Reset form
            this.reset();
            
            // Set minimum date to today
            const today = new Date().toISOString().split('T')[0];
            document.getElementById('date').min = today;
            
            // Switch to home page after booking
            switchPage('home');
        });
        
        // Update header transparency on scroll
        window.addEventListener('scroll', updateHeaderTransparency);
        
        // Initialize the page
        window.addEventListener('DOMContentLoaded', () => {
            // Load gallery slider on home page
            loadGallerySlider();
            
            // Load full gallery initially (in case user goes directly to gallery)
            loadFullGallery();
            
            // Set initial header transparency
            updateHeaderTransparency();
            
            // Set minimum date for booking form to today
            const today = new Date().toISOString().split('T')[0];
            document.getElementById('date').min = today;
            
            // Set placeholder date to tomorrow
            const tomorrow = new Date();
            tomorrow.setDate(tomorrow.getDate() + 1);
            const tomorrowFormatted = tomorrow.toISOString().split('T')[0];
            document.getElementById('date').value = tomorrowFormatted;
            
            // Check if there's a hash in the URL to navigate to specific page
            const hash = window.location.hash.substring(1);
            if (hash && pages[hash]) {
                switchPage(hash);
            }
        });
    </script>
</body>
</html>

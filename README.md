<!DOCTYPE html>
<html lang="pl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Ruch Młodych Kaszubów - Ankieta</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        body {
            background: #000000;
            color: #D4AF37;
            line-height: 1.6;
            min-height: 100vh;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            padding: 20px;
        }
        
        .container {
            max-width: 800px;
            width: 100%;
            background: rgba(0, 0, 0, 0.9);
            border-radius: 15px;
            overflow: hidden;
            box-shadow: 0 10px 30px rgba(212, 175, 55, 0.25);
            border: 2px solid #D4AF37;
            position: relative;
            z-index: 2;
        }
        
        /* Autentyczne wzory kaszubskie */
        .kaszubski-tlo {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: 
                /* Wzór z motywem roślinnym */
                radial-gradient(circle, transparent 65%, #D4AF37 65%, #D4AF37 70%, transparent 70%) 0 0/50px 50px,
                radial-gradient(circle, transparent 65%, #D4AF37 65%, #D4AF37 70%, transparent 70%) 25px 25px/50px 50px,
                /* Wzór geometryczny */
                linear-gradient(45deg, transparent 40%, rgba(212, 175, 55, 0.1) 40%, rgba(212, 175, 55, 0.1) 60%, transparent 60%),
                linear-gradient(-45deg, transparent 40%, rgba(212, 175, 55, 0.1) 40%, rgba(212, 175, 55, 0.1) 60%, transparent 60%);
            background-size: 100px 100px, 100px 100px, 20px 20px, 20px 20px;
            opacity: 0.2;
            z-index: -1;
            pointer-events: none;
        }
        
        .kaszubski-border {
            height: 25px;
            background: 
                /* Wzór z motywem lilii */
                repeating-linear-gradient(90deg, 
                    transparent, 
                    transparent 10px, 
                    #D4AF37 10px, 
                    #D4AF37 12px,
                    transparent 12px,
                    transparent 22px,
                    #D4AF37 22px,
                    #D4AF37 24px),
                /* Wzór z motywem serca */
                repeating-linear-gradient(90deg, 
                    #D4AF37, 
                    #D4AF37 2px, 
                    transparent 2px, 
                    transparent 4px,
                    #D4AF37 4px,
                    #D4AF37 6px,
                    transparent 6px,
                    transparent 16px);
            background-blend-mode: overlay;
            background-size: 24px 100%, 16px 100%;
            opacity: 0.7;
        }
        
        header {
            text-align: center;
            padding: 35px;
            background: linear-gradient(to right, #000000, #1a1a1a, #000000);
            color: #D4AF37;
            border-bottom: 2px solid #D4AF37;
            position: relative;
        }
        
        header h1 {
            font-size: 2.5rem;
            margin-bottom: 15px;
            text-shadow: 0 0 12px rgba(212, 175, 55, 0.6);
            letter-spacing: 1.5px;
        }
        
        header p {
            font-size: 1.2rem;
            opacity: 0.9;
            max-width: 600px;
            margin: 0 auto;
        }
        
        .form-container {
            padding: 35px;
            position: relative;
        }
        
        .form-group {
            margin-bottom: 28px;
            position: relative;
        }
        
        label {
            display: block;
            margin-bottom: 12px;
            font-weight: bold;
            color: #D4AF37;
            font-size: 1.15rem;
        }
        
        input[type="text"],
        input[type="email"],
        input[type="tel"],
        input[type="number"],
        textarea {
            width: 100%;
            padding: 16px;
            background: rgba(0, 0, 0, 0.7);
            border: 2px solid #D4AF37;
            border-radius: 8px;
            font-size: 17px;
            transition: all 0.3s;
            color: #D4AF37;
        }
        
        input:focus, textarea:focus {
            border-color: #FFD700;
            outline: none;
            box-shadow: 0 0 0 3px rgba(212, 175, 55, 0.35);
            background: rgba(0, 0, 0, 0.85);
        }
        
        textarea {
            min-height: 150px;
            resize: vertical;
        }
        
        .required {
            color: #FFD700;
        }
        
        button {
            background: linear-gradient(to right, #000000, #1a1a1a);
            color: #D4AF37;
            border: 2px solid #D4AF37;
            padding: 18px 35px;
            font-size: 20px;
            border-radius: 8px;
            cursor: pointer;
            width: 100%;
            transition: all 0.3s;
            font-weight: bold;
            letter-spacing: 1px;
            text-transform: uppercase;
            margin-top: 15px;
            position: relative;
            overflow: hidden;
        }
        
        button:hover {
            background: linear-gradient(to right, #1a1a1a, #000000);
            transform: translateY(-3px);
            box-shadow: 0 7px 20px rgba(212, 175, 55, 0.4);
            color: #FFD700;
            border-color: #FFD700;
        }
        
        button:active {
            transform: translateY(1px);
        }
        
        .error {
            color: #FFD700;
            font-size: 15px;
            margin-top: 8px;
            display: none;
            background: rgba(0, 0, 0, 0.7);
            padding: 8px 12px;
            border-radius: 5px;
            border-left: 3px solid #D4AF37;
        }
        
        footer {
            text-align: center;
            margin-top: 35px;
            color: #D4AF37;
            font-size: 1.05rem;
            opacity: 0.8;
            padding: 25px;
            border-top: 1px solid #333;
            width: 100%;
            max-width: 800px;
        }
        
        .success-message {
            display: none;
            background: rgba(212, 175, 55, 0.1);
            color: #FFD700;
            padding: 22px;
            border-radius: 8px;
            margin-top: 25px;
            text-align: center;
            border: 1px solid #D4AF37;
            font-size: 1.2rem;
        }
        
        @media (max-width: 600px) {
            .container {
                margin: 10px;
            }
            
            .form-container {
                padding: 25px;
            }
            
            header h1 {
                font-size: 2.1rem;
            }
            
            header {
                padding: 25px;
            }
        }
        
        .form-group i {
            position: absolute;
            right: 15px;
            top: 50px;
            color: #D4AF37;
            font-size: 20px;
        }
        
        .instructions {
            background: rgba(212, 175, 55, 0.1);
            padding: 18px;
            border-radius: 8px;
            margin-bottom: 30px;
            border-left: 4px solid #D4AF37;
        }
        
        .instructions h3 {
            margin-bottom: 12px;
            color: #FFD700;
        }
        
        .kaszubski-element {
            height: 40px;
            background: 
                /* Wzór z motywem gwiazdy */
                repeating-linear-gradient(90deg, 
                    transparent, 
                    transparent 5px, 
                    #D4AF37 5px, 
                    #D4AF37 7px,
                    transparent 7px,
                    transparent 12px,
                    #D4AF37 12px,
                    #D4AF37 14px),
                /* Wzór z motywem krzyża */
                repeating-linear-gradient(90deg, 
                    #D4AF37, 
                    #D4AF37 2px, 
                    transparent 2px, 
                    transparent 4px,
                    #D4AF37 4px,
                    #D4AF37 6px,
                    transparent 6px,
                    transparent 16px);
            background-blend-mode: overlay;
            background-size: 14px 100%, 16px 100%;
            margin: 20px 0;
            opacity: 0.7;
        }
        
        /* Wzory kaszubskie w formie SVG */
        .kaszubskie-ozdoby {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: -1;
            opacity: 0.1;
        }
        
        .kaszubskie-ozdoby svg {
            position: absolute;
        }
        
        .kaszubskie-ozdoby .wzor-1 {
            top: 10%;
            left: 5%;
            width: 60px;
            height: 60px;
        }
        
        .kaszubskie-ozdoby .wzor-2 {
            bottom: 15%;
            right: 5%;
            width: 70px;
            height: 70px;
        }
        
        .kaszubskie-ozdoby .wzor-3 {
            top: 40%;
            right: 10%;
            width: 50px;
            height: 50px;
        }
        
        .kaszubskie-ozdoby .wzor-4 {
            bottom: 25%;
            left: 8%;
            width: 55px;
            height: 55px;
        }
    </style>
</head>
<body>
    <div class="kaszubski-tlo"></div>
    
    <div class="kaszubskie-ozdoby">
        <svg class="wzor-1" viewBox="0 0 100 100">
            <!-- Wzór lilii -->
            <path fill="#D4AF37" d="M50 10 L60 30 L80 35 L65 50 L70 70 L50 60 L30 70 L35 50 L20 35 L40 30 Z"/>
        </svg>
        <svg class="wzor-2" viewBox="0 0 100 100">
            <!-- Wzór gwiazdy kaszubskiej -->
            <path fill="#D4AF37" d="M50 10 L55 35 L80 35 L60 50 L70 75 L50 60 L30 75 L40 50 L20 35 L45 35 Z"/>
        </svg>
        <svg class="wzor-3" viewBox="0 0 100 100">
            <!-- Wzór serca -->
            <path fill="#D4AF37" d="M50 85 C20 65, 15 40, 30 25 C40 15, 60 20, 50 35 C40 20, 60 15, 70 25 C85 40, 80 65, 50 85 Z"/>
        </svg>
        <svg class="wzor-4" viewBox="0 0 100 100">
            <!-- Wzór krzyża -->
            <path fill="#D4AF37" d="M40 10 H60 V40 H90 V60 H60 V90 H40 V60 H10 V40 H40 Z"/>
        </svg>
    </div>
    
    <div class="container">
        <header>
            <h1>Ruch Młodych Kaszubów</h1>
            <p>Ankieta rekrutacyjna dla nowych członków</p>
        </header>
        
        <div class="kaszubski-border"></div>
        
        <div class="form-container">
            <div class="instructions">
                <h3><i class="fas fa-info-circle"></i> Informacje</h3>
                <p>Wypełnij poniższą ankietę, aby dołączyć do Ruchu Młodych Kaszubów. Wszystkie pola są wymagane.</p>
            </div>
            
            <form id="recruitmentForm" action="https://formsubmit.io/send/piotrkamienna02@gmail.com" method="POST">
                <!-- Dodane pola dla FormSubmit -->
                <input type="hidden" name="_subject" value="Nowa ankieta - Ruch Młodych Kaszubów">
                <input type="hidden" name="_template" value="table">
                <input type="hidden" name="_captcha" value="false">
                
                <div class="form-group">
                    <label for="firstName"><i class="fas fa-user"></i> Imię <span class="required">*</span></label>
                    <input type="text" id="firstName" name="firstName" required placeholder="Podaj swoje imię">
                    <i class="fas fa-user"></i>
                    <div class="error" id="firstNameError">Proszę podać imię</div>
                </div>
                
                <div class="form-group">
                    <label for="lastName">Nazwisko <span class="required">*</span></label>
                    <input type="text" id="lastName" name="lastName" required placeholder="Podaj swoje nazwisko">
                    <i class="fas fa-user"></i>
                    <div class="error" id="lastNameError">Proszę podać nazwisko</div>
                </div>
                
                <div class="form-group">
                    <label for="age">Wiek <span class="required">*</span></label>
                    <input type="number" id="age" name="age" min="12" max="35" required placeholder="Podaj swój wiek">
                    <i class="fas fa-birthday-cake"></i>
                    <div class="error" id="ageError">Proszę podać wiek (12-35)</div>
                </div>
                
                <div class="form-group">
                    <label for="phone">Numer telefonu <span class="required">*</span></label>
                    <input type="tel" id="phone" name="phone" placeholder="np. 123-456-789" required>
                    <i class="fas fa-phone"></i>
                    <div class="error" id="phoneError">Proszę podać poprawny numer telefonu</div>
                </div>
                
                <div class="form-group">
                    <label for="email">Adres e-mail <span class="required">*</span></label>
                    <input type="email" id="email" name="email" required placeholder="Podaj swój adres e-mail">
                    <i class="fas fa-envelope"></i>
                    <div class="error" id="emailError">Proszę podać poprawny adres e-mail</div>
                </div>
                
                <div class="kaszubski-element"></div>
                
                <div class="form-group">
                    <label for="motivation">Dlaczego chcesz dołączyć do Ruchu Młodych Kaszubów? <span class="required">*</span></label>
                    <textarea id="motivation" name="motivation" required placeholder="Opisz swoją motywację..."></textarea>
                    <div class="error" id="motivationError">Proszę opisać swoją motywację</div>
                </div>
                
                <button type="submit"><i class="fas fa-paper-plane"></i> Wyślij ankietę</button>
                
                <div class="success-message" id="successMessage">
                    <i class="fas fa-check-circle"></i> Dziękujemy za wypełnienie ankiety! Twoje zgłoszenie zostało przesłane.
                </div>
            </form>
        </div>
        
        <div class="kaszubski-border"></div>
    </div>
    
    <footer>
        <p>© 2023 Ruch Młodych Kaszubów | Wszelkie prawa zastrzeżone</p>
    </footer>

    <script>
        document.getElementById('recruitmentForm').addEventListener('submit', function(e) {
            e.preventDefault();
            
            // Resetowanie błędów
            const errors = document.querySelectorAll('.error');
            errors.forEach(error => error.style.display = 'none');
            
            let isValid = true;
            
            // Walidacja imienia
            const firstName = document.getElementById('firstName').value.trim();
            if (!firstName) {
                document.getElementById('firstNameError').style.display = 'block';
                isValid = false;
            }
            
            // Walidacja nazwiska
            const lastName = document.getElementById('lastName').value.trim();
            if (!lastName) {
                document.getElementById('lastNameError').style.display = 'block';
                isValid = false;
            }
            
            // Walidacja wieku
            const age = parseInt(document.getElementById('age').value);
            if (isNaN(age) || age < 12 || age > 35) {
                document.getElementById('ageError').style.display = 'block';
                isValid = false;
            }
            
            // Walidacja telefonu
            const phone = document.getElementById('phone').value.trim();
            const phoneRegex = /^[0-9\-\+\s\(\)]{9,15}$/;
            if (!phoneRegex.test(phone)) {
                document.getElementById('phoneError').style.display = 'block';
                isValid = false;
            }
            
            // Walidacja emaila
            const email = document.getElementById('email').value.trim();
            const emailRegex = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;
            if (!emailRegex.test(email)) {
                document.getElementById('emailError').style.display = 'block';
                isValid = false;
            }
            
            // Walidacja motywacji
            const motivation = document.getElementById('motivation').value.trim();
            if (!motivation) {
                document.getElementById('motivationError').style.display = 'block';
                isValid = false;
            }
            
            if (isValid) {
                // Wysłanie formularza
                const form = e.target;
                const formData = new FormData(form);
                
                fetch(form.action, {
                    method: form.method,
                    body: formData
                })
                .then(response => {
                    if (response.ok) {
                        document.getElementById('successMessage').style.display = 'block';
                        form.reset();
                        
                        // Przewiń do komunikatu sukcesu
                        document.getElementById('successMessage').scrollIntoView({
                            behavior: 'smooth'
                        });
                    } else {
                        alert('Wystąpił błąd podczas wysyłania formularza. Spróbuj ponownie.');
                    }
                })
                .catch(error => {
                    alert('Wystąpił błąd podczas wysyłania formularza. Spróbuj ponownie.');
                    console.error('Error:', error);
                });
            }
        });
        
        // Dodanie efektu wizualnego dla pól formularza
        const inputs = document.querySelectorAll('input, textarea');
        inputs.forEach(input => {
            input.addEventListener('focus', function() {
                this.parentElement.classList.add('focused');
            });
            
            input.addEventListener('blur', function() {
                this.parentElement.classList.remove('focused');
            });
        });
    </script>
</body>
</html>

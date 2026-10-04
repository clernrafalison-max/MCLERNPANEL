<!DOCTYPE html>
<html lang="fr">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>MCLERN PANEL</title>

<style>
*{
    margin:0;
    padding:0;
    box-sizing:border-box;
    font-family:Arial,sans-serif;
}

html{
    scroll-behavior:smooth;
}

body{
    background:#080808;
    color:#fff;
    min-height:100vh;
}

/* NOISE */
body::before{
    content:"";
    position:fixed;
    inset:0;
    pointer-events:none;
    opacity:.035;
    background-image:url("data:image/svg+xml,%3Csvg viewBox='0 0 180 180' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='n'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='.8' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23n)' opacity='.8'/%3E%3C/svg%3E");
    z-index:9999;
}

/* HEADER */

header{
    position:sticky;
    top:0;
    z-index:1000;

    height:70px;

    display:flex;
    align-items:center;
    justify-content:space-between;

    padding:0 6%;

    background:rgba(8,8,8,.94);
    backdrop-filter:blur(15px);

    border-bottom:1px solid #222;
}

.logo{
    font-size:25px;
    font-weight:900;
    text-decoration:none;
    color:#fff;
}

.logo span{
    color:#777;
}

.menu{
    display:flex;
    gap:25px;
}

.menu a{
    color:#aaa;
    text-decoration:none;
    cursor:pointer;
}

.menu a:hover{
    color:#fff;
}

.menu-btn{
    display:none;
    background:none;
    border:0;
    color:white;
    font-size:28px;
}

/* PAGES */

.page{
    display:none;
    padding:45px 6%;
    min-height:calc(100vh - 70px);
}

.page.active{
    display:block;
}

/* HERO */

.hero{
    min-height:75vh;

    display:flex;
    flex-direction:column;
    align-items:center;
    justify-content:center;

    text-align:center;
}

.hero-logo{
    width:120px;
    height:120px;

    display:flex;
    align-items:center;
    justify-content:center;

    border:2px solid #444;
    border-radius:30px;

    font-size:55px;
    font-weight:900;

    background:#111;

    box-shadow:
    0 0 50px rgba(255,255,255,.08);
}

.hero h1{
    font-size:clamp(42px,8vw,75px);
    margin:25px 0 10px;
}

.hero h1 span{
    color:#888;
}

.hero p{
    max-width:650px;
    color:#888;
    line-height:1.7;
}

/* BUTTON */

.btn{
    display:inline-block;
    border:0;
    padding:13px 20px;
    border-radius:10px;
    background:#fff;
    color:#000;
    font-weight:bold;
    cursor:pointer;
    text-decoration:none;
    margin-top:20px;
}

.btn:hover{
    transform:translateY(-2px);
}

/* AUTH */

.auth{
    max-width:430px;
    margin:30px auto;
    padding:30px;

    background:#111;
    border:1px solid #292929;
    border-radius:20px;
}

.auth h2{
    margin-bottom:20px;
}

input,
select,
textarea{
    width:100%;
    padding:14px;
    margin:8px 0;

    background:#080808;
    color:#fff;

    border:1px solid #333;
    border-radius:9px;

    outline:none;
}

input:focus,
select:focus,
textarea:focus{
    border-color:#777;
}

/* DASHBOARD */

.dashboard-head{
    display:flex;
    justify-content:space-between;
    align-items:center;
    flex-wrap:wrap;
    gap:15px;
    margin-bottom:30px;
}

.balance{
    padding:20px 25px;
    background:#111;
    border:1px solid #292929;
    border-radius:15px;
}

.balance small{
    color:#777;
}

.balance strong{
    display:block;
    font-size:25px;
    margin-top:5px;
}

.cards{
    display:grid;
    grid-template-columns:repeat(3,1fr);
    gap:20px;
}

.card{
    background:#111;
    border:1px solid #252525;
    border-radius:18px;
    padding:25px;
}

.card h3{
    margin-bottom:10px;
}

.card p{
    color:#888;
    line-height:1.6;
}

.icon{
    font-size:35px;
    margin-bottom:15px;
}

/* TABLE */

.table-box{
    overflow-x:auto;
    margin-top:25px;
}

table{
    width:100%;
    border-collapse:collapse;
    min-width:600px;
}

th,
td{
    padding:14px;
    text-align:left;
    border-bottom:1px solid #252525;
}

th{
    color:#aaa;
}

/* SERVICES */

.service-grid{
    display:grid;
    grid-template-columns:repeat(3,1fr);
    gap:20px;
    margin-top:25px;
}

.service{
    background:#111;
    border:1px solid #282828;
    padding:25px;
    border-radius:18px;
}

.service .price{
    color:#aaa;
    margin-top:10px;
}

/* SUPPORT */

.ticket{
    max-width:700px;
    margin:auto;
}

/* ADMIN */

.admin-warning{
    padding:15px;
    margin-bottom:20px;

    border:1px solid #333;
    border-radius:10px;

    color:#aaa;
}

/* FOOTER */

footer{
    text-align:center;
    padding:30px;
    border-top:1px solid #222;
    color:#666;
}

/* TOAST */

.toast{
    position:fixed;
    right:20px;
    bottom:20px;

    background:#fff;
    color:#000;

    padding:15px 20px;
    border-radius:10px;

    transform:translateY(100px);
    opacity:0;

    transition:.3s;

    z-index:10000;
}

.toast.show{
    transform:translateY(0);
    opacity:1;
}

/* MOBILE */

@media(max-width:800px){

    .menu-btn{
        display:block;
    }

    .menu{
        display:none;

        position:absolute;
        top:70px;
        left:0;

        width:100%;

        flex-direction:column;

        padding:25px;

        background:#0b0b0b;
        border-bottom:1px solid #222;
    }

    .menu.open{
        display:flex;
    }

    .cards,
    .service-grid{
        grid-template-columns:1fr;
    }

    .page{
        padding:30px 5%;
    }

    .dashboard-head{
        align-items:stretch;
        flex-direction:column;
    }
}
</style>
</head>

<body>

<header>

    <a class="logo" onclick="showPage('home')">
        MCLERN<span>.</span>
    </a>

    <button class="menu-btn" onclick="toggleMenu()">☰</button>

    <nav class="menu" id="menu">
        <a onclick="showPage('home')">Accueil</a>
        <a onclick="showPage('services')">Services</a>
        <a onclick="showPage('login')">Connexion</a>
        <a onclick="showPage('register')">Inscription</a>
        <a onclick="showPage('support')">Support</a>
    </nav>

</header>


<!-- ACCUEIL -->

<section id="home" class="page active">

    <div class="hero">

        <div class="hero-logo">
            M.
        </div>

        <h1>
            MCLERN <span>PANEL</span>
        </h1>

        <p>
            Votre espace digital moderne pour gérer vos
            services, commandes, paiements et support
            depuis votre téléphone.
        </p>

        <button class="btn" onclick="showPage('register')">
            Créer un compte
        </button>

    </div>

</section>


<!-- INSCRIPTION -->

<section id="register" class="page">

    <div class="auth">

        <h2>Créer un compte</h2>

        <input
            id="regUsername"
            type="text"
            placeholder="Username"
        >

        <input
            id="regName"
            type="text"
            placeholder="Nom complet"
        >

        <input
            id="regTelegram"
            type="text"
            placeholder="Numéro Telegram"
        >

        <input
            id="regPassword"
            type="password"
            placeholder="Mot de passe"
        >

        <button class="btn" onclick="register()">
            S'inscrire
        </button>

        <p style="margin-top:15px;color:#777;">
            Déjà membre ?
            <a href="#" onclick="showPage('login')" style="color:white;">
                Se connecter
            </a>
        </p>

    </div>

</section>


<!-- CONNEXION -->

<section id="login" class="page">

    <div class="auth">

        <h2>Connexion</h2>

        <input
            id="loginUsername"
            type="text"
            placeholder="Username"
        >

        <input
            id="loginPassword"
            type="password"
            placeholder="Mot de passe"
        >

        <button class="btn" onclick="login()">
            Se connecter
        </button>

        <button
            class="btn"
            style="background:#222;color:white;width:100%;"
            onclick="googleDemo()"
        >
            Continuer avec Google
        </button>

    </div>

</section>


<!-- DASHBOARD -->

<section id="dashboard" class="page">

    <div class="dashboard-head">

        <div>
            <p style="color:#777;">Bienvenue</p>
            <h1 id="welcomeUser">Utilisateur</h1>
        </div>

        <div class="balance">

            <small>Solde actuel</small>

            <strong id="balance">
                0 Ar
            </strong>

            <button
                class="btn"
                onclick="showPage('payment')"
            >
                Ajouter du solde
            </button>

        </div>

    </div>


    <div class="cards">

        <div class="card">

            <div class="icon">🛒</div>

            <h3>Nouvelle commande</h3>

            <p>
                Créez une nouvelle commande.
            </p>

            <button
                class="btn"
                onclick="showPage('services')"
            >
                Commander
            </button>

        </div>


        <div class="card">

            <div class="icon">📊</div>

            <h3>Mes commandes</h3>

            <p>
                Consultez votre historique.
            </p>

            <button
                class="btn"
                onclick="showPage('orders')"
            >
                Voir
            </button>

        </div>


        <div class="card">

            <div class="icon">🎫</div>

            <h3>Support</h3>

            <p>
                Besoin d'aide ?
            </p>

            <button
                class="btn"
                onclick="showPage('support')"
            >
                Contacter
            </button>

        </div>

    </div>

</section>


<!-- SERVICES -->

<section id="services" class="page">

    <h1>Services</h1>

    <p style="color:#777;margin-top:10px;">
        Services digitaux disponibles sur MCLERN PANEL.
    </p>


    <div class="service-grid">

        <div class="service">

            <div class="icon">🎨</div>

            <h3>Design graphique</h3>

            <p>
                Création de visuels et contenus graphiques.
            </p>

            <div class="price">
                À partir de 2 000 Ar
            </div>

            <button
                class="btn"
                onclick="selectService('Design graphique')"
            >
                Commander
            </button>

        </div>


        <div class="service">

            <div class="icon">🌐</div>

            <h3>Création de site</h3>

            <p>
                Création de sites web modernes.
            </p>

            <div class="price">
                À partir de 10 000 Ar
            </div>

            <button
                class="btn"
                onclick="selectService('Création de site')"
            >
                Commander
            </button>

        </div>


        <div class="service">

            <div class="icon">📱</div>

            <h3>Service digital</h3>

            <p>
                Solutions digitales adaptées à vos projets.
            </p>

            <div class="price">
                Prix sur demande
            </div>

            <button
                class="btn"
                onclick="selectService('Service digital')"
            >
                Commander
            </button>

        </div>

    </div>

</section>


<!-- NOUVELLE COMMANDE -->

<section id="order" class="page">

    <div class="auth">

        <h2>Nouvelle commande</h2>

        <label>Service</label>

        <select id="orderService" onchange="calculatePrice()">

            <option value="Design graphique">
                Design graphique
            </option>

            <option value="Création de site">
                Création de site
            </option>

            <option value="Service digital">
                Service digital
            </option>

        </select>


        <input
            id="orderLink"
            type="text"
            placeholder="Lien / informations du projet"
        >


        <input
            id="orderQuantity"
            type="number"
            placeholder="Quantité"
            value="1"
            oninput="calculatePrice()"
        >


        <div
            style="
            margin-top:15px;
            padding:15px;
            background:#080808;
            border:1px solid #292929;
            border-radius:10px;
            "
        >

            Prix estimé :

            <strong id="orderPrice">
                2 000 Ar
            </strong>

        </div>


        <button
            class="btn"
            onclick="createOrder()"
        >
            Commander
        </button>

    </div>

</section>


<!-- COMMANDES -->

<section id="orders" class="page">

    <h1>Mes commandes</h1>

    <div class="table-box">

        <table>

            <thead>

                <tr>
                    <th>ID</th>
                    <th>Service</th>
                    <th>Date</th>
                    <th>Prix</th>
                    <th>Statut</th>
                </tr>

            </thead>

            <tbody id="ordersTable">

                <tr>
                    <td colspan="5">
                        Aucune commande.
                    </td>
                </tr>

            </tbody>

        </table>

    </div>

</section>


<!-- PAIEMENT -->

<section id="payment" class="page">

    <div class="auth">

        <h2>Ajouter du solde</h2>

        <p style="color:#888;line-height:1.6;">
            Paiement Mobile Money.
        </p>

        <div
            style="
            margin:20px 0;
            padding:18px;
            background:#080808;
            border:1px solid #333;
            border-radius:12px;
            "
        >

            <strong>Numéro de paiement</strong>

            <br><br>

            038 29 698 96

            <br>

            FLORIDA

        </div>


        <input
            id="paymentAmount"
            type="number"
            placeholder="Montant en Ariary"
        >

        <input
            id="paymentReference"
            type="text"
            placeholder="Référence du paiement"
        >

        <button
            class="btn"
            onclick="submitPayment()"
        >
            Envoyer le paiement
        </button>

    </div>

</section>


<!-- SUPPORT -->

<section id="support" class="page">

    <div class="ticket">

        <h1>Support</h1>

        <p style="color:#777;margin:10px 0 25px;">
            Ouvrez un ticket pour contacter le support.
        </p>

        <textarea
            id="ticketMessage"
            rows="7"
            placeholder="Décrivez votre problème..."
        ></textarea>

        <button
            class="btn"
            onclick="sendTicket()"
        >
            Envoyer le ticket
        </button>

        <div
            class="card"
            style="margin-top:25px;"
        >

            <h3>Contact direct</h3>

            <p>
                IMO : 0382969896
            </p>

            <p>
                Telegram : 0384908995
            </p>

        </div>

    </div>

</section>


<!-- ADMIN DEMO -->

<section id="admin" class="page">

    <h1>Administration</h1>

    <div class="admin-warning">
        ⚠️ Interface administrateur DEMO.
        Dans une vraie application, cette page doit
        être protégée par un backend sécurisé.
    </div>


    <div class="cards">

        <div class="card">
            <h3>👥 Utilisateurs</h3>
            <p id="userCount">0</p>
        </div>

        <div class="card">
            <h3>🛒 Commandes</h3>
            <p id="adminOrderCount">0</p>
        </div>

        <div class="card">
            <h3>💳 Paiements</h3>
            <p id="paymentCount">0</p>
        </div>

    </div>

</section>


<footer>

    <div class="logo">
        MCLERN<span>.</span>
    </div>

    <p>
        © 2026 MCLERN PANEL — Prototype
    </p>

</footer>


<div class="toast" id="toast"></div>


<script>

/* DATABASE DEMO */

let user =
    JSON.parse(localStorage.getItem("mclernUser")) || null;

let balance =
    Number(localStorage.getItem("mclernBalance")) || 0;

let orders =
    JSON.parse(localStorage.getItem("mclernOrders")) || [];

let payments =
    JSON.parse(localStorage.getItem("mclernPayments")) || [];


/* MENU */

function toggleMenu(){

    document
        .getElementById("menu")
        .classList.toggle("open");

}


/* PAGE NAVIGATION */

function showPage(page){

    document
        .querySelectorAll(".page")
        .forEach(p => p.classList.remove("active"));

    const target =
        document.getElementById(page);

    if(target){

        target.classList.add("active");

        window.scrollTo({
            top:0,
            behavior:"smooth"
        });

    }

    document
        .getElementById("menu")
        .classList.remove("open");


    updateDashboard();

}


/* TOAST */

function toast(message){

    const box =
        document.getElementById("toast");

    box.textContent = message;

    box.classList.add("show");

    setTimeout(() => {

        box.classList.remove("show");

    },3000);

}


/* REGISTER */

function register(){

    const username =
        document.getElementById("regUsername").value.trim();

    const name =
        document.getElementById("regName").value.trim();

    const telegram =
        document.getElementById("regTelegram").value.trim();

    const password =
        document.getElementById("regPassword").value;


    if(!username || !name || !telegram || !password){

        toast("Veuillez remplir tous les champs.");

        return;

    }


    user = {

        username,
        name,
        telegram,

        /*
        DEMO uniquement.
        En production, ne jamais stocker
        un mot de passe de cette façon.
        */

        password

    };


    localStorage.setItem(
        "mclernUser",
        JSON.stringify(user)
    );


    toast("Compte créé avec succès.");

    showPage("login");

}


/* LOGIN */

function login(){

    const username =
        document.getElementById("loginUsername").value.trim();

    const password =
        document.getElementById("loginPassword").value;


    if(!user){

        toast("Aucun compte trouvé.");

        return;

    }


    if(
        username === user.username &&
        password === user.password
    ){

        toast("Connexion réussie.");

        updateDashboard();

        showPage("dashboard");

    }else{

        toast("Username ou mot de passe incorrect.");

    }

}


/* GOOGLE DEMO */

function googleDemo(){

    toast(
        "Google Login nécessite une vraie authentification OAuth."
    );

}


/* DASHBOARD */

function updateDashboard(){

    if(user){

        document
            .getElementById("welcomeUser")
            .textContent =
            user.name || user.username;

    }


    document
        .getElementById("balance")
        .textContent =
        balance.toLocaleString("fr-FR") + " Ar";


    renderOrders();

}


/* SERVICES */

function selectService(service){

    document
        .getElementById("orderService")
        .value = service;

    calculatePrice();

    showPage("order");

}


/* CALCUL PRIX DEMO */

function calculatePrice(){

    const service =
        document
        .getElementById("orderService")
        .value;

    let quantity =
        Number(
            document
            .getElementById("orderQuantity")
            .value
        ) || 1;


    let unitPrice = 2000;


    if(service === "Création de site"){

        unitPrice = 10000;

    }

    if(service === "Service digital"){

        unitPrice = 5000;

    }


    const total =
        unitPrice * quantity;


    document
        .getElementById("orderPrice")
        .textContent =
        total.toLocaleString("fr-FR") + " Ar";

}


/* CREATE ORDER */

function createOrder(){

    if(!user){

        toast("Connectez-vous d'abord.");

        showPage("login");

        return;

    }


    const service =
        document
        .getElementById("orderService")
        .value;

    const link =
        document
        .getElementById("orderLink")
        .value.trim();

    const quantity =
        Number(
            document
            .getElementById("orderQuantity")
            .value
        ) || 1;


    if(!link){

        toast("Veuillez ajouter les informations du projet.");

        return;

    }


    let unitPrice = 2000;

    if(service === "Création de site")
        unitPrice = 10000;

    if(service === "Service digital")
        unitPrice = 5000;


    const total =
        unitPrice * quantity;


    if(balance < total){

        toast("Solde insuffisant.");

        showPage("payment");

        return;

    }


    balance -= total;


    const order = {

        id:
        "ML" +
        Date.now()
        .toString()
        .slice(-6),

        service,

        date:
        new Date()
        .toLocaleString("fr-FR"),

        price:total,

        status:"En attente"

    };


    orders.push(order);


    localStorage.setItem(
        "mclernOrders",
        JSON.stringify(orders)
    );


    localStorage.setItem(
        "mclernBalance",
        balance
    );


    toast("Commande créée avec succès.");

    document
        .getElementById("orderLink")
        .value = "";

    showPage("orders");

}


/* ORDERS */

function renderOrders(){

    const table =
        document
        .getElementById("ordersTable");


    if(!orders.length){

        table.innerHTML = `
        <tr>
            <td colspan="5">
                Aucune commande.
            </td>
        </tr>
        `;

        return;

    }


    table.innerHTML = "";


    orders.forEach(order => {

        table.innerHTML += `

        <tr>

            <td>${order.id}</td>

            <td>${order.service}</td>

            <td>${order.date}</td>

            <td>
                ${order.price.toLocaleString("fr-FR")} Ar
            </td>

            <td>
                ${order.status}
            </td>

        </tr>

        `;

    });

}


/* PAYMENT DEMO */

function submitPayment(){

    if(!user){

        toast("Connectez-vous d'abord.");

        showPage("login");

        return;

    }


    const amount =
        Number(
            document
            .getElementById("paymentAmount")
            .value
        );

    const reference =
        document
        .getElementById("paymentReference")
        .value.trim();


    if(!amount || amount <= 0 || !reference){

        toast("Remplissez les informations du paiement.");

        return;

    }


    const payment = {

        id:
        "PAY" +
        Date.now()
        .toString()
        .slice(-6),

        amount,

        reference,

        status:"En attente",

        date:
        new Date()
        .toLocaleString("fr-FR")

    };


    payments.push(payment);


    localStorage.setItem(
        "mclernPayments",
        JSON.stringify(payments)
    );


    toast(
        "Paiement envoyé. En attente de validation."
    );


    document
        .getElementById("paymentAmount")
        .value = "";

    document
        .getElementById("paymentReference")
        .value = "";

}


/* SUPPORT */

function sendTicket(){

    const message =
        document
        .getElementById("ticketMessage")
        .value.trim();


    if(!message){

        toast("Écrivez votre message.");

        return;

    }


    toast(
        "Ticket envoyé au support."
    );


    document
        .getElementById("ticketMessage")
        .value = "";

}


/* ADMIN DEMO */

function updateAdmin(){

    document
        .getElementById("userCount")
        .textContent =
        user ? "1 utilisateur demo" : "0";

    document
        .getElementById("adminOrderCount")
        .textContent =
        orders.length;

    document
        .getElementById("paymentCount")
        .textContent =
        payments.length;

}


/* INITIALISATION */

updateDashboard();

updateAdmin();

</script>

</body>
</html>

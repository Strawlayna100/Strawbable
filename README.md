# Strawbable
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Strawbabble - Sweet Strawberry Shenanigans</title>
    <link rel="stylesheet" href="styles.css">
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;600;700&display=swap" rel="stylesheet">
</head>
<body>
    <header>
        <nav class="navbar">
            <div class="nav-container">
                <h1 class="logo">🍓 Strawbabble</h1>
                <ul class="nav-menu">
                    <li><a href="#home">Home</a></li>
                    <li><a href="#facts">Fun Facts</a></li>
                    <li><a href="#recipes">Recipes</a></li>
                    <li><a href="#blog">Babble</a></li>
                </ul>
                <div class="hamburger">
                    <span></span>
                    <span></span>
                    <span></span>
                </div>
            </div>
        </nav>
    </header>

    <section id="home" class="hero">
        <div class="hero-content">
            <h2>Welcome to the Berry Babble!</h2>
            <p>Where strawberries whisper secrets and sweetness reigns supreme. Dive into juicy adventures!</p>
            <button class="cta-btn" onclick="scrollToSection('recipes')">Get Your Berry Fix</button>
        </div>
        <div class="hero-berry"></div>
    </section>

    <section id="facts" class="facts">
        <h2>Strawberry Fun Facts</h2>
        <div class="facts-grid">
            <div class="fact-card">
                <h3>🍓 Fact 1</h3>
                <p>Strawberries are the only fruit with seeds on the outside—over 200 per berry!</p>
            </div>
            <div class="fact-card">
                <h3>🍓 Fact 2</h3>
                <p>They're not actually berries; botanically, they're "aggregate fruits." Mind blown?</p>
            </div>
            <div class="fact-card">
                <h3>🍓 Fact 3</h3>
                <p>Ancient Romans believed strawberries could cure everything from bad breath to fainting.</p>
            </div>
            <div class="fact-card">
                <h3>🍓 Fact 4</h3>
                <p>The biggest strawberry ever? 8.1 ounces—bigger than your phone!</p>
            </div>
        </div>
    </section>

    <section id="recipes" class="recipes">
        <h2>Strawberry Delights</h2>
        <p class="section-intro">Whip up something sweet. Click a recipe for deets!</p>
        <div class="recipes-container">
            <div class="recipe-card" onclick="showRecipe('smoothie')">
                <h3>Berry Blast Smoothie</h3>
                <img src="https://via.placeholder.com/300x200/ff69b4/ffffff?text=Smoothie" alt="Smoothie">
                <p>Creamy, dreamy, and ready in 5 mins.</p>
            </div>
            <div class="recipe-card" onclick="showRecipe('salad')">
                <h3>Strawberry Spinach Salad</h3>
                <img src="https://via.placeholder.com/300x200/ff69b4/ffffff?text=Salad" alt="Salad">
                <p>Fresh greens meet ruby reds—healthy & yummy.</p>
            </div>
            <div class="recipe-card" onclick="showRecipe('shortcake')">
                <h3>Classic Shortcake</h3>
                <img src="https://via.placeholder.com/300x200/ff69b4/ffffff?text=Shortcake" alt="Shortcake">
                <p>Fluffy biscuits + whipped cream = heaven.</p>
            </div>
        </div>
        <div id="recipe-modal" class="modal">
            <div class="modal-content">
                <span class="close" onclick="closeRecipe()">&times;</span>
                <div id="recipe-details"></div>
            </div>
        </div>
    </section>

    <section id="blog" class="blog">
        <h2>Babble Away</h2>
        <p class="section-intro">Our chatty corner for strawberry stories and rants.</p>
        <div class="blog-posts">
            <article class="blog-post">
                <h3>Why Strawberries Are the Ultimate Mood Booster</h3>
                <p>Spilling the tea on how one bite can turn your frown upside down. Vitamin C overload, anyone?</p>
                <a href="#" class="read-more">Read More →</a>
            </article>
            <article class="blog-post">
                <h3>Strawbabble's Top Picks: Berry Festivals Worldwide</h3>
                <p>From Japan's strawberry picking to California's harvest bash—where to berry-hop next!</p>
                <a href="#" class="read-more">Read More →</a>
            </article>
        </div>
    </section>

    <footer>
        <p>&copy; 2025 Strawbabble. All rights reserved. Made with ❤️ and strawberries.</p>
    </footer>

    <script src="script.js"></script>
</body>
</html>
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

body {
    font-family: 'Poppins', sans-serif;
    line-height: 1.6;
    color: #333;
    overflow-x: hidden;
}

.navbar {
    background: linear-gradient(135deg, #ff69b4, #ff1493);
    padding: 1rem 0;
    position: fixed;
    width: 100%;
    top: 0;
    z-index: 1000;
    box-shadow: 0 2px 10px rgba(255, 105, 180, 0.3);
}

.nav-container {
    max-width: 1200px;
    margin: 0 auto;
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 0 2rem;
}

.logo {
    color: white;
    font-size: 1.5rem;
    font-weight: 700;
}

.nav-menu {
    display: flex;
    list-style: none;
    gap: 2rem;
}

.nav-menu a {
    color: white;
    text-decoration: none;
    font-weight: 400;
    transition: color 0.3s;
}

.nav-menu a:hover {
    color: #ffd700;
}

.hamburger {
    display: none;
    flex-direction: column;
    cursor: pointer;
}

.hamburger span {
    width: 25px;
    height: 3px;
    background: white;
    margin: 3px 0;
    transition: 0.3s;
}

/* Hero Section */
.hero {
    height: 100vh;
    background: linear-gradient(135deg, #ffc0cb, #ff69b4);
    display: flex;
    align-items: center;
    justify-content: center;
    text-align: center;
    position: relative;
    overflow: hidden;
}

.hero-content h2 {
    font-size: 3rem;
    color: white;
    margin-bottom: 1rem;
    animation: fadeInUp 1s ease-out;
}

.hero-content p {
    font-size: 1.2rem;
    color: white;
    margin-bottom: 2rem;
    animation: fadeInUp 1s ease-out 0.2s both;
}

.cta-btn {
    background: #ff1493;
    color: white;
    border: none;
    padding: 1rem 2rem;
    font-size: 1.1rem;
    border-radius: 50px;
    cursor: pointer;
    transition: transform 0.3s, box-shadow 0.3s;
    animation: fadeInUp 1s ease-out 0.4s both;
}

.cta-btn:hover {
    transform: scale(1.05);
    box-shadow: 0 5px 15px rgba(255, 20, 147, 0.4);
}

.hero-berry {
    position: absolute;
    bottom: 0;
    right: 10%;
    width: 200px;
    height: 200px;
    background: radial-gradient(circle, #ff69b4, #ff1493);
    border-radius: 50% 50% 50% 0;
    animation: bounce 2s infinite;
}

@keyframes fadeInUp {
    from { opacity: 0; transform: translateY(30px); }
    to { opacity: 1; transform: translateY(0); }
}

@keyframes bounce {
    0%, 20%, 50%, 80%, 100% { transform: translateY(0); }
    40% { transform: translateY(-20px); }
    60% { transform: translateY(-10px); }
}

/* Sections */
section {
    padding: 5rem 2rem;
    max-width: 1200px;
    margin: 0 auto;
}

h2 {
    text-align: center;
    font-size: 2.5rem;
    margin-bottom: 3rem;
    color: #ff69b4;
}

.section-intro {
    text-align: center;
    font-size: 1.1rem;
    margin-bottom: 2rem;
    color: #666;
}

/* Facts */
.facts-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
    gap: 2rem;
}

.fact-card {
    background: white;
    padding: 2rem;
    border-radius: 15px;
    box-shadow: 0 5px 20px rgba(255, 105, 180, 0.1);
    text-align: center;
    transition: transform 0.3s, box-shadow 0.3s;
}

.fact-card:hover {
    transform: translateY(-5px);
    box-shadow: 0 10px 30px rgba(255, 105, 180, 0.2);
}

.fact-card h3 {
    color: #ff69b4;
    margin-bottom: 1rem;
}

/* Recipes */
.recipes-container {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
    gap: 2rem;
}

.recipe-card {
    background: white;
    border-radius: 15px;
    overflow: hidden;
    box-shadow: 0 5px 20px rgba(255, 105, 180, 0.1);
    cursor: pointer;
    transition: transform 0.3s;
}

.recipe-card:hover {
    transform: scale(1.02);
}

.recipe-card img {
    width: 100%;
    height: 200px;
    object-fit: cover;
}

.recipe-card h3 {
    padding: 1rem;
    color: #ff69b4;
}

.recipe-card p {
    padding: 0 1rem 1rem;
}

/* Modal */
.modal {
    display: none;
    position: fixed;
    z-index: 2000;
    left: 0;
    top: 0;
    width: 100%;
    height: 100%;
    background: rgba(0,0,0,0.5);
    animation: fadeIn 0.3s;
}

.modal-content {
    background: white;
    margin: 10% auto;
    padding: 2rem;
    border-radius: 15px;
    width: 80%;
    max-width: 500px;
    position: relative;
    animation: slideIn 0.3s;
}

.close {
    position: absolute;
    right: 1rem;
    top: 1rem;
    font-size: 2rem;
    cursor: pointer;
    color: #ff69b4;
}

@keyframes fadeIn { from { opacity: 0; } to { opacity: 1; } }
@keyframes slideIn { from { transform: translateY(-50px); } to { transform: translateY(0); } }

/* Blog */
.blog-posts {
    display: flex;
    flex-direction: column;
    gap: 2rem;
}

.blog-post {
    background: white;
    padding: 2rem;
    border-radius: 15px;
    box-shadow: 0 5px 20px rgba(255, 105, 180, 0.1);
    transition: box-shadow 0.3s;
}

.blog-post:hover {
    box-shadow: 0 10px 30px rgba(255, 105, 180, 0.2);
}

.blog-post h3 {
    color: #ff69b4;
    margin-bottom: 1rem;
}

.read-more {
    color: #ff1493;
    text-decoration: none;
    font-weight: 600;
}

/* Footer */
footer {
    background: #ff69b4;
    color: white;
    text-align: center;
    padding: 2rem;
}

/* Mobile */
@media (max-width: 768px) {
    .hamburger {
        display: flex;
    }

    .nav-menu {
        position: fixed;
        left: -100%;
        top: 70px;
        flex-direction: column;
        background: #ff69b4;
        width: 100%;
        text-align: center;
        transition: 0.3s;
        padding: 2rem 0;
    }

    .nav-menu.active {
        left: 0;
    }

    .hero-content h2 {
        font-size: 2rem;
    }

    section {
        padding: 3rem 1rem;
    }
}
// Mobile menu toggle
const hamburger = document.querySelector('.hamburger');
const navMenu = document.querySelector('.nav-menu');

hamburger.addEventListener('click', () => {
    hamburger.classList.toggle('active');
    navMenu.classList.toggle('active');
});

// Close mobile menu on link click
document.querySelectorAll('.nav-menu a').forEach(link => {
    link.addEventListener('click', () => {
        hamburger.classList.remove('active');
        navMenu.classList.remove('active');
    });
});

// Smooth scroll to sections
function scrollToSection(id) {
    document.getElementById(id).scrollIntoView({ behavior: 'smooth' });
}

// Nav links
document.querySelectorAll('a[href^="#"]').forEach(anchor => {
    anchor.addEventListener('click', function (e) {
        e.preventDefault();
        const target = document.querySelector(this.getAttribute('href'));
        if (target) {
            target.scrollIntoView({ behavior: 'smooth' });
        }
    });
});

// Recipe modal
const recipes = {
    smoothie: {
        title: 'Berry Blast Smoothie',
        ingredients: ['2 cups strawberries', '1 banana', '1 cup yogurt', '1/2 cup milk', 'Ice'],
        instructions: 'Blend all until smooth. Serve chilled. Prep: 5 mins.'
    },
    salad: {
        title: 'Strawberry Spinach Salad',
        ingredients: ['4 cups spinach', '1 cup sliced strawberries', '1/4 cup feta', '1/4 cup almonds', 'Balsamic vinaigrette'],
        instructions: 'Toss everything together. Drizzle dressing. Ready in 10 mins!'
    },
    shortcake: {
        title: 'Classic Strawberry Shortcake',
        ingredients: ['Biscuits', '2 cups strawberries', 'Whipped cream', 'Sugar'],
        instructions: 'Slice biscuits, layer with macerated strawberries and cream. Indulge!'
    }
};

function showRecipe(type) {
    const modal = document.getElementById('recipe-modal');
    const details = document.getElementById('recipe-details');
    const recipe = recipes[type];

    details.innerHTML = `
        <h3>${recipe.title}</h3>
        <h4>Ingredients:</h4>
        <ul>${recipe.ingredients.map(ing => `<li>${ing}</li>`).join('')}</ul>
        <h4>Instructions:</h4>
        <p>${recipe.instructions}</p>
    `;
    modal.style.display = 'block';
}

function closeRecipe() {
    document.getElementById('recipe-modal').style.display = 'none';
}

// Close modal on outside click
window.onclick = function(event) {
    const modal = document.getElementById('recipe-modal');
    if (event.target === modal) {
        modal.style.display = 'none';
    }
}

// Random recipe suggestion on load (fun touch!)
window.addEventListener('load', () => {
    const randomKey = Object.keys(recipes)[Math.floor(Math.random() * Object.keys(recipes).length)];
    console.log(`Try this: ${recipes[randomKey].title}`); // Could add a toast notification here for UX
});

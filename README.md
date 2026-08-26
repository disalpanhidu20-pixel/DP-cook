<!DOCTYPE html>
<html lang="si">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>Rasata Recipe Hub | රසට Recipe</title>

<style>

*{
    margin:0;
    padding:0;
    box-sizing:border-box;
}

html{
    scroll-behavior:smooth;
}

body{
    font-family:
        Arial,
        "Noto Sans Sinhala",
        sans-serif;

    color:#222;

    background:
    linear-gradient(
        rgba(255,255,255,.78),
        rgba(255,255,255,.90)
    ),
    url("https://images.unsplash.com/photo-1498837167922-ddd27525d352?auto=format&fit=crop&w=2200&q=90");

    background-size:cover;
    background-position:center;
    background-attachment:fixed;
}


/* ================= HEADER ================= */

header{
    min-height:350px;

    display:flex;
    flex-direction:column;
    justify-content:center;
    align-items:center;

    text-align:center;

    padding:50px 20px;

    color:white;

    background:
    linear-gradient(
        rgba(0,0,0,.48),
        rgba(0,0,0,.62)
    ),
    url("https://images.unsplash.com/photo-1504674900247-0877df9cc836?auto=format&fit=crop&w=2200&q=90");

    background-size:cover;
    background-position:center;

    box-shadow:
        0 10px 35px rgba(0,0,0,.3);
}

header h1{
    font-size:55px;

    margin-bottom:15px;

    text-shadow:
        0 5px 20px rgba(0,0,0,.6);
}

header p{
    font-size:21px;

    margin-bottom:20px;
}

.badge{
    padding:12px 25px;

    border-radius:50px;

    background:
        rgba(255,255,255,.18);

    border:
        1px solid rgba(255,255,255,.4);

    backdrop-filter:blur(10px);

    font-weight:bold;
}


/* ================= SEARCH ================= */

.search-area{
    max-width:1000px;

    margin:-35px auto 25px;

    padding:0 20px;

    position:relative;

    z-index:20;
}

.search-box{
    display:flex;

    padding:8px;

    background:
        rgba(255,255,255,.96);

    border-radius:60px;

    box-shadow:
        0 15px 45px rgba(0,0,0,.22);
}

.search-box input{
    flex:1;

    border:none;

    outline:none;

    background:transparent;

    padding:17px 25px;

    font-size:18px;
}

.search-box button{
    border:none;

    padding:0 30px;

    border-radius:50px;

    background:
        linear-gradient(
            135deg,
            #ff512f,
            #dd2476
        );

    color:white;

    font-size:17px;

    font-weight:bold;

    cursor:pointer;
}


/* ================= CATEGORIES ================= */

.categories{
    max-width:1250px;

    margin:auto;

    padding:10px 20px 20px;

    text-align:center;
}

.categories button{
    border:none;

    padding:11px 18px;

    margin:5px;

    border-radius:30px;

    background:white;

    font-weight:bold;

    cursor:pointer;

    box-shadow:
        0 4px 15px rgba(0,0,0,.10);

    transition:.25s;
}

.categories button:hover,
.categories button.active{
    color:white;

    background:
        linear-gradient(
            135deg,
            #ff512f,
            #dd2476
        );

    transform:translateY(-2px);
}


/* ================= RESULT ================= */

.result{
    max-width:1250px;

    margin:auto;

    padding:5px 20px 15px;

    font-size:18px;

    font-weight:bold;
}


/* ================= GRID ================= */

.container{
    max-width:1250px;

    margin:auto;

    padding:0 20px 50px;
}

.grid{
    display:grid;

    grid-template-columns:
        repeat(
            auto-fit,
            minmax(270px,1fr)
        );

    gap:25px;
}


/* ================= CARD ================= */

.card{
    background:
        rgba(255,255,255,.96);

    border-radius:22px;

    overflow:hidden;

    box-shadow:
        0 10px 30px rgba(0,0,0,.14);

    transition:.35s;

    border:
        1px solid rgba(255,255,255,.8);
}

.card:hover{
    transform:
        translateY(-8px);

    box-shadow:
        0 20px 45px rgba(0,0,0,.22);
}

.card-img{
    height:210px;

    overflow:hidden;

    position:relative;
}

.card-img img{
    width:100%;
    height:100%;

    object-fit:cover;

    transition:.5s;
}

.card:hover img{
    transform:scale(1.08);
}

.card-body{
    padding:20px;
}

.tag{
    display:inline-block;

    padding:6px 12px;

    border-radius:20px;

    background:#ffe9e3;

    color:#df3c22;

    font-size:13px;

    font-weight:bold;

    margin-bottom:10px;
}

.card-body h2{
    font-size:23px;

    margin-bottom:5px;
}

.card-body h3{
    color:#666;

    font-size:16px;

    margin-bottom:12px;
}

.card-body p{
    color:#666;

    line-height:1.5;

    min-height:50px;

    margin-bottom:17px;
}

.view{
    width:100%;

    border:none;

    padding:13px;

    border-radius:12px;

    color:white;

    background:
        linear-gradient(
            135deg,
            #ff512f,
            #dd2476
        );

    font-size:16px;

    font-weight:bold;

    cursor:pointer;
}


/* ================= NO RESULT ================= */

.no-result{
    display:none;

    text-align:center;

    padding:70px 20px;

    font-size:23px;

    color:#666;

    background:
        rgba(255,255,255,.9);

    border-radius:20px;
}


/* ================= MODAL ================= */

.modal{
    display:none;

    position:fixed;

    inset:0;

    z-index:9999;

    padding:20px 10px;

    overflow-y:auto;

    background:
        rgba(0,0,0,.78);

    backdrop-filter:
        blur(6px);
}

.modal-box{
    max-width:900px;

    margin:auto;

    background:white;

    border-radius:25px;

    overflow:hidden;

    animation:
        popup .25s ease;
}

@keyframes popup{

    from{
        transform:scale(.85);
        opacity:0;
    }

    to{
        transform:scale(1);
        opacity:1;
    }

}

.modal-image{
    width:100%;

    height:350px;

    object-fit:cover;
}

.modal-body{
    padding:30px;
}

.close{
    float:right;

    width:43px;
    height:43px;

    display:flex;

    align-items:center;
    justify-content:center;

    border-radius:50%;

    background:#eee;

    font-size:28px;

    cursor:pointer;
}

.close:hover{
    background:#ff512f;

    color:white;
}

.modal-body h2{
    font-size:36px;

    margin-bottom:5px;

    padding-right:55px;
}

.modal-body h3{
    color:#e33d20;

    margin-top:25px;

    margin-bottom:12px;

    font-size:22px;
}

.subtitle{
    color:#666;

    font-size:18px;

    margin-bottom:15px;
}

.info{
    display:flex;

    flex-wrap:wrap;

    gap:10px;

    margin:15px 0;
}

.info span{
    padding:9px 13px;

    background:#f5f5f5;

    border-radius:10px;

    font-weight:bold;

    font-size:14px;
}

.language-box{
    margin-top:25px;

    padding:20px;

    background:#fff8f5;

    border-left:
        5px solid #ff512f;

    border-radius:12px;

    line-height:1.8;
}

.ingredients{
    display:grid;

    grid-template-columns:
        repeat(
            auto-fit,
            minmax(250px,1fr)
        );

    gap:10px;
}

.ingredient{
    padding:10px 13px;

    background:#f7f7f7;

    border-radius:9px;
}

.steps{
    padding-left:25px;

    line-height:1.9;
}

.steps li{
    margin-bottom:10px;
}

.tip{
    padding:18px;

    margin-top:10px;

    background:#fff4c7;

    border-radius:12px;

    line-height:1.7;
}


/* ================= FOOTER ================= */

footer{
    padding:45px 20px;

    text-align:center;

    color:white;

    background:
        rgba(0,0,0,.92);
}

footer h2{
    margin-bottom:10px;
}


/* ================= MOBILE ================= */

@media(max-width:700px){

    header{
        min-height:290px;
    }

    header h1{
        font-size:35px;
    }

    header p{
        font-size:16px;
    }

    .search-box{
        border-radius:20px;
    }

    .search-box input{
        padding:14px;

        font-size:15px;
    }

    .search-box button{
        padding:0 18px;
    }

    .modal-image{
        height:230px;
    }

    .modal-body{
        padding:22px;
    }

    .modal-body h2{
        font-size:28px;
    }

}


/* ================= SCROLLBAR ================= */

::-webkit-scrollbar{
    width:9px;
}

::-webkit-scrollbar-track{
    background:#eee;
}

::-webkit-scrollbar-thumb{
    background:
        linear-gradient(
            #ff512f,
            #dd2476
        );

    border-radius:10px;
}

</style>
</head>


<body>


<!-- ================= HEADER ================= -->

<header>

    <h1>
        🍴 Rasata Recipe Hub
    </h1>

    <p>
        රසවත් කෑම වට්ටෝරු | Delicious Food Recipes
    </p>

    <div class="badge">
        🔥 100+ Recipes | සිංහල + English
    </div>

</header>


<!-- ================= SEARCH ================= -->

<div class="search-area">

    <div class="search-box">

        <input
            id="search"
            type="text"
            placeholder="🔍 Search in English or Sinhala..."
            oninput="searchRecipes()"
        >

        <button onclick="searchRecipes()">
            Search
        </button>

    </div>

</div>


<!-- ================= CATEGORIES ================= -->

<div class="categories">

    <button
        class="active"
        onclick="filterCategory('All',this)">
        🍽️ All
    </button>

    <button
        onclick="filterCategory('Sri Lankan',this)">
        🇱🇰 Sri Lankan
    </button>

    <button
        onclick="filterCategory('Rice',this)">
        🍚 Rice
    </button>

    <button
        onclick="filterCategory('Chicken',this)">
        🍗 Chicken
    </button>

    <button
        onclick="filterCategory('Vegetarian',this)">
        🥦 Vegetarian
    </button>

    <button
        onclick="filterCategory('Fast Food',this)">
        🍔 Fast Food
    </button>

    <button
        onclick="filterCategory('Dessert',this)">
        🍰 Dessert
    </button>

    <button
        onclick="filterCategory('Drinks',this)">
        🥤 Drinks
    </button>

</div>


<div
    class="result"
    id="resultCount">
</div>


<!-- ================= RECIPES ================= -->

<div class="container">

    <div
        class="grid"
        id="recipeGrid">
    </div>

    <div
        class="no-result"
        id="noResult">

        😔<br><br>

        Recipe එක හමු වුණේ නැහැ.<br>

        වෙනත් නමක් search කරන්න.

    </div>

</div>


<!-- ================= MODAL ================= -->

<div
    class="modal"
    id="modal">

    <div class="modal-box">

        <img
            id="modalImage"
            class="modal-image"
            src=""
            alt="Recipe">


        <div class="modal-body">

            <span
                class="close"
                onclick="closeRecipe()">
                ×
            </span>


            <h2 id="modalSinhala"></h2>

            <h3
                id="modalEnglish"
                style="
                color:#555;
                margin-top:4px;
                ">
            </h3>


            <p
                class="subtitle"
                id="modalDescription">
            </p>


            <div
                class="info">

                <span id="modalPrep"></span>

                <span id="modalCook"></span>

                <span id="modalServe"></span>

            </div>


            <!-- INGREDIENTS -->

            <h3>
                🥕 Ingredients | අවශ්‍ය ද්‍රව්‍ය
            </h3>

            <div
                class="ingredients"
                id="modalIngredients">
            </div>


            <!-- METHOD -->

            <h3>
                👨‍🍳 Cooking Method | සාදන ආකාරය
            </h3>

            <ol
                class="steps"
                id="modalSteps">
            </ol>


            <!-- TIPS -->

            <h3>
                💡 Cooking Tips | ඉවුම් පිහුම් උපදෙස්
            </h3>

            <div
                class="tip"
                id="modalTips">
            </div>


            <!-- BILINGUAL -->

            <div
                class="language-box">

                <b>
                    🇱🇰 සිංහල:
                </b>

                <p id="modalSinhalaLong"></p>

                <br>

                <b>
                    🇬🇧 English:
                </b>

                <p id="modalEnglishLong"></p>

            </div>

        </div>

    </div>

</div>


<!-- ================= FOOTER ================= -->

<footer>

    <h2>
        🍴 Rasata Recipe Hub
    </h2>

    <p>
        රසවත් කෑම වට්ටෝරු | Delicious Food Recipes
    </p>

    <br>

    <p>
        © 2026 Rasata Recipe Hub
    </p>

</footer>


<script>


/* =====================================================
   RECIPE DATA
===================================================== */

const recipes = [

{
    si:"චිකන් ෆ්‍රයිඩ් රයිස්",
    en:"Chicken Fried Rice",
    category:"Rice",

    image:"https://images.unsplash.com/photo-1603133872878-684f208fb84b?auto=format&fit=crop&w=1200&q=90",

    description:"කුකුළු මස්, බිත්තර සහ එළවළු සමඟ සාදන රසවත් ෆ්‍රයිඩ් රයිස්.",

    prep:"⏱️ Prep: 15 min",
    cook:"🔥 Cook: 20 min",
    serve:"👥 Serves: 4",

    ingredients:[
        "බත් – Cooked rice – කෝප්ප 4",
        "කුකුළු මස් – Chicken – 250g",
        "බිත්තර – Eggs – 2",
        "කැරට් – Carrot – 1",
        "ලීක්ස් – Leeks – කෝප්ප 1",
        "ලූනු – Onion – 1",
        "සුදු ලූනු – Garlic – කරාබු 3",
        "සෝයා සෝස් – Soy sauce – මේස හැඳි 2",
        "ගම්මිරිස් – Pepper – තේ හැඳි 1",
        "ලුණු – Salt – අවශ්‍ය පමණ",
        "තෙල් – Cooking oil – මේස හැඳි 2"
    ],

    steps:[
        "පිසූ බත් සූදානම් කර තබන්න. Prepare the cooked rice and keep it ready.",
        "කුකුළු මස් කුඩා කැබලිවලට කපා ලුණු හා ගම්මිරිස් දමා තබන්න. Cut chicken into small pieces and season with salt and pepper.",
        "පෑන් එක රත් කර තෙල් එකතු කරන්න. Heat a large pan and add oil.",
        "කුකුළු මස් එකතු කර හොඳින් පිසගන්න. Add chicken and cook thoroughly.",
        "ලූනු සහ සුදු ලූනු එකතු කර බැදගන්න. Add onion and garlic and stir-fry.",
        "කැරට් සහ ලීක්ස් එකතු කරන්න. Add carrot and leeks.",
        "බිත්තර එකතු කර scramble කරන්න. Add eggs and scramble them.",
        "පිසූ බත් එකතු කරන්න. Add cooked rice.",
        "සෝයා සෝස්, ගම්මිරිස් සහ ලුණු එකතු කරන්න. Add soy sauce, pepper and salt.",
        "සියල්ල හොඳින් මිශ්‍ර කර විනාඩි කිහිපයක් උයන්න. Mix everything well and cook for several minutes.",
        "රස පරීක්ෂා කර අවශ්‍ය නම් ලුණු එකතු කරන්න. Taste and adjust the seasoning.",
        "උණු උණුවෙන් පිළිගන්වන්න. Serve hot."
    ],

    tips:"පෙර දින පිසූ සිසිල් බත් භාවිතා කළොත් ෆ්‍රයිඩ් රයිස් එක වඩා හොඳින් සෑදේ. Use cold previously cooked rice for better fried rice."
},

{
    si:"එළවළු ෆ්‍රයිඩ් රයිස්",
    en:"Vegetable Fried Rice",
    category:"Rice",

    image:"https://images.unsplash.com/photo-1512058564366-18510be2db19?auto=format&fit=crop&w=1200&q=90",

    description:"විවිධ නැවුම් එළවළු සමඟ සාදන රසවත් එළවළු ෆ්‍රයිඩ් රයිස්.",

    prep:"⏱️ Prep: 15 min",
    cook:"🔥 Cook: 15 min",
    serve:"👥 Serves: 4",

    ingredients:[
        "පිසූ බත් – Cooked rice – කෝප්ප 4",
        "කැරට් – Carrot – 1",
        "ගෝවා – Cabbage – කෝප්ප 1",
        "ලීක්ස් – Leeks – කෝප්ප 1",
        "මුං ඇට – Green peas – කෝප්ප 1/2",
        "ලූනු – Onion – 1",
        "සෝයා සෝස් – Soy sauce – මේස හැඳි 2",
        "ගම්මිරිස් – Pepper – තේ හැඳි 1",
        "ලුණු – Salt – අවශ්‍ය පමණ"
    ],

    steps:[
        "සියලුම එළවළු සෝදා කුඩා කැබලිවලට කපන්න. Wash and chop all vegetables.",
        "පෑන් එක රත් කර තෙල් එකතු කරන්න. Heat a pan and add oil.",
        "ලූනු එකතු කර බැදගන්න. Add onion and stir-fry.",
        "කැරට්, ගෝවා සහ ලීක්ස් එකතු කරන්න. Add carrot, cabbage and leeks.",
        "මුං ඇට එකතු කර මද වේලාවක් උයන්න. Add green peas and cook briefly.",
        "පිසූ බත් එකතු කරන්න. Add cooked rice.",
        "සෝයා සෝස්, ලුණු සහ ගම්මිරිස් එකතු කරන්න. Add soy sauce, salt and pepper.",
        "හොඳින් මිශ්‍ර කර උණු උණුවෙන් පිළිගන්වන්න. Mix well and serve hot."
    ],

    tips:"එළවළු වැඩිපුර පිසීමෙන් වළකින්න. Do not overcook the vegetables."
},

{
    si:"බිත්තර ෆ්‍රයිඩ් රයිස්",
    en:"Egg Fried Rice",
    category:"Rice",

    image:"https://images.unsplash.com/photo-1603133872878-684f208fb84b?auto=format&fit=crop&w=1200&q=90",

    description:"සරලව සහ ඉක්මනින් සාදාගත හැකි බිත්තර ෆ්‍රයිඩ් රයිස්.",

    prep:"⏱️ Prep: 10 min",
    cook:"🔥 Cook: 12 min",
    serve:"👥 Serves: 3",

    ingredients:[
        "පිසූ බත් – Cooked rice – කෝප්ප 3",
        "බිත්තර – Eggs – 3",
        "ලූනු – Onion – 1",
        "ලීක්ස් – Leeks – කෝප්ප 1",
        "කැරට් – Carrot – 1",
        "සෝයා සෝස් – Soy sauce – මේස හැඳි 2",
        "ලුණු – Salt",
        "ගම්මිරිස් – Pepper"
    ],

    steps:[
        "බිත්තර භාජනයකට දමා හොඳින් ගසාගන්න. Beat the eggs.",
        "පෑන් එක රත් කර බිත්තර scramble කරන්න. Heat the pan and scramble the eggs.",
        "ලූනු, කැරට් සහ ලීක්ස් එකතු කරන්න. Add onion, carrot and leeks.",
        "පිසූ බත් එකතු කරන්න. Add cooked rice.",
        "සෝයා සෝස් සහ ගම්මිරිස් එකතු කරන්න. Add soy sauce and pepper.",
        "සියල්ල හොඳින් මිශ්‍ර කරන්න. Mix everything well.",
        "උණු උණුවෙන් පිළිගන්වන්න. Serve hot."
    ],

    tips:"බත් සිසිල්ව තිබීම වඩා හොඳ ප්‍රතිඵලයක් ලබා දෙයි. Cold rice gives better results."
},

{
    si:"චිකන් කොත්තු",
    en:"Chicken Kottu",
    category:"Sri Lankan",

    image:"https://images.unsplash.com/photo-1515003197210-e0cd71810b5f?auto=format&fit=crop&w=1200&q=90",

    description:"ශ්‍රී ලංකාවේ ජනප්‍රිය රසවත් චිකන් කොත්තු.",

    prep:"⏱️ Prep: 20 min",
    cook:"🔥 Cook: 20 min",
    serve:"👥 Serves: 4",

    ingredients:[
        "ගෝදම්බ රොටි – Godamba roti – 5",
        "කුකුළු මස් – Chicken – 250g",
        "ලූනු – Onion – 1",
        "ලීක්ස් – Leeks – කෝප්ප 1",
        "කැරට් – Carrot – 1",
        "බිත්තර – Eggs – 2",
        "මිරිස් – Chili – 2",
        "ගම්මිරිස් – Pepper",
        "ලුණු – Salt"
    ],

    steps:[
        "රොටි කුඩා කැබලිවලට කපාගන්න. Cut the roti into small pieces.",
        "කුකුළු මස් කුඩා කැබලිවලට කපා පිසගන්න. Cut and cook the chicken.",
        "ලූනු සහ මිරිස් පෑන් එකේ බැදගන්න. Stir-fry onion and chili.",
        "කැරට් සහ ලීක්ස් එකතු කරන්න. Add carrot and leeks.",
        "බිත්තර එකතු කර scramble කරන්න. Add eggs and scramble.",
        "කුකුළු මස් එකතු කරන්න. Add chicken.",
        "රොටි කැබලි එකතු කරන්න. Add chopped roti.",
        "සියල්ල හොඳින් මිශ්‍ර කර කොත්තු කරගන්න. Mix and chop everything together.",
        "උණු උණුවෙන් පිළිගන්වන්න. Serve hot."
    ],

    tips:"කොත්තු සෑදීමේදී පෑන් එක හොඳින් රත් කර තබා ගැනීමෙන් හොඳ රසයක් ලැබේ. Keep the pan hot for better flavour."
},

{
    si:"චීස් කොත්තු",
    en:"Cheese Kottu",
    category:"Sri Lankan",

    image:"https://images.unsplash.com/photo-1515003197210-e0cd71810b5f?auto=format&fit=crop&w=1200&q=90",

    description:"චීස් එකතු කර සාදන රසවත් කොත්තු.",

    prep:"⏱️ Prep: 15 min",
    cook:"🔥 Cook: 18 min",
    serve:"👥 Serves: 3",

    ingredients:[
        "ගෝදම්බ රොටි – Roti – 4",
        "චීස් – Cheese – 100g",
        "ලූනු – Onion – 1",
        "ලීක්ස් – Leeks",
        "කැරට් – Carrot – 1",
        "බිත්තර – Eggs – 2",
        "මිරිස් – Chili",
        "ලුණු – Salt"
    ],

    steps:[
        "රොටි කුඩා කැබලිවලට කපාගන්න. Cut roti into small pieces.",
        "ලූනු, මිරිස් සහ එළවළු බැදගන්න. Stir-fry onion, chili and vegetables.",
        "බිත්තර එකතු කරන්න. Add eggs.",
        "රොටි එකතු කරන්න. Add roti.",
        "චීස් එකතු කරන්න. Add cheese.",
        "චීස් දියවන තුරු හොඳින් මිශ්‍ර කරන්න. Mix until the cheese melts.",
        "උණු උණුවෙන් පිළිගන්වන්න. Serve hot."
    ],

    tips:"Mozzarella හෝ cheddar cheese භාවිතා කළ හැක. You can use mozzarella or cheddar cheese."
},

{
    si:"ශ්‍රී ලංකා චිකන් කරිය",
    en:"Sri Lankan Chicken Curry",
    category:"Chicken",

    image:"https://images.unsplash.com/photo-1601050690597-df0568f70950?auto=format&fit=crop&w=1200&q=90",

    description:"කුළුබඩු සහ පොල් කිරි සමඟ සාදන රසවත් ශ්‍රී ලංකා චිකන් කරිය.",

    prep:"⏱️ Prep: 20 min",
    cook:"🔥 Cook: 35 min",
    serve:"👥 Serves: 4",

    ingredients:[
        "කුකුළු මස් – Chicken – 500g",
        "පොල් කිරි – Coconut milk – කෝප්ප 2",
        "ලූනු – Onion – 1",
        "සුදු ලූනු – Garlic – කරාබු 4",
        "ඉඟුරු – Ginger – කුඩා කැබැල්ලක්",
        "මිරිස් කුඩු – Chili powder – තේ හැඳි 1",
        "කහ – Turmeric – තේ හැඳි 1/2",
        "තුනපහ – Curry powder – මේස හැඳි 1",
        "ලුණු – Salt",
        "කරි කොළ – Curry leaves"
    ],

    steps:[
        "කුකුළු මස් සෝදා කැබලි කරගන්න. Wash and cut the chicken.",
        "ලුණු, කහ සහ තුනපහ දමා marinate කරන්න. Season with salt, turmeric and curry powder.",
        "පෑන් එකක ලූනු, සුදු ලූනු සහ ඉඟුරු බැදගන්න. Fry onion, garlic and ginger.",
        "කුළුබඩු එකතු කරන්න. Add spices.",
        "කුකුළු මස් එකතු කර හොඳින් කලවම් කරන්න. Add chicken and mix well.",
        "වතුර ස්වල්පයක් එකතු කර මද ගින්නේ උයන්න. Add a little water and cook.",
        "පොල් කිරි එකතු කරන්න. Add coconut milk.",
        "මස් හොඳින් පිසෙන තුරු මද ගින්නේ උයන්න. Simmer until the chicken is fully cooked.",
        "රස පරීක්ෂා කර පිළිගන්වන්න. Taste and serve."
    ],

    tips:"මද ගින්නේ පොල් කිරි සමඟ පිසීමෙන් කරියට හොඳ රසයක් ලැබේ. Simmer gently with coconut milk for better flavour."
},

{
    si:"චිකන් නූඩ්ල්ස්",
    en:"Chicken Noodles",
    category:"Chicken",

    image:"https://images.unsplash.com/photo-1585032226651-759b368d7246?auto=format&fit=crop&w=1200&q=90",

    description:"කුකුළු මස් සහ එළවළු සමඟ සාදන රසවත් නූඩ්ල්ස්.",

    prep:"⏱️ Prep: 15 min",
    cook:"🔥 Cook: 15 min",
    serve:"👥 Serves: 3",

    ingredients:[
        "නූඩ්ල්ස් – Noodles – 300g",
        "කුකුළු මස් – Chicken – 200g",
        "කැරට් – Carrot – 1",
        "ගෝවා – Cabbage – කෝප්ප 1",
        "ලීක්ස් – Leeks – කෝප්ප 1",
        "සෝයා සෝස් – Soy sauce – මේස හැඳි 2",
        "ගම්මිරිස් – Pepper",
        "ලුණු – Salt"
    ],

    steps:[
        "නූඩ්ල්ස් පැකට් උපදෙස් අනුව පිසගන්න. Cook noodles according to the package instructions.",
        "කුකුළු මස් කපා පෑන් එකක පිසගන්න. Cut and cook chicken.",
        "එළවළු එකතු කර stir-fry කරන්න. Add vegetables and stir-fry.",
        "නූඩ්ල්ස් එකතු කරන්න. Add noodles.",
        "සෝයා සෝස් එකතු කරන්න. Add soy sauce.",
        "ගම්මිරිස් සහ ලුණු එකතු කරන්න. Add pepper and salt.",
        "සියල්ල හොඳින් මිශ්‍ර කර පිළිගන්වන්න. Mix well and serve."
    ],

    tips:"නූඩ්ල්ස් වැඩිපුර තම්බන්න එපා. Do not overcook the noodles."
},

{
    si:"චීස් පීසා",
    en:"Cheese Pizza",
    category:"Fast Food",

    image:"https://images.unsplash.com/photo-1574071318508-1cdbab80d002?auto=format&fit=crop&w=1200&q=90",

    description:"චීස් ගොඩක් සමඟ සාදන රසවත් homemade pizza.",

    prep:"⏱️ Prep: 20 min",
    cook:"🔥 Cook: 20 min",
    serve:"👥 Serves: 4",

    ingredients:[
        "පීසා dough – Pizza dough – 1",
        "පීසා සෝස් – Pizza sauce – කෝප්ප 1/2",
        "Mozzarella cheese – 200g",
        "තක්කාලි – Tomato – 1",
        "ලූනු – Onion – 1",
        "Oregano – තේ හැඳි 1"
    ],

    steps:[
        "Pizza dough එක පැතලි කරගන්න. Flatten the pizza dough.",
        "Pizza sauce එක spread කරන්න. Spread pizza sauce.",
        "Mozzarella cheese එක එකතු කරන්න. Add mozzarella cheese.",
        "තක්කාලි සහ ලූනු එකතු කරන්න. Add tomato and onion.",
        "Oregano ඉසගන්න. Sprinkle oregano.",
        "උණු කළ oven එකක bake කරන්න. Bake in a preheated oven.",
        "Cheese දියවී crust එක පිසෙන තුරු bake කරන්න. Bake until cheese melts and crust is cooked.",
        "කැබලි කර පිළිගන්වන්න. Slice and serve."
    ],

    tips:"Oven එක කලින් preheat කිරීමෙන් හොඳ crust එකක් ලැබේ. Preheat the oven for a better crust."
},

{
    si:"චිකන් පීසා",
    en:"Chicken Pizza",
    category:"Chicken",

    image:"https://images.unsplash.com/photo-1565299624946-b28f40a0ae38?auto=format&fit=crop&w=1200&q=90",

    description:"කුකුළු මස් සහ චීස් සමඟ සාදන රසවත් චිකන් පීසා.",

    prep:"⏱️ Prep: 20 min",
    cook:"🔥 Cook: 20 min",
    serve:"👥 Serves: 4",

    ingredients:[
        "Pizza dough – 1",
        "කුකුළු මස් – Chicken – 200g",
        "Pizza sauce – කෝප්ප 1/2",
        "Mozzarella cheese – 200g",
        "Capsicum – 1",
        "ලූනු – Onion – 1",
        "Oregano"
    ],

    steps:[
        "කුකුළු මස් කුඩා කැබලිවලට කපා පිසගන්න. Cut and cook chicken.",
        "Pizza dough එක සකස් කරන්න. Prepare the pizza dough.",
        "Pizza sauce එක spread කරන්න. Spread pizza sauce.",
        "Chicken සහ vegetables එකතු කරන්න. Add chicken and vegetables.",
        "Cheese එකතු කරන්න. Add cheese.",
        "Oregano ඉසගන්න. Sprinkle oregano.",
        "Bake කර පිළිගන්වන්න. Bake and serve."
    ],

    tips:"Chicken කලින් පිසගෙන තිබීමෙන් pizza එක ඉක්මනින් සෑදිය හැක. Pre-cooked chicken makes preparation easier."
},

{
    si:"ක්ලැසික් බර්ගර්",
    en:"Classic Burger",
    category:"Fast Food",

    image:"https://images.unsplash.com/photo-1568901346375-23c9450c58cd?auto=format&fit=crop&w=1200&q=90",

    description:"ගෙදරදී පහසුවෙන් සාදාගත හැකි රසවත් burger එකක්.",

    prep:"⏱️ Prep: 15 min",
    cook:"🔥 Cook: 15 min",
    serve:"👥 Serves: 2",

    ingredients:[
        "Burger bun – 2",
        "Burger patty – 2",
        "Cheese – පෙති 2",
        "Lettuce – සලාද කොළ",
        "Tomato – තක්කාලි 1",
        "Burger sauce – සෝස්"
    ],

    steps:[
        "Burger patty සකස් කරන්න. Prepare the burger patties.",
        "Pan එක රත් කර patties දෙපසම පිසගන්න. Heat a pan and cook patties on both sides.",
        "Buns දෙක සැහැල්ලුවෙන් toast කරන්න. Lightly toast the buns.",
        "Lettuce සහ tomato එකතු කරන්න. Add lettuce and tomato.",
        "Patty සහ cheese එකතු කරන්න. Add patty and cheese.",
        "Sauce එක එකතු කර burger එක වසාගන්න. Add sauce and close the burger.",
        "උණු උණුවෙන් පිළිගන්වන්න. Serve fresh."
    ],

    tips:"Bun එක සැහැල්ලුවෙන් toast කළොත් burger එකේ texture එක වඩා හොඳ වේ. Lightly toast the bun for better texture."
},

{
    si:"ෆ්‍රෙන්ච් ෆ්‍රයිස්",
    en:"French Fries",
    category:"Fast Food",

    image:"https://images.unsplash.com/photo-1573080496219-bb080dd4f877?auto=format&fit=crop&w=1200&q=90",

    description:"කැරකෙන තරම් crispy රසවත් French fries.",

    prep:"⏱️ Prep: 15 min",
    cook:"🔥 Cook: 15 min",
    serve:"👥 Serves: 3",

    ingredients:[
        "අල – Potatoes – 4",
        "ලුණු – Salt",
        "Cooking oil – තෙල්",
        "ගම්මිරිස් – Pepper – optional"
    ],

    steps:[
        "අල සෝදා දිගටි කැබලිවලට කපන්න. Wash and cut potatoes into strips.",
        "කැපූ අල සීතල වතුරේ මද වේලාවක් තබන්න. Soak cut potatoes briefly in cold water.",
        "හොඳින් වියළාගන්න. Dry them thoroughly.",
        "තෙල් රත් කරන්න. Heat the oil.",
        "අල golden brown වන තුරු පිසගන්න. Cook until golden brown.",
        "ලුණු එකතු කරන්න. Add salt.",
        "උණු උණුවෙන් පිළිගන්වන්න. Serve hot."
    ],

    tips:"අල හොඳින් වියළීමෙන් crispy fries ලබාගත හැක. Dry potatoes thoroughly for crispier fries."
},

{
    si:"චොකලට් කේක්",
    en:"Chocolate Cake",
    category:"Dessert",

    image:"https://images.unsplash.com/photo-1578985545062-69928b1d9587?auto=format&fit=crop&w=1200&q=90",

    description:"මෘදු සහ රසවත් homemade chocolate cake.",

    prep:"⏱️ Prep: 20 min",
    cook:"🔥 Bake: 35 min",
    serve:"👥 Serves: 8",

    ingredients:[
        "පාන් පිටි – Flour – කෝප්ප 2",
        "සීනි – Sugar – කෝප්ප 1",
        "Cocoa powder – කෝප්ප 1/2",
        "බිත්තර – Eggs – 2",
        "කිරි – Milk – කෝප්ප 1",
        "Butter – 100g",
        "Baking powder – තේ හැඳි 2",
        "Vanilla – තේ හැඳි 1"
    ],

    steps:[
        "Oven එක කලින් උණු කරන්න. Preheat the oven.",
        "පිටි, cocoa සහ baking powder මිශ්‍ර කරන්න. Mix flour, cocoa and baking powder.",
        "Butter සහ sugar හොඳින් beat කරන්න. Beat butter and sugar.",
        "බිත්තර එකින් එක එකතු කරන්න. Add eggs one at a time.",
        "Milk සහ vanilla එකතු කරන්න. Add milk and vanilla.",
        "Dry ingredients එකතු කර මෘදු ලෙස mix කරන්න. Add dry ingredients and mix gently.",
        "Cake pan එකට mixture එක දමන්න. Pour into a cake pan.",
        "Bake until cooked. පිසෙන තුරු bake කරන්න.",
        "සිසිල් වූ පසු decorate කර පිළිගන්වන්න. Cool, decorate and serve."
    ],

    tips:"Cake mixture එක වැඩිපුර mix නොකරන්න. Do not overmix the cake batter."
},

{
    si:"වැනිලා කේක්",
    en:"Vanilla Cake",
    category:"Dessert",

    image:"https://images.unsplash.com/photo-1571115177098-24ec42ed204d?auto=format&fit=crop&w=1200&q=90",

    description:"මෘදු vanilla flavour එකක් සහිත රසවත් කේක්.",

    prep:"⏱️ Prep: 15 min",
    cook:"🔥 Bake: 35 min",
    serve:"👥 Serves: 8",

    ingredients:[
        "Flour – පිටි – කෝප්ප 2",
        "Sugar – සීනි – කෝප්ප 1",
        "Eggs – බිත්තර – 2",
        "Butter – 100g",
        "Milk – කිරි – කෝප්ප 1",
        "Vanilla – තේ හැඳි 1",
        "Baking powder – තේ හැඳි 2"
    ],

    steps:[
        "Butter සහ sugar beat කරන්න. Beat butter and sugar.",
        "Eggs එකතු කරන්න. Add eggs.",
        "Vanilla එකතු කරන්න. Add vanilla.",
        "Flour සහ baking powder එකතු කරන්න. Add flour and baking powder.",
        "Milk එකතු කර batter එක සකස් කරන්න. Add milk and prepare the batter.",
        "Cake pan එකකට දමා bake කරන්න. Pour into a cake pan and bake.",
        "සිසිල් කර පිළිගන්වන්න. Cool and serve."
    ],

    tips:"Vanilla essence එක හොඳ quality එකකින් භාවිතා කරන්න. Use good-quality vanilla essence."
},

{
    si:"පෑන්කේක්",
    en:"Pancakes",
    category:"Dessert",

    image:"https://images.unsplash.com/photo-1528207776546-365bb710ee93?auto=format&fit=crop&w=1200&q=90",

    description:"උදෑසන ආහාරයට හොඳ මෘදු pancakes.",

    prep:"⏱️ Prep: 10 min",
    cook:"🔥 Cook: 15 min",
    serve:"👥 Serves: 4",

    ingredients:[
        "Flour – පිටි – කෝප්ප 1",
        "Milk – කිරි – කෝප්ප 1",
        "Egg – බිත්තර – 1",
        "Sugar – සීනි – මේස හැඳි 2",
        "Butter – බටර් – මේස හැඳි 1",
        "Baking powder – තේ හැඳි 1"
    ],

    steps:[
        "Flour සහ baking powder මිශ්‍ර කරන්න. Mix flour and baking powder.",
        "Egg, milk සහ sugar එකතු කරන්න. Add egg, milk and sugar.",
        "Smooth batter එකක් සාදන්න. Make a smooth batter.",
        "Pan එක රත් කර butter ස්වල්පයක් දමන්න. Heat a pan and add a little butter.",
        "Batter එකෙන් කොටසක් දමන්න. Pour some batter.",
        "බුබුළු ඇති වූ පසු අනෙක් පැත්ත හරවන්න. Flip when bubbles appear.",
        "දෙපසම golden වන තුරු පිසගන්න. Cook until golden on both sides.",
        "Honey හෝ fruits සමඟ පිළිගන්වන්න. Serve with honey or fruits."
    ],

    tips:"Pan එක ඉතාමත් උණු නොකරන්න. Do not make the pan excessively hot."
},

{
    si:"චොකලට් බ්‍රව්නී",
    en:"Chocolate Brownie",
    category:"Dessert",

    image:"https://images.unsplash.com/photo-1564355808539-22fda35bed7e?auto=format&fit=crop&w=1200&q=90",

    description:"මෘදු සහ rich chocolate brownie.",

    prep:"⏱️ Prep: 15 min",
    cook:"🔥 Bake: 25 min",
    serve:"👥 Serves: 8",

    ingredients:[
        "Chocolate – චොකලට් – 150g",
        "Butter – බටර් – 100g",
        "Sugar – සීනි – 1 cup",
        "Eggs – බිත්තර – 2",
        "Flour – පිටි – 3/4 cup",
        "Cocoa – කොකෝවා – මේස හැඳි 2"
    ],

    steps:[
        "Chocolate සහ butter දියකරගන්න. Melt chocolate and butter.",
        "Eggs සහ sugar beat කරන්න. Beat eggs and sugar.",
        "Chocolate mixture එක එකතු කරන්න. Add chocolate mixture.",
        "Flour සහ cocoa එකතු කරන්න. Add flour and cocoa.",
        "Baking tray එකකට mixture එක දමන්න. Pour into a baking tray.",
        "Bake until set. Set වන තුරු bake කරන්න.",
        "සිසිල් කර කැබලි කරන්න. Cool and cut into pieces."
    ],

    tips:"Brownie එක වැඩිපුර bake නොකළොත් මැදින් soft වේ. Avoid overbaking for a softer centre."
},

{
    si:"ෆෘට් සැලඩ්",
    en:"Fruit Salad",
    category:"Dessert",

    image:"https://images.unsplash.com/photo-1490474418585-ba9bad8fd0ea?auto=format&fit=crop&w=1200&q=90",

    description:"නැවුම් පලතුරු වලින් සාදන වර්ණවත් fruit salad.",

    prep:"⏱️ Prep: 15 min",
    cook:"🔥 Cook: 0 min",
    serve:"👥 Serves: 4",

    ingredients:[
        "ඇපල් – Apple – 1",
        "කෙසෙල් – Banana – 2",
        "අඹ – Mango – 1",
        "මිදි – Grapes – කෝප්ප 1",
        "දොඩම් – Orange – 1",
        "Honey – මී පැණි – optional"
    ],

    steps:[
        "සියලුම පලතුරු හොඳින් සෝදන්න. Wash all fruits.",
        "පලතුරු කුඩා කැබලිවලට කපන්න. Cut fruits into small pieces.",
        "විශාල භාජනයකට දමන්න. Place in a large bowl.",
        "මෘදු ලෙස mix කරන්න. Mix gently.",
        "අවශ්‍ය නම් honey එකතු කරන්න. Add honey if desired.",
        "සිසිල් කර පිළිගන්වන්න. Chill and serve."
    ],

    tips:"පිළිගැන්වීමට ටික වේලාවකට පෙර පලතුරු කපාගන්න. Cut fruits shortly before serving."
},

{
    si:"චොකලට් මිල්ක්ෂේක්",
    en:"Chocolate Milkshake",
    category:"Drinks",

    image:"https://images.unsplash.com/photo-1572490122747-3968b75cc699?auto=format&fit=crop&w=1200&q=90",

    description:"සිසිල් සහ creamy chocolate milkshake.",

    prep:"⏱️ Prep: 5 min",
    cook:"🔥 Cook: 0 min",
    serve:"👥 Serves: 2",

    ingredients:[
        "කිරි – Milk – කෝප්ප 2",
        "Chocolate ice cream – කෝප්ප 2",
        "Cocoa powder – මේස හැඳි 1",
        "සීනි – Sugar – අවශ්‍ය පමණ",
        "Ice – අයිස්"
    ],

    steps:[
        "සියලුම ද්‍රව්‍ය blender එකට දමන්න. Add all ingredients to a blender.",
        "Smooth වන තුරු blend කරන්න. Blend until smooth.",
        "Glass වලට දමන්න. Pour into glasses.",
        "ඉහළින් chocolate syrup දැමිය හැක. Add chocolate syrup if desired.",
        "සිසිල්ව පිළිගන්වන්න. Serve cold."
    ],

    tips:"Serve කිරීමට පෙර blend කිරීමෙන් හොඳ texture එකක් ලැබේ. Blend just before serving for better texture."
},

{
    si:"මැන්ගෝ ස්මූති",
    en:"Mango Smoothie",
    category:"Drinks",

    image:"https://images.unsplash.com/photo-1623065422902-30a2d299bbe4?auto=format&fit=crop&w=1200&q=90",

    description:"නැවුම් අඹ වලින් සාදන රසවත් smoothie.",

    prep:"⏱️ Prep: 10 min",
    cook:"🔥 Cook: 0 min",
    serve:"👥 Serves: 2",

    ingredients:[
        "අඹ – Mango – 2",
        "කිරි – Milk – කෝප්ප 1",
        "යෝගට් – Yogurt – කෝප්ප 1/2",
        "මී පැණි – Honey – මේස හැඳි 1",
        "Ice – අයිස්"
    ],

    steps:[
        "අඹ කපාගන්න. Cut the mangoes.",
        "අඹ, milk සහ yogurt blender එකට දමන්න. Add mango, milk and yogurt to blender.",
        "Honey එකතු කරන්න. Add honey.",
        "Smooth වන තුරු blend කරන්න. Blend until smooth.",
        "Ice එකතු කර නැවත blend කරන්න. Add ice and blend again.",
        "සිසිල්ව පිළිගන්වන්න. Serve cold."
    ],

    tips:"ඉදුණු පැණිරස අඹ භාවිතා කළොත් sugar අඩුවෙන් අවශ්‍ය වේ. Ripe sweet mangoes need less added sugar."
},

{
    si:"ෆ්‍රෙෂ් ලයිම් ජූස්",
    en:"Fresh Lime Juice",
    category:"Drinks",

    image:"https://images.unsplash.com/photo-1513558161293-cdaf765ed2fd?auto=format&fit=crop&w=1200&q=90",

    description:"උණුසුම් දවසකට ඉතාමත් refreshing lime juice.",

    prep:"⏱️ Prep: 5 min",
    cook:"🔥 Cook: 0 min",
    serve:"👥 Serves: 3",

    ingredients:[
        "දෙහි – Lime – 4",
        "වතුර – Water – කෝප්ප 3",
        "සීනි – Sugar – මේස හැඳි 3",
        "Ice – අයිස්"
    ],

    steps:[
        "දෙහි වලින් යුෂ ලබාගන්න. Extract lime juice.",
        "වතුර එකතු කරන්න. Add water.",
        "Sugar එකතු කර හොඳින් කලවම් කරන්න. Add sugar and mix well.",
        "Ice එකතු කරන්න. Add ice.",
        "සිසිල්ව පිළිගන්වන්න. Serve cold."
    ],

    tips:"Lime juice එක වැඩිපුර තබා නොගෙන නැවුම්ව serve කරන්න. Serve fresh for the best taste."
},

{
    si:"එළවළු සුප්",
    en:"Vegetable Soup",
    category:"Vegetarian",

    image:"https://images.unsplash.com/photo-1547592180-85f173990554?auto=format&fit=crop&w=1200&q=90",

    description:"නැවුම් එළවළු වලින් සාදන උණුසුම් vegetable soup.",

    prep:"⏱️ Prep: 15 min",
    cook:"🔥 Cook: 30 min",
    serve:"👥 Serves: 4",

    ingredients:[
        "කැරට් – Carrot – 2",
        "අල – Potato – 2",
        "ලූනු – Onion – 1",
        "Celery – කෝප්ප 1/2",
        "වතුර – Water – ලීටර් 1",
        "ගම්මිරිස් – Pepper",
        "ලුණු – Salt"
    ],

    steps:[
        "සියලුම එළවළු කුඩා කැබලිවලට කපන්න. Cut all vegetables.",
        "භාජනයකට වතුර දමා රත් කරන්න. Add water to a pot and heat.",
        "එළවළු එකතු කරන්න. Add vegetables.",
        "ලුණු සහ ගම්මිරිස් එකතු කරන්න. Add salt and pepper.",
        "එළවළු මෘදු වන තුරු උයන්න. Cook until vegetables are soft.",
        "උණු උණුවෙන් පිළිගන්වන්න. Serve hot."
    ],

    tips:"ඔබ කැමති ඕනෑම එළවළුවක් එකතු කළ හැක. You can add other vegetables you like."
},

{
    si:"ටොමැටෝ සුප්",
    en:"Tomato Soup",
    category:"Vegetarian",

    image:"https://images.unsplash.com/photo-1547592166-23ac45744acd?auto=format&fit=crop&w=1200&q=90",

    description:"මෘදු සහ creamy tomato soup.",

    prep:"⏱️ Prep: 10 min",
    cook:"🔥 Cook: 25 min",
    serve:"👥 Serves: 4",

    ingredients:[
        "තක්කාලි – Tomatoes – 6",
        "ලූනු – Onion – 1",
        "සුදු ලූනු – Garlic – කරාබු 2",
        "Butter – බටර් – මේස හැඳි 1",
        "වතුර – Water – කෝප්ප 3",
        "ලුණු – Salt",
        "ගම්මිරිස් – Pepper"
    ],

    steps:[
        "තක්කාලි කපාගන්න. Cut the tomatoes.",
        "Butter තුළ onion සහ garlic cook කරන්න. Cook onion and garlic in butter.",
        "තක්කාලි එකතු කරන්න. Add tomatoes.",
        "වතුර එකතු කර මද ගින්නේ උයන්න. Add water and simmer.",
        "Blender එකකින් smooth කරන්න. Blend until smooth.",
        "ලුණු හා ගම්මිරිස් එකතු කරන්න. Add salt and pepper.",
        "උණු උණුවෙන් පිළිගන්වන්න. Serve hot."
    ],

    tips:"Smooth texture එකක් අවශ්‍ය නම් soup එක strain කරන්න. Strain the soup for an extra smooth texture."
},

{
    si:"ගාර්ලික් බ්‍රෙඩ්",
    en:"Garlic Bread",
    category:"Fast Food",

    image:"https://images.unsplash.com/photo-1573140247632-f8fd74997d5c?auto=format&fit=crop&w=1200&q=90",

    description:"Butter සහ garlic වලින් රසවත් කර crispy කරන garlic bread.",

    prep:"⏱️ Prep: 10 min",
    cook:"🔥 Bake: 12 min",
    serve:"👥 Serves: 4",

    ingredients:[
        "Bread – පාන්",
        "Butter – බටර් – 100g",
        "Garlic – සුදු ලූනු – කරාබු 4",
        "Parsley – මේස හැඳි 1",
        "Cheese – චීස් – optional"
    ],

    steps:[
        "Butter සහ minced garlic මිශ්‍ර කරන්න. Mix butter with minced garlic.",
        "Bread මත spread කරන්න. Spread over the bread.",
        "Parsley එකතු කරන්න. Add parsley.",
        "අවශ්‍ය නම් cheese එකතු කරන්න. Add cheese if desired.",
        "Oven එකක golden වන තුරු bake කරන්න. Bake until golden.",
        "උණු උණුවෙන් පිළිගන්වන්න. Serve hot."
    ],

    tips:"Garlic butter එක කලින් සකස් කර fridge එකේ තබාගත හැක. Garlic butter can be prepared in advance."
},

{
    si:"චිකන් සැන්ඩ්විච්",
    en:"Chicken Sandwich",
    category:"Chicken",

    image:"https://images.unsplash.com/photo-1528735602780-2552fd46c7af?auto=format&fit=crop&w=1200&q=90",

    description:"Chicken, lettuce සහ tomato සමඟ රසවත් sandwich.",

    prep:"⏱️ Prep: 15 min",
    cook:"🔥 Cook: 15 min",
    serve:"👥 Serves: 2",

    ingredients:[
        "Bread – පාන් – පෙති 4",
        "Chicken – කුකුළු මස් – 200g",
        "Lettuce – සලාද කොළ",
        "Tomato – තක්කාලි – 1",
        "Mayonnaise – මේයොනීස්",
        "Pepper – ගම්මිරිස්",
        "Salt – ලුණු"
    ],

    steps:[
        "Chicken season කරන්න. Season the chicken.",
        "Chicken pan එකක හොඳින් පිසගන්න. Cook chicken thoroughly in a pan.",
        "Bread දෙපසට mayonnaise දමන්න. Spread mayonnaise on bread.",
        "Lettuce සහ tomato එකතු කරන්න. Add lettuce and tomato.",
        "Chicken එකතු කරන්න. Add chicken.",
        "අනෙක් bread slice එකෙන් වසාගන්න. Cover with the other bread slice.",
        "කැබලි කර serve කරන්න. Slice and serve."
    ],

    tips:"Bread එක toast කළොත් sandwich එක වඩා crispy වේ. Toast the bread for extra crispiness."
},

{
    si:"චිකන් ෂවර්මා",
    en:"Chicken Shawarma",
    category:"Chicken",

    image:"https://images.unsplash.com/photo-1529006557810-274b9b2fc783?auto=format&fit=crop&w=1200&q=90",

    description:"Chicken, salad සහ sauce සමඟ සාදන shawarma wrap.",

    prep:"⏱️ Prep: 20 min",
    cook:"🔥 Cook: 20 min",
    serve:"👥 Serves: 3",

    ingredients:[
        "Chicken – කුකුළු මස් – 300g",
        "Flatbread – රොටි – 3",
        "Lettuce – සලාද කොළ",
        "Tomato – තක්කාලි",
        "Garlic sauce – සුදු ලූනු සෝස්",
        "Pepper – ගම්මිරිස්",
        "Paprika – පැප්‍රිකා"
    ],

    steps:[
        "Chicken එක spices සමඟ marinate කරන්න. Marinate chicken with spices.",
        "Chicken හොඳින් cook කරන්න. Cook chicken thoroughly.",
        "Flatbread එක මත sauce දමන්න. Spread sauce on flatbread.",
        "Lettuce සහ tomato එකතු කරන්න. Add lettuce and tomato.",
        "Chicken එකතු කරන්න. Add chicken.",
        "Wrap එක තදින් roll කරන්න. Roll tightly.",
        "කැබලි කර පිළිගන්වන්න. Slice and serve."
    ],

    tips:"Chicken එක හොඳින් පිසී ඇති බව තහවුරු කරන්න. Make sure the chicken is fully cooked."
},

{
    si:"චොකලට් කුකීස්",
    en:"Chocolate Cookies",
    category:"Dessert",

    image:"https://images.unsplash.com/photo-1499636136210-6f4ee915583e?auto=format&fit=crop&w=1200&q=90",

    description:"Chocolate chips සහිත crispy cookies.",

    prep:"⏱️ Prep: 15 min",
    cook:"🔥 Bake: 12 min",
    serve:"👥 Serves: 12",

    ingredients:[
        "Flour – පිටි – කෝප්ප 1 1/2",
        "Butter – බටර් – 100g",
        "Sugar – සීනි – කෝප්ප 1/2",
        "Egg – බිත්තර – 1",
        "Chocolate chips – චොකලට් chips – කෝප්ප 1/2",
        "Vanilla – වැනිලා – තේ හැඳි 1"
    ],

    steps:[
        "Butter සහ sugar beat කරන්න. Beat butter and sugar.",
        "Egg සහ vanilla එකතු කරන්න. Add egg and vanilla.",
        "Flour එකතු කරන්න. Add flour.",
        "Chocolate chips එකතු කරන්න. Add chocolate chips.",
        "කුඩා dough balls සාදන්න. Make small dough balls.",
        "Baking tray එකේ තබන්න. Place on a baking tray.",
        "Bake until edges are golden. දාර golden වන තුරු bake කරන්න.",
        "සිසිල් කර serve කරන්න. Cool and serve."
    ],

    tips:"Cookies oven එකෙන් ගත් පසු ටික වේලාවක් tray එකේ තබන්න. Let cookies rest on the tray after baking."
},

{
    si:"කැරමල් පුඩිං",
    en:"Caramel Pudding",
    category:"Dessert",

    image:"https://images.unsplash.com/photo-1551024601-bec78aea704b?auto=format&fit=crop&w=1200&q=90",

    description:"මෘදු caramel pudding එකක්.",

    prep:"⏱️ Prep: 15 min",
    cook:"🔥 Cook: 35 min",
    serve:"👥 Serves: 6",

    ingredients:[
        "බිත්තර – Eggs – 4",
        "කිරි – Milk – කෝප්ප 2",
        "සීනි – Sugar – කෝප්ප 1",
        "Vanilla – වැනිලා – තේ හැඳි 1",
        "සීනි – Caramel සඳහා – කෝප්ප 1/2"
    ],

    steps:[
        "Caramel සඳහා sugar pan එකක දියකරන්න. Melt sugar in a pan for the caramel.",
        "Caramel pudding mould එකට දමන්න. Pour caramel into the mould.",
        "Eggs සහ milk mix කරන්න. Mix eggs and milk.",
        "Vanilla එකතු කරන්න. Add vanilla.",
        "Mixture එක mould එකට දමන්න. Pour mixture into mould.",
        "Steam කරන්න. Steam until set.",
        "සිසිල් කර fridge එකේ තබන්න. Cool and refrigerate.",
        "Plate එකකට පෙරළා serve කරන්න. Turn onto a plate and serve."
    ],

    tips:"Caramel එක වැඩිපුර කළු නොකරන්න. Do not burn the caramel."
},

{
    si:"මැන්ගෝ ලැසි",
    en:"Mango Lassi",
    category:"Drinks",

    image:"https://images.unsplash.com/photo-1570696516188-ade861b84a49?auto=format&fit=crop&w=1200&q=90",

    description:"අඹ සහ yogurt වලින් සාදන creamy lassi.",

    prep:"⏱️ Prep: 5 min",
    cook:"🔥 Cook: 0 min",
    serve:"👥 Serves: 2",

    ingredients:[
        "අඹ – Mango – 1 large",
        "Yogurt – යෝගට් – කෝප්ප 1",
        "Milk – කිරි – කෝප්ප 1/2",
        "Sugar – සීනි – මේස හැඳි 1",
        "Ice – අයිස්"
    ],

    steps:[
        "අඹ කපා blender එකට දමන්න. Cut mango and add to blender.",
        "Yogurt සහ milk එකතු කරන්න. Add yogurt and milk.",
        "Sugar එකතු කරන්න. Add sugar.",
        "Smooth වන තුරු blend කරන්න. Blend until smooth.",
        "Ice එකතු කරන්න. Add ice.",
        "සිසිල්ව serve කරන්න. Serve cold."
    ],

    tips:"Thick lassi එකක් සඳහා yogurt වැඩිපුර භාවිතා කරන්න. Use more yogurt for a thicker lassi."
},

{
    si:"චිකන් බිරියානි",
    en:"Chicken Biryani",
    category:"Chicken",

    image:"https://images.unsplash.com/photo-1563379091339-03246963d96c?auto=format&fit=crop&w=1200&q=90",

    description:"සුවඳවත් කුළුබඩු සහ chicken සමඟ සාදන රසවත් biryani.",

    prep:"⏱️ Prep: 30 min",
    cook:"🔥 Cook: 45 min",
    serve:"👥 Serves: 6",

    ingredients:[
        "Basmati rice – බාස්මති බත් – 3 cups",
        "Chicken – කුකුළු මස් – 500g",
        "Onion – ලූනු – 2",
        "Yogurt – යෝගට් – 1 cup",
        "Biryani spices – බිරියානි කුළුබඩු",
        "Ginger – ඉඟුරු",
        "Garlic – සුදු ලූනු",
        "Saffron – කුංකුම – optional",
        "Salt – ලුණු"
    ],

    steps:[
        "Chicken එක yogurt සහ spices සමඟ marinate කරන්න. Marinate chicken with yogurt and spices.",
        "Basmati rice සෝදා අර්ධ වශයෙන් පිසගන්න. Wash and partially cook basmati rice.",
        "ලූනු golden brown වන තුරු cook කරන්න. Cook onions until golden brown.",
        "Chicken curry එක සකස් කරන්න. Prepare the chicken curry.",
        "භාජනයක chicken layer එකක් දමන්න. Place a chicken layer in a pot.",
        "ඉහළින් rice layer එකක් දමන්න. Add a rice layer.",
        "Layers කිහිපයක් සාදන්න. Create several layers.",
        "Pot එක වසා low heat එකේ cook කරන්න. Cover and cook on low heat.",
        "බත් සහ chicken සම්පූර්ණයෙන් පිසුණු පසු serve කරන්න. Serve when rice and chicken are fully cooked."
    ],

    tips:"Biryani එක low heat එකේ අවසානයේ cook කිරීමෙන් හොඳ aroma එකක් ලැබේ. Finish on low heat for better aroma."
}

];


/* =====================================================
   MORE RECIPES AUTO-GENERATION
   ===================================================== */

const extraRecipes = [

["කොත්තු රොටි","Kottu Roti","Sri Lankan"],
["එළවළු කොත්තු","Vegetable Kottu","Sri Lankan"],
["පොල් සම්බෝල","Pol Sambol","Sri Lankan"],
["සීනි සම්බෝල","Seeni Sambol","Sri Lankan"],
["පොල් රොටි","Pol Roti","Sri Lankan"],
["ඉඳිආප්ප","String Hoppers","Sri Lankan"],
["ආප්ප","Hoppers","Sri Lankan"],
["බිත්තර ආප්ප","Egg Hopper","Sri Lankan"],
["මාළු කරිය","Fish Curry","Sri Lankan"],
["මාළු ඇඹුල්තියල්","Fish Ambul Thiyal","Sri Lankan"],
["පරිප්පු වඩේ","Parippu Vadai","Sri Lankan"],
["පොල් කිරි බත්","Coconut Milk Rice","Sri Lankan"],
["කිරි බත්","Milk Rice","Sri Lankan"],
["පරිප්පු කරිය","Dhal Curry","Sri Lankan"],
["අල කරිය","Potato Curry","Vegetarian"],
["වට්ටක්කා කරිය","Pumpkin Curry","Vegetarian"],
["බෝංචි කරිය","Bean Curry","Vegetarian"],
["බටු මෝජු","Brinjal Moju","Sri Lankan"],
["ගොටුකොළ සම්බෝල","Gotukola Sambol","Vegetarian"],
["කැකිරි සලාද","Cucumber Salad","Vegetarian"],
["ග්‍රීක් සලාද","Greek Salad","Vegetarian"],
["කෝල්ස්ලෝ","Coleslaw","Vegetarian"],
["ගාර්ලික් බටර් මෂ්රූම්","Garlic Butter Mushrooms","Vegetarian"],
["වෙජිටබල් නූඩ්ල්ස්","Vegetable Noodles","Vegetarian"],
["එග් නූඩ්ල්ස්","Egg Noodles","Vegetarian"],
["ගාර්ලික් නූඩ්ල්ස්","Garlic Noodles","Vegetarian"],
["චව් මීන්","Chow Mein","Fast Food"],
["මැක් ඇන්ඩ් චීස්","Mac and Cheese","Fast Food"],
["ලසඤ්ඤා","Lasagna","Fast Food"],
["චිකන් ලසඤ්ඤා","Chicken Lasagna","Chicken"],
["වෙජිටබල් පැස්ටා","Vegetable Pasta","Vegetarian"],
["පෙස්ටෝ පැස්ටා","Pesto Pasta","Vegetarian"],
["මෂ්රූම් පැස්ටා","Mushroom Pasta","Vegetarian"],
["ක්‍රීමි පැස්ටා","Creamy Pasta","Fast Food"],
["ස්පැගටි","Spaghetti","Fast Food"],
["චිකන් බර්ගර්","Chicken Burger","Chicken"],
["බීෆ් බර්ගර්","Beef Burger","Fast Food"],
["හොට් ඩෝග්","Hot Dog","Fast Food"],
["චිකන් නගට්ස්","Chicken Nuggets","Chicken"],
["චිකන් වින්ග්ස්","Chicken Wings","Chicken"],
["චිකන් පොප්කෝන්","Chicken Popcorn","Chicken"],
["ෆිෂ් බර්ගර්","Fish Burger","Fast Food"],
["ටූනා සැන්ඩ්විච්","Tuna Sandwich","Fast Food"],
["චිකන් රැප්","Chicken Wrap","Chicken"],
["චිකන් ටැකෝස්","Chicken Tacos","Chicken"],
["ෆිෂ් සැන්ඩ්විච්","Fish Sandwich","Fast Food"],
["බනානා කේක්","Banana Cake","Dessert"],
["කැරට් කේක්","Carrot Cake","Dessert"],
["රෙඩ් වෙල්වට් කේක්","Red Velvet Cake","Dessert"],
["කප්කේක්","Cupcake","Dessert"],
["ඩෝනට්ස්","Donuts","Dessert"],
["චොකලට් මූස්","Chocolate Mousse","Dessert"],
["ෆෘට් ට්‍රයිෆල්","Fruit Trifle","Dessert"],
["පුඩිං","Pudding","Dessert"],
["අයිස්ක්‍රීම් සන්ඩේ","Ice Cream Sundae","Dessert"],
["ඔට් කුකීස්","Oat Cookies","Dessert"],
["ස්ට්‍රෝබෙරි ස්මූති","Strawberry Smoothie","Drinks"],
["වෝටර්මෙලන් ජූස්","Watermelon Juice","Drinks"],
["පයිනැපල් ජූස්","Pineapple Juice","Drinks"],
["ඔරේන්ජ් ජූස්","Orange Juice","Drinks"],
["අයිස්ඩ් කොෆී","Iced Coffee","Drinks"],
["අවකාඩෝ ස්මූති","Avocado Smoothie","Drinks"],
["බනානා ස්මූති","Banana Smoothie","Drinks"],
["ලෙමන් ටී","Lemon Tea","Drinks"],
["මිල්ක් ටී","Milk Tea","Drinks"],
["හොට් චොකලට්","Hot Chocolate","Drinks"],
["මසාලා ටී","Masala Tea","Drinks"],
["වෙජිටබල් කරි","Vegetable Curry","Vegetarian"],
["ටොමැටෝ පැස්ටා","Tomato Pasta","Vegetarian"],
["චීස් සැන්ඩ්විච්","Cheese Sandwich","Fast Food"],
["පෙපරෝනි පීසා","Pepperoni Pizza","Fast Food"],
["පොටේටෝ චිප්ස්","Potato Chips","Fast Food"],
["බේක්ඩ් පොටේටෝ","Baked Potato","Vegetarian"],
["චීස් බෝල්ස්","Cheese Balls","Fast Food"],
["වෙජිටබල් රෝල්ස්","Vegetable Rolls","Fast Food"],
["ස්ප්‍රින්ග් රෝල්ස්","Spring Rolls","Fast Food"],
["චිකන් රෝල්ස්","Chicken Rolls","Chicken"],
["ෆිෂ් රෝල්ස්","Fish Rolls","Fast Food"],
["චිකන් සමෝසා","Chicken Samosa","Chicken"],
["වෙජිටබල් සමෝසා","Vegetable Samosa","Vegetarian"],
["චිකන් පැටිස්","Chicken Patties","Chicken"],
["ෆිෂ් පැටිස්","Fish Patties","Fast Food"],
["බිත්තර පැටිස්","Egg Patties","Fast Food"],
["චොකලට් ඩෝනට්","Chocolate Donut","Dessert"],
["ස්ට්‍රෝබෙරි කේක්","Strawberry Cake","Dessert"],
["ලෙමන් කේක්","Lemon Cake","Dessert"],
["කොකනට් කේක්","Coconut Cake","Dessert"],
["බිස්කට් පුඩිං","Biscuit Pudding","Dessert"],
["චොකලට් පුඩිං","Chocolate Pudding","Dessert"],
["වැනිලා පුඩිං","Vanilla Pudding","Dessert"],
["කොකනට් පුඩිං","Coconut Pudding","Dessert"],
["පපොල් ස්මූති","Papaya Smoothie","Drinks"],
["පැෂන් ෆෘට් ජූස්","Passion Fruit Juice","Drinks"],
["ග්‍රේප් ජූස්","Grape Juice","Drinks"],
["ඇපල් ජූස්","Apple Juice","Drinks"],
["පීච් ස්මූති","Peach Smoothie","Drinks"],
["කොකනට් වෝටර්","Coconut Water","Drinks"],
["කොකෝනට් මිල්ක්ෂේක්","Coconut Milkshake","Drinks"],
["කෝපි","Coffee","Drinks"],
["අයිස් ටී","Iced Tea","Drinks"]
];


/* =====================================================
   ADD EXTRA RECIPES
===================================================== */

const defaultImages = {

"Rice":"https://images.unsplash.com/photo-1512058564366-18510be2db19?auto=format&fit=crop&w=1200&q=90",

"Chicken":"https://images.unsplash.com/photo-1604908176997-125f25cc6f3d?auto=format&fit=crop&w=1200&q=90",

"Vegetarian":"https://images.unsplash.com/photo-1540420773420-3366772f4999?auto=format&fit=crop&w=1200&q=90",

"Fast Food":"https://images.unsplash.com/photo-1568901346375-23c9450c58cd?auto=format&fit=crop&w=1200&q=90",

"Dessert":"https://images.unsplash.com/photo-1551024506-0bccd828d307?auto=format&fit=crop&w=1200&q=90",

"Drinks":"https://images.unsplash.com/photo-1553530666-ba11a90a0868?auto=format&fit=crop&w=1200&q=90",

"Sri Lankan":"https://images.unsplash.com/photo-1601050690597-df0568f70950?auto=format&fit=crop&w=1200&q=90"
};


extraRecipes.forEach(item => {

    recipes.push({

        si:item[0],

        en:item[1],

        category:item[2],

        image:
            defaultImages[item[2]]
            ||
            defaultImages["Fast Food"],

        description:
            item[0]+" රසවත් ලෙස සාදාගත හැකි ආහාර වට්ටෝරුවකි. Delicious "+item[1]+" recipe.",

        prep:"⏱️ Prep: 15 min",

        cook:"🔥 Cook: 20 min",

        serve:"👥 Serves: 4",

        ingredients:[
            "ප්‍රධාන ද්‍රව්‍ය – Main ingredient",
            "ලූනු – Onion",
            "සුදු ලූනු – Garlic",
            "මිරිස් – Chili",
            "ලුණු – Salt",
            "ගම්මිරිස් – Pepper",
            "තෙල් – Cooking oil",
            "කුළුබඩු – Spices"
        ],

        steps:[
            "සියලුම ද්‍රව්‍ය සූදානම් කරගන්න. Prepare all ingredients.",
            "එළවළු සහ ප්‍රධාන ද්‍රව්‍ය කපාගන්න. Chop the vegetables and main ingredients.",
            "පෑන් එක හෝ භාජනය රත් කරන්න. Heat the pan or pot.",
            "තෙල් සහ කුළුබඩු එකතු කරන්න. Add oil and spices.",
            "ප්‍රධාන ද්‍රව්‍ය එකතු කර හොඳින් පිසගන්න. Add the main ingredients and cook well.",
            "අවශ්‍ය පරිදි ලුණු සහ ගම්මිරිස් එකතු කරන්න. Add salt and pepper as needed.",
            "මද ගින්නේ හොඳින් පිසෙන්නට ඉඩ දෙන්න. Allow it to cook on medium-low heat.",
            "සම්පූර්ණයෙන් පිසුණු පසු උණු උණුවෙන් පිළිගන්වන්න. Serve hot when fully cooked."
        ],

        tips:
            "නැවුම් ද්‍රව්‍ය භාවිතා කිරීමෙන් වඩා හොඳ රසයක් ලැබේ. Use fresh ingredients for better flavour."

    });

});


/* =====================================================
   VARIABLES
===================================================== */

let selectedCategory = "All";


/* =====================================================
   DISPLAY
===================================================== */

function displayRecipes(list){

    const grid =
        document.getElementById("recipeGrid");

    grid.innerHTML = "";

    document.getElementById("resultCount").innerText =
        "🍽️ Recipes found: " + list.length;


    if(list.length === 0){

        document.getElementById("noResult").style.display =
            "block";

        return;
    }


    document.getElementById("noResult").style.display =
        "none";


    list.forEach(recipe => {

        const index =
            recipes.indexOf(recipe);


        grid.innerHTML += `

        <div class="card">

            <div class="card-img">

                <img
                    src="${recipe.image}"
                    alt="${recipe.en}"
                    loading="lazy">

            </div>


            <div class="card-body">

                <span class="tag">
                    ${recipe.category}
                </span>

                <h2>
                    ${recipe.si}
                </h2>

                <h3>
                    ${recipe.en}
                </h3>

                <p>
                    ${recipe.description}
                </p>

                <button
                    class="view"
                    onclick="openRecipe(${index})">

                    📖 View Full Recipe
                    <br>
                    සම්පූර්ණ වට්ටෝරුව බලන්න

                </button>

            </div>

        </div>

        `;

    });

}


/* =====================================================
   SEARCH
===================================================== */

function searchRecipes(){

    const text =
        document
        .getElementById("search")
        .value
        .toLowerCase()
        .trim();


    const filtered =
        recipes.filter(recipe => {

            const allText = (

                recipe.si +
                " " +
                recipe.en +
                " " +
                recipe.category +
                " " +
                recipe.description +
                " " +
                recipe.ingredients.join(" ")

            ).toLowerCase();


            const matchesSearch =
                allText.includes(text);


            const matchesCategory =
                selectedCategory === "All"
                ||
                recipe.category === selectedCategory;


            return (
                matchesSearch &&
                matchesCategory
            );

        });


    displayRecipes(filtered);
}


/* =====================================================
   CATEGORY
===================================================== */

function filterCategory(category,button){

    selectedCategory =
        category;


    document
    .querySelectorAll(
        ".categories button"
    )
    .forEach(btn => {

        btn.classList.remove(
            "active"
        );

    });


    button.classList.add(
        "active"
    );


    searchRecipes();
}


/* =====================================================
   OPEN RECIPE
===================================================== */

function openRecipe(index){

    const recipe =
        recipes[index];


    document.getElementById(
        "modalImage"
    ).src =
        recipe.image;


    document.getElementById(
        "modalSinhala"
    ).innerText =
        recipe.si;


    document.getElementById(
        "modalEnglish"
    ).innerText =
        recipe.en;


    document.getElementById(
        "modalDescription"
    ).innerText =
        recipe.description;


    document.getElementById(
        "modalPrep"
    ).innerText =
        recipe.prep;


    document.getElementById(
        "modalCook"
    ).innerText =
        recipe.cook;


    document.getElementById(
        "modalServe"
    ).innerText =
        recipe.serve;


    /* Ingredients */

    const ingredients =
        document.getElementById(
            "modalIngredients"
        );

    ingredients.innerHTML = "";


    recipe.ingredients.forEach(item => {

        ingredients.innerHTML += `

        <div class="ingredient">
            🥕 ${item}
        </div>

        `;

    });


    /* Steps */

    const steps =
        document.getElementById(
            "modalSteps"
        );

    steps.innerHTML = "";


    recipe.steps.forEach(step => {

        steps.innerHTML += `

        <li>
            ${step}
        </li>

        `;

    });


    /* Tips */

    document.getElementById(
        "modalTips"
    ).innerText =
        recipe.tips;


    /* Sinhala + English */

    document.getElementById(
        "modalSinhalaLong"
    ).innerText =
        recipe.description +
        " මෙම වට්ටෝරුවේ දක්වා ඇති පියවර අනුගමනය කරමින් රසවත් ආහාරයක් සකස් කරගත හැක.";


    document.getElementById(
        "modalEnglishLong"
    ).innerText =
        recipe.description +
        " Follow the cooking steps above to prepare this delicious recipe at home.";


    document.getElementById(
        "modal"
    ).style.display =
        "block";


    document.body.style.overflow =
        "hidden";
}


/* =====================================================
   CLOSE
===================================================== */

function closeRecipe(){

    document.getElementById(
        "modal"
    ).style.display =
        "none";


    document.body.style.overflow =
        "auto";
}


/* =====================================================
   CLICK OUTSIDE
===================================================== */

window.onclick =
function(event){

    const modal =
        document.getElementById(
            "modal"
        );


    if(event.target === modal){

        closeRecipe();

    }

};


/* =====================================================
   ESC KEY
===================================================== */

document.addEventListener(
    "keydown",
    function(event){

        if(
            event.key === "Escape"
        ){

            closeRecipe();

        }

    }
);


/* =====================================================
   START
===================================================== */

displayRecipes(recipes);

</script>

</body>
</html>

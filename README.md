[BoligInsight.html](https://github.com/user-attachments/files/33106583/BoligInsight.html)
<!DOCTYPE html>
<html lang="da">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1">
<title>BoligInsight Rapport</title>

<style>
*{margin:0;padding:0;box-sizing:border-box;font-family:Segoe UI,sans-serif}
body{background:#f4f7fb;color:#1f2937}
header{background:#0A4DB3;color:#fff;padding:25px;text-align:center}
header h1{font-size:38px}
.layout{display:flex;height:calc(100vh - 92px)}

.sidebar{
width:320px;
background:#fff;
border-right:1px solid #e5e7eb;
overflow-y:auto;
padding:20px;
}

.content{
flex:1;
padding:25px;
overflow-y:auto;
}

.search{
width:100%;
padding:12px;
border:1px solid #ddd;
border-radius:8px;
margin-bottom:15px;
}

.filters{
display:flex;
gap:8px;
margin-bottom:15px;
flex-wrap:wrap;
}

.filters button{
border:none;
padding:8px 12px;
border-radius:20px;
cursor:pointer;
}

.highBtn{background:#fee2e2}
.mediumBtn{background:#fef3c7}
.lowBtn{background:#dcfce7}

.issue{
padding:12px;
border-radius:10px;
background:#f8fafc;
margin-bottom:10px;
cursor:pointer;
border:1px solid #e5e7eb;
}

.issue:hover{
background:#eef4ff;
}

.card{
background:#fff;
border-radius:18px;
overflow:hidden;
box-shadow:0 5px 30px rgba(0,0,0,.07);
}

.heroimg{
height:420px;
background:linear-gradient(135deg,#0A4DB3,#4f85e6);
display:flex;
align-items:center;
justify-content:center;
color:white;
font-size:42px;
font-weight:bold;
}

.contentBox{
padding:25px;
}

.risk{
display:inline-block;
padding:10px 15px;
border-radius:30px;
color:#fff;
font-weight:bold;
margin-bottom:15px;
}

.high{background:#dc2626}
.medium{background:#f59e0b}
.low{background:#16a34a}

.info{
margin-top:15px;
line-height:1.7;
}

details{
margin-top:20px;
background:#f8fafc;
padding:15px;
border-radius:10px;
}

.price{
margin-top:20px;
background:#eef4ff;
padding:15px;
border-radius:10px;
}

.navButtons{
display:flex;
justify-content:space-between;
margin-top:20px;
}

.navButtons button{
padding:12px 18px;
border:none;
background:#0A4DB3;
color:white;
border-radius:8px;
cursor:pointer;
}

.progress{
margin-top:20px;
}

.bar{
height:12px;
background:#ddd;
border-radius:20px;
overflow:hidden;
}

.fill{
height:100%;
background:#0A4DB3;
width:0%;
transition:.3s;
}

.stats{
margin-bottom:20px;
padding:15px;
background:#eef4ff;
border-radius:10px;
}



header{
background:#0A4DB3;
color:#fff;
padding:25px;
text-align:center;
position:relative;
}

.burger{

    position:absolute;

    right:20px;
    top:20px;

    background:none;

    border:none;

    color:white;

    font-size:32px;

    cursor:pointer;

}

.sideMenu{

    position:fixed;

    top:0;
    right:-350px;

    width:320px;
    height:100vh;

    background:white;

    box-shadow:-5px 0 30px rgba(0,0,0,.15);

    padding:25px;

    transition:.3s;

    z-index:9999;

}

.sideMenu.open{
    right:0;
}

.sideMenu h2{
    margin-bottom:20px;
    color:#0A4DB3;
}

.sideMenu button{

    width:100%;

    padding:15px;

    margin-bottom:10px;

    border:none;

    border-radius:10px;

    background:#eef4ff;

    cursor:pointer;

    text-align:left;

}

@media(max-width:900px){
.layout{
flex-direction:column;
height:auto;
}
.sidebar{
width:100%;
max-height:300px;
}
}

.frontPage{

    min-height:100vh;

    background:#0A4DB3;

    display:flex;

    align-items:center;

    justify-content:center;

}

.frontContainer{

    text-align:center;

    color:white;

    max-width:900px;

    padding:40px;

}

.frontLogo{

    width:450px;

    max-width:90%;

    height:auto;

    margin-bottom:30px;

}

.frontContainer h1{

    font-size:60px;

    margin-bottom:10px;

}

.frontContainer h2{

    font-size:32px;

    font-weight:300;

    margin-bottom:25px;

}

.frontContainer p{

    font-size:20px;

    line-height:1.7;

    margin-bottom:35px;

}

.startBtn{

    background:white;

    color:#0A4DB3;

    border:none;

    padding:18px 45px;

    border-radius:12px;

    font-size:20px;

    font-weight:600;

    cursor:pointer;

}

.startBtn:hover{

    background:#eef4ff;

}

#legalPage{

    display:none;

    min-height:100vh;

    background:#f4f7fb;

    padding:40px;

}

</style>
</head>
<body>

<div id="frontPage" class="frontPage">

    <div class="frontContainer">

        <img src="logo.png"
             alt="BoligInsight Logo"
             class="frontLogo">

        <h1>BoligInsight</h1>

        <h2>Indsigt i din bolig</h2>

        <p>
            Denne rapport indeholder vejledende information om
            typiske forhold og skader i danske boliger.
        </p>

        <button class="startBtn" onclick="startReport()">
            Start rapport
        </button>

    </div>

</div>


<div id="reportPage" style="display:none;">

<header>

    <h1>BoligInsight</h1>
    <p>Indsigt i din bolig</p>

    <button class="burger" onclick="toggleMenu()">
        ☰
    </button>

</header>

<div id="sideMenu" class="sideMenu">

    <button class="menuClose" onclick="toggleMenu()">
        ← Luk menu
    </button>

    <h2>BoligInsight</h2>

    <button onclick="showFrontPage()">
    🏠 Forside
</button>

<button onclick="showReportPage()">
    📄 Rapport
</button>

<button onclick="showLegalPage()">
    ⚖️ Tro & Love / Ansvarsfraskrivelse
</button>

</div>

</div>

<div class="layout">

<div class="sidebar">

<div class="stats">
<strong>29 fund identificeret</strong>
</div>

<input
class="search"
id="search"
placeholder="Søg i rapport..."
onkeyup="renderList()"
>

<div class="filters">
<button class="highBtn" onclick="setFilter('high')">Høj</button>
<button class="mediumBtn" onclick="setFilter('medium')">Mellem</button>
<button class="lowBtn" onclick="setFilter('low')">Lav</button>
<button onclick="setFilter('all')">Alle</button>
</div>

<div id="issueList"></div>

</div>

<div class="content">

<div class="card">

<div class="heroimg" id="heroImage">
🏠
</div>

<div class="contentBox">

<div id="risk" class="risk high">
Høj risiko
</div>

<h2 id="title"></h2>

<div class="price">
    <strong>Beskrivelse</strong>
    <p id="description"></p>
</div>

<div class="price">
<strong>Sådan identificeres forholdet</strong>
<p id="identify"></p>
</div>

<div class="price">
<strong>Risiko / konsekvens</strong>
<p id="details"></p>
</div>

<div class="progress">
<strong>Fremdrift</strong>
<div class="bar">
<div id="progressFill" class="fill"></div>
</div>
<p id="progressText"></p>
</div>

<div class="navButtons">
<button onclick="prevIssue()">← Forrige</button>
<button onclick="nextIssue()">Næste →</button>
</div>

</div>

</div>

</div>

</div>

<div
id="legalPage"
style="
display:none;
padding:40px;
max-width:1100px;
margin:auto;
"
>

<button
onclick="showReportPage()"
style="
padding:12px 20px;
background:#0A4DB3;
color:white;
border:none;
border-radius:10px;
cursor:pointer;
margin-bottom:30px;
"
>
← Tilbage til rapport
</button>

<h1 style="color:#0A4DB3;margin-bottom:20px;">
Tro & Love Erklæring, Vilkår og Ansvarsfraskrivelse
</h1>

<div class="price">

    <strong>Vejledende informationsmateriale</strong>

    <p>
        Denne rapport er et vejledende informationsprodukt udarbejdet med det formål
        at øge brugerens generelle forståelse af typiske forhold og skader, som kan
        forekomme i danske boliger.
    </p>

    <p>
        Rapporten vedrører ikke en konkret ejendom og udgør ikke en vurdering af nogen
        specifik bolig, bygning eller grund.
    </p>

</div>

<div class="price">

    <strong>Ikke en tilstandsrapport</strong>

    <p>
        Rapporten er ikke en tilstandsrapport, elinstallationsrapport,
        energimærke eller anden lovpligtig rapport.
    </p>

    <p>
        Rapporten kan ikke erstatte vurderinger, undersøgelser eller erklæringer
        udført af beskikkede bygningssagkyndige, ingeniører, håndværkere,
        autoriserede installatører eller andre relevante fagpersoner.
    </p>

</div>

<div class="price">

    <strong>Ingen professionel rådgivning</strong>

    <p>
        Rapportens indhold udgør ikke juridisk, byggeteknisk, økonomisk,
        forsikringsmæssig eller anden professionel rådgivning.
    </p>

    <p>
        Brugeren bør altid søge konkret rådgivning hos relevante fagpersoner
        før køb, salg, renovering eller anden disposition vedrørende fast ejendom.
    </p>

</div>

<div class="price">

    <strong>Ansvarsfraskrivelse</strong>

    <p>
        Anvendelse af rapportens indhold sker udelukkende på brugerens eget ansvar.
    </p>

    <p>
        BoligInsight påtager sig intet ansvar for dispositioner, vurderinger,
        handlinger eller beslutninger truffet på baggrund af rapportens indhold.
    </p>

    <p>
        BoligInsight kan ikke gøres ansvarlig for direkte eller indirekte tab,
        driftstab, avancetab, følgeskader, personskader, tingsskader eller
        andre økonomiske konsekvenser som følge af brugen af rapporten.
    </p>

</div>

<div class="price">

    <strong>Ingen garanti</strong>

    <p>
        BoligInsight giver ingen garanti for rapportens fuldstændighed,
        nøjagtighed, anvendelighed eller aktualitet.
    </p>

    <p>
        Rapportens indhold er vejledende og kan ikke anvendes som garanti
        for faktiske forhold i en konkret bolig.
    </p>

</div>

<div class="price">

    <strong>Brugerens ansvar</strong>

    <p>
        Brugeren er selv ansvarlig for at verificere oplysninger,
        indhente professionel rådgivning og foretage relevante undersøgelser.
    </p>

    <p>
        Brugeren er endvidere ansvarlig for at overholde gældende lovgivning,
        sikkerhedskrav, myndighedskrav og producentanvisninger.
    </p>

</div>

<div class="price">

    <strong>Vedligeholdelse og udbedring</strong>

    <p>
        Eventuelle beskrivelser af vedligeholdelse, reparation eller udbedring
        er alene generelle vejledninger.
    </p>

    <p>
        BoligInsight tager ikke ansvar for resultatet af arbejde udført på
        baggrund af rapportens indhold.
    </p>

</div>

<div class="price">

    <strong>Tredjeparts brug</strong>

    <p>
        Rapporten er udarbejdet til den registrerede bruger og må ikke anses
        som en erklæring til fordel for tredjemand.
    </p>

    <p>
        BoligInsight fraskriver sig ethvert ansvar over for tredjeparter,
        som måtte modtage, anvende eller støtte ret på rapportens indhold.
    </p>

</div>

<div class="price">

    <strong>Ophavsret og anvendelsesbegrænsninger</strong>

    <p>
        Rapportens indhold, struktur, design, tekster, beskrivelser,
        illustrationer og øvrige materialer er ophavsretligt beskyttet.
    </p>

    <p>
        Rapporten må ikke kopieres, reproduceres, videredistribueres,
        offentliggøres, videresælges, udlånes, uploades, deles med tredjepart
        eller på anden måde stilles til rådighed uden forudgående
        skriftlig tilladelse fra BoligInsight.
    </p>

    <p>
        Rapporten må ikke anvendes kommercielt, helt eller delvist,
        uden skriftlig tilladelse fra BoligInsight.
    </p>

    <p>
        Uberettiget brug kan medføre erstatningsansvar og retslige skridt
        efter gældende lovgivning.
    </p>

</div>

<div class="price">

    <strong>Tro & Love Erklæring</strong>

    <p>
        Ved anvendelse af rapporten erklærer brugeren på tro og love,
        at rapporten forstås som et generelt vejledende informationsmateriale.
    </p>

    <p>
        Brugeren accepterer samtidig, at rapporten ikke kan stå alene som
        grundlag for køb, salg, investering, renovering eller andre
        væsentlige beslutninger vedrørende fast ejendom.
    </p>

</div>

<script>

function toggleMenu(){

    document
        .getElementById("sideMenu")
        .classList
        .toggle("open");

}


let filter = "all";

const issues = [

{title:"Vindskeder og sternbrædder med nedbrydning",risk:"medium",desc:"Nedbrudte vindskeder og sternbrædder.",det:"Risiko for råd og yderligere nedbrydning.",id:"Revner, opblødning eller smuldrende træ."},
{title:"Træbeklædning med råd",risk:"high",desc:"Træbeklædning er nedbrudt eller rådden.",det:"Yderligere nedbrydning kan forventes.",id:"Revner, sprækker og smuldrende træ."},
{title:"Tag med mos og alger",risk:"medium",desc:"Taget er kraftigt begroet.",det:"Øget fugtbelastning af tag og undertag.",id:"Mos og alger på tagflader."},
{title:"Revner i tagplader eller tagsten",risk:"high",desc:"Tagbelægning har revner.",det:"Fugtindtrængning og følgeskader.",id:"Revner i plader eller sten."},
{title:"Tagpap med dampbuler",risk:"high",desc:"Tagpap danner buler og lunker.",det:"Risiko for fugt og utætheder.",id:"Luftlommer og vandansamlinger."},
{title:"Defekt skorsten",risk:"high",desc:"Løse fuger og frostsprængninger.",det:"Kan svække konstruktionen.",id:"Afskallede sten og udfaldne fuger."},
{title:"Nedløb ikke tilsluttet brønd",risk:"medium",desc:"Regnvand udledes ved hus.",det:"Fugt omkring sokkel.",id:"Manglende forbindelse til tagbrønd."},
{title:"Tagrender med tæring",risk:"medium",desc:"Tagrender er gennemtærede.",det:"Kan medføre fugtpåvirkning.",id:"Hullerne og rust."},
{title:"Manglende redningsåbning",risk:"high",desc:"Vinduer opfylder ikke krav.",det:"Ikke i overensstemmelse med regler.",id:"Kontroller BR18 krav."},
{title:"Fugeslip ved vinduer",risk:"medium",desc:"Fuger slipper konstruktionen.",det:"Kan give fugtindtrængning.",id:"Utæt samling omkring vindue."},
{title:"Defekte fuger ved sålbænk",risk:"medium",desc:"Fuger er porøse.",det:"Fugt kan trænge ind.",id:"Mangelfulde samlinger."},
{title:"Revner i murværk",risk:"high",desc:"Revnedannelser i murværket.",det:"Kan udvikle sig yderligere.",id:"Lodrette og vandrette revner."},
{title:"Porøse murfuger",risk:"medium",desc:"Fuger nedbrydes.",det:"Risiko for yderligere skader.",id:"Mørtel falder ud."},
{title:"Revner i sokkel",risk:"high",desc:"Revner i sokkel eller puds.",det:"Kan påvirke stabilitet.",id:"Afskalninger og revner."},
{title:"Skader på trappesten",risk:"low",desc:"Klinker med dårlig vedhæftning.",det:"Risiko for løsrivelse.",id:"Afskalninger og hul lyd."},
{title:"Revnede vægfliser",risk:"high",desc:"Fliser i bruseniche revnede.",det:"Risiko for vandindtrængning.",id:"Revner og hul lyd."},
{title:"Revnede gulvklinker",risk:"high",desc:"Klinker i bruseniche revnede.",det:"Kan føre vand ned i konstruktion.",id:"Revner og hul lyd."},
{title:"Tæring i afløbsskål",risk:"high",desc:"Støbejernsafløb er tæret.",det:"Utætheder og fugtskader.",id:"Løft rist og inspicer."},
{title:"Forhøjelsesrammer i afløb",risk:"high",desc:"Afløb har afstandsrammer.",det:"Øget risiko for utæthed.",id:"Kig under afløbsrist."},
{title:"Utæt ventiltilslutning",risk:"medium",desc:"Utæt overgang ved aftræk.",det:"Kan skabe kondens.",id:"Kontroller samlingen."},
{title:"Tæring på vandrør",risk:"high",desc:"Korrosion på rør.",det:"Kan give vandskader.",id:"Misfarvninger og rust."},
{title:"Sikkerhedsventil uden afløb",risk:"medium",desc:"Overløb er ikke tilsluttet.",det:"Vandspild kan skade omgivelser.",id:"Kontroller afløb."},
{title:"Manglende værn på trappe",risk:"high",desc:"Trappe mangler håndliste.",det:"Risiko for personskade.",id:"Visuel kontrol."},
{title:"Punkteret termorude",risk:"low",desc:"Dårlig isoleringsevne.",det:"Nedsat energiydelse.",id:"Dug mellem glas."},
{title:"Revner i vægge",risk:"low",desc:"Kosmetiske revner.",det:"Normalt mindre betydning.",id:"Revner i overflader."},
{title:"Fugtskadet trægulv",risk:"high",desc:"Slidt og skadet gulv.",det:"Yderligere nedbrydning.",id:"Misfarvninger og gabende samlinger."},
{title:"Loftlem uden tætningsliste",risk:"low",desc:"Loftlem lukker ikke tæt.",det:"Varmetab og træk.",id:"Kontroller kant."},
{title:"Manglende ventilation ved tagfod",risk:"high",desc:"Isolering blokerer luft.",det:"Fugtskader kan opstå.",id:"Kontroller tagfod."},
{title:"Beskadiget undertag",risk:"high",desc:"Undertag med revner eller huller.",det:"Risiko for råd og skimmel.",id:"Se efter utætheder."}

];

let currentIndex = 0;

function riskText(r){
if(r==="high") return "Høj risiko";
if(r==="medium") return "Mellem risiko";
return "Lav risiko";
}

function showIssue(index){

currentIndex=index;

const i=issues[index];

document.getElementById("title").innerText=i.title;
document.getElementById("description").innerText=i.desc;
document.getElementById("details").innerText=i.det;
document.getElementById("identify").innerText=i.id;

const risk=document.getElementById("risk");

risk.className="risk "+i.risk;
risk.innerText=riskText(i.risk);

document.getElementById("heroImage").innerText="🔍";

document.getElementById("progressFill").style.width=
((index+1)/issues.length*100)+"%";

document.getElementById("progressText").innerText=
(index+1)+" af "+issues.length+" fund gennemgået";

}

function renderList(){

const q=document.getElementById("search").value.toLowerCase();

let html="";

issues.forEach((item,index)=>{

if(filter!=="all" && item.risk!==filter) return;

if(!item.title.toLowerCase().includes(q)) return;

html+=`
<div class="issue" onclick="showIssue(${index})">
${index+1}. ${item.title}
</div>
`;

});

document.getElementById("issueList").innerHTML=html;

}

function setFilter(f){
filter=f;
renderList();
}

function nextIssue(){
if(currentIndex<issues.length-1){
showIssue(currentIndex+1);
}
}

function prevIssue(){
if(currentIndex>0){
showIssue(currentIndex-1);
}
}

renderList();
showIssue(0);

function showLegalPage(){

    document.getElementById("frontPage")
        .style.display = "none";

    document.getElementById("reportPage")
        .style.display = "none";

    document.getElementById("legalPage")
        .style.display = "block";

    document.getElementById("sideMenu")
        .classList.remove("open");

}


function showReportPage(){

    document.getElementById("frontPage")
        .style.display = "none";

    document.getElementById("reportPage")
        .style.display = "block";

    const legalPage =
        document.getElementById("legalPage");

    if(legalPage){
        legalPage.style.display = "none";
    }

    document.getElementById("sideMenu")
        .classList.remove("open");

}


document.addEventListener("click", function(event){

    const menu =
        document.getElementById("sideMenu");

    const burger =
        document.querySelector(".burger");

    if(
        !menu.contains(event.target) &&
        !burger.contains(event.target)
    ){
        menu.classList.remove("open");
    }

});


function startReport(){

    document.getElementById("frontPage").style.display = "none";

    document.getElementById("reportPage").style.display = "block";

}

function showFrontPage(){

    document.getElementById("frontPage")
        .style.display = "flex";

    document.getElementById("reportPage")
        .style.display = "none";

    const legalPage =
        document.getElementById("legalPage");

    if(legalPage){
        legalPage.style.display = "none";
    }

    document.getElementById("sideMenu")
        .classList.remove("open");

}


function showLegalPage(){

    document.getElementById("frontPage").style.display = "none";

    document.getElementById("reportPage").style.display = "none";

    document.getElementById("legalPage").style.display = "block";

    document.getElementById("legalPage")
        .scrollIntoView();

    document.getElementById("sideMenu")
        .classList.remove("open");

}


</script>

<body>

<div id="frontPage">

</div>

<div id="reportPage">

    <header>
  
    </header>

    <div id="sideMenu">
    
    </div>

    <div class="layout">
    
    </div>

</div>

<div id="legalPage">

</div>

<script>
...
</script>

</body>
</html>

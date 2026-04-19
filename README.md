<!DOCTYPE html><html lang="en">  <head>  
  <meta charset="UTF-8">  
  <meta name="viewport" content="width=device-width, initial-scale=1.0">  
  <title>Ashish | CV & Cocktail Portfolio</title>  
  <script src="https://cdn.tailwindcss.com"></script>  
</head>  
<body class="bg-gray-100 text-gray-800">  <!-- Navbar -->  <nav class="bg-black text-white p-4 flex justify-between">  
    <h1 class="text-xl font-bold">Ashish Portfolio</h1>  
    <div class="space-x-4">  
      <a href="#cv">CV</a>  
      <a href="#cocktails">Cocktails</a>  
      <a href="#add">Add New</a>  
    </div>  
  </nav>  <!-- CV Section -->  <section id="cv" class="p-6">  
    <h2 class="text-2xl font-bold mb-4">My CV</h2>  
    <div class="bg-white p-4 rounded-2xl shadow">  
      <p><strong>Name:</strong> Ashish</p>  
      <p><strong>Role:</strong> Assistant Restaurant Manager</p>  
      <p><strong>Skills:</strong> Mixology, Customer Service, Bar Operations</p>  
      <p><strong>Experience:</strong> Add your experience here...</p>  
    </div>  
  </section>  <!-- Cocktails Section -->  <section id="cocktails" class="p-6">  
    <h2 class="text-2xl font-bold mb-4">Cocktail Menu</h2>  
    <div id="cocktailList" class="grid grid-cols-1 md:grid-cols-3 gap-4"></div>  
  </section>  <!-- Add Cocktail -->  <section id="add" class="p-6">  
    <h2 class="text-2xl font-bold mb-4">Add New Cocktail</h2>  
    <div class="bg-white p-4 rounded-2xl shadow space-y-3">  
      <input id="name" class="w-full p-2 border" placeholder="Cocktail Name" />  
      <input id="image" class="w-full p-2 border" placeholder="Image URL" />  
      <textarea id="desc" class="w-full p-2 border" placeholder="Description"></textarea>  
      <button onclick="addCocktail()" class="bg-black text-white px-4 py-2 rounded">Add</button>  
    </div>  
  </section>  <script>  
    let cocktails = JSON.parse(localStorage.getItem('cocktails')) || [];  function renderCocktails() {  
  const list = document.getElementById('cocktailList');  
  list.innerHTML = '';  
  cocktails.forEach(c => {  
    list.innerHTML += `  
      <div class="bg-white p-4 rounded-2xl shadow">  
        <img src="${c.image}" class="w-full h-40 object-cover rounded" />  
        <h3 class="text-xl font-bold mt-2">${c.name}</h3>  
        <p>${c.desc}</p>  
      </div>  
    `;  
  });  
}  

function addCocktail() {  
  const name = document.getElementById('name').value;  
  const image = document.getElementById('image').value;  
  const desc = document.getElementById('desc').value;  

  cocktails.push({ name, image, desc });  
  localStorage.setItem('cocktails', JSON.stringify(cocktails));  
  renderCocktails();  

  document.getElementById('name').value = '';  
  document.getElementById('image').value = '';  
  document.getElementById('desc').value = '';  
}  

renderCocktails();

</script></body>

</html>   Make a link of this

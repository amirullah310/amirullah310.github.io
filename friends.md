---
layout: default
title: Friends
---


<div class="friends-container">
<h1 class="page-title">Friends Page</h1>

<h2>Teman-Teman Saya di Kelas:</h2>

<!-- Fitur: Pencarian Teman -->
<input type="text" id="searchInput" placeholder="Cari teman..." onkeyup="filterFriends()" class="friend-search">

<!-- Pesan jika tidak ada teman yang ditemukan -->
<p id="noResults" class="no-results-message" style="display: none;">Nama tidak ditemukan</p>

<ol id="friendList" class="friends-list">
  {% for friend in site.data.friends %}
    <li class="friend-card">
      <a href="{{ friend.link }}" target="_blank">{{ friend.name }}</a>
    </li>
  {% endfor %}
</ol>
</div>

<script>
  function filterFriends() {
    const input = document.getElementById('searchInput');
    const filter = input.value.toLowerCase();
    const list = document.getElementById('friendList');
    const items = list.getElementsByTagName('li');
    let found = false;

    // Menyembunyikan semua teman
    for (let i = 0; i < items.length; i++) {
      const a = items[i].getElementsByTagName("a")[0];
      const txtValue = a.textContent || a.innerText;
      // Menampilkan hanya teman yang cocok
      if (txtValue.toLowerCase().includes(filter)) {
        items[i].style.display = "";
        found = true;
      } else {
        items[i].style.display = "none";
      }
    }

    // Menampilkan atau menyembunyikan pesan "Nama tidak ditemukan"
    const noResultsMessage = document.getElementById('noResults');
    if (found === false && filter !== "") {
      noResultsMessage.style.display = "block"; // Tampilkan pesan
    } else {
      noResultsMessage.style.display = "none"; // Sembunyikan pesan
    }
  }
  
</script>

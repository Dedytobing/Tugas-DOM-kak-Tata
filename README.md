<p align="center">
 <img width="100px" src="https://raw.githubusercontent.com/Dedytobing/personalWebsite/main/img/logo.png" align="center" alt="GitHub Readme Stats" />
 <h2 align="center">Dedy Kristianto Lumbantobing</h2>
 <p align="center">Front-end Web Develepoment</p>
</p>

# Tugas JS Dasar DOM - Introduction

- [Section 2 - 4 : Masing masing minimal 3 contoh dengan 1 usecase](#section2-4)
  - [Section 2](#section2)
  - [Section 3](#section3)
  - [Section 4](#section4)
- [Section 4-6 : Masing masing minimal 2 contoh dengan 1 usecase](#Section4-6)
  - [Section 4](#section4)
  - [Section 5](#section5)
  - [Section 6](#section6)
- [Section 7-8 : Masing masing minimal 2 contoh dengan 1 usecase](#section7-8)
  - [Section 7](#section7)
  - [Section 8](#section8)

# Section2-4

## Section2

jawaban tertera pada file [Section2.html](https://github.com/Dedytobing/Tugas-DOM-kak-Tata/blob/main/section2.html "Github Dedy")

> HTML

```html
<h1 id="hero">Biodata Saya</h1>
<ul id="menu">
  <li class="bio">Dedy</li>
  <li class="bio">Lumbantobing</li>
  <li class="bio">20 Tahun</li>
  <li class="bio">Pematangsiantar</li>
</ul>

<p>Pilih Merek Motor</p>
<p>
  <label for="motorSupra">
    <input type="radio" name="rate" value="Honda" id="honda" /> Honda
  </label>
  <label for="motorYamaha">
    <input type="radio" name="rate" value="Yamaha" id="yamaha" /> Yamaha
  </label>
  <label for="motorSuzuki">
    <input type="radio" name="rate" value="Suzuki" id="suzuki" /> Suzuki
  </label>
</p>
<p>
  <button id="btnRate">Submit</button>
</p>
<p id="output"></p>
```

> JavaScript

```javascript
<script>
      // GET ELEMENT BY ID
      const h1 = document.getElementById("hero");
      console.log(h1);

      // GET ELEMENT BY NAME
      let btn = document.getElementById("btnRate");
      let output = document.getElementById("output");

      btn.addEventListener("click", () => {
        let rates = document.getElementsByName("rate");
        rates.forEach((rate) => {
          if (rate.checked) {
            output.innerText = `Motor Kamu adalah ${rate.value}`;
          }
        });
      });

      // GET ELEMENT BY CLASS NAME
      let menu = document.getElementById("menu");
      let items = menu.getElementsByClassName("bio");
      let data = [].map.call(items, (item) => item.textContent);
      console.log(data);

      // JavaScript querySelector
      var judul = document.querySelector("#hero");
      judul.textContent = "Mengisi Biodata";
      judul.classList.add("Dedy");
    </script>
```

## Section3

jawaban tertera pada file [Section3.html](https://github.com/Dedytobing/Tugas-DOM-kak-Tata/blob/main/section3.html "Github Dedy")

> HTML

```html
<div id="main">
  <p class="note">Nama Saya Adalah Dedy Lumbantobing</p>
  <ul id="menu">
    <li class="pertama">Hallo</li>
    <li class="kedua">Nama saya</li>
    <li class="ketiga">Adalah</li>
    <li class="keempat">Dedy Lumbantobing</li>
  </ul>
</div>
```

> JavaScript

```javascript
<script>
      // get the parent element
      let note = document.querySelector(".note");
      console.log(note.parentNode);

      // get child element
      let menu = document.getElementById("menu");
      let children = menu.children;
      console.log(children);

      // get siblings element
      let getSiblings = function (e) {
        // for collecting siblings
        let siblings = [];
        // if no parent, return no sibling
        if (!e.parentNode) {
          return siblings;
        }
        // first child of the parent node
        let sibling = e.parentNode.firstChild;
        // collecting siblings
        while (sibling) {
          if (sibling.nodeType === 1 && sibling !== e) {
            siblings.push(sibling);
          }
          sibling = sibling.nextSibling;
        }
        return siblings;
      };

      let siblings = getSiblings(document.querySelector(".pertama"));
      siblingText = siblings.map((e) => e.innerHTML);
      console.log(siblingText);
    </script>
```

## Section4

jawaban tertera pada file [Section4.html](https://github.com/Dedytobing/Tugas-DOM-kak-Tata/blob/main/section4.html "Github Dedy")

> HTML

```html
<h3>Perkenalan diri</h3>
<ul id="dataDiri"></ul>
<button onclick="spill(); this.style.display = 'none';">Spill Dong!</button>
```

> JavaScript

```javascript
    <script>
      //=== createElement
      function spill() {
        var itemDataBaru = document.createElement("li");
        itemDataBaru.innerHTML = "Hallo,";

        var infoDataBaru = document.createTextNode(
          " Perkenalkan Nama Saya Dedy Kristianto Lumbantobing"
        );
        itemDataBaru.appendChild(infoDataBaru);

        var listData = document.getElementById("dataDiri");
        listData.appendChild(itemDataBaru);
      }
    </script>
```

# Section4-6

Karena sebelumnya sudah ada Section 4 maka untuk ini aku mulai dari section 5

## Section5

jawaban tertera pada file [Section5.html](https://github.com/Dedytobing/Tugas-DOM-kak-Tata/blob/main/section5.html "Github Dedy")

> HTML

```html
<h3 id="judul">Daftar Motor</h3>
<ul id="daftar-motor">
  <li data-motor="Honda">Honda</li>
  <li data-motor="Yamaha">Yamaha</li>
  <li data-motor="Suzuki">Suzuki</li>
</ul>
<br />
<button onclick="tampilkanMotor()">Tampilkan Data Motor</button>
```

> JavaScript

```javascript
    <script>
      function tampilkanMotor() {
        var listMotor = document.getElementById("daftar-motor");

        var itemPertama = document.querySelector("li:nth-child(2)");
        var dataMotor = itemPertama.getAttribute("data-motor");

        alert("Motor kamu adalah : " + dataMotor);

        itemPertama.setAttribute("style", "color: skyblue;");
      }
    </script>
```

## Section6

jawaban tertera pada file [Section6.html](https://github.com/Dedytobing/Tugas-DOM-kak-Tata/blob/main/section6.html "Github Dedy")

> CSS

```css
.warna-biru {
  color: skyblue;
}

.tebal {
  font-weight: bold;
}
```

> HTML

```html
<h3 id="judul">Daftar Motor</h3>
<ul id="daftar-motor">
  <li>Honda</li>
  <li>Yamaha</li>
  <li>Suzuki</li>
</ul>
<br />
<button onclick="ubahTampilan()">Ubah Tampilan</button>
```

> JavaScript

```javascript
	<script>
		function ubahTampilan() {
			var listMotor = document.getElementById("judul");

			// set style property
			listMotor.style.backgroundColor = "lightpink";

			// set class name property
			var itemPertama = document.querySelector("li:nth-child(2)");
			itemPertama.className = "tebal warna-biru";
		}
	</script>
```

# Section7-8

## Section7

jawaban tertera pada file [Section7.html](https://github.com/Dedytobing/Tugas-DOM-kak-Tata/blob/main/section7.html "Github Dedy")

> HTML

```html
<button onclick="alert('Tombol ini Telah di klik')">Alert</button>
<button onclick="tombolAlert()">Alert dengan Function</button>
```

> JavaScript

```javascript
    <script>
      const tombolAlert = () => {
        alert("Tombol dengan function tombolAlert() ini telah di klik");
      };
    </script>
```

## Section8

jawaban tertera pada file [Section8.html](https://github.com/Dedytobing/Tugas-DOM-kak-Tata/blob/main/section8.html "Github Dedy")

> CSS

```css
label {
  display: block;
  margin-bottom: 10px;
}

#log {
  margin-top: 20px;
}
```

> HTML

```html
<h2>Pilihan Jenis Kelamin</h2>
<!-- radio button jenis kelamin -->
<label
  ><input
    type="radio"
    name="gender"
    value="Laki-laki"
    onclick="tambahLog('Kamu berjenis kelamin Laki-laki')"
    checked
  />
  Laki-laki</label
>
<label
  ><input
    type="radio"
    name="gender"
    value="Perempuan"
    onclick="tambahLog('Kamu berjenis kelamin Perempuan')"
  />
  Perempuan</label
>

<h2>Pilihan Bahasa Pemrograman</h2>
<!-- checkbox bahasa pemrograman -->
<label
  ><input
    type="checkbox"
    name="programming"
    value="Javascript"
    onclick="tambahLog('Kamu memilih Javascript')"
  />
  Javascript</label
>
<label
  ><input
    type="checkbox"
    name="programming"
    value="HTML"
    onclick="tambahLog('Kamu memilih HTML')"
  />
  HTML</label
>
<label
  ><input
    type="checkbox"
    name="programming"
    value="CSS"
    onclick="tambahLog('Kamu memilih CSS')"
  />
  CSS</label
>
<div id="log"></div>
```

> JavaScript

```javascript
	<script>
		function tambahLog(teks) {
			var log = document.getElementById("log");
			if (teks.indexOf("Laki-laki") !== -1 || teks.indexOf("Perempuan") !== -1) {
				log.innerHTML = teks + "<br>";
			} else {
				var checkboxes = document.querySelectorAll('input[name="programming"]');
				var checkedCheckboxes = Array.prototype.slice.call(checkboxes).filter(function(checkbox) {
					return checkbox.checked;
				});

				if (checkedCheckboxes.length === 0) {
					log.innerHTML = "";
				} else {
					log.innerHTML += teks + "<br>";
				}
			}
		}
	</script>
```

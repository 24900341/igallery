# Ex.08 Design of Interactive Image Gallery

## Date: 11.05.2025

NAME : MOHAMED NIZAMUDDIN A 

REG NO : 212224040194


## AIM:
To design a web application for an inteactive image gallery with minimum five images.

## DESIGN STEPS:

### Step 1:
Clone the github repository and create Django admin interface.

### Step 2:
Change settings.py file to allow request from all hosts.

### Step 3:
Use CSS for positioning and styling.

### Step 4:
Write JavaScript program for implementing interactivity.

### Step 5:
Validate the HTML and CSS code.

### Step 6:
Publish the website in the given URL.

## PROGRAM :

```
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>CSK Interactive Gallery</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background-image: url('cskbgm.jpg');
      background-size: cover;
      background-repeat: no-repeat;
      background-attachment: fixed;
      text-align: center;
    }

    h1 {
      color: #eebd00;
      background-color: #002147;
      padding: 20px;
    }

    .gallery {
      display: flex;
      justify-content: center;
      flex-wrap: wrap;
      gap: 20px;
      padding: 30px;
    }

    .gallery img {
      width: 250px;
      height: 160px;
      border: 4px solid #eebd00;
      border-radius: 10px;
      cursor: pointer;
      transition: transform 0.3s;
    }

    .gallery img:hover {
      transform: scale(1.05);
    }

    .squad {
      margin-top: 20px;
      padding: 15px;
      border: 2px solid #002147;
      background-color: #ffffff;
      width: 60%;
      margin: auto;
      display: none;
    }
  </style>
</head>
<body>

  <h1>🏏 Chennai Super Kings Interactive Gallery 🏆</h1>

  <div class="gallery">
    <img src="s2.jpg" alt="CSK 2010" onclick="showSquad(2010)">
    <img src="s3.jpg" alt="CSK 2011" onclick="showSquad(2011)">
    <img src="s1.jpg" alt="CSK 2018" onclick="showSquad(2018)">
    <img src="s4.jpg" alt="CSK 2021" onclick="showSquad(2021)">
    <img src="s5.jpg" alt="CSK 2023" onclick="showSquad(2023)">
  </div>

  <div id="squadBox" class="squad"></div>

  <script>
    const squads = {
      2010: "<h1>CSK 2010 Squad</h1><h3>Mahendra Singh Dhoni (captain)</h3><br><h3>Matthew Hayden</h3><br><h3>Mike Hussey</h3><br><h3>Jacob Oram</h3><br><h3>Suresh Raina</h3><br><h3>Muttiah Muralitharan</h3><br><h3>Albie Morkel</h3><br><h3>Makhaya Ntini</h3><br><h3>Parthiv Patel</h3><br><h3>Thissira Perrera</h3><br><h3>George Bailey</h3><br><h3>S Badinath</h3><br><h3>Murali Vijay</h3><br><h3>Hemang Badani</h3><br><h3>Justin Kemp</h3><br><h3>Sudeep Tyagi</h3><br><h3>Thilan Tushara</h3><br><h3>R Ashwin</h3><br><h3>Arun Karthik</h3><br><h3>C Ganapathy</h3><br><h3>MS Gony</h3><br><h3>Lakshmipathy Balaji</h3><br><h3>S Jakat</h3><br>",
      2011: "<h1>CSK 2011 Squad</h1><h3>Mahendra Singh Dhoni (C)</h3><br><h3>Matthew Hayden</h3><br><h3>Mike Hussey</h3><br><h3>Jacob Oram</h3><br><h3>Suresh Raina</h3><br><h3>Muttiah Muralitharan</h3><br><h3>Albie Morkel</h3><br><h3>Makhaya Ntini</h3><br><h3>Parthiv Patel</h3><br><h3>Thissira Perrera</h3><br><h3>George Bailey</h3><br><h3>S Badinath</h3><br><h3>Murali Vijay</h3><br><h3>Hemang Badani</h3><br><h3>Justin Kemp</h3><br><h3>Sudeep Tyagi</h3><br><h3>Thilan Tushara</h3><br><h3>R Ashwin</h3><br><h3>Arun Karthik</h3><br><h3>C Ganapathy</h3><br><h3>MS Gony</h3><br><h3>Lakshmipathy Balaji</h3><br><h3>S Jakat</h3><br>",
      2018: "<h1>CSK 2018 Squad</h1><h3>MS Dhoni (C)</h3><br><h3>Dwayne Bravo</h3><br><h3>Suresh Raina</h3><br><h3>Faf du Plessis</h3><br><h3>Karn Sharma</h3><br><h3>Shane Watson</h3><br><h3>Shardul Thakur</h3><br><h3>Ambati Rayudu</h3><br><h3>Murali Vijay</h3><br><h3>Harbhajan Singh</h3><br><h3>Faf du Plessis</h3><br><h3>Mark Wood</h3><br><h3>Sam Billings</h3><br><h3>Imran Tahir</h3><br><h3>Deepak Chahar</h3><br><h3>Mitchell Santner</h3><br><h3>Lungi Ngidi</h3><br><h3>KM Asif</h3><br><h3>Narayan Jagadeesan</h3><br><h3>Kanishk Seth</h3><br><h3>Monu Singh</h3><br><h3>Dhruv Shorey</h3><br><h3>Kshitiz Sharma</h3><br><h3>Chaitanya Bishnoi</h3><br>",
      2021: "<h1>CSK 2021 Squad</h1><h3>MS Dhoni</h3><br><h3>Suresh Raina</h3><br><h3>Ruturaj Gaikwad</h3><br><h3>Ravindra Jadeja</h3><br><h3>Faf du Plessis</h3><br><h3>Ambati Rayudu</h3><br><h3>Robin Uthappa</h3><br><h3>Narayan Jagadeesan</h3><br><h3>Dwayne Bravo</h3><br><h3>Sam Curran</h3><br><h3>Moeen Ali</h3><br><h3>Karn Sharma</h3><br><h3>Ravisrinivasan Sai Kishore</h3><br><h3>Mitchell Santner</h3><br><h3>Imran Tahir</h3><br><h3>Deepak Chahar</h3><br><h3>Shardul Thakur</h3><br><h3>Lungi Ngidi</h3><br><h3>Josh Hazlewood</h3><br><h3>KM Asif</h3><br><h3>Ravichandran Ashwin</h3><br>",
      2023: "<h1>CSK 2023 Squad</h1><h3>MS Dhoni (c)</h3><br><h3>Devon Conway</h3><br><h3>Ruturaj Gaikwad</h3><br><h3>Ambati Rayudu</h3><br><h3>Subhranshu Senapati</h3><br><h3>Moeen Ali</h3><br><h3>Shivam Dube</h3><br><h3>Rajvardhan Hangargekar</h3><br><h3>Dwaine Pretorius</h3><br><h3>Mitchell Santner</h3><br><h3>Ravindra Jadeja</h3><br><h3>Tushar Deshpande</h3><br><h3>Akash Singh</h3><br><h3>Matheesha Pathirana</h3><br><h3>Simarjeet Singh</h3><br><h3>Deepak Chahar</h3><br><h3>Prashant Solanki</h3><br><h3>Maheesh Theekshana</h3><br><h3>Ajinkya Rahane</h3><br><h3>Ben Stokes</h3><br><h3>Shaik Rasheed</h3><br><h3>Nishant Sindhu</h3><br><h3>Sisanda Magala</h3><br><h3>Ajay Mandal</h3><br><h3>Bhagath Varma</h3><br>",
    };

    function showSquad(year) {
      const box = document.getElementById("squadBox");
      box.innerHTML = <h3>${squads[year]}</h3>;
      box.style.display = "block";
    }
  </script>

</body>
</html>

```


## OUTPUT:

![csk background](https://github.com/user-attachments/assets/39361a0d-91bf-42e8-afb0-396e2c06ee5b)

![csk2010](https://github.com/user-attachments/assets/736a0b9b-1c8d-40e0-9999-d74e85b957f7)

![csl2011](https://github.com/user-attachments/assets/8e4c97df-5a2a-4d3d-baac-c4963c0e374f)

![csk2018](https://github.com/user-attachments/assets/f0301853-a725-43ad-815d-ce006fa321c8)


![csk 2021](https://github.com/user-attachments/assets/9d0bd4f6-d7a6-48a6-863a-050e24e099f0)

![csk 2023](https://github.com/user-attachments/assets/17effa96-27ba-47a5-99d5-a7fadd0c72d6)

## RESULT:
The program for designing an interactive image gallery using HTML, CSS and JavaScript is executed successfully.

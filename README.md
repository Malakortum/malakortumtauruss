<!DOCTYPE html>
<html lang="th">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>ข่าวทั้งหมด | แจ้งภัยพิบัติ</title>
  <script src="https://cdn.tailwindcss.com"></script>
  <link href="https://fonts.googleapis.com/css2?family=Prompt&display=swap" rel="stylesheet">
  <style>
    body {
      font-family: 'Prompt', sans-serif;
    }

    .thumbnail-custom {
      width: 120px;
      height: 120px;
      font-size: 14px;
      border-radius: 50%;
    }
  </style>
</head>
<body class="bg-white text-gray-900 flex flex-col min-h-screen pb-20 mb-24">

  <!-- แถบค้นหา -->
  <div class="bg-gradient-to-r from-red-700 via-black to-red-800 p-4 flex items-center">
    <form action="search.html" method="GET" class="flex items-center w-full">
      <input 
        type="text" 
        name="query"
        placeholder="ค้นหาข่าว..." 
        class="flex-1 px-4 py-2 rounded-md text-black focus:outline-none focus:ring-2 focus:ring-red-600"
      />
      <button type="submit" class="ml-2 text-white text-xl hover:scale-110 transition-transform">🔍</button>
    </form>
  </div>

  <!-- ข่าวด่วน -->
  <div class="p-4 flex items-center space-x-4 bg-gradient-to-r from-white via-red-50 to-white shadow-md rounded-lg mx-4 mt-4">
    <img src="https://us-fbcloud.net/wb/data/1516/1516834-img.wdbnxk.w9hf.opsb1k4i.webp" alt="ด่วน" class="rounded-lg w-24 h-24 object-cover border-4 border-red-400" loading="lazy">
    <div>
      <h2 class="text-red-700 text-xl font-bold mb-1 animate-pulse">ด่วน</h2>
      <p class="text-sm text-gray-800">ง่วง<br>นอนไหม ไม่นอน อนน</p>
      <a href="#" class="inline-block mt-2 bg-red-600 text-white px-3 py-1 rounded-full text-sm hover:bg-red-700 transition-colors">แนวทางปฏิบัติ</a>
    </div>
  </div>

  <!-- หมวดหมู่ข่าว -->
  <div class="grid grid-cols-3 gap-6 px-4 py-6">
    <!-- Card Template -->
    <!-- ใส่พื้นหลังแบบไล่สีและเงา -->
    <template id="category-card">
      <a href="#" class="flex flex-col items-center text-center bg-gradient-to-br from-white to-gray-100 p-3 rounded-xl shadow hover:shadow-lg transform hover:-translate-y-1 transition-all">
        <img src="" class="thumbnail-custom object-cover border-2 border-brown-500" loading="lazy">
        <span class="mt-2 text-sm text-brown-700 font-semibold"></span>
      </a>
    </template>
  </div>

  <!-- ใช้ JS เติมการ์ดแบบไดนามิก -->
  <script>
    const categories = [
      { name: "การเมือง", href: "category-politics.html", img: "https://s.isanook.com/ns/0/ud/1953/9769358/new-thumbnail1200x720(5)(4).jpg" },
      { name: "เศรษฐกิจ", href: "category-economy.html", img: "https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTWbeTIuINwwhZGaobit6Ygnb8Wz6S0CTRCqg&s" },
      { name: "สังคม", href: "category-society.html", img: "https://cdni-hw.ch7.com/dm/sz-md/i/images/2024/12/09/67564b66a6b291.76457958.jpg" },
      { name: "กีฬา", href: "category-sport.html", img: "https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRWqI0OYqDfMJtY7_OQjD8cqZpw07-Ra7x_yg&s" },
      { name: "บันเทิง", href: "category-entertainment.html", img: "https://static.kpopping.com/33/1/240505-RIIZE-FAN-CON-RIIZING-DAY-in-SEOUL-Day-2-WONBIN-documents-4.jpeg" },
      { name: "สิ่งแวดล้อม", href: "category-environment.html", img: "https://arit.kpru.ac.th//contents/phubet/IMG/E-Calendar/International_day/03/03-21-2.webp" },
      { name: "ต่างประเทศ", href: "category-world.html", img: "https://img.pptvhd36.com/thumbor/2025/03/31/news-762d7dc.jpg" },
      { name: "วิทยาศาสตร์และเทคโนโลยี", href: "category-science.html", img: "https://i.redd.it/pv1wdfrnyjs91.jpg" },
      { name: "ทั่วไทย", href: "category-thailand.html", img: "https://img.pptvhd36.com/thumbor/2025/03/06/news-6ae96ff.jpg" }
    ];
    const container = document.querySelector(".grid");
    const template = document.getElementById("category-card").content;
    categories.forEach(cat => {
      const card = template.cloneNode(true);
      card.querySelector("a").href = cat.href;
      card.querySelector("img").src = cat.img;
      card.querySelector("span").textContent = cat.name;
      container.appendChild(card);
    });
  </script>

  <!-- แถบเมนูด้านล่าง -->
  <div class="fixed bottom-0 left-0 right-0 bg-gradient-to-r from-brown-600 to-black text-white flex justify-around items-center p-2 border-t z-10">
    <a href="login.html" class="flex flex-col items-center text-xs hover:text-red-300">
      <img src="https://icons.veryicon.com/png/o/miscellaneous/test-5/icon-my-page.png" class="w-8 h-8 mb-1" alt="บัญชี" loading="lazy"/>
      <span>บัญชี</span>
    </a>
    <a href="index.html" class="flex flex-col items-center text-xs hover:text-red-300">
      <img src="https://cdn-icons-png.flaticon.com/512/44/44907.png" class="w-8 h-8 mb-1" alt="โฮม" loading="lazy"/>
      <span>โฮม</span>
    </a>
    <a href="notifications.html" class="flex flex-col items-center text-xs hover:text-red-300">
      <img src="https://icon-library.com/images/notification-icon/notification-icon-3.jpg" class="w-8 h-8 mb-1" alt="แจ้งเตือน" loading="lazy"/>
      <span>แจ้งเตือน</span>
    </a>
  </div>

</body>
</html>

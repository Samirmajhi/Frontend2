<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Simple Nav + Table</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      margin: 0;
      padding: 0;
    }
    nav {
      background-color: #0077cc;
      padding: 10px;
      color: white;
      display: flex;
      gap: 20px;
    }
    .dropdown {
      position: relative;
    }
    .dropdown-content {
      display: none;
      position: absolute;
      background-color: white;
      color: black;
      box-shadow: 0px 4px 8px rgba(0,0,0,0.1);
      min-width: 150px;
      z-index: 1;
    }
    .dropdown:hover .dropdown-content {
      display: block;
    }
    .dropdown-content div {
      padding: 10px;
      cursor: pointer;
    }
    .dropdown-content div:hover {
      background-color: #f0f0f0;
    }
    #table-section {
      padding: 20px;
      display: none;
    }
    table {
      border-collapse: collapse;
      width: 100%;
    }
    th, td {
      border: 1px solid #ccc;
      padding: 8px;
    }
    #filter-input {
      margin-bottom: 10px;
      padding: 5px;
      width: 200px;
    }
  </style>
</head>
<body>

  <nav>
    <div>Home</div>
    <div>About</div>
    <div class="dropdown">
      <div>Dropdown1</div>
      <div class="dropdown-content">
        <div onclick="showTable('Item A1')">Item A1</div>
        <div onclick="showTable('Item A2')">Item A2</div>
      </div>
    </div>
    <div class="dropdown">
      <div>Dropdown2</div>
      <div class="dropdown-content">
        <div onclick="showTable('Item B1')">Item B1</div>
        <div onclick="showTable('Item B2')">Item B2</div>
      </div>
    </div>
    <div>Contact</div>
  </nav>

  <div id="table-section">
    <input type="text" id="filter-input" placeholder="Filter items..." onkeyup="filterTable()">
    <table id="data-table">
      <thead>
        <tr>
          <th>Name</th>
          <th>Value</th>
        </tr>
      </thead>
      <tbody id="table-body">
        <!-- Rows will be injected here -->
      </tbody>
    </table>
  </div>

  <script>
    const itemsMap = {
      'Item A1': [
        { name: 'Apple', value: 10 },
        { name: 'Avocado', value: 15 },
        { name: 'Apricot', value: 20 },
        { name: 'Artichoke', value: 12 },
        { name: 'Asparagus', value: 18 }
      ],
      'Item A2': [
        { name: 'Ant', value: 3 },
        { name: 'Ape', value: 7 },
        { name: 'Alligator', value: 9 },
        { name: 'Anaconda', value: 6 },
        { name: 'Alpaca', value: 11 }
      ],
      'Item B1': [
        { name: 'Ball', value: 5 },
        { name: 'Bat', value: 6 },
        { name: 'Bag', value: 9 },
        { name: 'Book', value: 12 },
        { name: 'Bottle', value: 15 }
      ],
      'Item B2': [
        { name: 'Boat', value: 13 },
        { name: 'Bus', value: 14 },
        { name: 'Bike', value: 11 },
        { name: 'Balloon', value: 10 },
        { name: 'Bin', value: 8 }
      ]
    };

    function showTable(itemKey) {
      const data = itemsMap[itemKey] || [];
      const tbody = document.getElementById('table-body');
      const section = document.getElementById('table-section');
      tbody.innerHTML = '';
      data.forEach(row => {
        const tr = document.createElement('tr');
        tr.innerHTML = `<td>${row.name}</td><td>${row.value}</td>`;
        tbody.appendChild(tr);
      });
      section.style.display = 'block';
    }

    function filterTable() {
      const input = document.getElementById("filter-input").value.toLowerCase();
      const rows = document.querySelectorAll("#table-body tr");
      rows.forEach(row => {
        const text = row.textContent.toLowerCase();
        row.style.display = text.includes(input) ? "" : "none";
      });
    }
  </script>

</body>
</html>

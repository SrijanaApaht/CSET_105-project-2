<!DOCTYPE html>
<head>
    <style>
        ul {
            list-style-type: none;
        }
        li {
            cursor: pointer;
        }
        .completed {
            text-decoration: line-through;
        }
    </style>
    <title>Grocery List Manager</title>
</head>
<body>
    <h1>Grocery List Manager</h1>
    <input type="text" id="newItem" placeholder="Add a new item">
    <button onclick="addItem()">Add</button>
    <button onclick="showAllItems()">Show All Items</button>
    <button onclick="showUnpurchasedItems()">Show Unpurchased Items</button>
    <button onclick="showPurchasedItems()">Show Purchased Items</button>
    <ul id="groceryList">
    </ul>

    <script>
        const groceryList = document.getElementById('groceryList');
        const newItemInput = document.getElementById('newItem');
        let items = [];

        function addItem() {
            const newItemText = newItemInput.value.trim();
            if (newItemText !== '') {
                items.push({ text: newItemText, purchased: false });
                updateList();
                newItemInput.value = '';
            }
        }

        function toggleItem(index) {
            items[index].purchased = !items[index].purchased;
            updateList();
        }

        function showAllItems() {
            updateList();
        }

        function showUnpurchasedItems() {
            const unpurchasedItems = items.filter(item => !item.purchased);
            displayItems(unpurchasedItems);
        }

        function showPurchasedItems() {
            const purchasedItems = items.filter(item => item.purchased);
            displayItems(purchasedItems);
        }

        function displayItems(displayItems) {
            groceryList.innerHTML = '';
            displayItems.forEach((item, index) => {
                const li = document.createElement('li');
                li.textContent = item.text;
                li.className = item.purchased ? 'completed' : '';
                li.onclick = () => toggleItem(index);
                groceryList.appendChild(li);
            });
        }

        function updateList() {
            displayItems(items);
        }

        updateList();
    </script>
</body>
</html>

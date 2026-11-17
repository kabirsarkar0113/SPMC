<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Shakipio Massage Company</title>

<style>
* {
    box-sizing: border-box;
}

body {
    margin: 0;
    font-family: Arial, sans-serif;
    background: #fff4a8;
    color: #353323;
}

header {
    padding: 22px;
    text-align: center;
    background: #ffe36e;
    font-size: 24px;
    font-weight: bold;
}

.page {
    display: none;
    min-height: 75vh;
    padding: 45px 20px;
    justify-content: center;
    align-items: center;
}

.page.active {
    display: flex;
}

.container {
    width: 100%;
    max-width: 650px;
    padding: 30px;
    background: #fffdf2;
    border-radius: 18px;
    box-shadow: 0 5px 20px #b7a64b33;
}

.home-content {
    text-align: center;
}

.hero-title {
    font-size: 42px;
    line-height: 1.3;
}

.chick {
    font-size: 125px;
    background: #fff9dc;
    padding: 25px;
    border-radius: 50%;
    display: inline-block;
    margin: 25px 0;
}

h2 {
    text-align: center;
}

.massage-option {
    display: flex;
    align-items: center;
    gap: 12px;
    margin: 17px 0;
}

.massage-option input {
    width: 19px;
    height: 19px;
    accent-color: #d5aa00;
}

.massage-option label {
    font-size: 17px;
}

button {
    background: #e5b900;
    color: #29250e;
    border: none;
    padding: 14px 25px;
    margin-top: 20px;
    border-radius: 8px;
    font-size: 16px;
    font-weight: bold;
    cursor: pointer;
}

button:hover {
    background: #d5aa00;
}

.button-row {
    display: flex;
    justify-content: space-between;
    flex-wrap: wrap;
    gap: 10px;
}

input[type="range"] {
    width: 100%;
    accent-color: #d5aa00;
    margin: 25px 0;
}

.duration-display {
    text-align: center;
    font-size: 26px;
    font-weight: bold;
}

#result {
    text-align: center;
    font-size: 25px;
    font-weight: bold;
    margin-top: 20px;
}

table {
    width: 100%;
    border-collapse: collapse;
    margin-top: 20px;
}

th, td {
    padding: 12px 6px;
    border-bottom: 1px solid #e6dcac;
    text-align: left;
    font-size: 14px;
}

th {
    background: #ffeaa0;
}

footer {
    text-align: center;
    padding: 20px;
    background: #ffe36e;
}

@media(max-width: 600px) {
    .hero-title {
        font-size: 32px;
    }

    .container {
        padding: 20px;
    }

    .button-row {
        justify-content: center;
    }
}
</style>
</head>

<body>

<header>
    🐥 Shakipio Massage Company
</header>

<!-- PAGE 1: HOME -->

<section class="page active" id="home">

    <div class="container home-content">

        <h1 class="hero-title">
            Relax. Refresh. Rejuvenate.
        </h1>

        <div class="chick" role="img" aria-label="Cute yellow chick">
            🐥
        </div>

        <br>

        <button onclick="showPage('selection')">
            Get Started →
        </button>

    </div>

</section>


<!-- PAGE 2: MASSAGE SELECTION -->

<section class="page" id="selection">

    <div class="container">

        <h2>Select Your Massage</h2>

        <p>Choose a maximum of two massages per session.</p>

        <div id="massageOptions">

            <div class="massage-option">
                <input type="checkbox" value="Head Massage">
                <label>Head Massage</label>
            </div>

            <div class="massage-option">
                <input type="checkbox" value="Leg Massage">
                <label>Leg Massage</label>
            </div>

            <div class="massage-option">
                <input type="checkbox" value="Hand Massage">
                <label>Hand Massage</label>
            </div>

            <div class="massage-option">
                <input type="checkbox" value="Arm Massage">
                <label>Arm Massage</label>
            </div>

            <div class="massage-option">
                <input type="checkbox" value="Foot Massage">
                <label>Foot Massage</label>
            </div>

            <div class="massage-option">
                <input type="checkbox" value="Shoulder Massage">
                <label>Shoulder Massage</label>
            </div>

            <div class="massage-option">
                <input type="checkbox" value="Back Massage">
                <label>Back Massage</label>
            </div>

            <div class="massage-option">
                <input type="checkbox" value="Full Body Massage">
                <label>Full Body Massage</label>
            </div>

        </div>

        <p id="selectionMessage">0 of 2 selected.</p>

        <div class="button-row">
            <button onclick="showPage('home')">← Back</button>
            <button onclick="continueBooking()">Continue →</button>
        </div>

    </div>

</section>


<!-- PAGE 3: DURATION -->

<section class="page" id="duration">

    <div class="container">

        <h2>Choose Your Duration</h2>

        <p>Select the number of minutes for each selected massage.</p>

        <input
            type="range"
            id="minutes"
            min="1"
            max="15"
            value="5"
            step="1"
        >

        <div class="duration-display">
            <span id="minuteValue">5</span> Minutes
        </div>

        <p style="text-align:center">
            Rate: ₹5 per minute, per massage.
        </p>

        <div class="button-row">
            <button onclick="showPage('selection')">← Back</button>
            <button onclick="calculatePrice()">Calculate Price</button>
        </div>

        <div id="result"></div>

        <div style="text-align:center">
            <button id="confirmButton"
                onclick="confirmBooking()"
                style="display:none">
                Confirm Booking →
            </button>
        </div>

    </div>

</section>


<!-- PAGE 4: BOOKING CONFIRMATION -->

<section class="page" id="confirmation">

    <div class="container home-content">

        <h2>Booking Confirmed!</h2>

        <div class="chick">🐥</div>

        <p id="confirmationDetails"></p>

        <button onclick="showPage('history')">
            View Transaction History
        </button>

        <br>

        <button onclick="newBooking()">
            Book Another Massage
        </button>

    </div>

</section>


<!-- PAGE 5: TRANSACTION HISTORY -->

<section class="page" id="history">

    <div class="container">

        <h2>Transaction History</h2>

        <table>
            <thead>
                <tr>
                    <th>Massage</th>
                    <th>Minutes</th>
                    <th>Amount</th>
                </tr>
            </thead>

            <tbody id="transactionList"></tbody>
        </table>

        <h3 id="totalAmount">Total Revenue: ₹0</h3>

        <div class="button-row">
            <button onclick="showPage('home')">Home</button>
            <button onclick="clearHistory()">Clear History</button>
        </div>

    </div>

</section>


<footer>
    🐥 Shakipio Massage Company
</footer>


<script>

const RATE = 5;

let currentPrice = 0;
let selectedMassages = [];

let transactions = [];

try {
    const saved = JSON.parse(
        localStorage.getItem("massageTransactions") || "[]"
    );

    transactions = Array.isArray(saved) ? saved : [];

} catch (error) {
    console.error("Could not load transaction history:", error);
    transactions = [];
}


// PAGE NAVIGATION

function showPage(pageId) {

    document.querySelectorAll(".page").forEach(page => {
        page.classList.remove("active");
    });

    document.getElementById(pageId).classList.add("active");

    window.scrollTo({
        top: 0,
        behavior: "smooth"
    });

    if (pageId === "history") {
        displayTransactions();
    }
}


// MASSAGE SELECTION

const checkboxes = document.querySelectorAll(
    '#massageOptions input[type="checkbox"]'
);

checkboxes.forEach(box => {

    box.addEventListener("change", function() {

        const selected = Array.from(checkboxes)
            .filter(item => item.checked);

        if (selected.length > 2) {
            box.checked = false;
            alert("Maximum two massages allowed.");
        }

        const count = Array.from(checkboxes)
            .filter(item => item.checked).length;

        document.getElementById("selectionMessage").innerText =
            count + " of 2 selected.";

        currentPrice = 0;
        document.getElementById("result").innerText = "";
        document.getElementById("confirmButton").style.display = "none";

    });

});


// CONTINUE TO DURATION

function continueBooking() {

    selectedMassages = Array.from(checkboxes)
        .filter(item => item.checked)
        .map(item => item.value);

    if (selectedMassages.length === 0) {
        alert("Please select at least one massage.");
        return;
    }

    currentPrice = 0;
    document.getElementById("result").innerText = "";
    document.getElementById("confirmButton").style.display = "none";

    showPage("duration");

    console.log("Selected massages:", selectedMassages);
}


// SLIDER

const slider = document.getElementById("minutes");

slider.addEventListener("input", function() {

    document.getElementById("minuteValue").innerText = slider.value;

    currentPrice = 0;
    document.getElementById("result").innerText = "";
    document.getElementById("confirmButton").style.display = "none";

});


// CALCULATE PRICE

function calculatePrice() {

    const minutes = Number(slider.value);

    currentPrice = minutes * RATE * selectedMassages.length;

    document.getElementById("result").innerText =
        "Your Total: ₹" + currentPrice;

    document.getElementById("confirmButton").style.display =
        "inline-block";

    console.log("Duration:", minutes);
    console.log("Price:", currentPrice);

}


// CONFIRM BOOKING

function confirmBooking() {

    const minutes = Number(slider.value);

    if (
        selectedMassages.length < 1 ||
        selectedMassages.length > 2 ||
        !Number.isInteger(minutes) ||
        minutes < 1 ||
        minutes > 15 ||
        currentPrice !== minutes * RATE * selectedMassages.length
    ) {
        alert("Please calculate your price again.");
        return;
    }

    const transaction = {

        massage: selectedMassages.join(" + "),
        minutes: minutes,
        amount: currentPrice,
        date: new Date().toLocaleString("en-IN")

    };

    transactions.push(transaction);

    try {
        localStorage.setItem(
            "massageTransactions",
            JSON.stringify(transactions)
        );
    } catch (error) {
        transactions.pop();
        console.error("Could not save transaction:", error);
        alert("Booking could not be saved. Please check browser storage.");
        return;
    }

    console.log("NEW TRANSACTION:", transaction);
    console.table(transactions);

    document.getElementById("confirmationDetails").innerText =
        "Massage: " + transaction.massage +
        " | Duration: " + minutes + " minutes per massage" +
        " | Total: ₹" + currentPrice;

    displayTransactions();

    showPage("confirmation");

}


// NEW BOOKING

function newBooking() {

    checkboxes.forEach(item => item.checked = false);

    selectedMassages = [];
    currentPrice = 0;

    document.getElementById("selectionMessage").innerText =
        "0 of 2 selected.";

    slider.value = 5;
    document.getElementById("minuteValue").innerText = "5";

    document.getElementById("result").innerText = "";
    document.getElementById("confirmButton").style.display = "none";

    showPage("home");

}


// TRANSACTION HISTORY

function displayTransactions() {

    const list = document.getElementById("transactionList");

    list.innerHTML = "";

    let total = 0;

    transactions.forEach(item => {

        total += Number(item.amount);

        const row = document.createElement("tr");

        [
            item.massage,
            item.minutes,
            "₹" + item.amount
        ].forEach(value => {

            const cell = document.createElement("td");
            cell.textContent = value;
            row.appendChild(cell);

        });

        list.appendChild(row);

    });

    document.getElementById("totalAmount").innerText =
        "Total Revenue: ₹" + total;

}


// CLEAR HISTORY

function clearHistory() {

    if (!confirm("Clear all transaction history?")) {
        return;
    }

    try {
        localStorage.removeItem("massageTransactions");
        transactions = [];
        displayTransactions();
        console.log("Transaction history cleared.");

    } catch (error) {
        console.error("Could not clear history:", error);
        alert("Unable to clear transaction history.");
    }

}


// INITIALISE WEBSITE

displayTransactions();

console.log("Shakipio Massage Company is ready!");
console.log("Rate: ₹5 per minute per massage.");

</script>

</body>
</html>

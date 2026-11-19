# Shakipio Massage Company

A responsive, single-page massage booking website built with HTML, CSS, and JavaScript. The project demonstrates a complete browser-based booking workflow, persistent transaction management with `localStorage`, and two iterations with increasingly refined functionality.

## Massage App V1

**File:** [`Massage.html`](Massage.html)

The first version provides the core massage booking experience:

- Offers seven massage types: Head, Leg, Hand, Arm, Foot, Shoulder, and Back.
- Allows one or two massage selections per booking session.
- Includes a duration slider with options from 2 to 14 minutes in 2-minute increments.
- Uses a fixed rate of ₹5 per minute for each selected massage.
- Calculates the total price dynamically based on the selected duration and number of massages.
- Saves confirmed bookings in the browser with `localStorage`.
- Displays transaction history, individual booking details, dates, and total revenue.
- Provides a payment action that clears transaction history when revenue exceeds ₹100.
- Uses a responsive, mobile-friendly interface with keyboard-visible focus states.

## Massage App V2

**File:** [`Massage_v2.html`](Massage_v2.html)

The second version improves the booking and payment experience while preserving the V1 workflow:

- Maintains the seven available massage options and the two-massage limit.
- Refines the duration slider to 2–7 minutes in 1-minute increments.
- Updates pricing to ₹6 per minute for each selected massage.
- Shows separate duration summaries for minutes per massage and combined total minutes.
- Uses a shared multi-massage calculation so a combined booking is priced accurately.
- Adds a dedicated home-page transaction history action.
- Introduces permanent payment receipts saved independently from active bookings.
- Stores active bookings and past payments in separate `localStorage` values.
- Automatically creates a receipt containing the paid items, combined duration, amount, date, and receipt number.
- Clears transaction history after a successful payment while retaining the receipt in “Past Payments.”
- Adds clearer success, validation, storage, and payment-limit feedback.

## Pricing and Payment Rules

- V1 price: duration × ₹5 × number of selected massages.
- V2 price: duration × ₹6 × number of selected massages.
- The duration entered applies to each selected massage.
- V1 and V2 only clear active transaction history through the **Pay** action when the total exceeds ₹100.
- V2 permanently saves each eligible payment as a receipt.
- Booking and payment records remain in the browser after refresh until storage is cleared or, for V2, the payment data is intentionally retained after clearing transaction history.

## Technologies

- HTML5
- CSS3
- Vanilla JavaScript
- Browser `localStorage`

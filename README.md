# JORR Toll Gate Automatic Toll System
This project simulates an automated toll gate system for the Jakarta Outer Ring Road (JORR) in Indonesia. It allows users to select entry and exit toll gates, calculates the shortest route and distance, determines the toll fare based on vehicle class and distance, and offers various payment methods.

# Table of Contents
Features

How it Works

Installation

Usage

System Architecture (Kamus)

Flow Diagram

Contribution

License

Features
Toll Gate Management: A predefined list of JORR toll gates.

Route Calculation: Finds the shortest path between entry and exit toll gates using a graph-based approach (DFS).

Distance Calculation: Calculates the total distance for the chosen route.

Dynamic Fare Calculation: Determines toll fare based on vehicle class (Golongan) and traveled distance, with a base rate for the first 10 km and an additional charge per km thereafter.

Multiple Payment Options:

E-Toll Card: Primary payment method, checking for sufficient balance.

QRIS: Alternative payment via QR code simulation.

Virtual Account: Alternative payment via bank virtual account simulation.

Transaction Receipt: Prints a detailed receipt upon successful payment, including route, distance, fare, and remaining balance (if paid with e-toll).

Interactive User Interface: Command-line interface guides the user through the toll payment process.

How it Works
The system operates by:

Gathering User Input: The user specifies their entry and exit toll gates and vehicle type.

Route Mapping: It uses a predefined graph of toll gate connections and distances to find possible routes.

Shortest Path Determination: The find_paths_via_neighbors function (which utilizes dfs_path) identifies the shortest available path between the selected gates.

Fare Calculation: Based on the chosen route's distance and the vehicle's golongan (class), the hitung_tarif function calculates the total fare.

Payment Processing:

The system first prompts for an e-toll card balance.

If the e-toll balance is insufficient, it offers alternative payment methods: QRIS or Virtual Account.

Each alternative payment method simulates a transaction and asks for user confirmation of success.

Gate Operation: Upon successful payment, an "OPEN TOLL GATE" message is displayed, and a receipt is printed. If payment fails or is insufficient, the "CLOSED TOLL GATE" message remains.

Simulation of Passage: The system asks for confirmation that the vehicle has passed, then closes the gate for the next transaction.

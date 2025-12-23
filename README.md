<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Fence Installation Cost Calculator - AED</title>
    <style>
        :root {
            --primary-color: #2c3e50;
            --secondary-color: #3498db;
            --accent-color: #e74c3c;
            --light-color: #ecf0f1;
            --dark-color: #34495e;
            --success-color: #2ecc71;
            --uae-green: #008753;
            --uae-red: #ce1126;
            --uae-black: #000000;
            --uae-white: #FFFFFF;
        }
        
        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        /* Password Protection Styles */
        #password-protection {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(135deg, var(--uae-green) 0%, var(--uae-red) 100%);
            display: flex;
            justify-content: center;
            align-items: center;
            z-index: 9999;
            color: white;
        }
        
        .password-box {
            background: white;
            padding: 40px;
            border-radius: 15px;
            box-shadow: 0 20px 40px rgba(0,0,0,0.3);
            text-align: center;
            color: var(--dark-color);
            max-width: 450px;
            width: 90%;
        }
        
        .password-box h2 {
            margin-bottom: 15px;
            color: var(--uae-green);
            font-size: 28px;
        }
        
        .password-box p {
            margin-bottom: 25px;
            font-size: 16px;
            opacity: 0.8;
        }
        
        .password-input {
            width: 100%;
            padding: 15px;
            margin: 20px 0;
            border: 2px solid #ddd;
            border-radius: 8px;
            font-size: 16px;
            text-align: center;
            transition: border-color 0.3s;
        }
        
        .password-input:focus {
            border-color: var(--uae-green);
            outline: none;
        }
        
        .password-btn {
            background: var(--uae-green);
            color: white;
            border: none;
            padding: 15px 30px;
            border-radius: 8px;
            cursor: pointer;
            font-size: 16px;
            font-weight: 600;
            width: 100%;
            transition: background-color 0.3s;
        }
        
        .password-btn:hover {
            background: #006b41;
        }
        
        .error-message {
            color: var(--uae-red);
            margin-top: 15px;
            display: none;
            font-weight: 600;
        }
        
        /* Hide main content initially */
        .container {
            display: none;
        }
        
        /* Your existing styles */
        body {
            background-color: #f5f7fa;
            color: var(--dark-color);
            line-height: 1.6;
        }
        
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 20px;
        }
        
        header {
            background: linear-gradient(135deg, var(--uae-green) 0%, var(--uae-red) 100%);
            color: white;
            padding: 20px 0;
            text-align: center;
            border-radius: 8px 8px 0 0;
            margin-bottom: 20px;
            position: relative;
            overflow: hidden;
        }
        
        .header-content {
            position: relative;
            z-index: 1;
        }
        
        h1 {
            font-size: 2.2rem;
            margin-bottom: 10px;
        }
        
        .subtitle {
            font-size: 1.1rem;
            opacity: 0.9;
        }
        
        .currency-selector {
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 10px;
            margin-top: 15px;
            background-color: rgba(255, 255, 255, 0.2);
            padding: 8px 15px;
            border-radius: 20px;
            display: inline-block;
        }
        
        .aed-currency {
            font-weight: bold;
            font-size: 1.1rem;
        }
        
        .app-container {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 20px;
        }
        
        @media (max-width: 768px) {
            .app-container {
                grid-template-columns: 1fr;
            }
        }
        
        .input-section, .results-section {
            background-color: white;
            border-radius: 8px;
            padding: 25px;
            box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
        }
        
        .section-title {
            font-size: 1.5rem;
            margin-bottom: 20px;
            padding-bottom: 10px;
            border-bottom: 2px solid var(--light-color);
            color: var(--primary-color);
        }
        
        .form-group {
            margin-bottom: 20px;
        }
        
        label {
            display: block;
            margin-bottom: 8px;
            font-weight: 600;
        }
        
        input, select {
            width: 100%;
            padding: 12px;
            border: 1px solid #ddd;
            border-radius: 4px;
            font-size: 1rem;
            transition: border-color 0.3s;
        }
        
        input:focus, select:focus {
            border-color: var(--secondary-color);
            outline: none;
        }
        
        .checkbox-group {
            display: flex;
            align-items: center;
            gap: 10px;
        }
        
        .checkbox-group input {
            width: auto;
        }
        
        .btn {
            background-color: var(--uae-green);
            color: white;
            border: none;
            padding: 12px 20px;
            border-radius: 4px;
            cursor: pointer;
            font-size: 1rem;
            font-weight: 600;
            transition: background-color 0.3s;
            width: 100%;
        }
        
        .btn:hover {
            background-color: #006b41;
        }
        
        .btn-print {
            background-color: var(--secondary-color);
            margin-bottom: 15px;
        }
        
        .btn-print:hover {
            background-color: #2980b9;
        }
        
        .results-grid {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 15px;
        }
        
        .result-card {
            background-color: var(--light-color);
            padding: 15px;
            border-radius: 6px;
            text-align: center;
            border-left: 4px solid var(--uae-green);
        }
        
        .result-value {
            font-size: 1.8rem;
            font-weight: 700;
            color: var(--primary-color);
            margin: 10px 0;
        }
        
        .result-label {
            font-size: 0.9rem;
            color: var(--dark-color);
        }
        
        .breakdown-section {
            margin-top: 25px;
        }
        
        .breakdown-table {
            width: 100%;
            border-collapse: collapse;
            margin-top: 10px;
        }
        
        .breakdown-table th, .breakdown-table td {
            padding: 12px 15px;
            text-align: left;
            border-bottom: 1px solid #ddd;
        }
        
        .breakdown-table th {
            background-color: var(--light-color);
            font-weight: 600;
        }
        
        .highlight {
            background-color: rgba(52, 152, 219, 0.1);
            font-weight: 600;
        }
        
        .total-row {
            font-weight: 700;
            font-size: 1.1rem;
            background-color: rgba(0, 135, 83, 0.1);
        }
        
        .footer {
            text-align: center;
            margin-top: 30px;
            padding: 20px;
            color: var(--dark-color);
            font-size: 0.9rem;
        }
        
        .cost-breakdown {
            background-color: #f9f9f9;
            padding: 15px;
            border-radius: 6px;
            margin-top: 15px;
        }
        
        .cost-item {
            display: flex;
            justify-content: space-between;
            margin-bottom: 8px;
            padding-bottom: 8px;
            border-bottom: 1px dashed #ddd;
        }
        
        .cost-item:last-child {
            border-bottom: none;
        }
        
        .cost-label {
            font-weight: 600;
        }
        
        .cost-value {
            font-weight: 600;
            color: var(--uae-green);
        }
        
        .note {
            font-size: 0.8rem;
            color: #666;
            margin-top: 10px;
            font-style: italic;
        }
        
        .post-details {
            background-color: #f0f8ff;
            padding: 15px;
            border-radius: 6px;
            margin-top: 15px;
        }
        
        .post-row {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 10px;
            margin-bottom: 10px;
        }
        
        .post-header {
            font-weight: bold;
            margin-bottom: 10px;
            padding-bottom: 5px;
            border-bottom: 1px solid #ddd;
        }
        
        .post-input-group {
            display: flex;
            flex-direction: column;
        }
        
        .post-input-group label {
            font-size: 0.9rem;
            margin-bottom: 5px;
        }
        
        .post-summary {
            margin-top: 15px;
            padding-top: 10px;
            border-top: 1px solid #ddd;
        }
        
        .no-print {
            display: block;
        }
        
        /* Collapsible sections */
        .collapsible {
            margin-top: 15px;
        }
        
        .collapsible-header {
            background-color: var(--light-color);
            padding: 12px 15px;
            border-radius: 6px;
            cursor: pointer;
            display: flex;
            justify-content: space-between;
            align-items: center;
            font-weight: 600;
            transition: background-color 0.3s;
        }
        
        .collapsible-header:hover {
            background-color: #e0e6ea;
        }
        
        .collapsible-content {
            max-height: 0;
            overflow: hidden;
            transition: max-height 0.3s ease-out;
            background-color: #f9f9f9;
            border-radius: 0 0 6px 6px;
        }
        
        .collapsible-content.expanded {
            max-height: 1000px;
            padding: 15px;
        }
        
        .collapsible-icon {
            transition: transform 0.3s;
        }
        
        .collapsible-icon.expanded {
            transform: rotate(180deg);
        }
        
        /* Gate table styles */
        .gate-table {
            width: 100%;
            border-collapse: collapse;
            margin-top: 10px;
        }
        
        .gate-table th, .gate-table td {
            padding: 10px;
            text-align: center;
            border: 1px solid #ddd;
        }
        
        .gate-table th {
            background-color: var(--light-color);
            font-weight: 600;
        }
        
        .gate-table input {
            width: 100%;
            padding: 8px;
            border: 1px solid #ddd;
            border-radius: 4px;
            text-align: center;
        }
        
        .gate-table .total-cell {
            font-weight: 600;
            background-color: #f0f8ff;
        }
        
        .gate-table .hidden-column {
            display: none;
        }
        
        .add-gate-row {
            background-color: var(--uae-green);
            color: white;
            border: none;
            padding: 8px 15px;
            border-radius: 4px;
            cursor: pointer;
            font-size: 0.9rem;
            margin-top: 10px;
        }
        
        .remove-gate-row {
            background-color: var(--uae-red);
            color: white;
            border: none;
            padding: 5px 10px;
            border-radius: 4px;
            cursor: pointer;
            font-size: 0.8rem;
        }
        
        /* Print styles would go here */
    </style>
</head>
<body>
    <!-- Password Protection -->
    <div id="password-protection">
        <div class="password-box">
            <h2>🔒 Protected Calculator</h2>
            <p>This calculator is confidential. Please enter the password to continue.</p>
            <input type="password" id="password-input" class="password-input" placeholder="Enter password">
            <button onclick="checkPassword()" class="password-btn">Access Calculator</button>
            <div id="error-message" class="error-message">Incorrect password. Please try again.</div>
        </div>
    </div>

    <!-- Main Calculator Content -->
    <div class="container">
        <header>
            <div class="header-content">
                <h1>Fence Cost Calculator</h1>
                <p class="subtitle">Calculate the total cost of fence installation including multiple gate types</p>
                <div class="currency-selector">
                    <span class="aed-currency">Currency: AED </span>
                </div>
            </div>
        </header>
        
        <div class="app-container">
            <section class="input-section">
                <h2 class="section-title">Project Details</h2>
                
                <div class="form-group">
                    <label for="distance">Distance (KM):</label>
                    <input type="number" id="distance" value="0" step="0.1" min="0">
                </div>
                
                <div class="form-group">
                    <label for="rate">Rate per KM (AED):</label>
                    <input type="number" id="rate" value="0" step="0.01" min="0">
                </div>
                
                <div class="form-group">
                    <label for="serviceType">Service Type:</label>
                    <select id="serviceType">
                        <option value="standard">Standard Installation</option>
                        <option value="premium">Premium Installation</option>
                    </select>
                </div>
                
                <div class="form-group">
                    <div class="checkbox-group">
                        <input type="checkbox" id="installation" checked>
                        <label for="installation">Include Installation?</label>
                    </div>
                </div>
                
                <h2 class="section-title">Post Details</h2>
                
                <div class="post-details">
                    <div class="post-header">Post Specifications</div>
                    
                    <div class="post-row">
                        <div class="post-input-group">
                            <label for="postQty">Number of Posts:</label>
                            <input type="number" id="postQty" value="0" min="1">
                        </div>
                        
                        <div class="post-input-group">
                            <label for="totalPostWeightInput">Total Post Weight (kg):</label>
                            <input type="number" id="totalPostWeightInput" value="0" step="0.01" min="0">
                        </div>
                    </div>
                    
                    <div class="post-row">
                        <div class="post-input-group">
                            <label for="calculatedWeight">Calculated Weight per Post (kg):</label>
                            <input type="number" id="calculatedWeight" value="0" step="0.01" min="0" readonly>
                        </div>
                    </div>
                    
                    <div class="post-summary">
                        <div class="cost-item">
                            <span class="cost-label">Weight per Post:</span>
                            <span class="cost-value" id="displayWeightPerPost">0.00 kg</span>
                        </div>
                    </div>
                </div>
                
                <!-- Gate Details - Collapsible -->
                <div class="collapsible">
                    <div class="collapsible-header" id="gateDetailsHeader">
                        <span>Gate Details (Multiple Types)</span>
                        <span class="collapsible-icon">▼</span>
                    </div>
                    <div class="collapsible-content" id="gateDetailsContent">
                        <div class="form-group">
                            <p>Add different gate types with their specifications:</p>
                            
                            <table class="gate-table">
                                <thead>
                                    <tr>
                                        <th>Gate Type</th>
                                        <th>Rate (AED)</th>
                                        <th>Quantity</th>
                                        <th>Weight (kg)</th>
                                        <th class="hidden-column">Total Cost</th>
                                        <th class="hidden-column">Total Weight</th>
                                        <th>Action</th>
                                    </tr>
                                </thead>
                                <tbody id="gateTableBody">
                                    <!-- Gate rows will be added here -->
                                </tbody>
                                <tfoot>
                                    <tr>
                                        <td colspan="3"><strong>Gates Total:</strong></td>
                                        <td class="total-cell" id="totalGatesWeight">0.00 kg</td>
                                        <td class="hidden-column total-cell" id="totalGatesCost">AED 0.00</td>
                                        <td class="hidden-column total-cell"></td>
                                        <td></td>
                                    </tr>
                                </tfoot>
                            </table>
                            
                            <button type="button" class="add-gate-row" onclick="addGateRow()">+ Add Gate Type</button>
                            
                            <div class="gate-types-info">
                                <p><strong>Common Gate Types:</strong></p>
                                <ul style="font-size: 0.9rem; margin-top: 10px; padding-left: 20px;">
                                    <li><strong>DLS</strong> - Double Leaf Swing Gate</li>
                                    <li><strong>SLS</strong> - Single Leaf Swing Gate</li>
                                    <li><strong>SLE</strong> - Sliding Gate</li>
                                </ul>
                            </div>
                        </div>
                    </div>
                </div>
                
                <button id="calculateBtn" class="btn">Calculate Total Cost</button>
                <button id="printBtn" class="btn btn-print no-print">Print Report</button>
            </section>
            
            <section class="results-section">
                <h2 class="section-title">Cost Breakdown</h2>
                
                <div class="results-grid">
                    <div class="result-card">
                        <div class="result-label">Total Distance Cost</div>
                        <div class="result-value" id="totalDistanceCost">AED 0.00</div>
                    </div>
                    
                    <div class="result-card">
                        <div class="result-label">Total Gates Value</div>
                        <div class="result-value" id="totalGatesValue">AED 0.00</div>
                    </div>
                    
                    <div class="result-card">
                        <div class="result-label">Material Cost</div>
                        <div class="result-value" id="materialCost">AED 0.00</div>
                    </div>
                    
                    <div class="result-card">
                        <div class="result-label">Installation Cost</div>
                        <div class="result-value" id="installationCost">AED 0.00</div>
                    </div>
                    
                    <!-- NEW: Gate Material Cost Box -->
                    <div class="result-card" id="gateMaterialCostCard" style="display: none;">
                        <div class="result-label">Gate Material Cost (70%)</div>
                        <div class="result-value" id="gateMaterialCostValue">AED 0.00</div>
                    </div>
                    
                    <!-- NEW: Gate Installation Cost Box -->
                    <div class="result-card" id="gateInstallationCostCard" style="display: none;">
                        <div class="result-label">Gate Installation Cost (30%)</div>
                        <div class="result-value" id="gateInstallationCostValue">AED 0.00</div>
                    </div>
                </div>
                
                <!-- Material Cost Breakdown - Collapsible -->
                <div class="collapsible">
                    <div class="collapsible-header" id="materialBreakdownHeader">
                        <span>Material Cost Breakdown</span>
                        <span class="collapsible-icon">▼</span>
                    </div>
                    <div class="collapsible-content" id="materialBreakdownContent">
                        <div class="cost-breakdown">
                            <div class="cost-item">
                                <span class="cost-label">Cost per KM (40%):</span>
                                <span class="cost-value" id="costPerKm">AED 0.00</span>
                            </div>
                            <div class="cost-item">
                                <span class="cost-label">Cost per Linear Meter:</span>
                                <span class="cost-value" id="costPerLM">AED 0.00</span>
                            </div>
                            <div class="cost-item">
                                <span class="cost-label">Cost per Post (60%):</span>
                                <span class="cost-value" id="costPerPost">AED 0.00</span>
                            </div>
                            <div class="cost-item">
                                <span class="cost-label">Cost per Post (Individual):</span>
                                <span class="cost-value" id="individualPostCost">AED 0.00</span>
                            </div>
                        </div>
                    </div>
                </div>
                
                <!-- Weight Summary - Collapsible -->
                <div class="collapsible">
                    <div class="collapsible-header" id="weightSummaryHeader">
                        <span>Weight Summary</span>
                        <span class="collapsible-icon">▼</span>
                    </div>
                    <div class="collapsible-content" id="weightSummaryContent">
                        <div class="post-details">
                            <div class="cost-item">
                                <span class="cost-label">Total Post Weight:</span>
                                <span class="cost-value" id="displayTotalPostWeight">0.00 kg</span>
                            </div>
                            <div class="cost-item">
                                <span class="cost-label">Total Gate Weight:</span>
                                <span class="cost-value" id="displayTotalGateWeight">0.00 kg</span>
                            </div>
                            <div class="cost-item">
                                <span class="cost-label">Total Weight (Posts + Gates):</span>
                                <span class="cost-value" id="displayTotalWeight">0.00 kg</span>
                            </div>
                            <div class="cost-item">
                                <span class="cost-label">Weight per Linear Meter:</span>
                                <span class="cost-value" id="displayWeightPerLM">0.00 kg</span>
                            </div>
                        </div>
                    </div>
                </div>
                
                <!-- Gate Breakdown - Collapsible -->
                <div class="collapsible">
                    <div class="collapsible-header" id="gateBreakdownHeader">
                        <span>Gate Breakdown Details</span>
                        <span class="collapsible-icon">▼</span>
                    </div>
                    <div class="collapsible-content" id="gateBreakdownContent">
                        <table class="breakdown-table" id="gateBreakdownTable">
                            <thead>
                                <tr>
                                    <th>Gate Type</th>
                                    <th>Quantity</th>
                                    <th>Rate (AED)</th>
                                    <th>Weight (kg)</th>
                                    <th>Total Cost</th>
                                    <th>Total Weight</th>
                                </tr>
                            </thead>
                            <tbody id="gateBreakdownBody">
                                <!-- Gate breakdown rows will be added here -->
                            </tbody>
                        </table>
                    </div>
                </div>
                
                <div class="breakdown-section">
                    <h3 class="section-title">Detailed Breakdown</h3>
                    
                    <table class="breakdown-table">
                        <thead>
                            <tr>
                                <th>Item</th>
                                <th>Amount (AED)</th>
                            </tr>
                        </thead>
                        <tbody>
                            <tr>
                                <td>Distance Cost (KM × Rate)</td>
                                <td id="distanceCostDetail">AED 0.00</td>
                            </tr>
                            <tr>
                                <td>Total Gates Value</td>
                                <td id="gatesValueDetail">AED 0.00</td>
                            </tr>
                            <tr class="highlight">
                                <td>Material Allocation (<span id="materialPercentage">70%</span>)</td>
                                <td id="materialAllocation">AED 0.00</td>
                            </tr>
                            <tr>
                                <td>&nbsp;&nbsp;• For Fence (40%)</td>
                                <td id="fenceCost">AED 0.00</td>
                            </tr>
                            <tr>
                                <td>&nbsp;&nbsp;&nbsp;&nbsp;Cost per Linear Meter</td>
                                <td id="costPerLMDetail">AED 0.00</td>
                            </tr>
                            <tr>
                                <td>&nbsp;&nbsp;• For Posts (60%)</td>
                                <td id="postCost">AED 0.00</td>
                            </tr>
                            <tr>
                                <td>&nbsp;&nbsp;&nbsp;&nbsp;Individual Post Cost</td>
                                <td id="individualPostCostDetail">AED 0.00</td>
                            </tr>
                            
                            <!-- NEW: Gate Material and Installation Breakdown -->
                            <tr class="highlight" id="gateMaterialRow" style="display: none;">
                                <td>Gate Material Cost (70%)</td>
                                <td id="gateMaterialDetail">AED 0.00</td>
                            </tr>
                            <tr class="highlight" id="gateInstallationRow" style="display: none;">
                                <td>Gate Installation Cost (30%)</td>
                                <td id="gateInstallationDetail">AED 0.00</td>
                            </tr>
                            
                            <tr class="highlight">
                                <td>Installation Cost (<span id="installationPercentage">30%</span>)</td>
                                <td id="installationCostDetail">AED 0.00</td>
                            </tr>
                            <tr class="total-row">
                                <td>GRAND TOTAL</td>
                                <td id="grandTotal">AED 0.00</td>
                            </tr>
                        </tbody>
                    </table>
                    <p class="note">Note: Installation costs are only applied when "Include Installation" is selected.</p>
                </div>
            </section>
        </div>
        
        <div class="footer no-print">
            <p>Fence Cost Calculator 2025 | Currency: AED</p>
            <p>Made by Vijay Goral</p>
        </div>
    </div>

    <script>
        // PASSWORD CONFIGURATION - CHANGE THIS!
        const CORRECT_PASSWORD = "fence2025"; // ⚠️ CHANGE THIS PASSWORD!
        
        function checkPassword() {
            const input = document.getElementById('password-input').value;
            const error = document.getElementById('error-message');
            
            if (input === CORRECT_PASSWORD) {
                // Correct password - show calculator
                document.getElementById('password-protection').style.display = 'none';
                document.querySelector('.container').style.display = 'block';
                
                // Store in session so password isn't needed again
                sessionStorage.setItem('authenticated', 'true');
            } else {
                // Wrong password - show error
                error.style.display = 'block';
                document.getElementById('password-input').value = '';
                document.getElementById('password-input').focus();
            }
        }
        
        // Check if already authenticated
        if (sessionStorage.getItem('authenticated') === 'true') {
            document.getElementById('password-protection').style.display = 'none';
            document.querySelector('.container').style.display = 'block';
        }
        
        // Allow pressing Enter to submit password
        document.getElementById('password-input').addEventListener('keypress', function(e) {
            if (e.key === 'Enter') {
                checkPassword();
            }
        });

        // Gate types data
        const GATE_TYPES = [
            { type: "DLS", description: "Double Leaf Swing Gate", defaultRate: 500, defaultWeight: 150 },
            { type: "SLS", description: "Single Leaf Swing Gate", defaultRate: 300, defaultWeight: 80 },
            { type: "SLE", description: "Sliding Gate", defaultRate: 800, defaultWeight: 200 }
        ];

        // Gate rows management
        let gateRows = [];

        // Initialize with one gate row
        document.addEventListener('DOMContentLoaded', function() {
            addGateRow("DLS");
            addGateRow("SLS");
            calculateCosts();
        });

        function addGateRow(gateType = "DLS") {
            const tableBody = document.getElementById('gateTableBody');
            const rowId = Date.now() + Math.random();
            
            const gateTypeData = GATE_TYPES.find(g => g.type === gateType) || GATE_TYPES[0];
            
            const row = document.createElement('tr');
            row.id = `gateRow-${rowId}`;
            row.innerHTML = `
                <td>
                    <select class="gate-type" onchange="updateGateRow('${rowId}', this.value)">
                        ${GATE_TYPES.map(g => 
                            `<option value="${g.type}" ${g.type === gateType ? 'selected' : ''}>${g.type} (${g.description})</option>`
                        ).join('')}
                    </select>
                </td>
                <td><input type="number" class="gate-rate" value="${gateTypeData.defaultRate}" min="0" step="0.01" oninput="calculateGateRow('${rowId}')"></td>
                <td><input type="number" class="gate-quantity" value="0" min="0" step="1" oninput="calculateGateRow('${rowId}')"></td>
                <td><input type="number" class="gate-weight" value="${gateTypeData.defaultWeight}" min="0" step="0.01" oninput="calculateGateRow('${rowId}')"></td>
                <td class="hidden-column gate-total-cost" data-row="${rowId}">AED 0.00</td>
                <td class="hidden-column gate-total-weight" data-row="${rowId}">0.00 kg</td>
                <td><button type="button" class="remove-gate-row" onclick="removeGateRow('${rowId}')">Remove</button></td>
            `;
            
            tableBody.appendChild(row);
            gateRows.push(rowId);
            calculateGateRow(rowId);
            calculateCosts();
        }

        function updateGateRow(rowId, newType) {
            const gateTypeData = GATE_TYPES.find(g => g.type === newType);
            if (!gateTypeData) return;
            
            const row = document.getElementById(`gateRow-${rowId}`);
            row.querySelector('.gate-rate').value = gateTypeData.defaultRate;
            row.querySelector('.gate-weight').value = gateTypeData.defaultWeight;
            
            calculateGateRow(rowId);
            calculateCosts();
        }

        function calculateGateRow(rowId) {
            const row = document.getElementById(`gateRow-${rowId}`);
            if (!row) return;
            
            const rate = parseFloat(row.querySelector('.gate-rate').value) || 0;
            const quantity = parseInt(row.querySelector('.gate-quantity').value) || 0;
            const weight = parseFloat(row.querySelector('.gate-weight').value) || 0;
            
            const totalCost = rate * quantity;
            const totalWeight = weight * quantity;
            
            row.querySelector(`.gate-total-cost[data-row="${rowId}"]`).textContent = formatCurrency(totalCost);
            row.querySelector(`.gate-total-weight[data-row="${rowId}"]`).textContent = formatWeight(totalWeight);
            
            updateGateTotals();
        }

        function updateGateTotals() {
            let totalQuantity = 0;
            let totalCost = 0;
            let totalWeight = 0;
            
            gateRows.forEach(rowId => {
                const row = document.getElementById(`gateRow-${rowId}`);
                if (row) {
                    const quantity = parseInt(row.querySelector('.gate-quantity').value) || 0;
                    const rate = parseFloat(row.querySelector('.gate-rate').value) || 0;
                    const weight = parseFloat(row.querySelector('.gate-weight').value) || 0;
                    
                    totalQuantity += quantity;
                    totalCost += rate * quantity;
                    totalWeight += weight * quantity;
                }
            });
            
            document.getElementById('totalGatesWeight').textContent = formatWeight(totalWeight);
            document.getElementById('totalGatesCost').textContent = formatCurrency(totalCost);
        }

        function removeGateRow(rowId) {
            const row = document.getElementById(`gateRow-${rowId}`);
            if (row) {
                row.remove();
                gateRows = gateRows.filter(id => id !== rowId);
                updateGateTotals();
                calculateCosts();
            }
        }

        // Your existing calculator JavaScript
        document.addEventListener('DOMContentLoaded', function() {
            const calculateBtn = document.getElementById('calculateBtn');
            const printBtn = document.getElementById('printBtn');
            
            // Add event listener to calculate button
            calculateBtn.addEventListener('click', calculateCosts);
            
            // Add event listener to print button
            printBtn.addEventListener('click', printReport);
            
            // Add event listeners to input fields for real-time calculation
            const inputFields = [
                'distance', 'rate', 'postQty', 'totalPostWeightInput'
            ];
            inputFields.forEach(field => {
                document.getElementById(field).addEventListener('input', calculateCosts);
            });
            
            // Add event listeners to gate inputs
            document.addEventListener('input', function(e) {
                if (e.target.classList.contains('gate-rate') || 
                    e.target.classList.contains('gate-quantity') || 
                    e.target.classList.contains('gate-weight')) {
                    calculateCosts();
                }
            });
            
            // Add event listener to installation checkbox
            document.getElementById('installation').addEventListener('change', function() {
                calculateCosts();
                updateGateCostCards();
            });
            
            // Add event listeners for collapsible sections
            document.getElementById('materialBreakdownHeader').addEventListener('click', function() {
                toggleCollapsible('materialBreakdownContent', 'materialBreakdownHeader');
            });
            
            document.getElementById('weightSummaryHeader').addEventListener('click', function() {
                toggleCollapsible('weightSummaryContent', 'weightSummaryHeader');
            });
            
            document.getElementById('gateDetailsHeader').addEventListener('click', function() {
                toggleCollapsible('gateDetailsContent', 'gateDetailsHeader');
            });
            
            document.getElementById('gateBreakdownHeader').addEventListener('click', function() {
                toggleCollapsible('gateBreakdownContent', 'gateBreakdownHeader');
            });
            
            function toggleCollapsible(contentId, headerId) {
                const content = document.getElementById(contentId);
                const header = document.getElementById(headerId);
                const icon = header.querySelector('.collapsible-icon');
                
                if (content.classList.contains('expanded')) {
                    content.classList.remove('expanded');
                    icon.classList.remove('expanded');
                } else {
                    content.classList.add('expanded');
                    icon.classList.add('expanded');
                }
            }
            
            function updateGateCostCards() {
                const includeInstallation = document.getElementById('installation').checked;
                const gateMaterialCard = document.getElementById('gateMaterialCostCard');
                const gateInstallationCard = document.getElementById('gateInstallationCostCard');
                const gateMaterialRow = document.getElementById('gateMaterialRow');
                const gateInstallationRow = document.getElementById('gateInstallationRow');
                
                if (includeInstallation) {
                    gateMaterialCard.style.display = 'block';
                    gateInstallationCard.style.display = 'block';
                    gateMaterialRow.style.display = 'table-row';
                    gateInstallationRow.style.display = 'table-row';
                    
                    // Update results grid to show 6 items (3x2 layout)
                    document.querySelector('.results-grid').style.gridTemplateColumns = '1fr 1fr';
                } else {
                    gateMaterialCard.style.display = 'none';
                    gateInstallationCard.style.display = 'none';
                    gateMaterialRow.style.display = 'none';
                    gateInstallationRow.style.display = 'none';
                    
                    // Update results grid to show 4 items (2x2 layout)
                    document.querySelector('.results-grid').style.gridTemplateColumns = '1fr 1fr';
                }
            }
            
            function calculateCosts() {
                // Get input values
                const distance = parseFloat(document.getElementById('distance').value) || 0;
                const rate = parseFloat(document.getElementById('rate').value) || 0;
                const postQty = parseInt(document.getElementById('postQty').value) || 0;
                const totalPostWeightInput = parseFloat(document.getElementById('totalPostWeightInput').value) || 0;
                const includeInstallation = document.getElementById('installation').checked;
                
                // Calculate gate totals
                let totalGatesValue = 0;
                let totalGateWeight = 0;
                let totalGateQuantity = 0;
                const gateDetails = [];
                
                gateRows.forEach(rowId => {
                    const row = document.getElementById(`gateRow-${rowId}`);
                    if (row) {
                        const gateType = row.querySelector('.gate-type').value;
                        const gateRate = parseFloat(row.querySelector('.gate-rate').value) || 0;
                        const gateQuantity = parseInt(row.querySelector('.gate-quantity').value) || 0;
                        const gateWeight = parseFloat(row.querySelector('.gate-weight').value) || 0;
                        const gateTotalCost = gateRate * gateQuantity;
                        const gateTotalWeight = gateWeight * gateQuantity;
                        
                        totalGatesValue += gateTotalCost;
                        totalGateWeight += gateTotalWeight;
                        totalGateQuantity += gateQuantity;
                        
                        if (gateQuantity > 0) {
                            gateDetails.push({
                                type: gateType,
                                rate: gateRate,
                                quantity: gateQuantity,
                                weight: gateWeight,
                                totalCost: gateTotalCost,
                                totalWeight: gateTotalWeight
                            });
                        }
                    }
                });
                
                // Update gate breakdown table
                updateGateBreakdownTable(gateDetails);
                
                // Calculate post values
                const totalPostWeight = totalPostWeightInput;
                const weightPerPost = postQty > 0 ? totalPostWeight / postQty : 0;
                
                // Update calculated values in UI
                document.getElementById('calculatedWeight').value = weightPerPost.toFixed(2);
                document.getElementById('displayWeightPerPost').textContent = formatWeight(weightPerPost);
                
                // Calculate costs
                const totalDistanceCost = distance * rate;
                
                // Material and installation allocation
                const materialPercentage = includeInstallation ? 0.7 : 1.0;
                const installationPercentage = includeInstallation ? 0.3 : 0.0;
                
                const materialAllocation = totalDistanceCost * materialPercentage;
                const installationAllocation = totalDistanceCost * installationPercentage;
                
                // Material breakdown
                const fenceCost = materialAllocation * 0.4; // 40% for fence (cost per KM)
                const postCost = materialAllocation * 0.6; // 60% for posts
                const individualPostCost = postQty > 0 ? postCost / postQty : 0;
                
                // Calculate cost per linear meter
                const costPerLM = distance > 0 ? fenceCost / distance : 0;
                
                // Gate material and installation costs
                const gateMaterialPercentage = includeInstallation ? 0.7 : 1.0;
                const gateInstallationPercentage = includeInstallation ? 0.3 : 0.0;
                
                const gateMaterialCost = totalGatesValue * gateMaterialPercentage;
                const gateInstallationCost = totalGatesValue * gateInstallationPercentage;
                
                // Grand total
                const grandTotal = totalDistanceCost + totalGatesValue + (includeInstallation ? gateInstallationCost : 0);
                
                // Weight calculations
                const distanceInMeters = distance * 1000;
                const totalWeight = totalPostWeight + totalGateWeight;
                const weightPerLM = distanceInMeters > 0 ? totalWeight / distanceInMeters : 0;
                
                // Update UI with calculated values
                document.getElementById('totalDistanceCost').textContent = formatCurrency(totalDistanceCost);
                document.getElementById('totalGatesValue').textContent = formatCurrency(totalGatesValue);
                document.getElementById('materialCost').textContent = formatCurrency(materialAllocation);
                document.getElementById('installationCost').textContent = formatCurrency(installationAllocation + (includeInstallation ? gateInstallationCost : 0));
                
                // Update gate cost boxes
                document.getElementById('gateMaterialCostValue').textContent = formatCurrency(gateMaterialCost);
                document.getElementById('gateInstallationCostValue').textContent = formatCurrency(gateInstallationCost);
                
                // Update detailed breakdown
                document.getElementById('distanceCostDetail').textContent = formatCurrency(totalDistanceCost);
                document.getElementById('gatesValueDetail').textContent = formatCurrency(totalGatesValue);
                document.getElementById('materialAllocation').textContent = formatCurrency(materialAllocation);
                document.getElementById('fenceCost').textContent = formatCurrency(fenceCost);
                document.getElementById('postCost').textContent = formatCurrency(postCost);
                document.getElementById('individualPostCostDetail').textContent = formatCurrency(individualPostCost);
                document.getElementById('installationCostDetail').textContent = formatCurrency(installationAllocation);
                
                // Update gate breakdown in detailed table
                document.getElementById('gateMaterialDetail').textContent = formatCurrency(gateMaterialCost);
                document.getElementById('gateInstallationDetail').textContent = formatCurrency(gateInstallationCost);
                
                // Remove old gate installation cost entry
                document.getElementById('grandTotal').textContent = formatCurrency(grandTotal);
                
                // Update percentages in the breakdown table
                document.getElementById('materialPercentage').textContent = (materialPercentage * 100) + '%';
                document.getElementById('installationPercentage').textContent = (installationPercentage * 100) + '%';
                
                // Update cost breakdown section
                document.getElementById('costPerKm').textContent = formatCurrency(fenceCost);
                document.getElementById('costPerPost').textContent = formatCurrency(postCost);
                document.getElementById('individualPostCost').textContent = formatCurrency(individualPostCost);
                
                // Update cost per linear meter
                document.getElementById('costPerLM').textContent = formatCurrency(costPerLM);
                document.getElementById('costPerLMDetail').textContent = formatCurrency(costPerLM);
                
                // Update weight summary
                document.getElementById('displayTotalPostWeight').textContent = formatWeight(totalPostWeight);
                document.getElementById('displayTotalGateWeight').textContent = formatWeight(totalGateWeight);
                document.getElementById('displayTotalWeight').textContent = formatWeight(totalWeight);
                document.getElementById('displayWeightPerLM').textContent = formatWeight(weightPerLM);
                
                // Update gate cost cards visibility
                updateGateCostCards();
            }
            
            function updateGateBreakdownTable(gateDetails) {
                const tbody = document.getElementById('gateBreakdownBody');
                tbody.innerHTML = '';
                
                if (gateDetails.length === 0) {
                    const row = document.createElement('tr');
                    row.innerHTML = `<td colspan="6" style="text-align: center; padding: 20px;">No gates added</td>`;
                    tbody.appendChild(row);
                    return;
                }
                
                gateDetails.forEach(gate => {
                    const row = document.createElement('tr');
                    row.innerHTML = `
                        <td>${gate.type}</td>
                        <td>${gate.quantity}</td>
                        <td>${formatCurrency(gate.rate)}</td>
                        <td>${formatWeight(gate.weight)}</td>
                        <td>${formatCurrency(gate.totalCost)}</td>
                        <td>${formatWeight(gate.totalWeight)}</td>
                    `;
                    tbody.appendChild(row);
                });
                
                // Add total row
                const totalRow = document.createElement('tr');
                totalRow.className = 'total-row';
                const totalCost = gateDetails.reduce((sum, gate) => sum + gate.totalCost, 0);
                const totalWeight = gateDetails.reduce((sum, gate) => sum + gate.totalWeight, 0);
                const totalQuantity = gateDetails.reduce((sum, gate) => sum + gate.quantity, 0);
                
                totalRow.innerHTML = `
                    <td><strong>Total</strong></td>
                    <td><strong>${totalQuantity}</strong></td>
                    <td></td>
                    <td></td>
                    <td><strong>${formatCurrency(totalCost)}</strong></td>
                    <td><strong>${formatWeight(totalWeight)}</strong></td>
                `;
                tbody.appendChild(totalRow);
            }
            
            function printReport() {
                window.print();
            }
            
            function formatCurrency(amount) {
                return 'AED ' + amount.toFixed(2).replace(/\d(?=(\d{3})+\.)/g, '$&,');
            }
            
            function formatWeight(weight) {
                return weight.toFixed(2).replace(/\d(?=(\d{3})+\.)/g, '$&,') + ' kg';
            }
        });
    </script>
</body>
</html>

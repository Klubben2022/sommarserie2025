<!DOCTYPE html>
<html lang="sv">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>KLUBBEN - Padelserie</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        body {
            font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, sans-serif;
            background: #f8f9fa;
            color: #333;
            line-height: 1.6;
        }
        
        .header {
            background: white;
            border-bottom: 1px solid #e9ecef;
            padding: 15px 30px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            box-shadow: 0 2px 4px rgba(0,0,0,0.05);
        }
        
        .logo {
            font-weight: bold;
            font-size: 20px;
            color: #333;
        }
        
        .logo-sub {
            font-size: 12px;
            color: #666;
            font-weight: normal;
        }
        
        .nav-buttons {
            display: flex;
            gap: 20px;
        }
        
        .nav-button {
            display: flex;
            align-items: center;
            gap: 8px;
            padding: 8px 16px;
            background: none;
            border: 1px solid #dee2e6;
            border-radius: 6px;
            color: #666;
            text-decoration: none;
            font-size: 14px;
            transition: all 0.2s;
            cursor: pointer;
        }
        
        .nav-button:hover {
            background: #f8f9fa;
            border-color: #adb5bd;
        }
        
        .nav-button.active {
            background: #e7f3ff;
            border-color: #007bff;
            color: #007bff;
        }
        
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 30px;
        }
        
        .page-title {
            text-align: center;
            font-size: 32px;
            font-weight: 600;
            margin-bottom: 40px;
            color: #333;
        }
        
        .division-tabs {
            display: flex;
            justify-content: center;
            margin-bottom: 40px;
            background: #f1f3f4;
            border-radius: 8px;
            padding: 4px;
            width: fit-content;
            margin-left: auto;
            margin-right: auto;
        }
        
        .division-tab {
            padding: 12px 24px;
            border: none;
            background: none;
            color: #666;
            font-size: 16px;
            font-weight: 500;
            cursor: pointer;
            border-radius: 6px;
            transition: all 0.2s;
        }
        
        .division-tab.active {
            background: white;
            color: #333;
            box-shadow: 0 2px 4px rgba(0,0,0,0.1);
        }
        
        .tournament-header {
            background: white;
            border-radius: 12px;
            padding: 30px;
            margin-bottom: 30px;
            box-shadow: 0 2px 8px rgba(0,0,0,0.1);
            text-align: center;
        }
        
        .tournament-title {
            color: #4caf50;
            font-size: 24px;
            font-weight: 600;
            margin-bottom: 20px;
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 10px;
        }
        
        .tournament-info {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 20px;
            margin-top: 20px;
        }
        
        .info-item {
            padding: 15px;
            background: #f8f9fa;
            border-radius: 8px;
        }
        
        .info-label {
            font-weight: 600;
            color: #333;
            margin-bottom: 5px;
        }
        
        .info-value {
            color: #666;
            font-size: 14px;
        }
        
        .content-section {
            background: white;
            border-radius: 12px;
            padding: 30px;
            margin-bottom: 30px;
            box-shadow: 0 2px 8px rgba(0,0,0,0.1);
        }
        
        .section-title {
            font-size: 20px;
            font-weight: 600;
            margin-bottom: 20px;
            color: #333;
        }
        
        .form-container {
            background: #f8f9fa;
            border-radius: 12px;
            padding: 30px;
            margin-bottom: 30px;
        }
        
        .form-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 20px;
            margin-bottom: 20px;
        }
        
        .form-group {
            display: flex;
            flex-direction: column;
        }
        
        .form-label {
            font-weight: 600;
            color: #333;
            margin-bottom: 8px;
            font-size: 14px;
        }
        
        .form-input, .form-select {
            padding: 12px 16px;
            border: 1px solid #dee2e6;
            border-radius: 8px;
            font-size: 16px;
            background: white;
            transition: border-color 0.2s;
        }
        
        .form-input:focus, .form-select:focus {
            outline: none;
            border-color: #007bff;
            box-shadow: 0 0 0 3px rgba(0, 123, 255, 0.1);
        }
        
        .sets-grid {
            display: grid;
            grid-template-columns: 1fr 1fr 1fr;
            gap: 10px;
        }
        
        .submit-btn {
            background: #4caf50;
            color: white;
            border: none;
            padding: 12px 30px;
            border-radius: 8px;
            font-size: 16px;
            font-weight: 600;
            cursor: pointer;
            transition: background 0.2s;
        }
        
        .submit-btn:hover {
            background: #45a049;
        }
        
        .team-selection {
            position: relative;
        }
        
        .team-dropdown {
            position: absolute;
            top: 100%;
            left: 0;
            right: 0;
            background: white;
            border: 1px solid #dee2e6;
            border-top: none;
            border-radius: 0 0 8px 8px;
            max-height: 200px;
            overflow-y: auto;
            z-index: 1000;
            display: none;
            box-shadow: 0 4px 12px rgba(0,0,0,0.15);
        }
        
        .team-option {
            padding: 12px 16px;
            cursor: pointer;
            border-bottom: 1px solid #f8f9fa;
            font-size: 14px;
        }
        
        .team-option:hover {
            background: #f8f9fa;
        }
        
        .team-option:last-child {
            border-bottom: none;
        }
        
        .alert {
            padding: 16px;
            border-radius: 8px;
            margin-bottom: 20px;
            font-weight: 500;
        }
        
        .alert-success {
            background: #d4edda;
            color: #155724;
            border: 1px solid #c3e6cb;
        }
        
        .alert-error {
            background: #f8d7da;
            color: #721c24;
            border: 1px solid #f5c6cb;
        }
        
        .data-table {
            width: 100%;
            border-collapse: collapse;
            background: white;
            border-radius: 12px;
            overflow: hidden;
            box-shadow: 0 2px 8px rgba(0,0,0,0.1);
        }
        
        .data-table th {
            background: #f8f9fa;
            color: #666;
            font-weight: 600;
            padding: 16px;
            text-align: left;
            font-size: 14px;
            border-bottom: 1px solid #dee2e6;
        }
        
        .data-table td {
            padding: 16px;
            border-bottom: 1px solid #f8f9fa;
            font-size: 14px;
        }
        
        .data-table tbody tr:hover {
            background: #f8f9fa;
        }
        
        .data-table tbody tr:last-child td {
            border-bottom: none;
        }
        
        .standings-table {
            width: 100%;
            border-collapse: collapse;
            background: white;
            border-radius: 12px;
            overflow: hidden;
            box-shadow: 0 2px 8px rgba(0,0,0,0.1);
        }
        
        .standings-table th {
            background: #f8f9fa;
            color: #666;
            font-weight: 600;
            padding: 16px;
            text-align: left;
            font-size: 14px;
            border-bottom: 1px solid #dee2e6;
        }
        
        .standings-table td {
            padding: 16px;
            border-bottom: 1px solid #f8f9fa;
            font-size: 14px;
        }
        
        .standings-table tbody tr:hover {
            background: #f8f9fa;
        }
        
        .position-cell {
            display: flex;
            align-items: center;
            gap: 12px;
        }
        
        .position-badge {
            width: 32px;
            height: 32px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-weight: bold;
            font-size: 14px;
            color: white;
        }
        
        .position-1 {
            background: #ffc107;
        }
        
        .position-2 {
            background: #6c757d;
        }
        
        .position-3 {
            background: #cd7f32;
        }
        
        .position-other {
            background: #dee2e6;
            color: #666;
        }
        
        .player-name {
            font-weight: 600;
            color: #333;
        }
        
        .points-cell {
            font-weight: bold;
            font-size: 16px;
            color: #333;
        }
        
        .filter-container {
            margin-bottom: 20px;
        }
        
        .filter-select {
            padding: 10px 16px;
            border: 1px solid #dee2e6;
            border-radius: 8px;
            background: white;
            font-size: 14px;
        }
        
        .players-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
            gap: 20px;
            margin-bottom: 30px;
        }
        
        .player-card {
            background: white;
            border: 1px solid #dee2e6;
            border-radius: 12px;
            padding: 20px;
            transition: box-shadow 0.2s;
        }
        
        .player-card:hover {
            box-shadow: 0 4px 12px rgba(0,0,0,0.1);
        }
        
        .player-card-name {
            font-weight: 600;
            color: #333;
            margin-bottom: 5px;
        }
        
        .player-card-info {
            color: #666;
            font-size: 14px;
        }
        
        .division-content {
            display: none;
        }
        
        .division-content.active {
            display: block;
        }
        
        .wins {
            color: #28a745;
            font-weight: 600;
        }
        
        .losses {
            color: #dc3545;
            font-weight: 600;
        }
        
        @media (max-width: 768px) {
            .header {
                flex-direction: column;
                gap: 15px;
                padding: 20px;
            }
            
            .nav-buttons {
                flex-wrap: wrap;
                justify-content: center;
            }
            
            .container {
                padding: 20px;
            }
            
            .form-grid {
                grid-template-columns: 1fr;
            }
            
            .division-tabs {
                flex-direction: column;
                width: 100%;
            }
            
            .tournament-info {
                grid-template-columns: 1fr;
            }
            
            .data-table, .standings-table {
                font-size: 12px;
            }
            
            .data-table th, .data-table td,
            .standings-table th, .standings-table td {
                padding: 12px 8px;
            }
            
            .players-grid {
                grid-template-columns: 1fr;
            }
        }
    </style>
</head>
<body>
    <div class="header">
        <div class="logo">
            KLUBBEN
            <div class="logo-sub">Göteborg</div>
        </div>
        <nav class="nav-buttons">
            <button class="nav-button" onclick="showScheduleView()">📋 Spelschema</button>
            <button class="nav-button active" onclick="showResultsView()">📊 Rapportera Resultat</button>
            <button class="nav-button" onclick="showRankingView()">🏆 Ranking</button>
            <button class="nav-button" onclick="showStatsView()">📈 Statistik</button>
        </nav>
    </div>

    <div class="container">
        <h1 class="page-title" id="page-title">Poängtabell</h1>
        
        <div class="tournament-header">
            <div class="tournament-title">
                🏆 Herrturnering 2025 & Damturnering 2025
            </div>
            <div class="tournament-info">
                <div class="info-item">
                    <div class="info-label">Herrar</div>
                    <div class="info-value">19 maj - 23 juni 2025</div>
                </div>
                <div class="info-item">
                    <div class="info-label">Damer</div>
                    <div class="info-value">20 maj - 24 juni 2025</div>
                </div>
                <div class="info-item">
                    <div class="info-label">Poängsystem</div>
                    <div class="info-value">2 poäng per vunnet set</div>
                </div>
                <div class="info-item">
                    <div class="info-label">Banor</div>
                    <div class="info-value">GLS, Konstsmide, WFI</div>
                </div>
            </div>
        </div>

        <div class="division-tabs" id="division-tabs">
            <button class="division-tab active" onclick="showDivision('herr1')">Herrar</button>
            <button class="division-tab" onclick="showDivision('dam1')">Damer</button>
        </div>

        <!-- Schedule View -->
        <div id="schedule-view" class="content-view" style="display: none;">
            <div class="content-section">
                <h2 class="section-title">🏆 Herrturnering 2025</h2>
                
                <div class="content-section">
                    <h3 class="section-title">Division 1 - 5 spelare</h3>
                    <p><strong>Startar:</strong> 19 maj 2025 (måndag) | <strong>Slutar:</strong> 23 juni 2025</p>
                    <table class="data-table">
                        <thead>
                            <tr>
                                <th>Vecka</th>
                                <th>Datum</th>
                                <th>Tid</th>
                                <th>Lag 1</th>
                                <th>Lag 2</th>
                                <th>Vilar</th>
                                <th>Bana</th>
                            </tr>
                        </thead>
                        <tbody>
                            <tr>
                                <td>1</td>
                                <td>19 maj</td>
                                <td>18:00</td>
                                <td>Kristoffer Arvidsson & Dennis Frånberg</td>
                                <td>Ahmedin Murtezic & Christer Sjölander</td>
                                <td><em>Jonas Lidén</em></td>
                                <td>GLS</td>
                            </tr>
                            <tr>
                                <td>2</td>
                                <td>26 maj</td>
                                <td>18:00</td>
                                <td>Christer Sjölander & Jonas Lidén</td>
                                <td>Ahmedin Murtezic & Dennis Frånberg</td>
                                <td><em>Kristoffer Arvidsson</em></td>
                                <td>GLS</td>
                            </tr>
                            <tr>
                                <td>3</td>
                                <td>2 juni</td>
                                <td>18:00</td>
                                <td>Dennis Frånberg & Jonas Lidén</td>
                                <td>Kristoffer Arvidsson & Ahmedin Murtezic</td>
                                <td><em>Christer Sjölander</em></td>
                                <td>GLS</td>
                            </tr>
                            <tr>
                                <td>4</td>
                                <td>9 juni</td>
                                <td>18:00</td>
                                <td>Ahmedin Murtezic & Jonas Lidén</td>
                                <td>Christer Sjölander & Kristoffer Arvidsson</td>
                                <td><em>Dennis Frånberg</em></td>
                                <td>GLS</td>
                            </tr>
                            <tr>
                                <td>5</td>
                                <td>16 juni</td>
                                <td>18:00</td>
                                <td>Jonas Lidén & Kristoffer Arvidsson</td>
                                <td>Christer Sjölander & Dennis Frånberg</td>
                                <td><em>Ahmedin Murtezic</em></td>
                                <td>GLS</td>
                            </tr>
                        </tbody>
                    </table>
                    <p><strong>Spelare:</strong> Christer Sjölander, Ahmedin Murtezic, Dennis Frånberg, Kristoffer Arvidsson, Jonas Lidén</p>
                    <p><em>Varje spelare byter partner varje vecka och vilar en vecka under turneringen (4 veckor).</em></p>
                </div>

                <div class="content-section">
                    <h3 class="section-title">Division 2 - 5 spelare</h3>
                    <p><strong>Startar:</strong> 19 maj 2025 (måndag) | <strong>Slutar:</strong> 23 juni 2025</p>
                    <table class="data-table">
                        <thead>
                            <tr>
                                <th>Vecka</th>
                                <th>Datum</th>
                                <th>Tid</th>
                                <th>Lag 1</th>
                                <th>Lag 2</th>
                                <th>Vilar</th>
                                <th>Bana</th>
                            </tr>
                        </thead>
                        <tbody>
                            <tr>
                                <td>1</td>
                                <td>19 maj</td>
                                <td>18:00</td>
                                <td>David Rudleuski & Pierre Hill</td>
                                <td>Edin Murtezic & Ajdin Batic</td>
                                <td><em>Kossal Alassmar</em></td>
                                <td>WFI</td>
                            </tr>
                            <tr>
                                <td>2</td>
                                <td>26 maj</td>
                                <td>18:00</td>
                                <td>David Rudleuski & Kossal Alassmar</td>
                                <td>Pierre Hill & Ajdin Batic</td>
                                <td><em>Edin Murtezic</em></td>
                                <td>WFI</td>
                            </tr>
                            <tr>
                                <td>3</td>
                                <td>2 juni</td>
                                <td>18:00</td>
                                <td>Pierre Hill & Edin Murtezic</td>
                                <td>Kossal Alassmar & David Rudleuski</td>
                                <td><em>Ajdin Batic</em></td>
                                <td>WFI</td>
                            </tr>
                            <tr>
                                <td>4</td>
                                <td>9 juni</td>
                                <td>18:00</td>
                                <td>Pierre Hill & Kossal Alassmar</td>
                                <td>Edin Murtezic & Ajdin Batic</td>
                                <td><em>David Rudleuski</em></td>
                                <td>WFI</td>
                            </tr>
                            <tr>
                                <td>5</td>
                                <td>16 juni</td>
                                <td>18:00</td>
                                <td>David Rudleuski & Edin Murtezic</td>
                                <td>Kossal Alassmar & Ajdin Batic</td>
                                <td><em>Pierre Hill</em></td>
                                <td>WFI</td>
                            </tr>
                        </tbody>
                    </table>
                    <p><strong>Spelare:</strong> David Rudleuski, Pierre Hill, Edin Murtezic, Ajdin Batic, Kossal Alassmar</p>
                    <p><em>Varje spelare byter partner varje vecka och vilar en vecka under turneringen (4 veckor).</em></p>
                </div>
            </div>

            <div class="content-section">
                <h2 class="section-title">🏆 Damturnering 2025</h2>
                
                <div class="content-section">
                    <h3 class="section-title">Division 1 - 12 spelare</h3>
                    <p><strong>Startar:</strong> 20 maj 2025 (tisdag) | <strong>Slutar:</strong> 24 juni 2025</p>
                    <p><strong>Spelare:</strong> Linnéa Leandersson, Magdalena Nilsson, Catharina Park, Cindy Goldschmidt, Ulrika Johansson, Mia Burghardt, Karin Nyberg, Linda FalkBoman, Anna Andersson, Malin Bräddhult, Sofia Svensson, Eva Månsson</p>
                </div>

                <div class="content-section">
                    <h3 class="section-title">Division 2 - 12 spelare</h3>
                    <p><strong>Startar:</strong> 20 maj 2025 (tisdag) | <strong>Slutar:</strong> 24 juni 2025</p>
                    <p><strong>Spelare:</strong> Ajsa Elezovic, Mai Khan Vo, Anna P, Maria Petersson, Harisa Santic, Emilia Andersson, Erika Falk, Ina Rudleuskaya, Valeska Blomberg, Amanda Johansson, Gunilla Ljungkvist, Madeleine Remnehöjd</p>
                </div>
            </div>
        </div>

        <!-- Results View (existing content) -->
        <div id="results-view" class="content-view">

        <!-- Herr Divisions -->
        <div id="herr1" class="division-content active">
            <div class="content-section">
                <h2 class="section-title">Rapportera Match</h2>
                
                <div class="form-container">
                    <div class="form-grid">
                        <div class="form-group">
                            <label class="form-label">Division</label>
                            <select class="form-select" id="herr-division">
                                <option value="herr1">Herr Division 1</option>
                                <option value="herr2">Herr Division 2</option>
                            </select>
                        </div>
                        <div class="form-group">
                            <label class="form-label">Vecka</label>
                            <select class="form-select" id="week-herr" onchange="updateTeamDropdowns('herr')">
                                <option value="1">Vecka 1 (19 maj) - 18:00</option>
                                <option value="2">Vecka 2 (26 maj) - 18:00</option>
                                <option value="3">Vecka 3 (2 juni) - 18:00</option>
                                <option value="4">Vecka 4 (9 juni) - 18:00</option>
                                <option value="5">Vecka 5 (16 juni) - 18:00</option>
                            </select>
                        </div>
                        <div class="form-group">
                            <label class="form-label">Lag A</label>
                            <div class="team-selection">
                                <input type="text" class="form-input" id="teamA-herr" placeholder="Välj lag A" onclick="showTeamDropdown('herr', 'A')" readonly>
                                <div class="team-dropdown" id="dropdown-herr-A"></div>
                            </div>
                        </div>
                        <div class="form-group">
                            <label class="form-label">Lag B</label>
                            <div class="team-selection">
                                <input type="text" class="form-input" id="teamB-herr" placeholder="Välj lag B" onclick="showTeamDropdown('herr', 'B')" readonly>
                                <div class="team-dropdown" id="dropdown-herr-B"></div>
                            </div>
                        </div>
                    </div>
                    
                    <div class="form-grid">
                        <div class="form-group">
                            <label class="form-label">Gem-resultat per set (A-B)</label>
                            <div class="sets-grid">
                                <input type="text" class="form-input" id="set1-herr" placeholder="Set 1: 6-4">
                                <input type="text" class="form-input" id="set2-herr" placeholder="Set 2: 6-2">
                                <input type="text" class="form-input" id="set3-herr" placeholder="Set 3: 6-1">
                            </div>
                        </div>
                        <div class="form-group">
                            <label class="form-label">&nbsp;</label>
                            <button class="submit-btn" onclick="submitMatch('herr')">Rapportera Match</button>
                        </div>
                    </div>
                </div>
                
                <div id="alert-herr"></div>
            </div>

            <!-- Herr Division 1 Standings -->
            <div class="content-section">
                <h2 class="section-title">Herrar Division 1</h2>
                <table class="standings-table" id="standings-herr1">
                    <thead>
                        <tr>
                            <th>Plats</th>
                            <th>Spelare</th>
                            <th>Matcher</th>
                            <th>Vinster</th>
                            <th>Förluster</th>
                            <th>Poäng</th>
                        </tr>
                    </thead>
                    <tbody></tbody>
                </table>
            </div>

            <!-- Herr Division 2 Standings -->
            <div class="content-section">
                <h2 class="section-title">Herrar Division 2</h2>
                <table class="standings-table" id="standings-herr2">
                    <thead>
                        <tr>
                            <th>Plats</th>
                            <th>Spelare</th>
                            <th>Matcher</th>
                            <th>Vinster</th>
                            <th>Förluster</th>
                            <th>Poäng</th>
                        </tr>
                    </thead>
                    <tbody></tbody>
                </table>
            </div>

            <!-- Match Results -->
            <div class="content-section">
                <h2 class="section-title">Matchresultat - Herrar</h2>
                <div class="filter-container">
                    <select class="filter-select" id="weekFilter-herr" onchange="filterResults('herr')">
                        <option value="all">Alla veckor</option>
                        <option value="1">Vecka 1 (19 maj) - 18:00</option>
                        <option value="2">Vecka 2 (26 maj) - 18:00</option>
                        <option value="3">Vecka 3 (2 juni) - 18:00</option>
                        <option value="4">Vecka 4 (9 juni) - 18:00</option>
                        <option value="5">Vecka 5 (16 juni) - 18:00</option>
                    </select>
                </div>
                <table class="data-table" id="results-herr">
                    <thead>
                        <tr>
                            <th>Vecka</th>
                            <th>Division</th>
                            <th>Lag A</th>
                            <th>Lag B</th>
                            <th>Set 1</th>
                            <th>Set 2</th>
                            <th>Set 3</th>
                            <th>Set-resultat</th>
                            <th>Poäng A</th>
                            <th>Poäng B</th>
                            <th>Tid</th>
                        </tr>
                    </thead>
                    <tbody></tbody>
                </table>
            </div>
        </div>

        <!-- Dam Divisions -->
        <div id="dam1" class="division-content">
            <div class="content-section">
                <h2 class="section-title">Rapportera Match</h2>
                
                <div class="form-container">
                    <div class="form-grid">
                        <div class="form-group">
                            <label class="form-label">Division</label>
                            <select class="form-select" id="dam-division">
                                <option value="dam1">Dam Division 1</option>
                                <option value="dam2">Dam Division 2</option>
                            </select>
                        </div>
                        <div class="form-group">
                            <label class="form-label">Vecka</label>
                            <select class="form-select" id="week-dam" onchange="updateTeamDropdowns('dam')">
                                <option value="1">Vecka 1 (20 maj)</option>
                                <option value="2">Vecka 2 (27 maj)</option>
                                <option value="3">Vecka 3 (3 juni)</option>
                                <option value="4">Vecka 4 (10 juni)</option>
                                <option value="5">Vecka 5 (17 juni)</option>
                            </select>
                        </div>
                        <div class="form-group">
                            <label class="form-label">Lag A</label>
                            <div class="team-selection">
                                <input type="text" class="form-input" id="teamA-dam" placeholder="Välj lag A" onclick="showTeamDropdown('dam', 'A')" readonly>
                                <div class="team-dropdown" id="dropdown-dam-A"></div>
                            </div>
                        </div>
                        <div class="form-group">
                            <label class="form-label">Lag B</label>
                            <div class="team-selection">
                                <input type="text" class="form-input" id="teamB-dam" placeholder="Välj lag B" onclick="showTeamDropdown('dam', 'B')" readonly>
                                <div class="team-dropdown" id="dropdown-dam-B"></div>
                            </div>
                        </div>
                    </div>
                    
                    <div class="form-grid">
                        <div class="form-group">
                            <label class="form-label">Gem-resultat per set (A-B)</label>
                            <div class="sets-grid">
                                <input type="text" class="form-input" id="set1-dam" placeholder="Set 1: 6-4">
                                <input type="text" class="form-input" id="set2-dam" placeholder="Set 2: 6-2">
                                <input type="text" class="form-input" id="set3-dam" placeholder="Set 3: 6-1">
                            </div>
                        </div>
                        <div class="form-group">
                            <label class="form-label">&nbsp;</label>
                            <button class="submit-btn" onclick="submitMatch('dam')">Rapportera Match</button>
                        </div>
                    </div>
                </div>
                
                <div id="alert-dam"></div>
            </div>

            <!-- Dam Division 1 Standings -->
            <div class="content-section">
                <h2 class="section-title">Damer Division 1</h2>
                <table class="standings-table" id="standings-dam1">
                    <thead>
                        <tr>
                            <th>Plats</th>
                            <th>Spelare</th>
                            <th>Matcher</th>
                            <th>Vinster</th>
                            <th>Förluster</th>
                            <th>Poäng</th>
                        </tr>
                    </thead>
                    <tbody></tbody>
                </table>
            </div>

            <!-- Dam Division 2 Standings -->
            <div class="content-section">
                <h2 class="section-title">Damer Division 2</h2>
                <table class="standings-table" id="standings-dam2">
                    <thead>
                        <tr>
                            <th>Plats</th>
                            <th>Spelare</th>
                            <th>Matcher</th>
                            <th>Vinster</th>
                            <th>Förluster</th>
                            <th>Poäng</th>
                        </tr>
                    </thead>
                    <tbody></tbody>
                </table>
            </div>

            <!-- Match Results -->
            <div class="content-section">
                <h2 class="section-title">Matchresultat - Damer</h2>
                <div class="filter-container">
                    <select class="filter-select" id="weekFilter-dam" onchange="filterResults('dam')">
                        <option value="all">Alla veckor</option>
                        <option value="1">Vecka 1 (20 maj)</option>
                        <option value="2">Vecka 2 (27 maj)</option>
                        <option value="3">Vecka 3 (3 juni)</option>
                        <option value="4">Vecka 4 (10 juni)</option>
                        <option value="5">Vecka 5 (17 juni)</option>
                    </select>
                </div>
                <table class="data-table" id="results-dam">
                    <thead>
                        <tr>
                            <th>Vecka</th>
                            <th>Division</th>
                            <th>Lag A</th>
                            <th>Lag B</th>
                            <th>Set 1</th>
                            <th>Set 2</th>
                            <th>Set 3</th>
                            <th>Set-resultat</th>
                            <th>Poäng A</th>
                            <th>Poäng B</th>
                            <th>Tid</th>
                        </tr>
                    </thead>
                    <tbody></tbody>
                </table>
            </div>
        </div>
    </div>

    <script>
        // Team data based on the exact tournament schedule
        const teamData = {
            herr1: {
                weeks: {
                    1: [
                        'Kristoffer Arvidsson & Dennis Frånberg',
                        'Ahmedin Murtezic & Christer Sjölander'
                    ],
                    2: [
                        'Christer Sjölander & Jonas Lidén',
                        'Ahmedin Murtezic & Dennis Frånberg'
                    ],
                    3: [
                        'Dennis Frånberg & Jonas Lidén',
                        'Kristoffer Arvidsson & Ahmedin Murtezic'
                    ],
                    4: [
                        'Ahmedin Murtezic & Jonas Lidén',
                        'Christer Sjölander & Kristoffer Arvidsson'
                    ],
                    5: [
                        'Jonas Lidén & Kristoffer Arvidsson',
                        'Christer Sjölander & Dennis Frånberg'
                    ]
                },
                players: ['Christer Sjölander', 'Ahmedin Murtezic', 'Dennis Frånberg', 'Kristoffer Arvidsson', 'Jonas Lidén'],
                restingPlayers: {
                    1: 'Jonas Lidén',
                    2: 'Kristoffer Arvidsson', 
                    3: 'Christer Sjölander',
                    4: 'Dennis Frånberg',
                    5: 'Ahmedin Murtezic'
                }
            },
            herr2: {
                weeks: {
                    1: [
                        'David Rudleuski & Pierre Hill',
                        'Edin Murtezic & Ajdin Batic'
                    ],
                    2: [
                        'David Rudleuski & Kossal Alassmar',
                        'Pierre Hill & Ajdin Batic'
                    ],
                    3: [
                        'Pierre Hill & Edin Murtezic',
                        'Kossal Alassmar & David Rudleuski'
                    ],
                    4: [
                        'Pierre Hill & Kossal Alassmar',
                        'Edin Murtezic & Ajdin Batic'
                    ],
                    5: [
                        'David Rudleuski & Edin Murtezic',
                        'Kossal Alassmar & Ajdin Batic'
                    ]
                },
                players: ['David Rudleuski', 'Pierre Hill', 'Edin Murtezic', 'Ajdin Batic', 'Kossal Alassmar'],
                restingPlayers: {
                    1: 'Kossal Alassmar',
                    2: 'Edin Murtezic',
                    3: 'Ajdin Batic', 
                    4: 'David Rudleuski',
                    5: 'Pierre Hill'
                }
            },
            dam1: {
                weeks: {
                    1: [
                        'Linnéa Leandersson & Magdalena Nilsson',
                        'Catharina Park & Cindy Goldschmidt',
                        'Ulrika Johansson & Mia Burghardt',
                        'Karin Nyberg & Linda FalkBoman',
                        'Anna Andersson & Malin Bräddhult',
                        'Sofia Svensson & Eva Månsson'
                    ],
                    2: [
                        'Linda FalkBoman & Magdalena Nilsson',
                        'Karin Nyberg & Mia Burghardt',
                        'Anna Andersson & Linnéa Leandersson',
                        'Sofia Svensson & Ulrika Johansson',
                        'Catharina Park & Malin Bräddhult',
                        'Cindy Goldschmidt & Eva Månsson'
                    ],
                    3: [
                        'Karin Nyberg & Sofia Svensson',
                        'Catharina Park & Magdalena Nilsson',
                        'Malin Bräddhult & Ulrika Johansson',
                        'Anna Andersson & Eva Månsson',
                        'Cindy Goldschmidt & Mia Burghardt',
                        'Linda FalkBoman & Linnéa Leandersson'
                    ],
                    4: [
                        'Linnéa Leandersson & Ulrika Johansson',
                        'Linda FalkBoman & Sofia Svensson',
                        'Catharina Park & Eva Månsson',
                        'Anna Andersson & Cindy Goldschmidt',
                        'Karin Nyberg & Magdalena Nilsson',
                        'Malin Bräddhult & Mia Burghardt'
                    ],
                    5: [
                        'Catharina Park & Linnéa Leandersson',
                        'Anna Andersson & Sofia Svensson',
                        'Magdalena Nilsson & Malin Bräddhult',
                        'Eva Månsson & Karin Nyberg',
                        'Linda FalkBoman & Mia Burghardt',
                        'Cindy Goldschmidt & Ulrika Johansson'
                    ]
                },
                players: ['Linnéa Leandersson', 'Magdalena Nilsson', 'Catharina Park', 'Cindy Goldschmidt', 'Ulrika Johansson', 'Mia Burghardt', 'Karin Nyberg', 'Linda FalkBoman', 'Anna Andersson', 'Malin Bräddhult', 'Sofia Svensson', 'Eva Månsson']
            },
            dam2: {
                weeks: {
                    1: [
                        'Ajsa Elezovic & Mai Khan Vo',
                        'Anna P & Maria Petersson',
                        'Harisa Santic & Emilia Andersson',
                        'Erika Falk & Ina Rudleuskaya',
                        'Valeska Blomberg & Amanda Johansson',
                        'Gunilla Ljungkvist & Madeleine Remnehöjd'
                    ],
                    2: [
                        'Madeleine Remnehöjd & Amanda Johansson',
                        'Ajsa Elezovic & Anna P',
                        'Valeska Blomberg & Gunilla Ljungkvist',
                        'Ina Rudleuskaya & Emilia Andersson',
                        'Erika Falk & Mai Khan Vo',
                        'Harisa Santic & Maria Petersson'
                    ],
                    3: [
                        'Emilia Andersson & Erika Falk',
                        'Ajsa Elezovic & Ina Rudleuskaya',
                        'Gunilla Ljungkvist & Amanda Johansson',
                        'Maria Petersson & Mai Khan Vo',
                        'Harisa Santic & Anna P',
                        'Madeleine Remnehöjd & Valeska Blomberg'
                    ],
                    4: [
                        'Ina Rudleuskaya & Anna P',
                        'Emilia Andersson & Gunilla Ljungkvist',
                        'Harisa Santic & Valeska Blomberg',
                        'Maria Petersson & Madeleine Remnehöjd',
                        'Erika Falk & Ajsa Elezovic',
                        'Mai Khan Vo & Amanda Johansson'
                    ],
                    5: [
                        'Emilia Andersson & Madeleine Remnehöjd',
                        'Amanda Johansson & Erika Falk',
                        'Valeska Blomberg & Maria Petersson',
                        'Gunilla Ljungkvist & Ajsa Elezovic',
                        'Anna P & Mai Khan Vo',
                        'Ina Rudleuskaya & Harisa Santic'
                    ]
                },
                players: ['Ajsa Elezovic', 'Mai Khan Vo', 'Anna P', 'Maria Petersson', 'Harisa Santic', 'Emilia Andersson', 'Erika Falk', 'Ina Rudleuskaya', 'Valeska Blomberg', 'Amanda Johansson', 'Gunilla Ljungkvist', 'Madeleine Remnehöjd']
            }
        };

        // Data structure to store all match results
        let matchData = {
            'herr1': [],
            'herr2': [],
            'dam1': [],
            'dam2': []
        };

        // Navigation functions
        function showScheduleView() {
            hideAllViews();
            document.getElementById('schedule-view').style.display = 'block';
            document.getElementById('page-title').textContent = 'Spelschema';
            document.getElementById('division-tabs').style.display = 'none';
            setActiveNavButton(0);
        }

        function showResultsView() {
            hideAllViews();
            document.getElementById('results-view').style.display = 'block';
            document.getElementById('page-title').textContent = 'Poängtabell';
            document.getElementById('division-tabs').style.display = 'flex';
            setActiveNavButton(1);
        }

        function showRankingView() {
            hideAllViews();
            document.getElementById('results-view').style.display = 'block';
            document.getElementById('page-title').textContent = 'Ranking';
            document.getElementById('division-tabs').style.display = 'flex';
            setActiveNavButton(2);
        }

        function showStatsView() {
            hideAllViews();
            document.getElementById('results-view').style.display = 'block';
            document.getElementById('page-title').textContent = 'Statistik';
            document.getElementById('division-tabs').style.display = 'flex';
            setActiveNavButton(3);
        }

        function hideAllViews() {
            document.querySelectorAll('.content-view').forEach(view => {
                view.style.display = 'none';
            });
        }

        function setActiveNavButton(index) {
            document.querySelectorAll('.nav-button').forEach((btn, i) => {
                if (i === index) {
                    btn.classList.add('active');
                } else {
                    btn.classList.remove('active');
                }
            });
        }

        // Initialize results view on page load
        window.onload = function() {
            // Move existing content to results view
            const resultsView = document.getElementById('results-view');
            const existingContent = document.querySelectorAll('#herr1, #dam1');
            existingContent.forEach(content => {
                resultsView.appendChild(content);
            });
            
            showResultsView();
            
            // Load data safely
            matchData = loadData();
            
            // Update all tables
            updateAllStandings();
            updateAllResults();
        };

        // Safe localStorage operations with fallback
        function saveData() {
            try {
                localStorage.setItem('padelMatchData', JSON.stringify(matchData));
            } catch (error) {
                console.warn('localStorage inte tillgängligt:', error.message);
                // Data sparas bara i minnet under sessionen
            }
        }

        function loadData() {
            try {
                const savedData = localStorage.getItem('padelMatchData');
                if (savedData) {
                    return JSON.parse(savedData);
                }
            } catch (error) {
                console.warn('Kan inte läsa från localStorage:', error.message);
            }
            return {
                'herr1': [],
                'herr2': [],
                'dam1': [],
                'dam2': []
            };
        }

        // Show division
        function showDivision(division) {
            // Hide all division content
            document.querySelectorAll('.division-content').forEach(div => {
                div.classList.remove('active');
            });
            
            // Hide all tabs
            document.querySelectorAll('.division-tab').forEach(tab => {
                tab.classList.remove('active');
            });
            
            // Show selected division
            document.getElementById(division).classList.add('active');
            event.target.classList.add('active');

            // Hide any open dropdowns
            document.querySelectorAll('.team-dropdown').forEach(dropdown => {
                dropdown.style.display = 'none';
            });
        }

        // Update team dropdowns based on selected division and week
        function updateTeamDropdowns(category) {
            // Clear existing dropdowns
            document.getElementById(`teamA-${category}`).value = '';
            document.getElementById(`teamB-${category}`).value = '';
        }

        // Show team dropdown based on selected week and division
        function showTeamDropdown(category, team) {
            const divisionSelect = document.getElementById(`${category}-division`);
            const weekSelect = document.getElementById(`week-${category}`);
            const division = divisionSelect.value;
            const week = weekSelect.value;
            const dropdown = document.getElementById(`dropdown-${category}-${team}`);
            const teams = teamData[division].weeks[week] || [];
            
            // Clear dropdown
            dropdown.innerHTML = '';
            
            // Add team options
            teams.forEach(teamName => {
                const option = document.createElement('div');
                option.className = 'team-option';
                option.textContent = teamName;
                option.onclick = () => selectTeam(category, team, teamName);
                dropdown.appendChild(option);
            });
            
            // Hide other dropdowns
            document.querySelectorAll('.team-dropdown').forEach(d => {
                if (d !== dropdown) d.style.display = 'none';
            });
            
            // Show/hide current dropdown
            dropdown.style.display = dropdown.style.display === 'block' ? 'none' : 'block';
        }

        // Select team
        function selectTeam(category, team, teamName) {
            document.getElementById(`team${team}-${category}`).value = teamName;
            document.getElementById(`dropdown-${category}-${team}`).style.display = 'none';
        }

        // Hide dropdowns when clicking outside
        document.addEventListener('click', function(event) {
            if (!event.target.closest('.team-selection')) {
                document.querySelectorAll('.team-dropdown').forEach(dropdown => {
                    dropdown.style.display = 'none';
                });
            }
        });

        // Calculate who wins a set based on gem score
        function calculateSetWinner(gemsA, gemsB) {
            const a = parseInt(gemsA);
            const b = parseInt(gemsB);
            if (a > b) return 'A';
            if (b > a) return 'B';
            return 'tie'; // shouldn't happen in padel
        }

        // Submit match result
        function submitMatch(category) {
            const divisionSelect = document.getElementById(`${category}-division`);
            const weekSelect = document.getElementById(`week-${category}`);
            const division = divisionSelect.value;
            const week = weekSelect.value;
            const teamA = document.getElementById(`teamA-${category}`).value.trim();
            const teamB = document.getElementById(`teamB-${category}`).value.trim();
            const set1 = document.getElementById(`set1-${category}`).value.trim();
            const set2 = document.getElementById(`set2-${category}`).value.trim();
            const set3 = document.getElementById(`set3-${category}`).value.trim();

            // Validation
            if (!teamA || !teamB) {
                showAlert(category, 'Vänligen välj båda lagen.', 'error');
                return;
            }

            if (teamA === teamB) {
                showAlert(category, 'Ett lag kan inte spela mot sig själv.', 'error');
                return;
            }

            if (!set1 || !set2 || !set3) {
                showAlert(category, 'Vänligen fyll i gem-resultat för alla tre set.', 'error');
                return;
            }

            // Parse and validate set scores
            const sets = [set1, set2, set3];
            let parsedSets = [];
            let setsWonA = 0;
            let setsWonB = 0;

            for (let i = 0; i < 3; i++) {
                const setScore = sets[i];
                if (!setScore.includes('-')) {
                    showAlert(category, `Set ${i + 1}: Använd format som 6-4`, 'error');
                    return;
                }
                
                const [gemsA, gemsB] = setScore.split('-');
                const winner = calculateSetWinner(gemsA, gemsB);
                
                if (winner === 'A') setsWonA++;
                else if (winner === 'B') setsWonB++;

                parsedSets.push({ 
                    gemsA: gemsA.trim(), 
                    gemsB: gemsB.trim(),
                    winner: winner
                });
            }

            // Calculate total points (2 points per set won)
            const pointsA = setsWonA * 2;
            const pointsB = setsWonB * 2;
            const setResult = `${setsWonA}-${setsWonB}`;

            // Get match time
            const matchTime = getMatchTime(division, week);

            // Create match object
            const match = {
                id: Date.now(),
                division: division,
                week: parseInt(week),
                teamA,
                teamB,
                sets: parsedSets,
                setsWonA: setsWonA,
                setsWonB: setsWonB,
                setResult: setResult,
                pointsA: pointsA,
                pointsB: pointsB,
                matchTime,
                timestamp: new Date().toLocaleString('sv-SE')
            };

            // Add to data
            matchData[division].push(match);
            saveData();

            // Update displays
            updateAllStandings();
            updateAllResults();

            // Clear form
            clearForm(category);

            // Show success message
            showAlert(category, 'Match rapporterad framgångsrikt!', 'success');
        }

        // Get match time based on division and week
        function getMatchTime(division, week) {
            const times = {
                herr1: '18:00',
                herr2: '18:00',
                dam1: {1: '16:30', 2: '18:00', 3: '16:30', 4: '18:00', 5: '16:30'},
                dam2: {1: '18:00', 2: '16:30', 3: '18:00', 4: '16:30', 5: '18:00'}
            };
            
            const divisionTimes = times[division];
            if (typeof divisionTimes === 'string') {
                return divisionTimes;
            } else if (typeof divisionTimes === 'object') {
                return divisionTimes[week] || '18:00';
            }
            return '18:00';
        }

        // Clear form
        function clearForm(category) {
            document.getElementById(`teamA-${category}`).value = '';
            document.getElementById(`teamB-${category}`).value = '';
            document.getElementById(`set1-${category}`).value = '';
            document.getElementById(`set2-${category}`).value = '';
            document.getElementById(`set3-${category}`).value = '';
        }

        // Show alert
        function showAlert(category, message, type) {
            const alertDiv = document.getElementById(`alert-${category}`);
            alertDiv.className = type === 'success' ? 'alert alert-success' : 'alert alert-error';
            alertDiv.textContent = message;
            alertDiv.style.display = 'block';
            
            setTimeout(() => {
                alertDiv.style.display = 'none';
            }, 3000);
        }

        // Update all standings
        function updateAllStandings() {
            ['herr1', 'herr2', 'dam1', 'dam2'].forEach(division => {
                updateStandings(division);
            });
        }

        // Update all results
        function updateAllResults() {
            filterResults('herr');
            filterResults('dam');
        }

        // Update standings for a specific division
        function updateStandings(division) {
            const standings = {};
            const players = teamData[division].players;

            // Initialize all players
            players.forEach(player => {
                standings[player] = {
                    player: player,
                    matches: 0,
                    setsWon: 0,
                    setsLost: 0,
                    points: 0
                };
            });

            // Calculate stats for each match
            matchData[division].forEach(match => {
                // Extract players from team names
                const playersA = match.teamA.split(' & ');
                const playersB = match.teamB.split(' & ');

                // Update match count for all players
                [...playersA, ...playersB].forEach(player => {
                    if (standings[player]) {
                        standings[player].matches++;
                    }
                });

                // Update sets won/lost and points based on match result
                playersA.forEach(player => {
                    if (standings[player]) {
                        standings[player].setsWon += match.setsWonA;
                        standings[player].setsLost += match.setsWonB;
                        standings[player].points += match.pointsA;
                    }
                });

                playersB.forEach(player => {
                    if (standings[player]) {
                        standings[player].setsWon += match.setsWonB;
                        standings[player].setsLost += match.setsWonA;
                        standings[player].points += match.pointsB;
                    }
                });
            });

            // Convert to array and sort by points (descending), then by sets difference
            const sortedStandings = Object.values(standings).sort((a, b) => {
                if (b.points !== a.points) return b.points - a.points;
                return (b.setsWon - b.setsLost) - (a.setsWon - a.setsLost);
            });

            // Update table
            const tbody = document.querySelector(`#standings-${division} tbody`);
            tbody.innerHTML = '';

            sortedStandings.forEach((player, index) => {
                const row = tbody.insertRow();
                const position = index + 1;
                let positionClass = 'position-other';
                if (position === 1) positionClass = 'position-1';
                else if (position === 2) positionClass = 'position-2';
                else if (position === 3) positionClass = 'position-3';

                row.innerHTML = `
                    <td class="position-cell">
                        <div class="position-badge ${positionClass}">${position}</div>
                    </td>
                    <td class="player-name">${player.player}</td>
                    <td>${player.matches}</td>
                    <td class="wins">${player.setsWon}</td>
                    <td class="losses">${player.setsLost}</td>
                    <td class="points-cell">${player.points}</td>
                `;
            });
        }

        // Filter and update results table
        function filterResults(category) {
            const weekFilter = document.getElementById(`weekFilter-${category}`).value;
            const tbody = document.querySelector(`#results-${category} tbody`);
            tbody.innerHTML = '';

            // Get all matches for this category (herr or dam)
            let allMatches = [];
            if (category === 'herr') {
                allMatches = [...matchData.herr1, ...matchData.herr2];
            } else if (category === 'dam') {
                allMatches = [...matchData.dam1, ...matchData.dam2];
            }

            // Filter by week if selected
            let filteredMatches = allMatches;
            if (weekFilter !== 'all') {
                filteredMatches = allMatches.filter(match => match.week === parseInt(weekFilter));
            }

            // Sort by timestamp (newest first)
            filteredMatches.sort((a, b) => b.timestamp.localeCompare(a.timestamp));

            // Add rows to table
            filteredMatches.forEach(match => {
                const row = tbody.insertRow();
                const divisionName = match.division === 'herr1' ? 'Herr Div 1' : 
                                   match.division === 'herr2' ? 'Herr Div 2' :
                                   match.division === 'dam1' ? 'Dam Div 1' : 'Dam Div 2';
                
                row.innerHTML = `
                    <td>Vecka ${match.week}</td>
                    <td>${divisionName}</td>
                    <td>${match.teamA}</td>
                    <td>${match.teamB}</td>
                    <td>${match.sets[0].gemsA}-${match.sets[0].gemsB}</td>
                    <td>${match.sets[1].gemsA}-${match.sets[1].gemsB}</td>
                    <td>${match.sets[2].gemsA}-${match.sets[2].gemsB}</td>
                    <td><strong>${match.setResult}</strong></td>
                    <td>${match.pointsA}</td>
                    <td>${match.pointsB}</td>
                    <td>${match.matchTime}</td>
                `;
            });
        }
    </script>
</body>
</html>

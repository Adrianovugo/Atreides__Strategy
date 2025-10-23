# Atreides__Strategy
"Site oficial da Atreides-Strategy-painel de investimentos"
<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>AtreidesStrategy - Painel de Investimentos</title>
    <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        :root {
            --primary-color: #1a472a;
            --secondary-color: #2a623d;
            --accent-color: #5d8c5a;
            --light-color: #f5f5f5;
            --dark-color: #333;
        }
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        body {
            background-color: #f0f2f5;
            color: var(--dark-color);
        }
        
        .container {
            max-width: 1400px;
            margin: 0 auto;
            padding: 20px;
        }
        
        header {
            background: linear-gradient(135deg, var(--primary-color), var(--secondary-color));
            color: white;
            padding: 15px 0;
            box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
        }
        
        .header-content {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }
        
        .logo-container {
            display: flex;
            align-items: center;
            gap: 15px;
        }
        
        .logo {
            width: 60px;
            height: 60px;
            background: linear-gradient(135deg, #fff, #e8f5e8);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-weight: bold;
            font-size: 24px;
            color: var(--primary-color);
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
            border: 2px solid white;
        }
        
        .logo-text h1 {
            font-size: 28px;
            font-weight: 700;
            margin-bottom: 5px;
        }
        
        .logo-text p {
            font-size: 14px;
            opacity: 0.9;
        }
        
        nav ul {
            display: flex;
            list-style: none;
        }
        
        nav ul li {
            margin-left: 20px;
        }
        
        nav ul li a {
            color: white;
            text-decoration: none;
            font-weight: 500;
            padding: 8px 15px;
            border-radius: 4px;
            transition: background-color 0.3s;
        }
        
        nav ul li a:hover, nav ul li a.active {
            background-color: rgba(255, 255, 255, 0.2);
        }
        
        .social-links {
            display: flex;
            gap: 15px;
            margin-left: 30px;
        }
        
        .social-links a {
            color: white;
            font-size: 20px;
            transition: transform 0.3s;
        }
        
        .social-links a:hover {
            transform: translateY(-3px);
        }
        
        .dashboard {
            margin-top: 30px;
        }
        
        .dashboard-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 30px;
        }
        
        .dashboard-title h2 {
            font-size: 24px;
            color: var(--primary-color);
        }
        
        .dashboard-title p {
            color: #666;
        }
        
        .date-filter select {
            padding: 8px 15px;
            border: 1px solid #ddd;
            border-radius: 4px;
            background-color: white;
        }
        
        .cards {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 20px;
            margin-bottom: 30px;
        }
        
        .card {
            background-color: white;
            border-radius: 8px;
            padding: 20px;
            box-shadow: 0 2px 4px rgba(0, 0, 0, 0.05);
            transition: transform 0.3s, box-shadow 0.3s;
        }
        
        .card:hover {
            transform: translateY(-5px);
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
        }
        
        .card-title {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 15px;
        }
        
        .card-title h3 {
            font-size: 16px;
            color: #666;
        }
        
        .card-value {
            font-size: 24px;
            font-weight: 700;
            color: var(--primary-color);
        }
        
        .card-change {
            display: flex;
            align-items: center;
            font-size: 14px;
            margin-top: 5px;
        }
        
        .positive {
            color: #2ecc71;
        }
        
        .negative {
            color: #e74c3c;
        }
        
        .charts {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(500px, 1fr));
            gap: 30px;
            margin-bottom: 30px;
        }
        
        .chart-container {
            background-color: white;
            border-radius: 8px;
            padding: 20px;
            box-shadow: 0 2px 4px rgba(0, 0, 0, 0.05);
        }
        
        .chart-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 20px;
        }
        
        .chart-header h3 {
            font-size: 18px;
            color: var(--primary-color);
        }
        
        .chart-wrapper {
            position: relative;
            height: 300px;
        }
        
        footer {
            background-color: var(--primary-color);
            color: white;
            text-align: center;
            padding: 30px 0;
            margin-top: 50px;
        }
        
        .footer-content {
            display: flex;
            flex-direction: column;
            align-items: center;
            gap: 20px;
        }
        
        .footer-logo {
            display: flex;
            align-items: center;
            gap: 10px;
            margin-bottom: 10px;
        }
        
        .footer-logo .logo {
            width: 40px;
            height: 40px;
            font-size: 18px;
        }
        
        .footer-logo h3 {
            font-size: 20px;
        }
        
        .footer-social {
            display: flex;
            gap: 20px;
            margin: 15px 0;
        }
        
        .footer-social a {
            color: white;
            font-size: 24px;
            transition: transform 0.3s;
        }
        
        .footer-social a:hover {
            transform: translateY(-3px);
        }
        
        .footer-links {
            display: flex;
            gap: 30px;
            margin-top: 20px;
        }
        
        .footer-links a {
            color: white;
            text-decoration: none;
            transition: opacity 0.3s;
        }
        
        .footer-links a:hover {
            opacity: 0.8;
        }
        
        .copyright {
            margin-top: 20px;
            font-size: 14px;
            opacity: 0.8;
        }
        
        @media (max-width: 768px) {
            .charts {
                grid-template-columns: 1fr;
            }
            
            .header-content {
                flex-direction: column;
                text-align: center;
                gap: 15px;
            }
            
            nav ul {
                margin-top: 15px;
                justify-content: center;
                flex-wrap: wrap;
            }
            
            nav ul li {
                margin: 5px 10px;
            }
            
            .social-links {
                margin-left: 0;
                justify-content: center;
            }
            
            .footer-links {
                flex-direction: column;
                gap: 15px;
            }
        }
    </style>
</head>
<body>
    <header>
        <div class="container">
            <div class="header-content">
                <div class="logo-container">
                    <div class="logo">AS</div>
                    <div class="logo-text">
                        <h1>AtreidesStrategy</h1>
                        <p>Investimentos Inteligentes</p>
                    </div>
                </div>
                
                <nav>
                    <ul>
                        <li><a href="#" class="active">Dashboard</a></li>
                        <li><a href="#">Investimentos</a></li>
                        <li><a href="#">Agronegócio</a></li>
                        <li><a href="#">Relatórios</a></li>
                        <li><a href="#">Contato</a></li>
                    </ul>
                </nav>
                
                <div class="social-links">
                    <a href="https://youtube.com/@atreides_strategy?si=YmtXGQ37H6339GvG" target="_blank" title="YouTube">
                        <i class="fab fa-youtube"></i>
                    </a>
                    <a href="https://www.instagram.com/atreides_estrategy?igsh=MXY1ZHN3YTJyZXB6OA==" target="_blank" title="Instagram">
                        <i class="fab fa-instagram"></i>
                    </a>
                </div>
            </div>
        </div>
    </header>
    
    <div class="container">
        <section class="dashboard">
            <div class="dashboard-header">
                <div class="dashboard-title">
                    <h2>Painel de Investimentos</h2>
                    <p>Visão geral dos investimentos e desempenho do portfólio</p>
                </div>
                <div class="date-filter">
                    <select id="period-select">
                        <option value="7d">Últimos 7 dias</option>
                        <option value="30d" selected>Últimos 30 dias</option>
                        <option value="90d">Últimos 90 dias</option>
                        <option value="1y">Último ano</option>
                    </select>
                </div>
            </div>
            
            <div class="cards">
                <div class="card">
                    <div class="card-title">
                        <h3>Valor do Portfólio</h3>
                        <span>📈</span>
                    </div>
                    <div class="card-value">R$ 12.458.320</div>
                    <div class="card-change positive">+3.2% (R$ 385.420)</div>
                </div>
                
                <div class="card">
                    <div class="card-title">
                        <h3>CDB + CDI</h3>
                        <span>🏦</span>
                    </div>
                    <div class="card-value">R$ 4.250.000</div>
                    <div class="card-change positive">+1.8% (R$ 75.200)</div>
                </div>
                
                <div class="card">
                    <div class="card-title">
                        <h3>Terras & Fazendas</h3>
                        <span>🌾</span>
                    </div>
                    <div class="card-value">R$ 5.780.000</div>
                    <div class="card-change positive">+4.5% (R$ 248.900)</div>
                </div>
                
                <div class="card">
                    <div class="card-title">
                        <h3>Agronegócio</h3>
                        <span>🚜</span>
                    </div>
                    <div class="card-value">R$ 2.428.320</div>
                    <div class="card-change positive">+2.7% (R$ 63.320)</div>
                </div>
            </div>
            
            <div class="charts">
                <div class="chart-container">
                    <div class="chart-header">
                        <h3>Performance CDB vs CDI</h3>
                    </div>
                    <div class="chart-wrapper">
                        <canvas id="cdbCdiChart"></canvas>
                    </div>
                </div>
                
                <div class="chart-container">
                    <div class="chart-header">
                        <h3>Investimento em Terras e Fazendas</h3>
                    </div>
                    <div class="chart-wrapper">
                        <canvas id="landInvestmentChart"></canvas>
                    </div>
                </div>
                
                <div class="chart-container">
                    <div class="chart-header">
                        <h3>Distribuição de Investimentos no Agronegócio</h3>
                    </div>
                    <div class="chart-wrapper">
                        <canvas id="agroDistributionChart"></canvas>
                    </div>
                </div>
                
                <div class="chart-container">
                    <div class="chart-header">
                        <h3>Rentabilidade por Segmento</h3>
                    </div>
                    <div class="chart-wrapper">
                        <canvas id="profitabilityChart"></canvas>
                    </div>
                </div>
            </div>
        </section>
    </div>
    
    <footer>
        <div class="container">
            <div class="footer-content">
                <div class="footer-logo">
                    <div class="logo">AS</div>
                    <h3>AtreidesStrategy</h3>
                </div>
                
                <p>Investimentos inteligentes para um futuro próspero</p>
                
                <div class="footer-social">
                    <a href="https://youtube.com/@atreides_strategy?si=YmtXGQ37H6339GvG" target="_blank" title="YouTube">
                        <i class="fab fa-youtube"></i>
                    </a>
                    <a href="https://www.instagram.com/atreides_estrategy?igsh=MXY1ZHN3YTJyZXB6OA==" target="_blank" title="Instagram">
                        <i class="fab fa-instagram"></i>
                    </a>
                </div>
                
                <div class="footer-links">
                    <a href="#">Home</a>
                    <a href="#">Sobre Nós</a>
                    <a href="#">Serviços</a>
                    <a href="#">Investimentos</a>
                    <a href="#">Contato</a>
                </div>
                
                <div class="copyright">
                    &copy; 2023 AtreidesStrategy. Todos os direitos reservados.
                </div>
            </div>
        </div>
    </footer>

    <script>
        // Dados para os gráficos
        const months = ['Jan', 'Fev', 'Mar', 'Abr', 'Mai', 'Jun', 'Jul', 'Ago', 'Set', 'Out', 'Nov', 'Dez'];
        const regions = ['Centro-Oeste', 'Sudeste', 'Sul', 'Norte', 'Nordeste'];
        const agroSegments = ['Grãos', 'Bovinos', 'Equinos', 'Florestas', 'Outros'];
        
        // Gerar dados aleatórios
        const generateData = (points, startValue, volatility, trend = 0) => {
            const data = [];
            let value = startValue;
            for (let i = 0; i < points; i++) {
                value = value * (1 + (Math.random() * volatility * 2 - volatility) + trend);
                data.push(value);
            }
            return data;
        };
        
        // Gráfico CDB vs CDI
        new Chart(document.getElementById('cdbCdiChart'), {
            type: 'line',
            data: {
                labels: months,
                datasets: [
                    {
                        label: 'CDB',
                        data: generateData(12, 1000000, 0.02, 0.005),
                        borderColor: '#1a472a',
                        backgroundColor: 'rgba(26, 71, 42, 0.1)',
                        tension: 0.3,
                        fill: true
                    },
                    {
                        label: 'CDI',
                        data: generateData(12, 1000000, 0.015, 0.003),
                        borderColor: '#2a623d',
                        backgroundColor: 'rgba(42, 98, 61, 0.1)',
                        tension: 0.3,
                        fill: true
                    }
                ]
            },
            options: {
                responsive: true,
                maintainAspectRatio: false,
                plugins: {
                    legend: { position: 'top' },
                    tooltip: {
                        callbacks: {
                            label: function(context) {
                                return context.dataset.label + ': R$ ' + context.parsed.y.toLocaleString('pt-BR');
                            }
                        }
                    }
                },
                scales: {
                    y: {
                        beginAtZero: false,
                        ticks: {
                            callback: function(value) {
                                return 'R$ ' + (value / 1000).toFixed(0) + 'K';
                            }
                        }
                    }
                }
            }
        });
        
        // Gráfico de Investimento em Terras
        new Chart(document.getElementById('landInvestmentChart'), {
            type: 'bar',
            data: {
                labels: regions,
                datasets: [{
                    label: 'Valor Investido (R$)',
                    data: [1850000, 1520000, 980000, 750000, 680000],
                    backgroundColor: [
                        'rgba(26, 71, 42, 0.7)',
                        'rgba(42, 98, 61, 0.7)',
                        'rgba(93, 140, 90, 0.7)',
                        'rgba(139, 175, 117, 0.7)',
                        'rgba(189, 215, 166, 0.7)'
                    ],
                    borderColor: [
                        'rgb(26, 71, 42)',
                        'rgb(42, 98, 61)',
                        'rgb(93, 140, 90)',
                        'rgb(139, 175, 117)',
                        'rgb(189, 215, 166)'
                    ],
                    borderWidth: 1
                }]
            },
            options: {
                responsive: true,
                maintainAspectRatio: false,
                plugins: {
                    legend: { display: false },
                    tooltip: {
                        callbacks: {
                            label: function(context) {
                                return 'Valor: R$ ' + context.parsed.y.toLocaleString('pt-BR');
                            }
                        }
                    }
                },
                scales: {
                    y: {
                        beginAtZero: true,
                        ticks: {
                            callback: function(value) {
                                return 'R$ ' + (value / 1000).toFixed(0) + 'K';
                            }
                        }
                    }
                }
            }
        });
        
        // Gráfico de Distribuição do Agronegócio
        new Chart(document.getElementById('agroDistributionChart'), {
            type: 'doughnut',
            data: {
                labels: agroSegments,
                datasets: [{
                    data: [45, 25, 15, 10, 5],
                    backgroundColor: [
                        'rgba(26, 71, 42, 0.7)',
                        'rgba(42, 98, 61, 0.7)',
                        'rgba(93, 140, 90, 0.7)',
                        'rgba(139, 175, 117, 0.7)',
                        'rgba(189, 215, 166, 0.7)'
                    ],
                    borderWidth: 1
                }]
            },
            options: {
                responsive: true,
                maintainAspectRatio: false,
                plugins: {
                    legend: { position: 'right' },
                    tooltip: {
                        callbacks: {
                            label: function(context) {
                                return context.label + ': ' + context.parsed + '%';
                            }
                        }
                    }
                }
            }
        });
        
        // Gráfico de Rentabilidade por Segmento
        new Chart(document.getElementById('profitabilityChart'), {
            type: 'bar',
            data: {
                labels: ['CDB/CDI', 'Terras', 'Grãos', 'Bovinos', 'Equinos'],
                datasets: [{
                    label: 'Rentabilidade (%)',
                    data: [4.2, 6.8, 8.5, 7.2, 5.9],
                    backgroundColor: 'rgba(26, 71, 42, 0.7)',
                    borderColor: 'rgb(26, 71, 42)',
                    borderWidth: 1
                }]
            },
            options: {
                responsive: true,
                maintainAspectRatio: false,
                plugins: {
                    legend: { display: false },
                    tooltip: {
                        callbacks: {
                            label: function(context) {
                                return 'Rentabilidade: ' + context.parsed.y + '%';
                            }
                        }
                    }
                },
                scales: {
                    y: {
                        beginAtZero: true,
                        ticks: {
                            callback: function(value) {
                                return value + '%';
                            }
                        }
                    }
                }
            }
        });
        
        // Filtro de período
        document.getElementById('period-select').addEventListener('change', function() {
            alert('Período alterado para: ' + this.options[this.selectedIndex].text);
            // Em uma aplicação real, aqui você atualizaria os dados dos gráficos
        });
    </script>
</body>
</html>

<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>StockPro - Sistema de Gestão de Estoque</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        :root {
            --primary: #4361ee;
            --primary-dark: #3a56d4;
            --secondary: #7209b7;
            --success: #4cc9f0;
            --warning: #f72585;
            --danger: #e63946;
            --light: #f8f9fa;
            --dark: #212529;
            --gray: #6c757d;
            --border: #dee2e6;
            --sidebar: #2b2d42;
            --card-bg: #ffffff;
            --hover: #f1f3f9;
        }
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        body {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: var(--dark);
            line-height: 1.6;
            min-height: 100vh;
            padding: 20px;
        }
        
        .app-container {
            display: flex;
            max-width: 1400px;
            margin: 0 auto;
            background: var(--card-bg);
            border-radius: 20px;
            box-shadow: 0 15px 30px rgba(0, 0, 0, 0.1);
            overflow: hidden;
            min-height: 90vh;
        }
        
        /* Sidebar */
        .sidebar {
            width: 260px;
            background: var(--sidebar);
            color: white;
            padding: 30px 0;
            transition: all 0.3s;
        }
        
        .logo {
            display: flex;
            align-items: center;
            gap: 12px;
            padding: 0 25px 25px;
            border-bottom: 1px solid rgba(255,255,255,0.1);
            margin-bottom: 25px;
        }
        
        .logo-icon {
            font-size: 28px;
            background: var(--primary);
            width: 45px;
            height: 45px;
            border-radius: 12px;
            display: flex;
            align-items: center;
            justify-content: center;
        }
        
        .logo h1 {
            font-size: 22px;
            font-weight: 700;
        }
        
        .nav-menu {
            list-style: none;
            padding: 0 15px;
        }
        
        .nav-item {
            margin-bottom: 8px;
        }
        
        .nav-link {
            display: flex;
            align-items: center;
            gap: 15px;
            padding: 14px 15px;
            color: rgba(255,255,255,0.8);
            text-decoration: none;
            border-radius: 12px;
            transition: all 0.3s;
            font-weight: 500;
            cursor: pointer;
        }
        
        .nav-link:hover {
            background: rgba(255,255,255,0.1);
            color: white;
            transform: translateX(5px);
        }
        
        .nav-link.active {
            background: var(--primary);
            color: white;
            box-shadow: 0 5px 15px rgba(67, 97, 238, 0.3);
        }
        
        .nav-link i {
            font-size: 18px;
            width: 20px;
            text-align: center;
        }
        
        /* Main Content */
        .main-content {
            flex: 1;
            padding: 30px;
            background: var(--light);
            overflow-y: auto;
        }
        
        .header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 30px;
        }
        
        .page-title h1 {
            font-size: 28px;
            color: var(--dark);
            margin-bottom: 5px;
        }
        
        .page-title p {
            color: var(--gray);
            font-size: 16px;
        }
        
        .user-info {
            display: flex;
            align-items: center;
            gap: 15px;
            background: white;
            padding: 10px 20px;
            border-radius: 50px;
            box-shadow: 0 5px 15px rgba(0,0,0,0.05);
        }
        
        .user-avatar {
            width: 45px;
            height: 45px;
            background: var(--primary);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-weight: bold;
            font-size: 18px;
        }
        
        /* Stats Grid */
        .stats-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(240px, 1fr));
            gap: 20px;
            margin-bottom: 30px;
        }
        
        .stat-card {
            background: white;
            padding: 25px;
            border-radius: 16px;
            box-shadow: 0 5px 15px rgba(0,0,0,0.05);
            display: flex;
            align-items: center;
            gap: 20px;
            transition: transform 0.3s, box-shadow 0.3s;
        }
        
        .stat-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 25px rgba(0,0,0,0.1);
        }
        
        .stat-icon {
            width: 60px;
            height: 60px;
            border-radius: 12px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 24px;
        }
        
        .stat-icon.products {
            background: rgba(67, 97, 238, 0.1);
            color: var(--primary);
        }
        
        .stat-icon.low-stock {
            background: rgba(247, 37, 133, 0.1);
            color: var(--warning);
        }
        
        .stat-icon.movements {
            background: rgba(76, 201, 240, 0.1);
            color: var(--success);
        }
        
        .stat-info h3 {
            font-size: 14px;
            color: var(--gray);
            margin-bottom: 5px;
        }
        
        .stat-number {
            font-size: 28px;
            font-weight: 700;
            color: var(--dark);
            margin-bottom: 5px;
        }
        
        .stat-description {
            font-size: 13px;
            color: var(--gray);
        }
        
        /* Content Grid */
        .content-grid {
            display: grid;
            grid-template-columns: 2fr 1fr;
            gap: 25px;
        }
        
        .panel {
            background: white;
            border-radius: 16px;
            box-shadow: 0 5px 15px rgba(0,0,0,0.05);
            overflow: hidden;
        }
        
        .panel-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 20px 25px;
            border-bottom: 1px solid var(--border);
        }
        
        .panel-title {
            font-size: 18px;
            font-weight: 600;
            color: var(--dark);
        }
        
        .panel-actions {
            display: flex;
            gap: 10px;
        }
        
        .btn {
            padding: 10px 20px;
            border: none;
            border-radius: 10px;
            cursor: pointer;
            font-weight: 600;
            display: flex;
            align-items: center;
            gap: 8px;
            transition: all 0.3s;
            font-size: 14px;
        }
        
        .btn-primary {
            background: var(--primary);
            color: white;
        }
        
        .btn-primary:hover {
            background: var(--primary-dark);
            transform: translateY(-2px);
            box-shadow: 0 5px 15px rgba(67, 97, 238, 0.3);
        }
        
        .btn-outline {
            background: transparent;
            border: 1px solid var(--border);
            color: var(--dark);
        }
        
        .btn-outline:hover {
            background: var(--hover);
        }
        
        .panel-body {
            padding: 25px;
        }
        
        /* Products List */
        .products-list {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(220px, 1fr));
            gap: 20px;
        }
        
        .product-card {
            border: 1px solid var(--border);
            border-radius: 12px;
            padding: 20px;
            transition: all 0.3s;
            position: relative;
            overflow: hidden;
        }
        
        .product-card:hover {
            border-color: var(--primary);
            box-shadow: 0 5px 15px rgba(0,0,0,0.08);
            transform: translateY(-3px);
        }
        
        .product-card.critical {
            border-left: 4px solid var(--danger);
        }
        
        .product-card.low-stock {
            border-left: 4px solid var(--warning);
        }
        
        .product-header {
            display: flex;
            justify-content: space-between;
            align-items: flex-start;
            margin-bottom: 15px;
        }
        
        .product-name {
            font-weight: 600;
            color: var(--dark);
            font-size: 16px;
            margin-bottom: 5px;
        }
        
        .product-code {
            font-size: 12px;
            color: var(--gray);
            background: var(--hover);
            padding: 3px 8px;
            border-radius: 20px;
            display: inline-block;
        }
        
        .product-category {
            font-size: 13px;
            color: var(--gray);
            margin-bottom: 15px;
        }
        
        .product-stock {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }
        
        .stock-info {
            font-size: 24px;
            font-weight: 700;
            color: var(--dark);
        }
        
        .stock-label {
            font-size: 12px;
            color: var(--gray);
        }
        
        .stock-actions {
            display: flex;
            gap: 8px;
        }
        
        .stock-btn {
            width: 36px;
            height: 36px;
            border: none;
            border-radius: 8px;
            cursor: pointer;
            display: flex;
            align-items: center;
            justify-content: center;
            font-weight: bold;
            transition: all 0.3s;
        }
        
        .stock-in {
            background: var(--success);
            color: white;
        }
        
        .stock-in:hover {
            background: #3ab0d6;
            transform: scale(1.1);
        }
        
        .stock-out {
            background: var(--danger);
            color: white;
        }
        
        .stock-out:hover {
            background: #c1121f;
            transform: scale(1.1);
        }
        
        /* Movements List */
        .movements-list {
            max-height: 400px;
            overflow-y: auto;
        }
        
        .movement-item {
            padding: 18px 0;
            border-bottom: 1px solid var(--border);
            display: flex;
            align-items: center;
            gap: 15px;
        }
        
        .movement-item:last-child {
            border-bottom: none;
        }
        
        .movement-icon {
            width: 40px;
            height: 40px;
            border-radius: 10px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 16px;
        }
        
        .movement-icon.entrada {
            background: rgba(76, 201, 240, 0.1);
            color: var(--success);
        }
        
        .movement-icon.saida {
            background: rgba(230, 57, 70, 0.1);
            color: var(--danger);
        }
        
        .movement-details {
            flex: 1;
        }
        
        .movement-product {
            font-weight: 600;
            color: var(--dark);
            margin-bottom: 4px;
        }
        
        .movement-date {
            font-size: 12px;
            color: var(--gray);
            margin-bottom: 4px;
        }
        
        .movement-user {
            font-size: 13px;
            color: var(--gray);
        }
        
        .movement-quantity {
            font-weight: 700;
            font-size: 16px;
        }
        
        .movement-quantity.entrada {
            color: var(--success);
        }
        
        .movement-quantity.saida {
            color: var(--danger);
        }
        
        /* Lista de Produtos */
        .products-table {
            width: 100%;
            border-collapse: collapse;
        }
        
        .products-table th {
            background: var(--hover);
            padding: 15px;
            text-align: left;
            font-weight: 600;
            color: var(--dark);
            border-bottom: 2px solid var(--border);
        }
        
        .products-table td {
            padding: 15px;
            border-bottom: 1px solid var(--border);
        }
        
        .products-table tr:hover {
            background: var(--hover);
        }
        
        .stock-badge {
            padding: 4px 10px;
            border-radius: 20px;
            font-size: 12px;
            font-weight: 600;
        }
        
        .stock-badge.normal {
            background: rgba(76, 201, 240, 0.1);
            color: var(--success);
        }
        
        .stock-badge.low {
            background: rgba(247, 37, 133, 0.1);
            color: var(--warning);
        }
        
        .stock-badge.critical {
            background: rgba(230, 57, 70, 0.1);
            color: var(--danger);
        }
        
        /* Modal */
        .modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0,0,0,0.5);
            z-index: 1000;
            align-items: center;
            justify-content: center;
            backdrop-filter: blur(5px);
        }
        
        .modal-content {
            background: white;
            padding: 30px;
            border-radius: 20px;
            width: 90%;
            max-width: 500px;
            box-shadow: 0 20px 40px rgba(0,0,0,0.1);
            transform: translateY(20px);
            opacity: 0;
            transition: all 0.3s;
        }
        
        .modal.show .modal-content {
            transform: translateY(0);
            opacity: 1;
        }
        
        .modal-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 25px;
        }
        
        .modal-title {
            font-size: 22px;
            color: var(--dark);
            font-weight: 600;
        }
        
        .close-modal {
            background: none;
            border: none;
            font-size: 24px;
            cursor: pointer;
            color: var(--gray);
            transition: color 0.3s;
        }
        
        .close-modal:hover {
            color: var(--dark);
        }
        
        .form-group {
            margin-bottom: 20px;
        }
        
        label {
            display: block;
            margin-bottom: 8px;
            font-weight: 600;
            color: var(--dark);
        }
        
        input, select {
            width: 100%;
            padding: 12px 15px;
            border: 1px solid var(--border);
            border-radius: 10px;
            font-size: 16px;
            transition: border 0.3s;
        }
        
        input:focus, select:focus {
            border-color: var(--primary);
            outline: none;
            box-shadow: 0 0 0 3px rgba(67, 97, 238, 0.1);
        }
        
        .form-actions {
            display: flex;
            justify-content: flex-end;
            gap: 15px;
            margin-top: 25px;
        }
        
        .btn-cancel {
            background: var(--gray);
            color: white;
        }
        
        .btn-cancel:hover {
            background: #5a6268;
        }
        
        /* Empty States */
        .empty-state {
            text-align: center;
            padding: 40px 20px;
            color: var(--gray);
        }
        
        .empty-state i {
            font-size: 48px;
            margin-bottom: 15px;
            color: var(--border);
        }
        
        /* Alertas */
        .alert-banner {
            background: linear-gradient(135deg, var(--warning), #ff6b9d);
            color: white;
            padding: 15px 25px;
            border-radius: 12px;
            margin-bottom: 25px;
            display: flex;
            align-items: center;
            gap: 15px;
            box-shadow: 0 5px 15px rgba(247, 37, 133, 0.3);
        }
        
        .alert-banner i {
            font-size: 24px;
        }
        
        .alert-banner.critical {
            background: linear-gradient(135deg, var(--danger), #ff4757);
        }
        
        /* Seções ocultas */
        .section {
            display: none;
        }
        
        .section.active {
            display: block;
        }
        
        /* Responsive */
        @media (max-width: 1024px) {
            .content-grid {
                grid-template-columns: 1fr;
            }
        }
        
        @media (max-width: 768px) {
            body {
                padding: 10px;
            }
            
            .app-container {
                flex-direction: column;
            }
            
            .sidebar {
                width: 100%;
                padding: 20px;
            }
            
            .stats-grid {
                grid-template-columns: 1fr;
            }
            
            .products-list {
                grid-template-columns: 1fr;
            }
        }
    </style>
</head>
<body>
    <div class="app-container">
        <!-- Sidebar -->
        <nav class="sidebar">
            <div class="logo">
                <div class="logo-icon">
                    <i class="fas fa-boxes"></i>
                </div>
                <h1>StockPro</h1>
            </div>
            <ul class="nav-menu">
                <li class="nav-item">
                    <a class="nav-link active" data-section="dashboard">
                        <i class="fas fa-tachometer-alt"></i>
                        <span>Dashboard</span>
                    </a>
                </li>
                <li class="nav-item">
                    <a class="nav-link" data-section="products-list">
                        <i class="fas fa-list"></i>
                        <span>Listar Produtos</span>
                    </a>
                </li>
                <li class="nav-item">
                    <a class="nav-link" id="new-product-btn">
                        <i class="fas fa-plus-circle"></i>
                        <span>Adicionar Produto</span>
                    </a>
                </li>
                <li class="nav-item">
                    <a class="nav-link" id="new-movement-btn">
                        <i class="fas fa-exchange-alt"></i>
                        <span>Nova Movimentação</span>
                    </a>
                </li>
                <li class="nav-item">
                    <a class="nav-link" data-section="stock-in">
                        <i class="fas fa-arrow-down"></i>
                        <span>Entrada de Estoque</span>
                    </a>
                </li>
                <li class="nav-item">
                    <a class="nav-link" data-section="stock-out">
                        <i class="fas fa-arrow-up"></i>
                        <span>Saída de Estoque</span>
                    </a>
                </li>
                <li class="nav-item">
                    <a class="nav-link" data-section="low-stock">
                        <i class="fas fa-exclamation-triangle"></i>
                        <span>Estoque Baixo</span>
                    </a>
                </li>
                <li class="nav-item">
                    <a class="nav-link" data-section="reports">
                        <i class="fas fa-chart-bar"></i>
                        <span>Relatórios</span>
                    </a>
                </li>
            </ul>
        </nav>
        
        <!-- Main Content -->
        <main class="main-content">
            <!-- Dashboard Section -->
            <section id="dashboard" class="section active">
                <div class="header">
                    <div class="page-title">
                        <h1>Dashboard</h1>
                        <p>Visão geral do seu estoque em tempo real</p>
                    </div>
                    <div class="user-info">
                        <div class="user-avatar">E</div>
                        <div>
                            <div style="font-weight: 600;">Esterio Lima Ramos</div>
                            <div style="font-size: 13px; color: var(--gray);">Administrador</div>
                        </div>
                    </div>
                </div>
                
                <!-- Alertas de Estoque Baixo -->
                <div id="alerts-container"></div>
                
                <!-- Stats Grid -->
                <div class="stats-grid">
                    <div class="stat-card">
                        <div class="stat-icon products">
                            <i class="fas fa-box-open"></i>
                        </div>
                        <div class="stat-info">
                            <h3>Total de Produtos</h3>
                            <div class="stat-number" id="total-products">8</div>
                            <div class="stat-description">produtos cadastrados</div>
                        </div>
                    </div>
                    
                    <div class="stat-card">
                        <div class="stat-icon low-stock">
                            <i class="fas fa-exclamation-triangle"></i>
                        </div>
                        <div class="stat-info">
                            <h3>Estoque Baixo</h3>
                            <div class="stat-number" id="low-stock-count">2</div>
                            <div class="stat-description">produtos com estoque baixo</div>
                        </div>
                    </div>
                    
                    <div class="stat-card">
                        <div class="stat-icon movements">
                            <i class="fas fa-exchange-alt"></i>
                        </div>
                        <div class="stat-info">
                            <h3>Movimentações Hoje</h3>
                            <div class="stat-number" id="today-movements">0</div>
                            <div class="stat-description">movimentações hoje</div>
                        </div>
                    </div>
                </div>
                
                <!-- Content Grid -->
                <div class="content-grid">
                    <!-- Products Section -->
                    <section class="panel">
                        <div class="panel-header">
                            <h2 class="panel-title">Produtos em Estoque</h2>
                            <div class="panel-actions">
                                <button class="btn btn-outline">
                                    <i class="fas fa-filter"></i>
                                    Filtrar
                                </button>
                                <button class="btn btn-primary" id="add-product-btn-dash">
                                    <i class="fas fa-plus"></i>
                                    Novo Produto
                                </button>
                            </div>
                        </div>
                        <div class="panel-body">
                            <div class="products-list" id="products-container">
                                <!-- Products will be loaded here by JavaScript -->
                            </div>
                        </div>
                    </section>
                    
                    <!-- Movements Section -->
                    <section class="panel">
                        <div class="panel-header">
                            <h2 class="panel-title">Movimentações Recentes</h2>
                            <div class="panel-actions">
                                <button class="btn btn-primary" id="add-movement-btn-dash">
                                    <i class="fas fa-plus"></i>
                                    Nova Movimentação
                                </button>
                            </div>
                        </div>
                        <div class="panel-body">
                            <div class="movements-list" id="movements-container">
                                <!-- Movements will be loaded here by JavaScript -->
                            </div>
                        </div>
                    </section>
                </div>
            </section>

            <!-- Lista de Produtos Section -->
            <section id="products-list" class="section">
                <div class="header">
                    <div class="page-title">
                        <h1>Lista de Produtos</h1>
                        <p>Gerencie todos os produtos do seu estoque</p>
                    </div>
                    <div class="user-info">
                        <div class="user-avatar">E</div>
                        <div>
                            <div style="font-weight: 600;">Esterio Lima Ramos</div>
                            <div style="font-size: 13px; color: var(--gray);">Administrador</div>
                        </div>
                    </div>
                </div>

                <div class="panel">
                    <div class="panel-header">
                        <h2 class="panel-title">Todos os Produtos</h2>
                        <div class="panel-actions">
                            <button class="btn btn-primary" id="add-product-btn-list">
                                <i class="fas fa-plus"></i>
                                Novo Produto
                            </button>
                        </div>
                    </div>
                    <div class="panel-body">
                        <table class="products-table">
                            <thead>
                                <tr>
                                    <th>Produto</th>
                                    <th>Código</th>
                                    <th>Categoria</th>
                                    <th>Estoque</th>
                                    <th>Mínimo</th>
                                    <th>Status</th>
                                    <th>Ações</th>
                                </tr>
                            </thead>
                            <tbody id="products-table-body">
                                <!-- Products table will be loaded here -->
                            </tbody>
                        </table>
                    </div>
                </div>
            </section>

            <!-- Estoque Baixo Section -->
            <section id="low-stock" class="section">
                <div class="header">
                    <div class="page-title">
                        <h1>Estoque Baixo</h1>
                        <p>Produtos que precisam de atenção</p>
                    </div>
                    <div class="user-info">
                        <div class="user-avatar">E</div>
                        <div>
                            <div style="font-weight: 600;">Esterio Lima Ramos</div>
                            <div style="font-size: 13px; color: var(--gray);">Administrador</div>
                        </div>
                    </div>
                </div>

                <div class="panel">
                    <div class="panel-header">
                        <h2 class="panel-title">Produtos com Estoque Baixo</h2>
                    </div>
                    <div class="panel-body">
                        <div id="low-stock-container">
                            <!-- Low stock products will be loaded here -->
                        </div>
                    </div>
                </div>
            </section>

            <!-- Outras seções (simplificadas) -->
            <section id="stock-in" class="section">
                <div class="header">
                    <div class="page-title">
                        <h1>Entrada de Estoque</h1>
                        <p>Registre entradas de produtos</p>
                    </div>
                </div>
                <div class="panel">
                    <div class="panel-body">
                        <p>Funcionalidade de entrada de estoque em desenvolvimento.</p>
                    </div>
                </div>
            </section>

            <section id="stock-out" class="section">
                <div class="header">
                    <div class="page-title">
                        <h1>Saída de Estoque</h1>
                        <p>Registre saídas de produtos</p>
                    </div>
                </div>
                <div class="panel">
                    <div class="panel-body">
                        <p>Funcionalidade de saída de estoque em desenvolvimento.</p>
                    </div>
                </div>
            </section>

            <section id="reports" class="section">
                <div class="header">
                    <div class="page-title">
                        <h1>Relatórios</h1>
                        <p>Relatórios e análises do estoque</p>
                    </div>
                </div>
                <div class="panel">
                    <div class="panel-body">
                        <p>Funcionalidade de relatórios em desenvolvimento.</p>
                    </div>
                </div>
            </section>
        </main>
    </div>
    
    <!-- New Product Modal -->
    <div class="modal" id="product-modal">
        <div class="modal-content">
            <div class="modal-header">
                <h3 class="modal-title">Adicionar Novo Produto</h3>
                <button class="close-modal">&times;</button>
            </div>
            <form id="product-form">
                <div class="form-group">
                    <label for="product-name">Nome do Produto</label>
                    <input type="text" id="product-name" required placeholder="Ex: Fita Isolante">
                </div>
                <div class="form-group">
                    <label for="product-code">Código</label>
                    <input type="text" id="product-code" placeholder="Ex: AA2">
                </div>
                <div class="form-group">
                    <label for="product-category">Categoria</label>
                    <select id="product-category">
                        <option value="Geral">Geral</option>
                        <option value="Ferramentas">Ferramentas</option>
                        <option value="Materiais">Materiais</option>
                        <option value="Equipamentos">Equipamentos</option>
                    </select>
                </div>
                <div class="form-group">
                    <label for="product-stock">Estoque Inicial</label>
                    <input type="number" id="product-stock" value="0" min="0">
                </div>
                <div class="form-group">
                    <label for="product-min-stock">Estoque Mínimo</label>
                    <input type="number" id="product-min-stock" value="5" min="0">
                </div>
                <div class="form-actions">
                    <button type="button" class="btn btn-cancel close-modal">Cancelar</button>
                    <button type="submit" class="btn btn-primary">
                        <i class="fas fa-plus"></i>
                        Adicionar Produto
                    </button>
                </div>
            </form>
        </div>
    </div>
    
    <!-- New Movement Modal -->
    <div class="modal" id="movement-modal">
        <div class="modal-content">
            <div class="modal-header">
                <h3 class="modal-title">Nova Movimentação</h3>
                <button class="close-modal">&times;</button>
            </div>
            <form id="movement-form">
                <div class="form-group">
                    <label for="movement-product">Produto</label>
                    <select id="movement-product" required>
                        <option value="">Selecione um produto</option>
                    </select>
                </div>
                <div class="form-group">
                    <label for="movement-type">Tipo de Movimentação</label>
                    <select id="movement-type" required>
                        <option value="entrada">Entrada</option>
                        <option value="saida">Saída</option>
                    </select>
                </div>
                <div class="form-group">
                    <label for="movement-quantity">Quantidade</label>
                    <input type="number" id="movement-quantity" required min="1" value="1">
                </div>
                <div class="form-group">
                    <label for="movement-reason">Motivo</label>
                    <input type="text" id="movement-reason" placeholder="Ex: Compra, Venda, Ajuste">
                </div>
                <div class="form-actions">
                    <button type="button" class="btn btn-cancel close-modal">Cancelar</button>
                    <button type="submit" class="btn btn-primary">
                        <i class="fas fa-exchange-alt"></i>
                        Registrar Movimentação
                    </button>
                </div>
            </form>
        </div>
    </div>

    <script>
        // Sample data
        let products = JSON.parse(localStorage.getItem('products')) || [
            { id: 1, name: "Fita Isolante", code: "AA2", category: "Geral", stock: 2, minStock: 6 },
            { id: 2, name: "Cola", code: "h1", category: "Geral", stock: 1, minStock: 5 },
            { id: 3, name: "Furadeira", code: "F001", category: "Ferramentas", stock: 3, minStock: 2 },
            { id: 4, name: "Caixa de Ferramentas", code: "CF01", category: "Ferramentas", stock: 5, minStock: 3 },
            { id: 5, name: "Parafusos", code: "P001", category: "Materiais", stock: 100, minStock: 50 },
            { id: 6, name: "Porcas", code: "P002", category: "Materiais", stock: 80, minStock: 40 },
            { id: 7, name: "Chave de Fenda", code: "CF02", category: "Ferramentas", stock: 4, minStock: 3 },
            { id: 8, name: "Martelo", code: "M001", category: "Ferramentas", stock: 2, minStock: 2 }
        ];

        let movements = JSON.parse(localStorage.getItem('movements')) || [
            { id: 1, productId: 4, productName: "Caixa de Ferramentas", type: "entrada", quantity: 2, date: "2025-10-07T13:59:22", user: "Esterio Lima Ramos", reason: "Compra" },
            { id: 2, productId: 4, productName: "Caixa de Ferramentas", type: "saida", quantity: 1, date: "2025-10-07T13:49:36", user: "Esterio Lima Ramos", reason: "Venda" }
        ];

        // Initialize the application
        document.addEventListener('DOMContentLoaded', function() {
            initializeApp();
            renderDashboard();
            checkAlerts();
        });

        function initializeApp() {
            // Navigation
            const navLinks = document.querySelectorAll('.nav-link[data-section]');
            const sections = document.querySelectorAll('.section');
            
            navLinks.forEach(link => {
                link.addEventListener('click', function() {
                    const sectionId = this.getAttribute('data-section');
                    
                    // Update active nav link
                    navLinks.forEach(l => l.classList.remove('active'));
                    this.classList.add('active');
                    
                    // Show selected section
                    sections.forEach(section => section.classList.remove('active'));
                    document.getElementById(sectionId).classList.add('active');
                    
                    // Load section content
                    if (sectionId === 'products-list') {
                        renderProductsTable();
                    } else if (sectionId === 'low-stock') {
                        renderLowStock();
                    } else if (sectionId === 'dashboard') {
                        renderDashboard();
                    }
                });
            });

            // Modal functionality
            const productModal = document.getElementById('product-modal');
            const movementModal = document.getElementById('movement-modal');
            const closeButtons = document.querySelectorAll('.close-modal');
            
            // Open product modal from multiple places
            document.getElementById('add-product-btn').addEventListener('click', function() {
                showModal(productModal);
            });
            
            document.getElementById('add-product-btn-dash').addEventListener('click', function() {
                showModal(productModal);
            });
            
            document.getElementById('add-product-btn-list').addEventListener('click', function() {
                showModal(productModal);
            });
            
            // Open movement modal from multiple places
            document.getElementById('add-movement-btn').addEventListener('click', function() {
                updateProductSelect();
                showModal(movementModal);
            });
            
            document.getElementById('add-movement-btn-dash').addEventListener('click', function() {
                updateProductSelect();
                showModal(movementModal);
            });
            
            // Close modals
            closeButtons.forEach(button => {
                button.addEventListener('click', function() {
                    hideModal(productModal);
                    hideModal(movementModal);
                });
            });
            
            // Close modal when clicking outside
            window.addEventListener('click', function(e) {
                if (e.target === productModal) {
                    hideModal(productModal);
                }
                if (e.target === movementModal) {
                    hideModal(movementModal);
                }
            });
            
            // Form submissions
            document.getElementById('product-form').addEventListener('submit', function(e) {
                e.preventDefault();
                addProduct();
            });
            
            document.getElementById('movement-form').addEventListener('submit', function(e) {
                e.preventDefault();
                addMovement();
            });
        }

        function showModal(modal) {
            modal.style.display = 'flex';
            setTimeout(() => {
                modal.classList.add('show');
            }, 10);
        }

        function hideModal(modal) {
            modal.classList.remove('show');
            setTimeout(() => {
                modal.style.display = 'none';
            }, 300);
        }

        function renderDashboard() {
            renderProducts();
            renderMovements();
            updateStats();
            checkAlerts();
        }

        function renderProducts() {
            const container = document.getElementById('products-container');
            container.innerHTML = '';
            
            if (products.length === 0) {
                container.innerHTML = `
                    <div class="empty-state">
                        <i class="fas fa-box-open"></i>
                        <h3>Nenhum produto cadastrado</h3>
                        <p>Adicione seu primeiro produto para começar</p>
                    </div>
                `;
                return;
            }
            
            // Show only 6 products on dashboard
            const displayProducts = products.slice(0, 6);
            
            displayProducts.forEach(product => {
                const productCard = document.createElement('div');
                productCard.className = 'product-card';
                
                // Add class for low stock
                if (product.stock === 0) {
                    productCard.classList.add('critical');
                } else if (product.stock < product.minStock) {
                    productCard.classList.add('low-stock');
                }
                
                productCard.innerHTML = `
                    <div class="product-header">
                        <div>
                            <div class="product-name">${product.name}</div>
                            <div class="product-code">${product.code}</div>
                        </div>
                    </div>
                    <div class="product-category">Categoria: ${product.category}</div>
                    <div class="product-stock">
                        <div>
                            <div class="stock-info">${product.stock}</div>
                            <div class="stock-label">unidades</div>
                        </div>
                        <div class="stock-actions">
                            <button class="stock-btn stock-in" data-id="${product.id}">
                                <i class="fas fa-plus"></i>
                            </button>
                            <button class="stock-btn stock-out" data-id="${product.id}">
                                <i class="fas fa-minus"></i>
                            </button>
                        </div>
                    </div>
                `;
                
                container.appendChild(productCard);
            });
            
            // Add event listeners to stock buttons
            document.querySelectorAll('.stock-in').forEach(button => {
                button.addEventListener('click', function() {
                    const productId = parseInt(this.getAttribute('data-id'));
                    quickStockUpdate(productId, 1);
                });
            });
            
            document.querySelectorAll('.stock-out').forEach(button => {
                button.addEventListener('click', function() {
                    const productId = parseInt(this.getAttribute('data-id'));
                    quickStockUpdate(productId, -1);
                });
            });
        }

        function renderProductsTable() {
            const container = document.getElementById('products-table-body');
            container.innerHTML = '';
            
            if (products.length === 0) {
                container.innerHTML = `
                    <tr>
                        <td colspan="7" style="text-align: center; padding: 40px;">
                            <div class="empty-state">
                                <i class="fas fa-box-open"></i>
                                <h3>Nenhum produto cadastrado</h3>
                                <p>Adicione seu primeiro produto para começar</p>
                            </div>
                        </td>
                    </tr>
                `;
                return;
            }
            
            products.forEach(product => {
                const row = document.createElement('tr');
                
                // Determine stock status
                let statusClass = 'normal';
                let statusText = 'Normal';
                
                if (product.stock === 0) {
                    statusClass = 'critical';
                    statusText = 'Crítico';
                } else if (product.stock < product.minStock) {
                    statusClass = 'low';
                    statusText = 'Baixo';
                }
                
                row.innerHTML = `
                    <td>
                        <div style="font-weight: 600;">${product.name}</div>
                    </td>
                    <td>${product.code}</td>
                    <td>${product.category}</td>
                    <td>${product.stock}</td>
                    <td>${product.minStock}</td>
                    <td>
                        <span class="stock-badge ${statusClass}">${statusText}</span>
                    </td>
                    <td>
                        <div style="display: flex; gap: 8px;">
                            <button class="stock-btn stock-in" data-id="${product.id}" title="Adicionar estoque">
                                <i class="fas fa-plus"></i>
                            </button>
                            <button class="stock-btn stock-out" data-id="${product.id}" title="Remover estoque">
                                <i class="fas fa-minus"></i>
                            </button>
                        </div>
                    </td>
                `;
                
                container.appendChild(row);
            });
            
            // Add event listeners to stock buttons in table
            document.querySelectorAll('#products-table-body .stock-in').forEach(button => {
                button.addEventListener('click', function() {
                    const productId = parseInt(this.getAttribute('data-id'));
                    quickStockUpdate(productId, 1);
                });
            });
            
            document.querySelectorAll('#products-table-body .stock-out').forEach(button => {
                button.addEventListener('click', function() {
                    const productId = parseInt(this.getAttribute('data-id'));
                    quickStockUpdate(productId, -1);
                });
            });
        }

        function renderLowStock() {
            const container = document.getElementById('low-stock-container');
            container.innerHTML = '';
            
            const lowStockProducts = products.filter(p => p.stock < p.minStock);
            
            if (lowStockProducts.length === 0) {
                container.innerHTML = `
                    <div class="empty-state">
                        <i class="fas fa-check-circle"></i>
                        <h3>Nenhum produto com estoque baixo</h3>
                        <p>Todos os produtos estão com estoque adequado</p>
                    </div>
                `;
                return;
            }
            
            lowStockProducts.forEach(product => {
                const productCard = document.createElement('div');
                productCard.className = 'product-card critical';
                
                const status = product.stock === 0 ? 'ESGOTADO' : 'ESTOQUE BAIXO';
                const statusClass = product.stock === 0 ? 'critical' : 'low-stock';
                
                productCard.innerHTML = `
                    <div class="product-header">
                        <div>
                            <div class="product-name">${product.name}</div>
                            <div class="product-code">${product.code}</div>
                        </div>
                        <span class="stock-badge ${statusClass}">${status}</span>
                    </div>
                    <div class="product-category">Categoria: ${product.category}</div>
                    <div class="product-stock">
                        <div>
                            <div class="stock-info">${product.stock}</div>
                            <div class="stock-label">unidades (mínimo: ${product.minStock})</div>
                        </div>
                        <div class="stock-actions">
                            <button class="stock-btn stock-in" data-id="${product.id}">
                                <i class="fas fa-plus"></i>
                            </button>
                            <button class="stock-btn stock-out" data-id="${product.id}" ${product.stock === 0 ? 'disabled' : ''}>
                                <i class="fas fa-minus"></i>
                            </button>
                        </div>
                    </div>
                `;
                
                container.appendChild(productCard);
            });
            
            // Add event listeners to stock buttons
            document.querySelectorAll('#low-stock-container .stock-in').forEach(button => {
                button.addEventListener('click', function() {
                    const productId = parseInt(this.getAttribute('data-id'));
                    quickStockUpdate(productId, 1);
                });
            });
            
            document.querySelectorAll('#low-stock-container .stock-out').forEach(button => {
                button.addEventListener('click', function() {
                    const productId = parseInt(this.getAttribute('data-id'));
                    quickStockUpdate(productId, -1);
                });
            });
        }

        function renderMovements() {
            const container = document.getElementById('movements-container');
            container.innerHTML = '';
            
            // Sort movements by date (newest first)
            const sortedMovements = [...movements].sort((a, b) => new Date(b.date) - new Date(a.date));
            
            // Show only the 5 most recent movements
            const recentMovements = sortedMovements.slice(0, 5);
            
            if (recentMovements.length === 0) {
                container.innerHTML = `
                    <div class="empty-state">
                        <i class="fas fa-exchange-alt"></i>
                        <h3>Nenhuma movimentação</h3>
                        <p>Registre a primeira movimentação</p>
                    </div>
                `;
                return;
            }
            
            recentMovements.forEach(movement => {
                const movementItem = document.createElement('div');
                movementItem.className = 'movement-item';
                
                const date = new Date(movement.date);
                const formattedDate = date.toLocaleDateString('pt-BR') + ', ' + date.toLocaleTimeString('pt-BR', {hour: '2-digit', minute: '2-digit'});
                
                movementItem.innerHTML = `
                    <div class="movement-icon ${movement.type}">
                        <i class="fas fa-${movement.type === 'entrada' ? 'arrow-down' : 'arrow-up'}"></i>
                    </div>
                    <div class="movement-details">
                        <div class="movement-product">${movement.productName}</div>
                        <div class="movement-date">${formattedDate}</div>
                        <div class="movement-user">Por: ${movement.user}</div>
                    </div>
                    <div class="movement-quantity ${movement.type}">
                        ${movement.type === 'entrada' ? '+' : '-'}${movement.quantity}
                    </div>
                `;
                
                container.appendChild(movementItem);
            });
        }

        function updateStats() {
            // Update total products
            document.getElementById('total-products').textContent = products.length;
            
            // Update low stock count
            const lowStockCount = products.filter(p => p.stock < p.minStock).length;
            document.getElementById('low-stock-count').textContent = lowStockCount;
            
            // Update today's movements
            const today = new Date().toDateString();
            const todayMovements = movements.filter(m => {
                const movementDate = new Date(m.date).toDateString();
                return movementDate === today;
            }).length;
            document.getElementById('today-movements').textContent = todayMovements;
        }

        function checkAlerts() {
            const container = document.getElementById('alerts-container');
            container.innerHTML = '';
            
            const criticalProducts = products.filter(p => p.stock === 0);
            const lowStockProducts = products.filter(p => p.stock > 0 && p.stock < p.minStock);
            
            if (criticalProducts.length > 0) {
                const alert = document.createElement('div');
                alert.className = 'alert-banner critical';
                alert.innerHTML = `
                    <i class="fas fa-exclamation-triangle"></i>
                    <div>
                        <strong>ATENÇÃO CRÍTICA!</strong> ${criticalProducts.length} produto(s) completamente esgotado(s).
                        <div style="font-size: 14px; margin-top: 5px;">
                            ${criticalProducts.map(p => p.name).join(', ')}
                        </div>
                    </div>
                `;
                container.appendChild(alert);
            }
            
            if (lowStockProducts.length > 0) {
                const alert = document.createElement('div');
                alert.className = 'alert-banner';
                alert.innerHTML = `
                    <i class="fas fa-exclamation-circle"></i>
                    <div>
                        <strong>ALERTA DE ESTOQUE BAIXO!</strong> ${lowStockProducts.length} produto(s) com estoque abaixo do mínimo.
                        <div style="font-size: 14px; margin-top: 5px;">
                            ${lowStockProducts.map(p => p.name).join(', ')}
                        </div>
                    </div>
                `;
                container.appendChild(alert);
            }
        }

        function updateProductSelect() {
            const select = document.getElementById('movement-product');
            select.innerHTML = '<option value="">Selecione um produto</option>';
            
            products.forEach(product => {
                const option = document.createElement('option');
                option.value = product.id;
                option.textContent = `${product.name} (${product.stock} em estoque)`;
                select.appendChild(option);
            });
        }

        function addProduct() {
            const name = document.getElementById('product-name').value;
            const code = document.getElementById('product-code').value;
            const category = document.getElementById('product-category').value;
            const stock = parseInt(document.getElementById('product-stock').value) || 0;
            const minStock = parseInt(document.getElementById('product-min-stock').value) || 5;
            
            if (!name) {
                alert('Por favor, insira o nome do produto');
                return;
            }
            
            const newProduct = {
                id: products.length > 0 ? Math.max(...products.map(p => p.id)) + 1 : 1,
                name: name,
                code: code,
                category: category,
                stock: stock,
                minStock: minStock
            };
            
            products.push(newProduct);
            saveData();
            
            // Close modal and reset form
            hideModal(document.getElementById('product-modal'));
            document.getElementById('product-form').reset();
            
            // Update all views
            renderDashboard();
            renderProductsTable();
            renderLowStock();
            
            showNotification('Produto adicionado com sucesso!', 'success');
        }

        function addMovement() {
            const productId = parseInt(document.getElementById('movement-product').value);
            const type = document.getElementById('movement-type').value;
            const quantity = parseInt(document.getElementById('movement-quantity').value);
            const reason = document.getElementById('movement-reason').value;
            
            if (!productId || !quantity || quantity <= 0) {
                alert('Por favor, preencha todos os campos obrigatórios');
                return;
            }
            
            const product = products.find(p => p.id === productId);
            if (!product) {
                alert('Produto não encontrado');
                return;
            }
            
            // Check if there's enough stock for output
            if (type === 'saida' && product.stock < quantity) {
                alert(`Estoque insuficiente! Disponível: ${product.stock}`);
                return;
            }
            
            // Update product stock
            if (type === 'entrada') {
                product.stock += quantity;
            } else {
                product.stock -= quantity;
            }
            
            // Record movement
            const newMovement = {
                id: movements.length > 0 ? Math.max(...movements.map(m => m.id)) + 1 : 1,
                productId: productId,
                productName: product.name,
                type: type,
                quantity: quantity,
                date: new Date().toISOString(),
                user: 'Esterio Lima Ramos',
                reason: reason
            };
            
            movements.unshift(newMovement);
            saveData();
            
            // Close modal and reset form
            hideModal(document.getElementById('movement-modal'));
            document.getElementById('movement-form').reset();
            
            // Update all views
            renderDashboard();
            renderProductsTable();
            renderLowStock();
            
            showNotification('Movimentação registrada com sucesso!', 'success');
        }

        function quickStockUpdate(productId, change) {
            const product = products.find(p => p.id === productId);
            if (!product) return;
            
            // Check if we can remove stock
            if (change < 0 && product.stock < Math.abs(change)) {
                alert(`Estoque insuficiente! Disponível: ${product.stock}`);
                return;
            }
            
            // Update stock
            product.stock += change;
            
            // Record movement
            const newMovement = {
                id: movements.length > 0 ? Math.max(...movements.map(m => m.id)) + 1 : 1,
                productId: productId,
                productName: product.name,
                type: change > 0 ? 'entrada' : 'saida',
                quantity: Math.abs(change),
                date: new Date().toISOString(),
                user: 'Esterio Lima Ramos',
                reason: 'Ajuste rápido'
            };
            
            movements.unshift(newMovement);
            saveData();
            
            // Update all views
            renderDashboard();
            renderProductsTable();
            renderLowStock();
            
            showNotification(`Estoque ${change > 0 ? 'aumentado' : 'reduzido'} com sucesso!`, 'success');
        }

        function showNotification(message, type) {
            // Create notification element
            const notification = document.createElement('div');
            notification.style.cssText = `
                position: fixed;
                top: 20px;
                right: 20px;
                padding: 15px 20px;
                background: ${type === 'success' ? '#4caf50' : '#f44336'};
                color: white;
                border-radius: 8px;
                box-shadow: 0 5px 15px rgba(0,0,0,0.2);
                z-index: 1001;
                transform: translateX(100%);
                transition: transform 0.3s;
            `;
            notification.textContent = message;
            
            document.body.appendChild(notification);
            
            // Animate in
            setTimeout(() => {
                notification.style.transform = 'translateX(0)';
            }, 10);
            
            // Remove after 3 seconds
            setTimeout(() => {
                notification.style.transform = 'translateX(100%)';
                setTimeout(() => {
                    document.body.removeChild(notification);
                }, 300);
            }, 3000);
        }

        function saveData() {
            localStorage.setItem('products', JSON.stringify(products));
            localStorage.setItem('movements', JSON.stringify(movements));
        }
    </script>
</body>
</html>

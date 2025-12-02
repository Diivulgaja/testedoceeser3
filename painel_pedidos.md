<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Doce e Ser | Painel de Pedidos (Tempo Real)</title>
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@400;600;700&display=swap" rel="stylesheet">
    <style>
        /* Estilos CSS (Idênticos ao prompt do Painel para consistência) */
        :root {
            --cor-acento: #e91e63; --cor-fundo: #f8f8f8; --cor-texto: #333;
            --status-novo: #ff6347; --status-prep: #ffc107; --status-saiu: #17a2b8; --status-conc: #28a745;
        }
        body { font-family: 'Poppins', sans-serif; background-color: var(--cor-fundo); color: var(--cor-texto); margin: 0; padding: 20px; }
        .dashboard { max-width: 1400px; margin: auto; }
        .dashboard h1 { color: var(--cor-acento); text-align: center; margin-bottom: 30px; }
        .status-kanban { display: grid; grid-template-columns: repeat(4, 1fr); gap: 20px; }
        .coluna { background: white; padding: 15px; border-radius: 8px; box-shadow: 0 4px 10px rgba(0, 0, 0, 0.05); }
        .coluna h2 { font-size: 1.2em; text-align: center; margin-top: 0; padding-bottom: 10px; border-bottom: 2px solid #eee; color: #666; }
        .pedido-card { background-color: #fffaf0; border: 1px solid #ddd; padding: 15px; margin-bottom: 15px; border-radius: 8px; box-shadow: 0 2px 5px rgba(0, 0, 0, 0.05); }
        .pedido-card.novo { border-left: 5px solid var(--status-novo); }
        .pedido-card.preparacao { border-left: 5px solid var(--status-prep); }
        .pedido-card.entrega { border-left: 5px solid var(--status-saiu); }
        .pedido-card h3 { margin: 0 0 10px; font-size: 1.1em; color: var(--cor-acento); }
        .detalhes-itens { font-size: 0.8em; color: #666; margin-top: 10px; padding-top: 5px; border-top: 1px dashed #eee; }
        .btn-status { color: white; border: none; padding: 8px 10px; margin-top: 10px; border-radius: 5px; cursor: pointer; font-size: 0.9em; width: 100%; }
        .btn-status.prep { background-color: var(--status-prep); }
        .btn-status.saiu { background-color: var(--status-saiu); }
        .btn-status.conc { background-color: var(--status-conc); }
        @media (max-width: 1024px) { .status-kanban { grid-template-columns: repeat(2, 1fr); } }
    </style>
</head>
<body>
    <div class="dashboard">
        <h1>Painel de Pedidos - Doce e Ser (Tempo Real) <button onclick="window.location.href='login.html'" style="float: right; padding: 5px 10px; background-color: #ccc; border: none; cursor: pointer;">Sair</button></h1>

        <div class="status-kanban">
            <div class="coluna">
                <h2>Novo Pedido (Aguardando)</h2>
                <div class="pedido-card novo">
                    <h3>Pedido #1024 - R$ 116,00</h3>
                    <p>Cliente: Ana Silva</p><p>Entrega: Delivery</p><p>Pagamento: **PIX (Aguardando)**</p>
                    <div class="detalhes-itens">Itens: Bolo Cenoura (1), Taça Red Velvet (2)</div>
                    <button class="btn-status prep" onclick="alert('Pedido #1024 movido para EM PREPARAÇÃO. Cliente notificado!')">Aceitar Pedido</button>
                </div>
            </div>
            <div class="coluna">
                <h2>Em Preparação</h2>
                <div class="pedido-card preparacao">
                    <h3>Pedido #1023 - R$ 90,00</h3>
                    <p>Cliente: Carla Rocha</p><p>Entrega: Delivery</p><p>Pagamento: **Cartão Online**</p>
                    <div class="detalhes-itens">Itens: Bolo Baunilha Frutas (1), Café Latte (2)</div>
                    <button class="btn-status saiu" onclick="alert('Pedido #1023 movido para SAIU PARA ENTREGA. Cliente notificado!')">Marcar como Pronto</button>
                </div>
            </div>
            <div class="coluna">
                <h2>Pronto / Saiu para Entrega</h2>
                <div class="pedido-card entrega">
                    <h3>Pedido #1022 - R$ 35,00</h3>
                    <p>Cliente: Pedro Souza</p><p>Entrega: Retirada na Loja</p><p>Pagamento: **Dinheiro (Troco para 50)**</p>
                    <div class="detalhes-itens">Itens: Macarons (1)</div>
                    <button class="btn-status conc" onclick="alert('Pedido #1022 FINALIZADO.')" style="background-color: var(--status-conc);">Concluir</button>
                </div>
            </div>
            <div class="coluna">
                <h2>Concluídos</h2>
                <div class="pedido-card" style="border-left: 5px solid var(--status-conc);">
                    <h3>Pedido #1021 - R$ 78,00</h3><p>Status: Entregue/Retirado</p>
                </div>
            </div>
        </div>
    </div>
</body>
</html>
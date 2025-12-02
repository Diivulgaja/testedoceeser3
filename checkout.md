<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Doce e Ser | Finalizar Pedido</title>
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@400;600&family=Playfair+Display:wght@700&display=swap" rel="stylesheet">
    <style>
        /* Estilos CSS (Idênticos ao prompt de Checkout para manter a consistência) */
        :root { --cor-acento: #e91e63; --cor-fundo: #fdfdff; --cor-texto: #333; --cor-sucesso: #4CAF50; --cor-primaria: #ffccd5;}
        body { font-family: 'Poppins', sans-serif; background-color: var(--cor-fundo); color: var(--cor-texto); margin: 0; padding: 20px; }
        .checkout-container { max-width: 1000px; margin: auto; background: white; padding: 30px; border-radius: 10px; box-shadow: 0 4px 15px rgba(0, 0, 0, 0.1); }
        .checkout-container h2 { font-family: 'Playfair Display', serif; color: var(--cor-acento); border-bottom: 2px solid var(--cor-primaria); padding-bottom: 10px; margin-bottom: 20px; }
        .secoes { display: grid; grid-template-columns: 2fr 1fr; gap: 40px; }
        .revisao-pedido, .metodos-pagamento, .detalhes-entrega { margin-bottom: 30px; padding: 20px; border: 1px solid #eee; border-radius: 8px; }
        .item-carrinho { display: flex; justify-content: space-between; padding: 10px 0; border-bottom: 1px dashed #eee; }
        .total { font-size: 1.5em; font-weight: 600; color: var(--cor-acento); padding-top: 15px; text-align: right; }
        .radio-tile-group { display: flex; flex-wrap: wrap; gap: 10px; margin-bottom: 15px; }
        .radio-tile-group label { flex-grow: 1; background-color: var(--cor-fundo); padding: 15px; border: 1px solid #ccc; border-radius: 8px; text-align: center; cursor: pointer; transition: border-color 0.3s, background-color 0.3s; }
        input[type="radio"]:checked + label { border-color: var(--cor-acento); background-color: var(--cor-primaria); font-weight: 600; }
        input[type="radio"] { display: none; }
        .btn-finalizar { background-color: var(--cor-sucesso); color: white; border: none; padding: 15px; border-radius: 8px; width: 100%; font-size: 1.2em; font-weight: 600; cursor: pointer; margin-top: 20px; }
        .info-pagamento { margin-top: 15px; padding: 10px; border: 1px dashed var(--cor-acento); background-color: var(--cor-primaria); border-radius: 5px; font-size: 0.9em; }
        @media (max-width: 768px) { .secoes { grid-template-columns: 1fr; } }
    </style>
</head>
<body>
    <div class="checkout-container">
        <h2 onclick="window.location.href='index.html'" style="cursor: pointer;">&larr; Finalizar Pedido - Doce e Ser</h2>
        <div class="secoes">
            <div class="coluna-esquerda">
                <div class="detalhes-entrega">
                    <h3>1. Entrega ou Retirada</h3>
                    <div class="radio-tile-group">
                        <input type="radio" id="delivery" name="modo_entrega" checked><label for="delivery">Delivery (R$ 15,00)</label>
                        <input type="radio" id="retirada" name="modo_entrega"><label for="retirada">Retirada na Loja (Grátis)</label>
                    </div>
                    <label for="endereco" style="display: block; margin-top: 15px;">Endereço de Entrega / Observações</label>
                    <textarea id="endereco" rows="3" style="width: 100%; padding: 10px; border: 1px solid #ccc; border-radius: 5px; box-sizing: border-box;" placeholder="Rua, Número, Bairro, CEP."></textarea>
                </div>
                <div class="metodos-pagamento">
                    <h3>2. Forma de Pagamento</h3>
                    <div class="radio-tile-group">
                        <input type="radio" id="pix" name="forma_pagamento" checked><label for="pix">PIX (Online)</label>
                        <input type="radio" id="cartao_online" name="forma_pagamento"><label for="cartao_online">Cartão (Online)</label>
                        <input type="radio" id="cartao_maquina" name="forma_pagamento"><label for="cartao_maquina">Cartão (Na Entrega)</label>
                        <input type="radio" id="dinheiro" name="forma_pagamento"><label for="dinheiro">Dinheiro</label>
                    </div>
                    <div class="info-pagamento">
                        * Se escolher **Dinheiro**, informe o troco necessário nas observações de endereço.
                    </div>
                </div>
            </div>
            <div class="coluna-direita">
                <div class="revisao-pedido">
                    <h3>3. Resumo do Pedido</h3>
                    <div class="item-carrinho"><span>1x Bolo de Cenoura</span> <span>R$ 45,00</span></div>
                    <div class="item-carrinho"><span>2x Taça Red Velvet</span> <span>R$ 56,00</span></div>
                    <div class="item-carrinho"><span>Subtotal</span> <span>R$ 101,00</span></div>
                    <div class="item-carrinho"><span>Taxa de Entrega</span> <span>R$ 15,00</span></div>
                    <div class="total">Total a Pagar: R$ 116,00</div>
                    <button class="btn-finalizar" onclick="alert('Pedido Recebido! O status será atualizado no Painel do Lojista assim que o pagamento for confirmado.'); window.location.href='index.html'">Finalizar e Pagar</button>
                </div>
            </div>
        </div>
    </div>
</body>
</html>
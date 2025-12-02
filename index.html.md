<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Doce & Ser | Cardápio e Pedidos Online (Oficial)</title>
    <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@700&family=Poppins:wght@300;400;600&display=swap" rel="stylesheet">
    <style>
        /* Estilos CSS (Idênticos ao último prompt para manter a consistência visual) */
        :root {
            --cor-primaria: #ffccd5; 
            --cor-secundaria: #f0e68c; 
            --cor-fundo: #fdfdff;
            --cor-texto: #333;
            --cor-acento: #e91e63;
            --cor-sucesso: #4CAF50;
        }

        body { font-family: 'Poppins', sans-serif; background-color: var(--cor-fundo); color: var(--cor-texto); margin: 0; padding-top: 80px; scroll-behavior: smooth; }
        .header { background-color: white; padding: 10px 30px; display: flex; justify-content: space-between; align-items: center; position: fixed; width: 100%; top: 0; z-index: 1000; box-shadow: 0 1px 10px rgba(0, 0, 0, 0.1); }
        .header h1 { font-family: 'Playfair Display', serif; font-size: 2.2em; color: var(--cor-acento); margin: 0; }
        section { padding: 60px 20px; margin: 20px auto; max-width: 1200px; }
        h2 { font-family: 'Playfair Display', serif; font-size: 2.5em; text-align: center; color: var(--cor-acento); margin-bottom: 40px; }
        #hero { background: linear-gradient(135deg, var(--cor-primaria), var(--cor-secundaria)); text-align: center; padding: 100px 20px 80px; margin-top: -20px; }
        .btn-principal { background-color: var(--cor-acento); color: white; padding: 15px 35px; border-radius: 30px; text-decoration: none; font-weight: 600; transition: background-color 0.3s; display: inline-block; margin-top: 20px; }
        .btn-principal:hover { background-color: #d81b60; }
        #beneficios { background-color: #fff; padding-top: 20px; }
        .beneficios-grid { display: flex; justify-content: space-around; text-align: center; gap: 20px; }
        .beneficio-card { max-width: 300px; padding: 20px; border-radius: 10px; border: 1px solid var(--cor-primaria); }
        .beneficio-card h3 { color: var(--cor-sucesso); font-size: 1.2em; }
        .categorias-menu { display: flex; justify-content: center; gap: 15px; margin-bottom: 30px; flex-wrap: wrap; }
        .categorias-menu button { background-color: white; color: var(--cor-acento); border: 2px solid var(--cor-acento); padding: 10px 20px; border-radius: 25px; cursor: pointer; font-weight: 600; }
        .cardapio-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(280px, 1fr)); gap: 30px; }
        .produto-card { background: white; border-radius: 15px; overflow: hidden; box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1); text-align: center; }
        .produto-card img { width: 100%; height: 200px; object-fit: cover; }
        .produto-info { padding: 15px; }
        .produto-info p { min-height: 40px; }
        .preco { font-size: 1.6em; color: var(--cor-sucesso); font-weight: bold; display: block; margin-bottom: 10px; }
        .btn-pedido { background-color: var(--cor-sucesso); color: white; border: none; padding: 12px 25px; border-radius: 25px; cursor: pointer; font-weight: 600; width: 90%; margin-bottom: 10px; }
        #contato { text-align: center; background-color: #f0f0f0; }
        .carrinho-flutuante { position: fixed; bottom: 0; width: 100%; background-color: #333; color: white; padding: 15px 20px; display: none; justify-content: space-between; align-items: center; z-index: 1000; }
        .carrinho-flutuante.ativo { display: flex; }
        .carrinho-flutuante button { background-color: var(--cor-acento); color: white; border: none; padding: 10px 25px; border-radius: 25px; font-weight: bold; cursor: pointer; }
        @media (max-width: 768px) { .header h1 { font-size: 1.8em; } .header .nav { display: none; } .beneficios-grid { flex-direction: column; } }
    </style>
</head>
<body>
    <header class="header"><h1>Doce & Ser</h1><nav class="nav"><a href="#cardapio">Cardápio</a><a href="#beneficios">Por que Pedir Online?</a><a href="#contato">Contato</a></nav></header>
    <section id="hero">
        <h2>Seu Desejo Doce a Um Clique de Distância!</h2>
        <p style="color: #444; font-size: 1.1em; max-width: 700px; margin: 20px auto;">Agora ficou mais fácil e rápido. Navegue pelo nosso cardápio completo, veja fotos e finalize seu pedido em segundos, sem esperar por resposta!</p>
        <a href="#cardapio" class="btn-principal">Comece a Pedir Agora!</a>
    </section>
    <section id="beneficios">
        <h2>Por que Pedir Direto no Nosso Site?</h2>
        <div class="beneficios-grid">
            <div class="beneficio-card"><h3>Agilidade Máxima ⚡</h3><p>O pedido é enviado diretamente para a produção. Zero espera e sem erros de comunicação.</p></div>
            <div class="beneficio-card"><h3>Pagamento Facilitado 💳</h3><p>PIX automático, Cartão Online, ou Pague na Entrega. Você escolhe!</p></div>
            <div class="beneficio-card"><h3>Saber o Status em Tempo Real 📲</h3><p>Acompanhe quando seu pedido entra em preparo e quando sai para entrega.</p></div>
        </div>
    </section>
    <section id="cardapio">
        <h2>Nosso Cardápio Completo</h2>
        <div class="categorias-menu">
            <button class="active" onclick="filtrar('todos')">Todos</button>
            <button onclick="filtrar('bolos')">Bolos</button>
            <button onclick="filtrar('doces-finos')">Doces Finos</button>
            <button onclick="filtrar('sobremesas')">Sobremesas</button>
        </div>
        <div class="cardapio-grid" id="cardapio-grid">
            <div class="produto-card bolos" data-categoria="bolos">
                <img src="" alt="Bolo de Cenoura">
                <div class="produto-info"><h3 style="color: var(--cor-acento);">Bolo de Cenoura Clássico</h3><p>Massa úmida e cobertura de brigadeiro cremoso.</p><span class="preco">R$ 45,00</span><button class="btn-pedido" onclick="adicionarAoCarrinho('Bolo de Cenoura', 45.00)">Adicionar ao Carrinho</button></div>
            </div>
            <div class="produto-card doces-finos" data-categoria="doces-finos">
                <img src="" alt="Brigadeiros Gourmet">
                <div class="produto-info"><h3 style="color: var(--cor-acento);">Caixa de Brigadeiros (12 un.)</h3><p>Sabores especiais: pistache, limão siciliano e chocolate belga.</p><span class="preco">R$ 60,00</span><button class="btn-pedido" onclick="adicionarAoCarrinho('Brigadeiros Gourmet', 60.00)">Adicionar ao Carrinho</button></div>
            </div>
            <div class="produto-card sobremesas" data-categoria="sobremesas">
                <img src="" alt="Torta de Limão">
                <div class="produto-info"><h3 style="color: var(--cor-acento);">Torta de Limão Merengada (Fatia)</h3><p>Recheio azedinho, base crocante e merengue maçaricado.</p><span class="preco">R$ 18,00</span><button class="btn-pedido" onclick="adicionarAoCarrinho('Torta de Limão', 18.00)">Adicionar ao Carrinho</button></div>
            </div>
            <div class="produto-card sobremesas" data-categoria="sobremesas">
                <img src="" alt="Taça Red Velvet">
                <div class="produto-info"><h3 style="color: var(--cor-acento);">Taça Red Velvet</h3><p>Camadas de bolo aveludado e creme de cream cheese.</p><span class="preco">R$ 28,00</span><button class="btn-pedido" onclick="adicionarAoCarrinho('Taça Red Velvet', 28.00)">Adicionar ao Carrinho</button></div>
            </div>
        </div>
    </section>
    <section id="contato">
        <h2>Fácil de Pedir, Fácil de Pagar!</h2>
        <h3 style="color: var(--cor-acento); margin-top: 30px;">Formas de Pagamento Aceitas</h3>
        <p style="font-weight: 600;">Você escolhe no checkout:</p>
        <p>✅ **PIX** | ✅ **Cartão Online** | ✅ **Na Entrega/Retirada**</p>
        <h3 style="color: var(--cor-acento); margin-top: 30px;">Fale Conosco (Suporte)</h3>
        <p>📞 **WhatsApp:** (XX) XXXX-XXXX</p><p>📍 **Endereço da Loja:** [Rua, Bairro]</p>
    </section>
    <div class="carrinho-flutuante" id="carrinho-flutuante">
        <span id="carrinho-texto">0 itens | Total: R$ 0,00</span>
        <button onclick="window.location.href='checkout.html'">Avançar para Checkout</button>
    </div>
    <footer>&copy; 2025 Doce & Ser. Todos os direitos reservados.</footer>
    <script>
        let totalItens = 0; let valorTotal = 0.00;
        const carrinhoFlutuante = document.getElementById('carrinho-flutuante');
        const carrinhoTexto = document.getElementById('carrinho-texto');

        function adicionarAoCarrinho(nome, preco) {
            totalItens++; valorTotal += preco;
            carrinhoTexto.textContent = `${totalItens} item(s) | Total: R$ ${valorTotal.toFixed(2).replace('.', ',')}`;
            carrinhoFlutuante.classList.add('ativo');
            // Nota: Em um site real, isso salvaria os itens em localStorage ou sessionStorage.
        }

        function filtrar(categoria) {
            document.querySelectorAll('.categorias-menu button').forEach(btn => btn.classList.remove('active'));
            event.currentTarget.classList.add('active');
            const produtos = document.querySelectorAll('.produto-card');
            produtos.forEach(produto => {
                const categoriaProduto = produto.getAttribute('data-categoria');
                if (categoria === 'todos' || categoriaProduto === categoria) {
                    produto.style.display = 'grid';
                } else {
                    produto.style.display = 'none';
                }
            });
            document.getElementById('cardapio').scrollIntoView({ behavior: 'smooth' });
        }
    </script>
</body>
</html>
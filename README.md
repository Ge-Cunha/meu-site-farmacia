<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Farmácia Drogaria Gonçalvez</title>
    <link rel="stylesheet" href="styles.css">
    <script>
        function addToCart(productName, productPrice) {
            const cart = document.getElementById('cart-items');
            const cartItem = document.createElement('div');
            cartItem.classList.add('cart-item');
            cartItem.innerHTML = `
                <p>${productName}</p>
                <p>R$ ${productPrice.toFixed(2)}</p>
                <button onclick="removeFromCart(this, ${productPrice.toFixed(2)})">Remover</button>
            `;
            cart.appendChild(cartItem);
            updateTotal(productPrice);
        }

        function removeFromCart(element, productPrice) {
            element.parentElement.remove();
            updateTotal(-productPrice);
        }

        function updateTotal(price) {
            const totalElement = document.getElementById('cart-total');
            let currentTotal = parseFloat(totalElement.innerText.replace('Total: R$', ''));
            currentTotal += price;
            totalElement.innerText = `Total: R$ ${currentTotal.toFixed(2)}`;
        }
        function redirectToWhatsApp() {
    const cartItems = document.querySelectorAll('.cart-item p:first-child');
    const cartTotal = document.getElementById('cart-total').innerText;
    let message = "Olá, gostaria de fazer o pedido dos seguintes produtos:\n";
    cartItems.forEach(item => {
        message += `- ${item.innerText}\n`;
    });
    message += `\n${cartTotal}`;
    
    const encodedMessage = encodeURIComponent(message);
    const whatsappUrl = `https://wa.me/5543984026621?text=${encodedMessage}`;
    window.open(whatsappUrl, '_blank');
}

window.onscroll = function() {scrollFunction()}; function scrollFunction() { var backToTopButton = document.getElementById("backToTopButton"); if (document.body.scrollTop > 20 || document.documentElement.scrollTop > 20) { backToTopButton.style.display = "block"; } else { backToTopButton.style.display = "none"; } } function scrollToTop() { document.body.scrollTop = 0; document.documentElement.scrollTop = 0; }

    </script>
</head>

<body>

    <!-- Conteúdo da página --> <button onclick="scrollToTop()" id="backToTopButton">↑</button>

    <header>
        <h1>Farmácia Drogaria Gonçalvez</h1>
        <p>Assaí, Paraná - Em frente ao Banco do Brasil</p>
    </header>

    <nav>
        <ul>
            <li><a href="#cart">Carrinho de Compras</a></li>
            <li><a href="#home">Início</a></li>
            <li><a href="#promocoes">Promoções</a></li>
            <li><a href="#medicamentos">Medicamentos</a></li>
            <li><a href="#Higiene e Belezas">Higiene e Belezas</a></li>
            
            <li><a href="#fraldas-cuidados-infantis">Fraldas e Cuidado Infantil</a></li>
            
            <li><a href="#equipamentos-medicos">Equipamentos Médicos</a></li>
            <li><a href="#contact">Contato</a></li>
        </ul>
    </nav>
    <hr>

    <section id="home">
        <h2>Bem-vindo à Drogaria Gonçalvez</h2>
        <p>Sua saúde é nossa prioridade. Confira nossos serviços e produtos de alta qualidade.</p>
    </section>

    <hr>

    <section id="promocoes">
        <h2>Promoções</h2>
        <p>Confira as promoções imperdíveis deste mês!</p>
    
        <div class="product">
            <img src="https://uploads.consultaremedios.com.br/product_variation_images/full/33ac7b40c66017f522c333c52467c81757247df5.png?1663098422" alt="Ambrol 15mg/5mL">
            <p>Ambrol 15mg/5mL, caixa com 1 frasco com 100mL de xarope infantil + 1 copo medidor</p>
            <p>De R$ 23,00 por R$ 14,99</p>
            <button onclick="addToCart('Ambrol 15mg/5mL, caixa com 1 frasco com 100mL de xarope infantil + 1 copo medidor', 14.99)">Adicionar ao Carrinho</button>
        </div>
    
        <div class="product">
            <img src="https://www.vitamedic.ind.br/wp-content/uploads/2021/09/Hedera-Helix-768x768.png" alt="Hedera Helix Xarope 7mg/ml">
            <p>Hedera Helix Xarope 7mg/ml – frasco com 100ml</p>
            <p>De R$ 21,00 por R$ 14,99</p>
            <button onclick="addToCart('Hedera Helix Xarope 7mg/ml – frasco com 100ml', 14.99)">Adicionar ao Carrinho</button>
        </div>
    
        <div class="product">
            <img src="https://m.media-amazon.com/images/I/51DzYTnETtL._AC_UF894,1000_QL80_.jpg" alt="Toalhinha Umedecida Papegu Baby Com 50 Un">
            <p>Toalhinha Umedecida Papegu Baby Com 50 Un</p>
            <p>De R$ 7,00 por R$ 4,99</p>
            <button onclick="addToCart('Toalhinha Umedecida Papegu Baby Com 50 Un', 4.99)">Adicionar ao Carrinho</button>
        </div>
    </section>
    
    
    <hr>
    <section id="medicamentos">
        <h2>Medicamentos</h2>
        <div class="product">
            <img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcSsoRijS7rmjG9BCge9_IEG1Dp6dapLhWlCAg&s" alt="Dorflex">
            <p>Dorflex - Cartela com 10 comprimidos</p>
            <p>R$ 7,50</p>
            <button onclick="addToCart('Dorflex - Cartela com 10 comprimidos', 7.50)">Adicionar ao Carrinho</button>
        </div>
        
        <div class="product">
            <img src="https://drogal.vtexassets.com/arquivos/ids/208994/87878.jpg?v=638542521670200000" alt="Dipirona">
            <p>Dipirona - Analgésico e antipirético</p>
            <p>R$ 5,00</p>
            <button onclick="addToCart('Dipirona - Analgésico e antipirético', 5.00)">Adicionar ao Carrinho</button>
        </div>
        <div class="product">
            <img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTyXwyBE0GeUnDM7Ck25ykGZhg2E74PbvRfTg&s" alt="Glifage XR">
            <p>Glifage XR (Merck) - Antidiabético</p>
            <p>R$ 12,00</p>
            <button onclick="addToCart('Glifage XR (Merck) 500mg', 12.00)">Adicionar ao Carrinho</button>
        </div>
        <div class="product">
            <img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcSOldG5-0WVZf4aYIsHBAhKaxL-YqqJDdnTYA&s" alt="Losartana Potássica">
            <p>Losartana Potássica 50mg CX 3BL X 10 COMP REV</p>
            <p>R$ 7,00</p>
            <button onclick="addToCart('Losartana Potássica 50mg CX 3BL X 10 COMP REV', 7.00)">Adicionar ao Carrinho</button>
        </div>
        <div class="product"> <img src="https://hyperapharma.vteximg.com.br/arquivos/ids/165618-1000-1000/Hypera-Neoquimica-Neosoro-AD-A3-300dpi-RGB-1000px.png?v=638229767897770000" alt="Neosoro"> 
            <p>Neosoro Solução Nasal Adulto 30ml</p> <p>R$ 5,99</p> <!-- Coloque o preço correto se for diferente --> 
            <button onclick="addToCart('Neosoro Solução Nasal Adulto 30ml', 10.00)">Adicionar ao Carrinho</button> 
        </div>
    </section>
    
    
    <hr>
    
    <section id="Higiene e Belezas">
        <h2>Higiene e Beleza</h2>
    
            <div class="product">
                <img src="https://down-br.img.susercontent.com/file/br-11134207-7r98o-lkquaoobc91yb3" alt="Body Splash Giovanna Baby">
                <p>Body Splash Giovanna Baby 260ml</p>
                <p>R$ 31,90</p>
                <button onclick="addToCart('Body Splash Giovanna Baby 260ml', 31.90)">Adicionar ao Carrinho</button>
            </div>
        
            <div class="product">
                <img src="https://prezunic.vtexassets.com/arquivos/ids/178727/656788c31ef3739680760dc8.jpg?v=638368808437700000" alt="Creme Dental Colgate Total 12 Clean Mint 90g">
                <p>Creme Dental Colgate Total 12 Clean Mint 90g</p>
                <p>R$ 9,99</p>
                <button onclick="addToCart('Creme Dental Colgate Total 12 Clean Mint 90g', 9.99)">Adicionar ao Carrinho</button>
            </div>
        
            <div class="product">
                <img src="https://drogariamoderna.vtexassets.com/arquivos/ids/252198-800-auto?v=638151236226670000&width=800&height=auto&aspect=true" alt="Desodorante Rexona 150ml">
                <p>Desodorante Rexona 150ml</p>
                <p>R$ 17,99</p>
                <button onclick="addToCart('Desodorante Rexona 150ml', 17.99)">Adicionar ao Carrinho</button>
            </div>
        
            <div class="product">
                <img src="https://m.media-amazon.com/images/I/51g3dQZFoIS._AC_UF1000,1000_QL80_.jpg" alt="Sabonete Líquido Facial Nupill Firmness Intensive 200ml Vitamina C">
                <p>Sabonete Líquido Facial Nupill Firmness Intensive 200ml Vitamina C</p>
                <p>R$ 26,90</p>
                <button onclick="addToCart('Sabonete Líquido Facial Nupill Firmness Intensive 200ml Vitamina C', 26.90)">Adicionar ao Carrinho</button>
            </div>
        
            <div class="product">
                <img src="https://muffatosupermercados.vtexassets.com/arquivos/ids/378465-800-auto?v=638436161712370000&width=800&height=auto&aspect=true" alt="Shampoo Pantene Restauração 350ml + Condicionador 175ml">
                <p>Shampoo Pantene Restauração 350ml + Condicionador 175ml</p>
                <p>R$ 32,99</p>
                <button onclick="addToCart('Shampoo Pantene Restauração 350ml + Condicionador 175ml', 32.99)">Adicionar ao Carrinho</button>
            </div>
        
            <div class="product">
                <img src="https://m.media-amazon.com/images/I/51DzYTnETtL._AC_UF894,1000_QL80_.jpg" alt="Toalhas Umedecidas Personalidade Baby c/100">
                <p>Toalhas Umedecidas Personalidade Baby c/100</p>
                <p>R$ 14,90</p>
                <button onclick="addToCart('Toalhas Umedecidas Personalidade Baby c/100', 14.90)">Adicionar ao Carrinho</button>
            </div>
        </section>

    
    <hr>
    
    <section id="fraldas-cuidados-infantis">
        <h2>Fraldas e Cuidados Infantis</h2>
    
        <div class="product">
            <img src="https://m.media-amazon.com/images/I/519Cn1TlCFL._AC_UF1000,1000_QL80_.jpg" alt="Fralda Babysec Galinha Pintadinha">
            <p>Fralda Babysec Galinha Pintadinha</p>
            <p>R$ 49,99</p>
            <button onclick="addToCart('Fralda Babysec Galinha Pintadinha', 49.99)">Adicionar ao Carrinho</button>
        </div>
    
        <div class="product">
            <img src="https://cdn.awsli.com.br/600x700/1128/1128644/produto/88995725/huggies-supreme-care-xxg-com-26---1864-2n0kqz3jh3.png" alt="Fralda Infantil Huggies Supreme Care">
            <p>Fralda Infantil Huggies Supreme Care</p>
            <p>R$ 89,99</p>
            <button onclick="addToCart('Fralda Infantil Huggies Supreme Care', 89.99)">Adicionar ao Carrinho</button>
        </div>
    
        <div class="product">
            <img src="https://cdn.awsli.com.br/300x300/1191/1191777/produto/315191510/personalidade-plus-l4pl3akwzy.png" alt="Fralda Personalidade Baby Plus Hiper">
            <p>Fralda Personalidade Baby Plus Hiper</p>
            <p>R$ 59,99</p>
            <button onclick="addToCart('Fralda Personalidade Baby Plus Hiper', 59.99)">Adicionar ao Carrinho</button>
        </div>
    
        <div class="product">
            <img src="https://m.media-amazon.com/images/I/51DzYTnETtL._AC_UF894,1000_QL80_.jpg" alt="Toalhas Umedecidas Personalidade Baby c/100">
            <p>Toalhas Umedecidas Personalidade Baby c/100</p>
            <p>R$ 14,90</p>
            <button onclick="addToCart('Toalhas Umedecidas Personalidade Baby c/100', 14.90)">Adicionar ao Carrinho</button>
        </div>
    </section>
    
     
    <hr>
    
    <section id="equipamentos-medicos">
        <h2>Equipamentos Médicos</h2>
    
        <div class="product">
            <img src="https://images.tcdn.com.br/img/img_prod/1077001/kit_esfigmomanometro_aneroide_com_estetoscopio_premium_207_2_80e00ef83f4f7a1ce3762ca378f0c7d3.jpg" alt="Esfigmomanômetro Premium">
            <p>Esfigmomanômetro Premium</p>
            <p>R$ 135,00</p>
            <button onclick="addToCart('Esfigmomanômetro Premium', 135.00)">Adicionar ao Carrinho</button>
        </div>
    
        <div class="product">
            <img src="https://www.incoterm.com.br/media/2024/06/500x500-oxi320.png" alt="Oxímetro de Pulso Portátil de Dedo OX320 Incoterm">
            <p>Oxímetro de Pulso Portátil de Dedo OX320 Incoterm</p>
            <p>R$ 149,99</p>
            <button onclick="addToCart('Oxímetro de Pulso Portátil de Dedo OX320 Incoterm', 149.99)">Adicionar ao Carrinho</button>
        </div>
    
        <div class="product">
            <img src="https://indavidas.com.br/wp-content/uploads/2021/02/Termometro-Digital-Branco.jpg" alt="Termômetro Clínico Digital Branco (G-TECH)">
            <p>Termômetro Clínico Digital Branco (G-TECH)</p>
            <p>R$ 23,50</p>
            <button onclick="addToCart('Termômetro Clínico Digital Branco (G-TECH)', 23.50)">Adicionar ao Carrinho</button>
        </div>
    </section>
    
    
    <hr>

    <section id="cart">
        <h2>Carrinho de Compras</h2>
        <div id="cart-items"></div>
        <div id="cart-total" class="cart-total">Total: R$ 0.00</div>
        <button onclick="redirectToWhatsApp()">Enviar pelo WhatsApp</button>
    </section>

    <hr>

    <section id="contact">
        <h2>Contato</h2>
        <p>Endereço: Avenida Rio de Janeiro, 707 - Assaí, Paraná, em frente ao Banco do Brasil</p>
        <p>Telefone fixo: ☎️(43) 3262-3327</p>
        <p>Telefone e WhatsApp: <a href="https://wa.me/5543984026621" target="_blank">📱(43) 98402-6621</a></p>
        <p>Siga-nos no Instagram: <a href="https://www.instagram.com/drogariagoncalves_/" target="_blank">@drogariagoncalves_</a></p>
    </section>

    <hr>

    <footer>
        <p>&copy; 2024 Drogaria Gonçalvez - Todos os direitos reservados</p>
        <p>Siga-nos nas redes sociais!</p>
    </footer>
</body>
</html>

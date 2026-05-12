<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8">
<title>Tulipa's HotDog</title>

<style>
body { font-family: Arial; background: #f7f7f7; margin: 0; }
.topo { background: #ea1d2c; color: white; padding: 15px; text-align: center; font-size: 20px; }
.produto { background: white; margin: 10px; padding: 10px; border-radius: 10px; }
.footer { position: fixed; bottom: 0; width: 100%; background: white; padding: 10px; }

input, select { width: 100%; padding: 5px; margin-top: 5px; }

</style>
</head>

<body>

<div class="topo">Tulipa's HotDog 🌭</div>

<div class="produto">
Americano R$12<br>
Qtd: <input type="number" id="p1" value="0">
Obs: <input id="o1">
</div>

<div class="produto">
Tradicional R$10<br>
Qtd: <input type="number" id="p2" value="0">
Obs: <input id="o2">
</div>

<div class="produto">
Carne de Sol na Nata R$18<br>
Qtd: <input type="number" id="p3" value="0">
Obs: <input id="o3">
</div>

<div class="produto">
Franbacon R$16<br>
Qtd: <input type="number" id="p4" value="0">
Obs: <input id="o4">
</div>

<div class="produto">
Refrigerante R$6<br>
Qtd: <input type="number" id="p5" value="0">
Obs: <input id="o5">
</div>

<div class="produto">
Molho R$2<br>
Qtd: <input type="number" id="p6" value="0">
Obs: <input id="o6">
</div>

<div class="produto">
<b>Dados do cliente</b>
<input id="nome" placeholder="Seu nome">
<input id="endereco" placeholder="Endereço">
</div>

<div class="produto">
<b>Pagamento</b>
<select id="pagamento" onchange="trocoCampo()">
  <option>Pix</option>
  <option>Cartão</option>
  <option>Espécie</option>
</select>

<div id="trocoDiv" style="display:none;">
  <input id="troco" placeholder="Troco para quanto?">
</div>
</div>

<div class="footer">
<button onclick="enviar()">Enviar Pedido</button>
</div>

<script>

function trocoCampo() {
  let p = document.getElementById("pagamento").value;
  document.getElementById("trocoDiv").style.display = p == "Espécie" ? "block" : "none";
}

function enviar() {
  let msg = "🌭 Pedido Tulipa's HotDog:%0A";

  function add(nome, qtd, obs){
    if(qtd > 0){
      msg += nome + ": " + qtd;
      if(obs) msg += " (Obs: "+obs+")";
      msg += "%0A";
    }
  }

  add("Americano", p1.value, o1.value);
  add("Tradicional", p2.value, o2.value);
  add("Carne de Sol", p3.value, o3.value);
  add("Franbacon", p4.value, o4.value);
  add("Refrigerante", p5.value, o5.value);
  add("Molho", p6.value, o6.value);

  msg += "%0ANome: "+ nome.value;
  msg += "%0AEndereço: "+ endereco.value;
  msg += "%0APagamento: "+ pagamento.value;

  if(pagamento.value == "Espécie"){
    msg += "%0ATroco para: "+ troco.value;
  }

  window.open("https://wa.me/558496564129?text="+msg);
}

</script>

</body>
</html>

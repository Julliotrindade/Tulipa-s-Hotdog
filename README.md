import { useState } from "react";

export default function App() {
  const telefone = "558496564129";
  const [cliente, setCliente] = useState("");
  const [endereco, setEndereco] = useState("");
  const [pagamento, setPagamento] = useState("");
  const [observacao, setObservacao] = useState("");
  const [produtos, setProdutos] = useState([
    { nome: "Hot Dog Americano", preco: 12, qtd: 0, img: "https://via.placeholder.com/80" },
    { nome: "Hot Dog Tradicional", preco: 10, qtd: 0, img: "https://via.placeholder.com/80" },
    { nome: "Hot Dog Carne de Sol na Nata", preco: 18, qtd: 0, img: "https://via.placeholder.com/80" },
    { nome: "Hot Dog Franbacon", preco: 16, qtd: 0, img: "https://via.placeholder.com/80" },
    { nome: "Refrigerante", preco: 6, qtd: 0, img: "https://via.placeholder.com/80" },
    { nome: "Molho Extra", preco: 2, qtd: 0, img: "https://via.placeholder.com/80" }
  ]);

  const alterarQtd = (index, valor) => {
    const novos = [...produtos];
    novos[index].qtd = Math.max(0, novos[index].qtd + valor);
    setProdutos(novos);
  };

  const limparPedido = () => {
    const reset = produtos.map(p => ({ ...p, qtd: 0 }));
    setProdutos(reset);
  };


  const total = produtos.reduce((acc, p) => acc + p.qtd * p.preco, 0);

  const enviarPedido = () => {
    let mensagem = "🌭 *Pedido - Tulipa's HotDog* %0A";


    produtos.forEach(p => {
      if (p.qtd > 0) {
        mensagem += `${p.nome}: ${p.qtd}%0A`;
      }
    });

    mensagem += `%0ATotal: R$ ${total}%0A`;
    mensagem += `%0ANome: ${cliente}%0A`;
    mensagem += `Endereço: ${endereco}%0A`;

    if (pagamento) {
      mensagem += `Forma de pagamento: ${pagamento}%0A`;
    }


    if (observacao) {
      mensagem += `Observação: ${observacao}%0A`;
    }


    const url = `https://wa.me/${telefone}?text=${mensagem}`;
    window.open(url, "_blank");
  };

  return (
    <div style={{ fontFamily: "Arial", background: "#f7f7f7", minHeight: "100vh", paddingBottom: "100px" }}>
      <div style={{ background: "#ea1d2c", color: "white", padding: "15px", textAlign: "center", fontSize: "20px", fontWeight: "bold" }}>
        Tulipa's HotDog 🌭
      </div>

      <div style={{ padding: "10px" }}>
        {produtos.map((p, i) => (
          <div key={i} style={{ display: "flex", background: "white", borderRadius: "12px", marginBottom: "10px", padding: "10px", alignItems: "center", boxShadow: "0 2px 5px rgba(0,0,0,0.05)" }}>
            <img src={p.img} width={70} height={70} style={{ borderRadius: "10px", marginRight: "10px" }} />
            <div style={{ flex: 1 }}>
              <div style={{ fontWeight: "bold" }}>{p.nome}</div>
              <div style={{ color: "#555" }}>R$ {p.preco}</div>
            </div>
            <div style={{ display: "flex", alignItems: "center", gap: "8px" }}>
              <button onClick={() => alterarQtd(i, -1)} style={{ borderRadius: "50%", width: "30px", height: "30px" }}>-</button>
              <span>{p.qtd}</span>
              <button onClick={() => alterarQtd(i, 1)} style={{ borderRadius: "50%", width: "30px", height: "30px" }}>+</button>
            </div>
          </div>
        ))}
      </div>

      <div style={{ background: "white", padding: "15px", margin: "10px", borderRadius: "12px" }}>
        <h4>Seus Dados</h4>
        <input
          placeholder="Seu nome"
          value={cliente}
          onChange={(e) => setCliente(e.target.value)}
          style={{ width: "100%", marginBottom: "8px", padding: "8px" }}
        />
        <input
          placeholder="Endereço"
          value={endereco}
          onChange={(e) => setEndereco(e.target.value)}
          style={{ width: "100%", marginBottom: "8px", padding: "8px" }}
        />


        <input
          placeholder="Forma de pagamento (Pix, dinheiro, cartão...)"
          value={pagamento}
          onChange={(e) => setPagamento(e.target.value)}
          style={{ width: "100%", marginBottom: "8px", padding: "8px" }}
        />


        <textarea
          placeholder="Observações (sem molho, tirar algo, etc...)"
          value={observacao}
          onChange={(e) => setObservacao(e.target.value)}
          style={{ width: "100%", padding: "8px" }}
        />
      </div>

      <div style={{ position: "fixed", bottom: 0, width: "100%", background: "white", padding: "10px", boxShadow: "0 -2px 10px rgba(0,0,0,0.1)" }}>
        <div style={{ display: "flex", justifyContent: "space-between", marginBottom: "5px" }}>
          <strong>Total:</strong>
          <strong>R$ {total}</strong>
        </div>


        <div style={{ display: "flex", gap: "8px" }}>
          <button
            onClick={limparPedido}
            style={{ flex: 1, background: "#999", color: "white", padding: "12px", borderRadius: "10px", border: "none" }}
          >
            Limpar
          </button>


          <button
            onClick={enviarPedido}
            style={{ flex: 2, background: "#ea1d2c", color: "white", padding: "12px", borderRadius: "10px", fontSize: "16px", border: "none" }}
          >
            Enviar no WhatsApp
          </button>
        </div>
      </div>
    </div>
  );
}

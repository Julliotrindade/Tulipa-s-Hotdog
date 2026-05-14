import { useState } from "react";

export default function App() {
  const telefone = "558496564129";

  const [cliente, setCliente] = useState("");
  const [endereco, setEndereco] = useState("");
  const [pagamento, setPagamento] = useState("");
  const [observacao, setObservacao] = useState("");

  const [produtos, setProdutos] = useState([
    {
      nome: "Hot Dog Americano",
      preco: 10,
      qtd: 0,
      img: "https://i.imgur.com/5bXG3kF.png",
      adicionais: [
        { nome: "Bacon", preco: 3, selecionado: false },
        { nome: "Cheddar", preco: 2, selecionado: false }
      ]
    },
    {
      nome: "Hot Dog Tradicional",
      preco: 10,
      qtd: 0,
      img: "https://i.imgur.com/5bXG3kF.png",
      adicionais: []
    },
    {
      nome: "Refrigerante",
      preco: 6,
      qtd: 0,
      img: "https://i.imgur.com/5bXG3kF.png",
      adicionais: []
    }
  ]);

  const alterarQtd = (index, valor) => {
    const novos = [...produtos];
    novos[index].qtd = Math.max(0, novos[index].qtd + valor);
    setProdutos(novos);
  };

  const toggleAdicional = (pIndex, aIndex) => {
    const novos = [...produtos];
    novos[pIndex].adicionais[aIndex].selecionado =
      !novos[pIndex].adicionais[aIndex].selecionado;
    setProdutos(novos);
  };

  const limparPedido = () => {
    const reset = produtos.map(p => ({
      ...p,
      qtd: 0,
      adicionais: p.adicionais.map(a => ({ ...a, selecionado: false }))
    }));
    setProdutos(reset);
  };

  const calcularTotal = () => {
    let total = 0;
    produtos.forEach(p => {
      if (p.qtd > 0) {
        total += p.qtd * p.preco;
        p.adicionais.forEach(a => {
          if (a.selecionado) total += a.preco * p.qtd;
        });
      }
    });
    return total;
  };

  const total = calcularTotal();

  const enviarPedido = () => {
    let mensagem = "🌭 *Pedido - Tulipa's HotDog* \n\n";

    produtos.forEach(p => {
      if (p.qtd > 0) {
        mensagem += `*${p.nome}* x${p.qtd}\n`;

        p.adicionais.forEach(a => {
          if (a.selecionado) {
            mensagem += `  + ${a.nome}\n`;
          }
        });

        mensagem += "\n";
      }
    });

    mensagem += `💰 Total: R$ ${total}\n\n`;
    mensagem += `👤 Nome: ${cliente}\n`;
    mensagem += `📍 Endereço: ${endereco}\n`;
    if (pagamento) mensagem += `💳 Pagamento: ${pagamento}\n`;
    if (observacao) mensagem += `📝 Obs: ${observacao}\n`;

    const url = `https://wa.me/${telefone}?text=${encodeURIComponent(mensagem)}`;
    window.open(url, "_blank");
  };

  return (
    <div style={{ fontFamily: "Arial", background: "#f2f2f2", minHeight: "100vh", paddingBottom: "120px" }}>
      
      <div style={{ background: "#ea1d2c", color: "white", padding: "15px", textAlign: "center", fontSize: "22px", fontWeight: "bold" }}>
        Tulipa's HotDog 🌭
      </div>

      <div style={{ padding: "10px" }}>
        {produtos.map((p, i) => (
          <div key={i} style={{ background: "white", borderRadius: "12px", marginBottom: "12px", padding: "10px" }}>
            
            <div style={{ display: "flex", alignItems: "center" }}>
              <img src={p.img} width={70} height={70} style={{ borderRadius: "10px", marginRight: "10px" }} />

              <div style={{ flex: 1 }}>
                <div style={{ fontWeight: "bold" }}>{p.nome}</div>
                <div style={{ color: "#666" }}>R$ {p.preco}</div>
              </div>

              <div style={{ display: "flex", alignItems: "center", gap: "8px" }}>
                <button onClick={() => alterarQtd(i, -1)}>-</button>
                <span>{p.qtd}</span>
                <button onClick={() => alterarQtd(i, 1)}>+</button>
              </div>
            </div>

            {p.qtd > 0 && p.adicionais.length > 0 && (
              <div style={{ marginTop: "10px" }}>
                <strong>Adicionar:</strong>
                {p.adicionais.map((a, ai) => (
                  <div key={ai}>
                    <label>
                      <input
                        type="checkbox"
                        checked={a.selecionado}
                        onChange={() => toggleAdicional(i, ai)}
                      />
                      {a.nome} (+R$ {a.preco})
                    </label>
                  </div>
                ))}
              </div>
            )}

          </div>
        ))}
      </div>

      <div style={{ background: "white", margin: "10px", padding: "15px", borderRadius: "12px" }}>
        <h4>Entrega</h4>

        <input placeholder="Seu nome" value={cliente} onChange={(e) => setCliente(e.target.value)} style={{ width: "100%", marginBottom: "8px", padding: "8px" }} />
        <input placeholder="Endereço" value={endereco} onChange={(e) => setEndereco(e.target.value)} style={{ width: "100%", marginBottom: "8px", padding: "8px" }} />

        <select value={pagamento} onChange={(e) => setPagamento(e.target.value)} style={{ width: "100%", marginBottom: "8px", padding: "8px" }}>
          <option value="">Forma de pagamento</option>
          <option>Pix</option>
          <option>Dinheiro</option>
          <option>Cartão</option>
        </select>

        <textarea placeholder="Observações" value={observacao} onChange={(e) => setObservacao(e.target.value)} style={{ width: "100%", padding: "8px" }} />
      </div>

      <div style={{ position: "fixed", bottom: 0, width: "100%", background: "white", padding: "10px", boxShadow: "0 -2px 10px rgba(0,0,0,0.1)" }}>
        <div style={{ display: "flex", justifyContent: "space-between" }}>
          <strong>Total</strong>
          <strong>R$ {total}</strong>
        </div>

        <div style={{ display: "flex", gap: "8px", marginTop: "8px" }}>
          <button onClick={limparPedido} style={{ flex: 1, background: "#999", color: "white" }}>
            Limpar
          </button>

          <button onClick={enviarPedido} style={{ flex: 2, background: "#ea1d2c", color: "white" }}>
            Pedir no WhatsApp
          </button>
        </div>
      </div>

    </div>
  );
}

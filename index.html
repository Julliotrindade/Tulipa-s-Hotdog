import { useState } from "react";

export default function App() {
  const telefone = "558496564129";

  const [produtos, setProdutos] = useState([
    {
      nome: "Hot Dog Americano",
      preco: 10,
      qtd: 0,
      img: "https://i.imgur.com/5bXG3kF.png",
    },
    {
      nome: "Hot Dog Tradicional",
      preco: 8,
      qtd: 0,
      img: "https://i.imgur.com/5bXG3kF.png",
    },
    {
      nome: "Refrigerante",
      preco: 6,
      qtd: 0,
      img: "https://i.imgur.com/5bXG3kF.png",
    }
  ]);

  const alterarQtd = (i, v) => {
    const n = [...produtos];
    n[i].qtd = Math.max(0, n[i].qtd + v);
    setProdutos(n);
  };

  const total = produtos.reduce((t, p) => t + p.qtd * p.preco, 0);

  const enviar = () => {
    let msg = "🍔 Pedido\n\n";
    produtos.forEach(p => {
      if (p.qtd > 0) msg += `${p.nome} x${p.qtd}\n`;
    });
    msg += `\nTotal: R$ ${total}`;

    window.open(`https://wa.me/${telefone}?text=${encodeURIComponent(msg)}`);
  };

  return (
    <div style={{ background: "#f4f4f4", minHeight: "100vh", fontFamily: "Arial" }}>
      
      <div style={{ background: "#ea1d2c", color: "white", padding: 15, textAlign: "center", fontSize: 20 }}>
        🌭 Tulipa’s HotDog
      </div>

      <div style={{ padding: 15 }}>
        {produtos.map((p, i) => (
          <div key={i} style={{
            background: "white",
            marginBottom: 15,
            borderRadius: 15,
            padding: 15,
            display: "flex",
            alignItems: "center",
            boxShadow: "0 4px 8px rgba(0,0,0,0.1)"
          }}>
            
            <img src={p.img} width={70} style={{ borderRadius: 10 }} />

            <div style={{ flex: 1, marginLeft: 10 }}>
              <div style={{ fontWeight: "bold" }}>{p.nome}</div>
              <div style={{ color: "#666" }}>R$ {p.preco}</div>
            </div>

            <div>
              <button onClick={() => alterarQtd(i, -1)}>-</button>
              <span style={{ margin: "0 10px" }}>{p.qtd}</span>
              <button onClick={() => alterarQtd(i, 1)}>+</button>
            </div>
          </div>
        ))}
      </div>

      <div style={{
        position: "fixed",
        bottom: 0,
        width: "100%",
        background: "white",
        padding: 15,
        boxShadow: "0 -2px 10px rgba(0,0,0,0.1)"
      }}>
        <div style={{ display: "flex", justifyContent: "space-between" }}>
          <strong>Total</strong>
          <strong>R$ {total}</strong>
        </div>

        <button onClick={enviar} style={{
          width: "100%",
          marginTop: 10,
          padding: 12,
          background: "#ea1d2c",
          color: "white",
          border: "none",
          borderRadius: 10,
          fontSize: 16
        }}>
          Pedir no WhatsApp
        </button>
      </div>

    </div>
  );
}

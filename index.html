<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Gestão de EPIs — Sementes Tormenta</title>
  <script src="https://cdnjs.cloudflare.com/ajax/libs/react/18.2.0/umd/react.production.min.js"></script>
  <script src="https://cdnjs.cloudflare.com/ajax/libs/react-dom/18.2.0/umd/react-dom.production.min.js"></script>
  <script src="https://cdnjs.cloudflare.com/ajax/libs/babel-standalone/7.23.2/babel.min.js"></script>
  <style>
    * { box-sizing: border-box; margin: 0; padding: 0; }
    body { font-family: 'Segoe UI', sans-serif; }
    @keyframes fadeIn { from { opacity:0; transform:translateX(30px); } to { opacity:1; transform:translateX(0); } }
    input[type=number]::-webkit-inner-spin-button { -webkit-appearance: none; }
    select option { background: #252b3d; }
    input, select, textarea { font-family: inherit; }
    ::-webkit-scrollbar { width: 6px; } 
    ::-webkit-scrollbar-track { background: rgba(0,0,0,0.2); }
    ::-webkit-scrollbar-thumb { background: rgba(80,160,60,0.3); border-radius: 3px; }
  </style>
</head>
<body>
<div id="root"></div>
<script type="text/babel">
const { useState } = React;

const EMOJIS = ["🪖","🧤","🥽","🎧","🦺","👢","😷","🔗","🧣","🧥","🩺","⛑️","🔦","🧲","🪝","🛡️","🔧","⚙️"];
const CATEGORIAS = ["Cabeça","Mãos","Olhos","Audição","Corpo","Pés","Respiração","Queda","Outros"];
const UNIDADES = ["un","par","cx","kg","m","rolo"];
const CORES = ["#e74c3c","#3498db","#1abc9c","#f39c12","#8e44ad","#e67e22"];

const EPIS_INICIAIS = [
  { id: 1, nome: "Capacete de Segurança", categoria: "Cabeça",     estoque: 15, minimo: 10, unidade: "un",  img: "🪖", ca: "31469",  validade: "2026-12-31", codigo: "EPI-001" },
  { id: 2, nome: "Luva de Borracha",       categoria: "Mãos",      estoque: 8,  minimo: 20, unidade: "par", img: "🧤", ca: "10918",  validade: "2025-06-30", codigo: "EPI-002" },
  { id: 3, nome: "Óculos de Proteção",     categoria: "Olhos",     estoque: 4,  minimo: 15, unidade: "un",  img: "🥽", ca: "19793",  validade: "2026-09-15", codigo: "EPI-003" },
  { id: 4, nome: "Protetor Auricular",     categoria: "Audição",   estoque: 30, minimo: 25, unidade: "un",  img: "🎧", ca: "5674",   validade: "2027-03-01", codigo: "EPI-004" },
  { id: 5, nome: "Colete Refletivo",       categoria: "Corpo",     estoque: 2,  minimo: 8,  unidade: "un",  img: "🦺", ca: "41139",  validade: "2026-05-20", codigo: "EPI-005" },
  { id: 6, nome: "Bota de Segurança",      categoria: "Pés",       estoque: 6,  minimo: 10, unidade: "par", img: "👢", ca: "28001",  validade: "2026-08-10", codigo: "EPI-006" },
  { id: 7, nome: "Máscara PFF2",           categoria: "Respiração",estoque: 45, minimo: 30, unidade: "un",  img: "😷", ca: "39503",  validade: "2025-12-01", codigo: "EPI-007" },
  { id: 8, nome: "Cinto de Segurança",     categoria: "Queda",     estoque: 3,  minimo: 5,  unidade: "un",  img: "🔗", ca: "12345",  validade: "2027-01-15", codigo: "EPI-008" },
];

const USUARIOS_INICIAIS = [
  { id: 1, nome: "Carlos Silva", whatsapp: "(47) 99100-0001", cargo: "Técnico de Segurança", perfil: "admin",  status: "ativo", avatar: "CS", cor: "#8e44ad" },
  { id: 2, nome: "Ana Oliveira", whatsapp: "(47) 99100-0002", cargo: "Almoxarife",           perfil: "editor", status: "ativo", avatar: "AO", cor: "#3498db" },
];

const S = {
  input: { width: "100%", background: "rgba(15,20,15,0.6)", border: "1px solid rgba(80,160,60,0.25)", borderRadius: 10, color: "#e8eaf0", fontSize: 14, padding: "10px 14px", outline: "none", boxSizing: "border-box" },
  label: { fontSize: 13, color: "#a8c8a0", display: "block", marginBottom: 6 },
  card:  { background: "rgba(10,20,12,0.72)", border: "1px solid rgba(80,160,60,0.18)", borderRadius: 18, padding: "20px 20px 14px", backdropFilter: "blur(12px)", WebkitBackdropFilter: "blur(12px)" },
};

function Btn({ onClick, children, style = {}, disabled = false }) {
  return (
    <button onClick={onClick} disabled={disabled}
      style={{ border: "none", cursor: disabled ? "not-allowed" : "pointer", fontWeight: 700, fontSize: 14, borderRadius: 10, padding: "10px 18px", color: "#fff", transition: "opacity .2s", opacity: disabled ? 0.5 : 1, ...style }}>
      {children}
    </button>
  );
}

function Modal({ onClose, borderColor = "rgba(80,160,60,0.2)", children }) {
  return (
    <div onClick={onClose} style={{ position: "fixed", inset: 0, zIndex: 500, background: "#000a", display: "flex", alignItems: "center", justifyContent: "center" }}>
      <div onClick={e => e.stopPropagation()} style={{ background: "rgba(10,20,12,0.97)", borderRadius: 20, padding: "36px 32px", minWidth: 320, maxWidth: 400, width: "90%", boxShadow: "0 8px 48px #000c", border: `1px solid ${borderColor}` }}>
        {children}
      </div>
    </div>
  );
}

function NumericInput({ value, onChange, min = 1, max }) {
  return (
    <div style={{ display: "flex", gap: 10, alignItems: "center" }}>
      <button onClick={() => onChange(Math.max(min, value - 1))}
        style={{ width: 36, height: 36, borderRadius: 8, background: "rgba(20,35,20,0.7)", border: "none", color: "#e8eaf0", fontSize: 20, cursor: "pointer" }}>−</button>
      <input type="number" value={value} min={min} max={max}
        onChange={e => onChange(Math.max(min, max !== undefined ? Math.min(max, Number(e.target.value)) : Number(e.target.value)))}
        style={{ width: 64, textAlign: "center", background: "rgba(20,35,20,0.7)", border: "1px solid rgba(80,160,60,0.2)", borderRadius: 8, color: "#e8eaf0", fontSize: 16, padding: "6px 0", fontWeight: 700 }} />
      <button onClick={() => onChange(max !== undefined ? Math.min(max, value + 1) : value + 1)}
        style={{ width: 36, height: 36, borderRadius: 8, background: "rgba(20,35,20,0.7)", border: "none", color: "#e8eaf0", fontSize: 20, cursor: "pointer" }}>+</button>
    </div>
  );
}

function App() {
  const [epis, setEpis]         = useState(EPIS_INICIAIS);
  const [usuarios, setUsuarios] = useState(USUARIOS_INICIAIS);
  const [aba, setAba]           = useState("estoque");
  const [toast, setToast]       = useState(null);

  const [modalRetirada, setModalRetirada] = useState(null);
  const [modalEntrada,  setModalEntrada]  = useState(null);
  const [qtdRetirada,   setQtdRetirada]   = useState(1);
  const [qtdEntrada,    setQtdEntrada]    = useState(1);

  const EPI0  = { nome: "", categoria: "Cabeça", estoque: 0, minimo: 5, unidade: "un", img: "🪖", ca: "", validade: "", codigo: "" };
  const USER0 = { nome: "", whatsapp: "", cargo: "", perfil: "visualizador" };
  const [novoEpi,   setNovoEpi]   = useState(EPI0);
  const [errosEpi,  setErrosEpi]  = useState({});
  const [novoUser,  setNovoUser]  = useState(USER0);
  const [errosUser, setErrosUser] = useState({});
  const [msgCompra, setMsgCompra] = useState("");
  const [enviado,   setEnviado]   = useState(false);

  const criticos = epis.filter(e => e.estoque < e.minimo);
  const pct      = epi => Math.min(100, Math.round((epi.estoque / epi.minimo) * 100));
  const corBarra = epi => epi.estoque < epi.minimo ? "#e74c3c" : pct(epi) < 60 ? "#f39c12" : "#1abc9c";

  function statusValidade(val) {
    if (!val) return null;
    const hoje = new Date(); hoje.setHours(0,0,0,0);
    const d = new Date(val + "T00:00:00");
    const dias = Math.round((d - hoje) / 86400000);
    if (dias < 0)   return { label: "VENCIDO",            cor: "#e74c3c", dias };
    if (dias <= 30) return { label: `Vence em ${dias}d`,  cor: "#e74c3c", dias };
    if (dias <= 90) return { label: `Vence em ${dias}d`,  cor: "#f39c12", dias };
    return { label: `Válido (${dias}d)`, cor: "#1abc9c", dias };
  }

  function fmtData(val) {
    if (!val) return "—";
    const [y, m, d] = val.split("-");
    return `${d}/${m}/${y}`;
  }

  function showToast(msg, tipo = "ok") {
    setToast({ msg, tipo });
    setTimeout(() => setToast(null), 3000);
  }

  function retirar(id, qtd) {
    setEpis(prev => prev.map(e => e.id === id ? { ...e, estoque: Math.max(0, e.estoque - qtd) } : e));
    showToast(`${qtd}x retirado(s) ✅`);
    setModalRetirada(null); setQtdRetirada(1);
  }

  function entrar(id, qtd) {
    setEpis(prev => prev.map(e => e.id === id ? { ...e, estoque: e.estoque + qtd } : e));
    showToast(`+${qtd} adicionado(s) ao estoque ✅`);
    setModalEntrada(null); setQtdEntrada(1);
  }

  function salvarEpi() {
    const e = {};
    if (!novoEpi.nome.trim()) e.nome = "Nome obrigatório";
    if (novoEpi.minimo <= 0)  e.minimo = "Deve ser > 0";
    setErrosEpi(e);
    if (Object.keys(e).length) return;
    setEpis(prev => [...prev, { ...novoEpi, id: Date.now() }]);
    showToast(`${novoEpi.nome} cadastrado! 🎉`);
    setNovoEpi(EPI0); setErrosEpi({});
    setAba("estoque");
  }

  function excluirEpi(id) {
    if (!window.confirm("Excluir este EPI?")) return;
    setEpis(prev => prev.filter(e => e.id !== id));
    showToast("EPI removido");
  }

  function gerarMsgCompra() {
    const linhas = criticos.map(e => {
      const ca  = e.ca       ? ` | CA: ${e.ca}`                     : "";
      const val = e.validade ? ` | Validade: ${fmtData(e.validade)}` : "";
      return `• ${e.img} ${e.nome}: ${e.estoque} ${e.unidade} (mín: ${e.minimo})${ca}${val}`;
    }).join("\n");
    setMsgCompra(`Solicitação de Compra de EPIs — URGENTE\n\nPrezados,\n\nOs seguintes EPIs estão abaixo do estoque mínimo:\n\n${linhas}\n\nSolicitamos reposição urgente.\n\nAtenciosamente,\nSetor de Segurança do Trabalho`);
  }

  function enviarWhatsapp() {
    navigator.clipboard.writeText(msgCompra).catch(() => {});
    window.open(`https://web.whatsapp.com/send?text=${encodeURIComponent(msgCompra)}`, "_blank");
    setEnviado(true); showToast("WhatsApp aberto!");
    setTimeout(() => setEnviado(false), 3000);
  }

  function convidar() {
    const e = {};
    if (!novoUser.nome.trim())     e.nome    = "Nome obrigatório";
    if (!novoUser.whatsapp.trim()) e.contato = "Informe o WhatsApp";
    setErrosUser(e);
    if (Object.keys(e).length) return;

    const initials = novoUser.nome.split(" ").map(p => p[0]).join("").slice(0, 2).toUpperCase();
    const cor      = CORES[Math.floor(Math.random() * CORES.length)];
    const novo     = { ...novoUser, id: Date.now(), status: "pendente", avatar: initials, cor };
    setUsuarios(prev => [...prev, novo]);
    setNovoUser(USER0); setErrosUser({});

    const perfis = { admin: "Administrador", editor: "Editor", visualizador: "Visualizador" };
    const link = window.location.href;
    const msg = `Olá ${novo.nome}! 👷\n\nVocê foi convidado para acessar o sistema de *Gestão de EPIs* da Sementes Tormenta com o perfil de *${perfis[novo.perfil] || novo.perfil}*.\n\n🔗 Acesse o aplicativo pelo link abaixo:\n${link}\n\nAtenciosamente,\nSetor de Segurança do Trabalho 🌱`;
    const num = novo.whatsapp.replace(/\D/g, "");
    window.open(`https://wa.me/55${num}?text=${encodeURIComponent(msg)}`, "_blank");
    showToast(`WhatsApp aberto para ${novo.nome}! 📲`);
  }

  function enviarWppConvite(u) {
    const perfis = { admin: "Administrador", editor: "Editor", visualizador: "Visualizador" };
    const link = window.location.href;
    const msg = `Olá ${u.nome}! 👷\n\nVocê foi convidado para acessar o sistema de *Gestão de EPIs* da Sementes Tormenta com o perfil de *${perfis[u.perfil] || u.perfil}*.\n\n🔗 Acesse o aplicativo pelo link abaixo:\n${link}\n\nAtenciosamente,\nSetor de Segurança do Trabalho 🌱`;
    const num = u.whatsapp.replace(/\D/g, "");
    window.open(`https://wa.me/55${num}?text=${encodeURIComponent(msg)}`, "_blank");
    showToast("WhatsApp aberto! 📲");
  }

  function gerarPDF() {
    const hoje = new Date().toLocaleDateString("pt-BR");
    const criticosCount = epis.filter(e => e.estoque < e.minimo).length;
    const linhas = epis.map(e => {
      const sv = (() => {
        if (!e.validade) return { label: "—", cor: "#a8c8a0" };
        const hoje2 = new Date(); hoje2.setHours(0,0,0,0);
        const d = new Date(e.validade + "T00:00:00");
        const dias = Math.round((d - hoje2) / 86400000);
        if (dias < 0)   return { label: "VENCIDO",          cor: "#e74c3c" };
        if (dias <= 90) return { label: "Vence em " + dias + "d", cor: "#f39c12" };
        return { label: "Válido", cor: "#27ae60" };
      })();
      const status = e.estoque < e.minimo ? "CRÍTICO" : "OK";
      const cor    = e.estoque < e.minimo ? "#e74c3c" : "#27ae60";
      const datVal = e.validade ? e.validade.split("-").reverse().join("/") : "—";
      return "<tr><td>" + e.img + " " + e.nome + "</td><td>" + (e.codigo||"—") + "</td><td>" + e.categoria + "</td><td style='font-weight:700;color:" + cor + "'>" + status + "</td><td style='text-align:center'>" + e.estoque + " " + e.unidade + "</td><td style='text-align:center'>" + e.minimo + " " + e.unidade + "</td><td>" + (e.ca||"—") + "</td><td style='color:" + sv.cor + ";font-weight:600'>" + datVal + "<br/><small>" + sv.label + "</small></td></tr>";
    }).join("");

    const vencidos = epis.filter(e => {
      if (!e.validade) return false;
      const d = new Date(e.validade + "T00:00:00");
      const hoje2 = new Date(); hoje2.setHours(0,0,0,0);
      return d < hoje2;
    }).length;

    const html = "<!DOCTYPE html><html lang='pt-BR'><head><meta charset='UTF-8'/>"
      + "<title>Relatório de EPIs — Sementes Tormenta</title>"
      + "<style>"
      + "body{font-family:Arial,sans-serif;margin:0;padding:24px;color:#222}"
      + "h1{color:#1a5c1a;font-size:22px;margin-bottom:2px}"
      + ".sub{color:#555;font-size:13px;margin-bottom:20px}"
      + ".resumo{display:flex;gap:16px;margin-bottom:24px;flex-wrap:wrap}"
      + ".card-r{background:#f4f9f4;border:1px solid #c8e6c8;border-radius:10px;padding:12px 20px;min-width:120px;text-align:center}"
      + ".card-r .num{font-size:28px;font-weight:900;color:#1a5c1a}"
      + ".card-r .lbl{font-size:11px;color:#555;margin-top:2px}"
      + ".critico .num{color:#c0392b}"
      + "table{width:100%;border-collapse:collapse;font-size:12px}"
      + "th{background:#1a5c1a;color:#fff;padding:9px 10px;text-align:left}"
      + "td{padding:8px 10px;border-bottom:1px solid #e0e0e0;vertical-align:middle}"
      + "tr:nth-child(even) td{background:#f9f9f9}"
      + ".footer{margin-top:24px;font-size:11px;color:#888;text-align:center}"
      + "@media print{body{padding:0}}"
      + "</style></head><body>"
      + "<h1>🌱 Sementes Tormenta — Relatório de EPIs</h1>"
      + "<div class='sub'>Gerado em: " + hoje + " &nbsp;|&nbsp; Total: " + epis.length + " &nbsp;|&nbsp; Críticos: " + criticosCount + "</div>"
      + "<div class='resumo'>"
      + "<div class='card-r'><div class='num'>" + epis.length + "</div><div class='lbl'>Total EPIs</div></div>"
      + "<div class='card-r critico'><div class='num'>" + criticosCount + "</div><div class='lbl'>Críticos</div></div>"
      + "<div class='card-r'><div class='num'>" + (epis.length - criticosCount) + "</div><div class='lbl'>Estoque OK</div></div>"
      + "<div class='card-r'><div class='num'>" + vencidos + "</div><div class='lbl'>Vencidos</div></div>"
      + "</div>"
      + "<table><thead><tr><th>EPI</th><th>Código</th><th>Categoria</th><th>Status</th><th>Estoque</th><th>Mínimo</th><th>CA</th><th>Validade</th></tr></thead>"
      + "<tbody>" + linhas + "</tbody></table>"
      + "<div class='footer'>Sementes Tormenta &nbsp;|&nbsp; Setor de Segurança do Trabalho &nbsp;|&nbsp; " + hoje + "</div>"
      + "</body></html>";

    const w = window.open("", "_blank");
    w.document.open();
    w.document.write(html);
    w.document.close();
    setTimeout(() => w.print(), 800);
  }
    if (!window.confirm("Remover usuário?")) return;
    setUsuarios(prev => prev.filter(u => u.id !== id));
    showToast("Usuário removido");
  }

  function toggleUser(id) {
    setUsuarios(prev => prev.map(u => u.id === id ? { ...u, status: u.status === "ativo" ? "inativo" : "ativo" } : u));
  }

  const ABAS = [
    { key: "estoque",  label: "📋 Estoque" },
    { key: "entrada",  label: "📥 Entrada" },
    { key: "criticos", label: "🚨 Críticos", badge: criticos.length },
    { key: "novo",     label: "➕ Novo EPI" },
    { key: "codigos",  label: "🔢 Códigos" },
    { key: "compra",   label: "📲 Solicitar Compra" },
    { key: "relatorio",label: "📄 Relatório PDF" },
    { key: "usuarios", label: "👥 Usuários" },
  ];

  return (
    <div style={{ fontFamily: "'Segoe UI',sans-serif", minHeight: "100vh", color: "#e8eaf0", background: "linear-gradient(160deg,#0a2e0a 0%,#0d3d10 30%,#0b4a12 55%,#093508 80%,#071f07 100%)", position: "relative", overflow: "hidden" }}>

      {/* BG */}
      <div style={{ position: "fixed", inset: 0, pointerEvents: "none", zIndex: 0, overflow: "hidden" }}>
        <svg width="100%" height="100%" style={{ position: "absolute", inset: 0, opacity: 0.07 }} preserveAspectRatio="none">
          {Array.from({ length: 30 }).map((_, i) => (
            <line key={i} x1={`${(i/30)*100}%`} y1="0" x2={`${(i/30)*100}%`} y2="100%" stroke="#4ade80" strokeWidth="1.5" />
          ))}
        </svg>
        <div style={{ position: "absolute", inset: 0, background: "radial-gradient(ellipse at 50% 0%,rgba(34,197,94,0.12) 0%,transparent 70%)" }} />
        <div style={{ position: "absolute", top: "50%", left: "50%", transform: "translate(-50%,-50%)", textAlign: "center", userSelect: "none" }}>
          <div style={{ fontSize: "clamp(60px,12vw,160px)", fontWeight: 900, letterSpacing: "-4px", color: "rgba(74,222,128,0.06)", lineHeight: 1, fontFamily: "Georgia,serif", whiteSpace: "nowrap" }}>SEMENTES</div>
          <div style={{ fontSize: "clamp(40px,8vw,110px)", fontWeight: 900, letterSpacing: "8px", color: "rgba(74,222,128,0.09)", lineHeight: 1, fontFamily: "Georgia,serif", whiteSpace: "nowrap" }}>TORMENTA</div>
        </div>
      </div>

      {/* TOAST */}
      {toast && (
        <div style={{ position: "fixed", top: 24, right: 24, zIndex: 999, background: toast.tipo === "erro" ? "#c0392b" : "#1abc9c", color: "#fff", borderRadius: 12, padding: "12px 22px", fontWeight: 600, fontSize: 14, boxShadow: "0 4px 24px #0008", animation: "fadeIn .3s ease" }}>
          {toast.msg}
        </div>
      )}

      {/* MODAL RETIRADA */}
      {modalRetirada && (
        <Modal onClose={() => setModalRetirada(null)} borderColor="#e74c3c44">
          <div style={{ textAlign: "center", fontSize: 44, marginBottom: 8 }}>{modalRetirada.img}</div>
          <div style={{ textAlign: "center", fontWeight: 700, fontSize: 18, marginBottom: 4 }}>{modalRetirada.nome}</div>
          <div style={{ textAlign: "center", color: "#a8c8a0", fontSize: 13, marginBottom: 20 }}>
            Estoque atual: <b style={{ color: "#e8eaf0" }}>{modalRetirada.estoque} {modalRetirada.unidade}</b>
          </div>
          <label style={S.label}>Quantidade a retirar</label>
          <div style={{ marginBottom: 18 }}>
            <NumericInput value={qtdRetirada} onChange={setQtdRetirada} min={1} max={modalRetirada.estoque} />
          </div>
          <Btn onClick={() => retirar(modalRetirada.id, qtdRetirada)} disabled={modalRetirada.estoque === 0}
            style={{ width: "100%", padding: "13px 0", background: modalRetirada.estoque === 0 ? "#333" : "linear-gradient(90deg,#e74c3c,#c0392b)", marginBottom: 10 }}>
            {modalRetirada.estoque === 0 ? "SEM ESTOQUE" : "CONFIRMAR RETIRADA"}
          </Btn>
          <Btn onClick={() => setModalRetirada(null)} style={{ width: "100%", background: "transparent", border: "1px solid rgba(80,160,60,0.2)", color: "#a8c8a0" }}>Cancelar</Btn>
        </Modal>
      )}

      {/* MODAL ENTRADA */}
      {modalEntrada && (
        <Modal onClose={() => setModalEntrada(null)} borderColor="#1abc9c44">
          <div style={{ textAlign: "center", fontSize: 44, marginBottom: 8 }}>{modalEntrada.img}</div>
          <div style={{ textAlign: "center", fontWeight: 700, fontSize: 18, marginBottom: 4 }}>{modalEntrada.nome}</div>
          <div style={{ textAlign: "center", color: "#a8c8a0", fontSize: 13, marginBottom: 20 }}>
            Estoque atual: <b style={{ color: "#1abc9c" }}>{modalEntrada.estoque} {modalEntrada.unidade}</b>
          </div>
          <label style={S.label}>Quantidade a adicionar</label>
          <div style={{ marginBottom: 14 }}>
            <NumericInput value={qtdEntrada} onChange={setQtdEntrada} min={1} />
          </div>
          <div style={{ background: "#1abc9c11", border: "1px solid #1abc9c33", borderRadius: 10, padding: "10px 14px", fontSize: 13, color: "#1abc9c", marginBottom: 18, textAlign: "center" }}>
            Novo estoque: <b>{modalEntrada.estoque + qtdEntrada} {modalEntrada.unidade}</b>
          </div>
          <Btn onClick={() => entrar(modalEntrada.id, qtdEntrada)} style={{ width: "100%", padding: "13px 0", background: "linear-gradient(90deg,#1abc9c,#16a085)", marginBottom: 10 }}>
            ✅ CONFIRMAR ENTRADA
          </Btn>
          <Btn onClick={() => setModalEntrada(null)} style={{ width: "100%", background: "transparent", border: "1px solid rgba(80,160,60,0.2)", color: "#a8c8a0" }}>Cancelar</Btn>
        </Modal>
      )}

      {/* CONTEÚDO */}
      <div style={{ position: "relative", zIndex: 1, maxWidth: 980, margin: "0 auto", padding: "32px 16px 60px" }}>

        {/* HEADER */}
        <div style={{ textAlign: "center", padding: "16px 0 14px", marginBottom: 24 }}>
          <div style={{ fontSize: "clamp(22px,5vw,36px)", fontWeight: 900, letterSpacing: 2, color: "#e8eaf0", textTransform: "uppercase", fontFamily: "Georgia,serif" }}>
            🌱 Sementes Tormenta
          </div>
          <div style={{ fontSize: 13, color: "#a8c8a0", letterSpacing: 4, textTransform: "uppercase", marginTop: 4 }}>
            Gestão de EPIs
          </div>
        </div>

        {/* ABAS VERTICAIS + CONTEÚDO */}
        <div style={{ display: "flex", gap: 16, alignItems: "flex-start" }}>

          {/* SIDEBAR */}
          <div style={{ display: "flex", flexDirection: "column", gap: 4, background: "rgba(10,20,12,0.72)", borderRadius: 14, padding: 6, minWidth: 170, flexShrink: 0 }}>
            {ABAS.map(t => (
              <button key={t.key}
                onClick={() => { setAba(t.key); if (t.key === "compra") gerarMsgCompra(); }}
                style={{ position: "relative", padding: "11px 14px", borderRadius: 10, border: "none", background: aba === t.key ? "linear-gradient(90deg,#e74c3c,#8e44ad)" : "transparent", color: aba === t.key ? "#fff" : "#a8c8a0", fontWeight: aba === t.key ? 700 : 500, cursor: "pointer", fontSize: 13, textAlign: "left", display: "flex", alignItems: "center", gap: 6 }}>
                {t.label}
                {t.badge > 0 && (
                  <span style={{ marginLeft: "auto", background: "#e74c3c", color: "#fff", borderRadius: "50%", width: 18, height: 18, fontSize: 10, display: "flex", alignItems: "center", justifyContent: "center", fontWeight: 800, flexShrink: 0 }}>{t.badge}</span>
                )}
              </button>
            ))}
          </div>

          {/* CONTEÚDO PRINCIPAL */}
          <div style={{ flex: 1, minWidth: 0 }}>

            {/* ── ESTOQUE ── */}
            {aba === "estoque" && (
              <div style={{ display: "grid", gridTemplateColumns: "repeat(auto-fill,minmax(260px,1fr))", gap: 14 }}>
                {epis.map(epi => {
                  const p  = pct(epi);
                  const cb = corBarra(epi);
                  const cr = epi.estoque < epi.minimo;
                  const sv = statusValidade(epi.validade);
                  return (
                    <div key={epi.id} style={{ ...S.card, border: cr ? "1px solid #e74c3c55" : "1px solid #2a2f45", boxShadow: cr ? "0 0 18px #e74c3c22" : "none", position: "relative" }}>
                      {cr && <div style={{ position: "absolute", top: 12, right: 12, background: "#e74c3c", color: "#fff", borderRadius: 8, padding: "3px 9px", fontSize: 10, fontWeight: 800 }}>CRÍTICO</div>}
                      <div style={{ display: "flex", alignItems: "center", gap: 12, marginBottom: 12 }}>
                        <div style={{ fontSize: 28, width: 48, height: 48, borderRadius: 12, background: "rgba(20,35,20,0.7)", display: "flex", alignItems: "center", justifyContent: "center" }}>{epi.img}</div>
                        <div>
                          <div style={{ fontWeight: 700, fontSize: 15 }}>{epi.nome}</div>
                          <div style={{ fontSize: 12, color: "#a8c8a0" }}>{epi.categoria}</div>
                        </div>
                      </div>
                      <div style={{ display: "flex", justifyContent: "space-between", fontSize: 13, marginBottom: 5 }}>
                        <span style={{ color: "#a8c8a0" }}>Estoque atual</span>
                        <span style={{ fontWeight: 700, color: cr ? "#e74c3c" : "#e8eaf0" }}>{epi.estoque} <span style={{ color: "#a8c8a0", fontWeight: 400 }}>{epi.unidade}</span></span>
                      </div>
                      <div style={{ display: "flex", justifyContent: "space-between", fontSize: 13, marginBottom: 8 }}>
                        <span style={{ color: "#a8c8a0" }}>Mínimo</span>
                        <span style={{ color: "#a8c8a0" }}>{epi.minimo} {epi.unidade}</span>
                      </div>
                      <div style={{ display: "flex", gap: 6, marginBottom: 10, flexWrap: "wrap" }}>
                        {epi.codigo && <span style={{ fontSize: 11, background: "rgba(52,152,219,0.15)", border: "1px solid rgba(52,152,219,0.3)", color: "#3498db", borderRadius: 6, padding: "3px 9px", fontWeight: 700 }}>🔢 {epi.codigo}</span>}
                        {epi.ca && <span style={{ fontSize: 11, background: "rgba(30,50,30,0.8)", border: "1px solid rgba(80,160,60,0.2)", color: "#a8c8a0", borderRadius: 6, padding: "3px 9px", fontWeight: 600 }}>🏷️ CA {epi.ca}</span>}
                        {sv && <span style={{ fontSize: 11, background: sv.cor+"22", border:`1px solid ${sv.cor}44`, color: sv.cor, borderRadius: 6, padding: "3px 9px", fontWeight: 600 }}>📅 {fmtData(epi.validade)} — {sv.label}</span>}
                      </div>
                      <div style={{ background: "rgba(20,35,20,0.7)", borderRadius: 99, height: 7, overflow: "hidden", marginBottom: 4 }}>
                        <div style={{ height: "100%", borderRadius: 99, width: `${p}%`, background: `linear-gradient(90deg,${cb}aa,${cb})`, transition: "width .5s" }} />
                      </div>
                      <div style={{ fontSize: 11, color: "#a8c8a0", textAlign: "right", marginBottom: 12 }}>{p}% do mínimo</div>
                      <div style={{ display: "flex", gap: 8 }}>
                        <Btn onClick={() => { setModalEntrada(epi); setQtdEntrada(1); }} style={{ flex: 1, padding: "8px 0", fontSize: 12, background: "linear-gradient(90deg,#1abc9c,#16a085)" }}>📥 Entrada</Btn>
                        <Btn onClick={() => { setModalRetirada(epi); setQtdRetirada(1); }} style={{ flex: 1, padding: "8px 0", fontSize: 12, background: "linear-gradient(90deg,#e74c3c,#c0392b)" }}>📤 Retirada</Btn>
                        <Btn onClick={() => excluirEpi(epi.id)} style={{ width: 34, padding: "8px 0", background: "transparent", border: "1px solid rgba(80,160,60,0.2)", color: "#a8c8a0", fontSize: 14 }}>🗑</Btn>
                      </div>
                    </div>
                  );
                })}
              </div>
            )}

            {/* ── ENTRADA ── */}
            {aba === "entrada" && (
              <div style={{ display: "flex", flexDirection: "column", gap: 12 }}>
                <div style={{ background: "#1abc9c11", border: "1px solid #1abc9c33", borderRadius: 14, padding: "12px 18px", color: "#1abc9c", fontSize: 14, fontWeight: 600 }}>
                  📥 Selecione o EPI para registrar entrada de estoque
                </div>
                {epis.map(epi => {
                  const cr = epi.estoque < epi.minimo;
                  const sv = statusValidade(epi.validade);
                  return (
                    <div key={epi.id} style={{ ...S.card, border: cr ? "1px solid #e74c3c44" : "1px solid #2a2f45", display: "flex", alignItems: "center", gap: 16 }}>
                      <div style={{ fontSize: 28, width: 48, height: 48, borderRadius: 12, background: "rgba(20,35,20,0.7)", display: "flex", alignItems: "center", justifyContent: "center", flexShrink: 0 }}>{epi.img}</div>
                      <div style={{ flex: 1 }}>
                        <div style={{ fontWeight: 700, fontSize: 15 }}>{epi.nome}</div>
                        <div style={{ fontSize: 12, color: "#a8c8a0", marginBottom: 6 }}>{epi.categoria}</div>
                        <div style={{ display: "flex", gap: 8, flexWrap: "wrap", marginBottom: 4 }}>
                          <span style={{ fontSize: 12, background: cr ? "#e74c3c22" : "#252b3d", color: cr ? "#e74c3c" : "#a8c8a0", borderRadius: 6, padding: "3px 10px", fontWeight: cr ? 700 : 400 }}>Atual: {epi.estoque} {epi.unidade}</span>
                          <span style={{ fontSize: 12, background: "rgba(20,35,20,0.7)", color: "#a8c8a0", borderRadius: 6, padding: "3px 10px" }}>Mín: {epi.minimo} {epi.unidade}</span>
                          {cr && <span style={{ fontSize: 12, background: "#f39c1222", color: "#f39c12", borderRadius: 6, padding: "3px 10px", fontWeight: 700 }}>Falta: {epi.minimo - epi.estoque}</span>}
                        </div>
                        <div style={{ display: "flex", gap: 8, flexWrap: "wrap" }}>
                          {epi.ca && <span style={{ fontSize: 11, background: "rgba(30,50,30,0.8)", border: "1px solid rgba(80,160,60,0.2)", color: "#a8c8a0", borderRadius: 6, padding: "2px 8px" }}>🏷️ CA {epi.ca}</span>}
                          {sv && <span style={{ fontSize: 11, background: sv.cor+"22", border:`1px solid ${sv.cor}44`, color: sv.cor, borderRadius: 6, padding: "2px 8px" }}>📅 {fmtData(epi.validade)} — {sv.label}</span>}
                        </div>
                      </div>
                      <Btn onClick={() => { setModalEntrada(epi); setQtdEntrada(1); }} style={{ background: "linear-gradient(90deg,#1abc9c,#16a085)", flexShrink: 0 }}>📥 Entrada</Btn>
                    </div>
                  );
                })}
              </div>
            )}

            {/* ── CRÍTICOS ── */}
            {aba === "criticos" && (
              <div>
                {criticos.length === 0 ? (
                  <div style={{ textAlign: "center", padding: "60px 0", color: "#1abc9c", fontSize: 18, fontWeight: 600 }}>✅ Todos os EPIs estão com estoque normal!</div>
                ) : (
                  <div style={{ display: "flex", flexDirection: "column", gap: 12 }}>
                    {criticos.map(epi => (
                      <div key={epi.id} style={{ ...S.card, border: "1px solid #e74c3c55", display: "flex", alignItems: "center", gap: 16, boxShadow: "0 0 20px #e74c3c1a" }}>
                        <div style={{ fontSize: 32, width: 52, height: 52, borderRadius: 14, background: "#e74c3c22", display: "flex", alignItems: "center", justifyContent: "center" }}>{epi.img}</div>
                        <div style={{ flex: 1 }}>
                          <div style={{ fontWeight: 700, fontSize: 16 }}>{epi.nome}</div>
                          <div style={{ fontSize: 12, color: "#a8c8a0", marginBottom: 6 }}>{epi.categoria}</div>
                          <div style={{ display: "flex", gap: 8, flexWrap: "wrap", marginBottom: 5 }}>
                            <span style={{ fontSize: 12, background: "#e74c3c22", color: "#e74c3c", borderRadius: 6, padding: "3px 10px", fontWeight: 600 }}>Atual: {epi.estoque} {epi.unidade}</span>
                            <span style={{ fontSize: 12, background: "rgba(20,35,20,0.7)", color: "#a8c8a0", borderRadius: 6, padding: "3px 10px" }}>Mín: {epi.minimo} {epi.unidade}</span>
                            <span style={{ fontSize: 12, background: "#f39c1222", color: "#f39c12", borderRadius: 6, padding: "3px 10px", fontWeight: 600 }}>Falta: {epi.minimo - epi.estoque}</span>
                          </div>
                          <div style={{ display: "flex", gap: 8, flexWrap: "wrap" }}>
                            {epi.ca && <span style={{ fontSize: 11, background: "rgba(30,50,30,0.8)", border: "1px solid rgba(80,160,60,0.2)", color: "#a8c8a0", borderRadius: 6, padding: "2px 8px" }}>🏷️ CA {epi.ca}</span>}
                            {epi.validade && (() => { const sv = statusValidade(epi.validade); return sv ? <span style={{ fontSize: 11, background: sv.cor+"22", border:`1px solid ${sv.cor}44`, color: sv.cor, borderRadius: 6, padding: "2px 8px" }}>📅 {fmtData(epi.validade)} — {sv.label}</span> : null; })()}
                          </div>
                        </div>
                        <div style={{ display: "flex", gap: 8 }}>
                          <Btn onClick={() => { setModalEntrada(epi); setQtdEntrada(1); }} style={{ padding: "8px 12px", fontSize: 13, background: "linear-gradient(90deg,#1abc9c,#16a085)" }}>📥</Btn>
                          <Btn onClick={() => { setModalRetirada(epi); setQtdRetirada(1); }} style={{ padding: "8px 12px", fontSize: 13, background: "linear-gradient(90deg,#e74c3c,#c0392b)" }}>📤</Btn>
                        </div>
                      </div>
                    ))}
                  </div>
                )}
              </div>
            )}

            {/* ── NOVO EPI ── */}
            {aba === "novo" && (
              <div style={{ maxWidth: 560 }}>
                <div style={{ ...S.card }}>
                  <div style={{ fontWeight: 700, fontSize: 17, marginBottom: 22 }}>➕ Cadastrar Novo EPI</div>
                  <div style={{ marginBottom: 18 }}>
                    <label style={S.label}>Ícone</label>
                    <div style={{ display: "flex", flexWrap: "wrap", gap: 8 }}>
                      {EMOJIS.map(em => (
                        <button key={em} onClick={() => setNovoEpi(n => ({ ...n, img: em }))}
                          style={{ width: 40, height: 40, borderRadius: 10, border: novoEpi.img === em ? "2px solid #e74c3c" : "1px solid #2a2f45", background: novoEpi.img === em ? "#e74c3c22" : "#252b3d", fontSize: 20, cursor: "pointer", display: "flex", alignItems: "center", justifyContent: "center" }}>
                          {em}
                        </button>
                      ))}
                    </div>
                  </div>
                  <div style={{ marginBottom: 14 }}>
                    <label style={S.label}>Nome *</label>
                    <input style={{ ...S.input, borderColor: errosEpi.nome ? "#e74c3c" : "rgba(80,160,60,0.2)" }} placeholder="Ex: Luva de Vaqueta"
                      value={novoEpi.nome} onChange={e => setNovoEpi(n => ({ ...n, nome: e.target.value }))} />
                    {errosEpi.nome && <div style={{ color: "#e74c3c", fontSize: 12, marginTop: 4 }}>{errosEpi.nome}</div>}
                  </div>
                  <div style={{ display: "grid", gridTemplateColumns: "1fr 1fr", gap: 14, marginBottom: 14 }}>
                    <div>
                      <label style={S.label}>Categoria</label>
                      <select style={S.input} value={novoEpi.categoria} onChange={e => setNovoEpi(n => ({ ...n, categoria: e.target.value }))}>
                        {CATEGORIAS.map(c => <option key={c}>{c}</option>)}
                      </select>
                    </div>
                    <div>
                      <label style={S.label}>Unidade</label>
                      <select style={S.input} value={novoEpi.unidade} onChange={e => setNovoEpi(n => ({ ...n, unidade: e.target.value }))}>
                        {UNIDADES.map(u => <option key={u}>{u}</option>)}
                      </select>
                    </div>
                  </div>
                  <div style={{ display: "grid", gridTemplateColumns: "1fr 1fr", gap: 14, marginBottom: 14 }}>
                    <div>
                      <label style={S.label}>Estoque inicial</label>
                      <input type="number" min={0} style={S.input} value={novoEpi.estoque}
                        onChange={e => setNovoEpi(n => ({ ...n, estoque: Number(e.target.value) }))} />
                    </div>
                    <div>
                      <label style={S.label}>Estoque mínimo *</label>
                      <input type="number" min={1} style={{ ...S.input, borderColor: errosEpi.minimo ? "#e74c3c" : "rgba(80,160,60,0.2)" }} value={novoEpi.minimo}
                        onChange={e => setNovoEpi(n => ({ ...n, minimo: Number(e.target.value) }))} />
                      {errosEpi.minimo && <div style={{ color: "#e74c3c", fontSize: 12, marginTop: 4 }}>{errosEpi.minimo}</div>}
                    </div>
                  </div>
                  <div style={{ display: "grid", gridTemplateColumns: "1fr 1fr 1fr", gap: 14, marginBottom: 20 }}>
                    <div>
                      <label style={S.label}>🔢 Código interno</label>
                      <input style={S.input} placeholder="Ex: EPI-009"
                        value={novoEpi.codigo} onChange={e => setNovoEpi(n => ({ ...n, codigo: e.target.value }))} />
                    </div>
                    <div>
                      <label style={S.label}>🏷️ Nº CA</label>
                      <input style={S.input} placeholder="Ex: 31469"
                        value={novoEpi.ca} onChange={e => setNovoEpi(n => ({ ...n, ca: e.target.value }))} />
                    </div>
                    <div>
                      <label style={S.label}>📅 Prazo de Validade</label>
                      <input type="date" style={S.input}
                        value={novoEpi.validade} onChange={e => setNovoEpi(n => ({ ...n, validade: e.target.value }))} />
                    </div>
                  </div>
                  <div style={{ background: "rgba(20,35,20,0.7)", borderRadius: 14, padding: "14px 18px", marginBottom: 20, display: "flex", alignItems: "center", gap: 14 }}>
                    <div style={{ fontSize: 30 }}>{novoEpi.img}</div>
                    <div style={{ flex: 1 }}>
                      <div style={{ fontWeight: 700 }}>{novoEpi.nome || "Nome do EPI"}</div>
                      <div style={{ fontSize: 12, color: "#a8c8a0" }}>{novoEpi.categoria} · {novoEpi.estoque} {novoEpi.unidade} · mín. {novoEpi.minimo}</div>
                      <div style={{ fontSize: 11, color: "#a8c8a0", marginTop: 3 }}>
                        {novoEpi.ca && <span style={{ marginRight: 10 }}>🏷️ CA {novoEpi.ca}</span>}
                        {novoEpi.validade && <span>📅 {fmtData(novoEpi.validade)}</span>}
                      </div>
                    </div>
                    {novoEpi.estoque < novoEpi.minimo && <div style={{ background: "#e74c3c", color: "#fff", borderRadius: 8, padding: "3px 9px", fontSize: 10, fontWeight: 800 }}>CRÍTICO</div>}
                  </div>
                  <Btn onClick={salvarEpi} style={{ width: "100%", padding: "14px 0", fontSize: 15, background: "linear-gradient(90deg,#8e44ad,#e74c3c)" }}>
                    ➕ CADASTRAR EPI
                  </Btn>
                </div>
              </div>
            )}

            {/* ── SOLICITAR COMPRA ── */}
            {aba === "compra" && (
              <div style={{ maxWidth: 620 }}>
                <div style={{ ...S.card }}>
                  <div style={{ fontWeight: 700, fontSize: 17, marginBottom: 18 }}>📲 Solicitar Compra via WhatsApp</div>
                  {criticos.length === 0
                    ? <div style={{ background: "#1abc9c22", border: "1px solid #1abc9c44", borderRadius: 12, padding: "12px 16px", color: "#1abc9c", fontSize: 14, marginBottom: 18, fontWeight: 600 }}>✅ Nenhum EPI crítico no momento.</div>
                    : <div style={{ background: "#e74c3c22", border: "1px solid #e74c3c44", borderRadius: 12, padding: "12px 16px", color: "#e74c3c", fontSize: 14, marginBottom: 18, fontWeight: 600 }}>⚠️ {criticos.length} EPI(s) abaixo do mínimo — reposição urgente!</div>
                  }
                  <div style={{ marginBottom: 18 }}>
                    <label style={S.label}>Mensagem</label>
                    <textarea value={msgCompra} onChange={e => setMsgCompra(e.target.value)} rows={12}
                      style={{ ...S.input, resize: "vertical", fontFamily: "monospace", lineHeight: 1.7 }} />
                  </div>
                  <div style={{ display: "flex", gap: 10 }}>
                    <Btn onClick={gerarMsgCompra} style={{ padding: "11px 22px", background: "rgba(20,35,20,0.7)", border: "1px solid rgba(80,160,60,0.2)", color: "#a8c8a0" }}>🔄 Regenerar</Btn>
                    <Btn onClick={enviarWhatsapp} style={{ flex: 1, padding: "12px 0", fontSize: 15, background: enviado ? "#1abc9c" : "linear-gradient(90deg,#25d366,#128c7e)" }}>
                      {enviado ? "✅ Aberto!" : "📲 Enviar pelo WhatsApp Web"}
                    </Btn>
                  </div>
                </div>
              </div>
            )}

            {/* ── CÓDIGOS ── */}
            {aba === "codigos" && (
              <div style={{ maxWidth: 720 }}>
                <div style={{ ...S.card, marginBottom: 16 }}>
                  <div style={{ fontWeight: 700, fontSize: 17, marginBottom: 4 }}>🔢 Gerenciar Códigos dos EPIs</div>
                  <div style={{ fontSize: 13, color: "#a8c8a0" }}>Edite o código interno de cada EPI diretamente na tabela abaixo.</div>
                </div>
                <div style={{ display: "flex", flexDirection: "column", gap: 10 }}>
                  {epis.map(epi => (
                    <div key={epi.id} style={{ ...S.card, display: "flex", alignItems: "center", gap: 14 }}>
                      <div style={{ fontSize: 26, width: 44, height: 44, borderRadius: 10, background: "rgba(20,35,20,0.7)", display: "flex", alignItems: "center", justifyContent: "center", flexShrink: 0 }}>{epi.img}</div>
                      <div style={{ flex: 1, minWidth: 0 }}>
                        <div style={{ fontWeight: 700, fontSize: 14, marginBottom: 2 }}>{epi.nome}</div>
                        <div style={{ fontSize: 12, color: "#a8c8a0" }}>{epi.categoria}</div>
                      </div>
                      <div style={{ display: "flex", gap: 10, alignItems: "center", flexShrink: 0 }}>
                        <div>
                          <div style={{ fontSize: 11, color: "#a8c8a0", marginBottom: 4 }}>Código</div>
                          <input
                            style={{ ...S.input, width: 130, padding: "7px 10px", fontSize: 13, borderColor: "rgba(52,152,219,0.4)" }}
                            placeholder="Ex: EPI-001"
                            value={epi.codigo || ""}
                            onChange={e => setEpis(prev => prev.map(ep => ep.id === epi.id ? { ...ep, codigo: e.target.value } : ep))}
                          />
                        </div>
                        <div>
                          <div style={{ fontSize: 11, color: "#a8c8a0", marginBottom: 4 }}>CA</div>
                          <input
                            style={{ ...S.input, width: 110, padding: "7px 10px", fontSize: 13 }}
                            placeholder="Ex: 31469"
                            value={epi.ca || ""}
                            onChange={e => setEpis(prev => prev.map(ep => ep.id === epi.id ? { ...ep, ca: e.target.value } : ep))}
                          />
                        </div>
                      </div>
                    </div>
                  ))}
                </div>
                <div style={{ marginTop: 16, background: "#1abc9c11", border: "1px solid #1abc9c33", borderRadius: 12, padding: "10px 16px", fontSize: 13, color: "#1abc9c" }}>
                  ✅ As alterações são salvas automaticamente na sessão atual.
                </div>
              </div>
            )}

            {/* ── RELATÓRIO PDF ── */}
            {aba === "relatorio" && (
              <div style={{ maxWidth: 720 }}>
                <div style={{ ...S.card, marginBottom: 16 }}>
                  <div style={{ fontWeight: 700, fontSize: 17, marginBottom: 12 }}>📄 Gerar Relatório PDF</div>
                  <div style={{ fontSize: 13, color: "#a8c8a0", marginBottom: 18 }}>
                    Clique em <b style={{ color: "#e8eaf0" }}>Imprimir / Salvar como PDF</b> para exportar o relatório completo do estoque de EPIs.
                  </div>
                  <Btn onClick={gerarPDF} style={{ padding: "13px 28px", fontSize: 15, background: "linear-gradient(90deg,#e74c3c,#8e44ad)", marginRight: 10 }}>
                    🖨️ IMPRIMIR / SALVAR PDF
                  </Btn>
                </div>

                {/* Preview da tabela */}
                <div style={{ ...S.card, overflowX: "auto" }}>
                  <div style={{ fontWeight: 700, fontSize: 14, marginBottom: 14, color: "#a8c8a0" }}>Prévia do relatório</div>
                  <table style={{ width: "100%", borderCollapse: "collapse", fontSize: 12 }}>
                    <thead>
                      <tr>
                        {["EPI","Código","Categoria","Status","Estoque","Mínimo","CA","Validade"].map(h => (
                          <th key={h} style={{ background: "rgba(20,35,20,0.9)", color: "#a8c8a0", padding: "8px 10px", textAlign: "left", fontWeight: 700, fontSize: 11, whiteSpace: "nowrap" }}>{h}</th>
                        ))}
                      </tr>
                    </thead>
                    <tbody>
                      {epis.map((epi, i) => {
                        const cr = epi.estoque < epi.minimo;
                        const sv = statusValidade(epi.validade);
                        return (
                          <tr key={epi.id} style={{ background: i % 2 === 0 ? "rgba(15,25,15,0.3)" : "transparent" }}>
                            <td style={{ padding: "7px 10px", color: "#e8eaf0" }}>{epi.img} {epi.nome}</td>
                            <td style={{ padding: "7px 10px", color: "#3498db", fontWeight: 700 }}>{epi.codigo || "—"}</td>
                            <td style={{ padding: "7px 10px", color: "#a8c8a0" }}>{epi.categoria}</td>
                            <td style={{ padding: "7px 10px" }}>
                              <span style={{ background: cr ? "#e74c3c22" : "#1abc9c22", color: cr ? "#e74c3c" : "#1abc9c", borderRadius: 6, padding: "2px 8px", fontWeight: 700, fontSize: 11 }}>{cr ? "CRÍTICO" : "OK"}</span>
                            </td>
                            <td style={{ padding: "7px 10px", color: cr ? "#e74c3c" : "#e8eaf0", fontWeight: 700 }}>{epi.estoque} {epi.unidade}</td>
                            <td style={{ padding: "7px 10px", color: "#a8c8a0" }}>{epi.minimo} {epi.unidade}</td>
                            <td style={{ padding: "7px 10px", color: "#a8c8a0" }}>{epi.ca || "—"}</td>
                            <td style={{ padding: "7px 10px", color: sv ? sv.cor : "#a8c8a0", fontSize: 11 }}>
                              {fmtData(epi.validade)}{sv ? ` (${sv.label})` : ""}
                            </td>
                          </tr>
                        );
                      })}
                    </tbody>
                  </table>
                </div>
              </div>
            )}

            {/* ── USUÁRIOS ── */}
            {aba === "usuarios" && (
              <div style={{ maxWidth: 680 }}>
                <div style={{ ...S.card, marginBottom: 20 }}>
                  <div style={{ fontWeight: 700, fontSize: 16, marginBottom: 18 }}>👥 Convidar Novo Usuário</div>
                  <div style={{ display: "grid", gridTemplateColumns: "1fr 1fr", gap: 14, marginBottom: 14 }}>
                    <div>
                      <label style={S.label}>Nome completo *</label>
                      <input style={{ ...S.input, borderColor: errosUser.nome ? "#e74c3c" : "rgba(80,160,60,0.2)" }} placeholder="João da Silva"
                        value={novoUser.nome} onChange={e => setNovoUser(n => ({ ...n, nome: e.target.value }))} />
                      {errosUser.nome && <div style={{ color: "#e74c3c", fontSize: 12, marginTop: 4 }}>{errosUser.nome}</div>}
                    </div>
                    <div>
                      <label style={S.label}>Cargo / Função</label>
                      <input style={S.input} placeholder="Ex: Almoxarife"
                        value={novoUser.cargo} onChange={e => setNovoUser(n => ({ ...n, cargo: e.target.value }))} />
                    </div>
                  </div>
                  <div style={{ marginBottom: 14 }}>
                    <label style={S.label}>📲 WhatsApp</label>
                    <input type="tel" style={{ ...S.input, borderColor: errosUser.contato ? "#e74c3c" : "rgba(80,160,60,0.2)" }} placeholder="(47) 99999-0000"
                      value={novoUser.whatsapp} onChange={e => setNovoUser(n => ({ ...n, whatsapp: e.target.value }))} />
                    {errosUser.contato && <div style={{ color: "#e74c3c", fontSize: 12, marginTop: 4 }}>⚠️ {errosUser.contato}</div>}
                  </div>
                  <div style={{ marginBottom: 18 }}>
                    <label style={S.label}>Perfil de acesso</label>
                    <select style={S.input} value={novoUser.perfil} onChange={e => setNovoUser(n => ({ ...n, perfil: e.target.value }))}>
                      <option value="admin">👑 Administrador — acesso total</option>
                      <option value="editor">✏️ Editor — pode editar estoque</option>
                      <option value="visualizador">👁 Visualizador — somente leitura</option>
                    </select>
                  </div>
                  <Btn onClick={convidar} style={{ width: "100%", padding: "13px 0", fontSize: 15, background: "linear-gradient(90deg,#25d366,#128c7e)" }}>
                    📲 CONVIDAR PELO WHATSAPP
                  </Btn>
                </div>

                <div style={{ display: "grid", gridTemplateColumns: "repeat(3,1fr)", gap: 10, marginBottom: 20 }}>
                  {[
                    { label: "Administrador", desc: "Acesso total",         icon: "👑", cor: "#8e44ad" },
                    { label: "Editor",        desc: "Edita estoque e EPIs", icon: "✏️", cor: "#3498db" },
                    { label: "Visualizador",  desc: "Somente leitura",      icon: "👁", cor: "#a8c8a0" },
                  ].map(p => (
                    <div key={p.label} style={{ ...S.card, padding: "14px 16px" }}>
                      <div style={{ fontSize: 20, marginBottom: 4 }}>{p.icon}</div>
                      <div style={{ fontWeight: 700, fontSize: 13, color: p.cor }}>{p.label}</div>
                      <div style={{ fontSize: 11, color: "#a8c8a0", marginTop: 2 }}>{p.desc}</div>
                    </div>
                  ))}
                </div>

                <div style={{ fontWeight: 700, fontSize: 14, color: "#a8c8a0", marginBottom: 12 }}>Usuários cadastrados ({usuarios.length})</div>
                <div style={{ display: "flex", flexDirection: "column", gap: 10 }}>
                  {usuarios.map(u => {
                    const perfilCor   = u.perfil === "admin" ? "#8e44ad" : u.perfil === "editor" ? "#3498db" : "#a8c8a0";
                    const perfilLabel = u.perfil === "admin" ? "👑 Admin" : u.perfil === "editor" ? "✏️ Editor" : "👁 Viewer";
                    return (
                      <div key={u.id} style={{ ...S.card, display: "flex", alignItems: "center", gap: 14 }}>
                        <div style={{ width: 44, height: 44, borderRadius: 12, background: u.cor+"33", border: `2px solid ${u.cor}66`, display: "flex", alignItems: "center", justifyContent: "center", fontWeight: 800, fontSize: 14, color: u.cor, flexShrink: 0 }}>
                          {u.avatar}
                        </div>
                        <div style={{ flex: 1, minWidth: 0 }}>
                          <div style={{ fontWeight: 700, fontSize: 15, display: "flex", alignItems: "center", gap: 8, flexWrap: "wrap" }}>
                            {u.nome}
                            <span style={{ fontSize: 10, background: u.status === "ativo" ? "#1abc9c22" : u.status === "pendente" ? "#f39c1222" : "#8892b022", color: u.status === "ativo" ? "#1abc9c" : u.status === "pendente" ? "#f39c12" : "#a8c8a0", borderRadius: 6, padding: "2px 8px", fontWeight: 600, textTransform: "uppercase" }}>
                              {u.status === "pendente" ? "⏳ pendente" : u.status}
                            </span>
                          </div>
                          <div style={{ fontSize: 12, color: "#a8c8a0", marginTop: 3 }}>{u.whatsapp && `📲 ${u.whatsapp}`}</div>
                          {u.cargo && <div style={{ fontSize: 11, color: "#a8c8a0", marginTop: 2 }}>{u.cargo}</div>}
                        </div>
                        <div style={{ display: "flex", alignItems: "center", gap: 6, flexShrink: 0 }}>
                          <span style={{ fontSize: 11, padding: "4px 10px", borderRadius: 8, background: perfilCor+"22", color: perfilCor, fontWeight: 600 }}>{perfilLabel}</span>
                          {u.whatsapp && (
                            <Btn onClick={() => enviarWppConvite(u)} title="Reenviar convite"
                              style={{ width: 32, height: 32, padding: 0, fontSize: 14, background: "rgba(20,35,20,0.7)", border: "1px solid rgba(80,160,60,0.2)" }}>📲</Btn>
                          )}
                          {u.status !== "pendente" && (
                            <Btn onClick={() => toggleUser(u.id)}
                              style={{ width: 32, height: 32, padding: 0, fontSize: 14, background: "transparent", border: "1px solid rgba(80,160,60,0.2)", color: u.status === "ativo" ? "#1abc9c" : "#a8c8a0" }}>
                              {u.status === "ativo" ? "✅" : "⛔"}
                            </Btn>
                          )}
                          <Btn onClick={() => removerUser(u.id)}
                            style={{ width: 32, height: 32, padding: 0, fontSize: 14, background: "transparent", border: "1px solid rgba(80,160,60,0.2)", color: "#e74c3c" }}>🗑</Btn>
                        </div>
                      </div>
                    );
                  })}
                </div>
              </div>
            )}

          </div>{/* fim conteúdo principal */}
        </div>{/* fim flex sidebar+conteúdo */}
      </div>
    </div>
  );
}

ReactDOM.createRoot(document.getElementById("root")).render(<App />);
</script>
</body>
</html>

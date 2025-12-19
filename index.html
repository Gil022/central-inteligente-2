
<!DOCTYPE html>
<html lang="pt-BR">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>Central Inteligente</title>

<script src="https://cdn.jsdelivr.net/npm/@supabase/supabase-js@2"></script>

<style>
body {
  font-family: Arial, sans-serif;
  background: #f6f6f6;
  display: flex;
  justify-content: center;
  padding: 20px;
}
.container {
  background: #fff;
  width: 100%;
  max-width: 700px;
  padding: 20px;
  border-radius: 10px;
}
form {
  display: flex;
  gap: 10px;
}
input {
  flex: 1;
  padding: 10px;
}
button {
  padding: 10px;
}
.card {
  background: #f1f1f1;
  padding: 10px;
  margin-top: 10px;
  border-left: 4px solid #d63384;
}
.pergunta {
  font-weight: bold;
}
.resposta {
  margin-top: 5px;
}
</style>
</head>

<body>
<div class="container">
  <h2>Central Inteligente</h2>

  <form id="form">
    <input
      id="pergunta"
      placeholder="Digite sua pergunta..."
      required
    />
    <button>Enviar</button>
  </form>

  <div id="lista"></div>
</div>

<script>
/* ================= CONFIGURAÇÃO SUPABASE ================= */

// URL do seu projeto
const SUPABASE_URL = "https://pjrwtxskphvmdkfesevm.supabase.co";

// ✅ ANON KEY JÁ INCLUÍDA (pública)
const SUPABASE_ANON_KEY =
  "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJzdXBhYmFzZSIsInJlZiI6InBqcnd0eHNrcGh2bWRrZmVzZXZtIiwicm9sZSI6ImFub24iLCJpYXQiOjE3NjYwNjk2ODgsImV4cCI6MjA4MTY0NTY4OH0.9F4I5pvsV1FwAfOOynnsmtCOkwJFEHi7x2UBAwf4jWo";

// evita erro de redeclaração no TrebEdit
if (!window.supabaseClient) {
  window.supabaseClient = supabase.createClient(
    SUPABASE_URL,
    SUPABASE_ANON_KEY
  );
}

const supabaseClient = window.supabaseClient;

/* ================= FUNÇÕES ================= */

// chama a Edge Function (OpenAI está no backend)
async function gerarResposta(pergunta) {
  const response = await fetch(
    `${SUPABASE_URL}/functions/v1/gerar-resposta`,
    {
      method: "POST",
      headers: {
        "Content-Type": "application/json",
        "apikey": SUPABASE_ANON_KEY,
        "Authorization": `Bearer ${SUPABASE_ANON_KEY}`
      },
      body: JSON.stringify({ pergunta })
    }
  );

  const data = await response.json();
  return data.resposta || "Não foi possível gerar resposta.";
}

// salva no Supabase
async function salvarPergunta(pergunta, resposta) {
  await supabaseClient
    .from("perguntas")
    .insert([{ texto: pergunta, resposta }]);
}

// carrega histórico
async function carregarPerguntas() {
  const { data } = await supabaseClient
    .from("perguntas")
    .select("*")
    .order("created_at", { ascending: false });

  const lista = document.getElementById("lista");
  lista.innerHTML = "";

  data.forEach(item => {
    lista.innerHTML += `
      <div class="card">
        <div class="pergunta">${item.texto}</div>
        <div class="resposta">${item.resposta}</div>
      </div>
    `;
  });
}

/* ================= EVENTO ================= */

document.getElementById("form").addEventListener("submit", async e => {
  e.preventDefault();

  const input = document.getElementById("pergunta");
  const pergunta = input.value;
  input.value = "";

  const resposta = await gerarResposta(pergunta);
  await salvarPergunta(pergunta, resposta);
  carregarPerguntas();
});

/* ================= INICIAL ================= */
carregarPerguntas();
</script>
</body>
</html>


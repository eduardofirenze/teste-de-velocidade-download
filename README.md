# 🚀 Teste de Velocidade da Internet (JavaScript)

Um medidor simples de velocidade de **download** feito com **JavaScript puro** usando `fetch()` e `performance.now()`.

Este projeto baixa um arquivo de teste e calcula a velocidade da conexão em **Mbps**.

---

## 📌 Demonstração

Ao clicar no botão:

* O navegador baixa um arquivo de tamanho conhecido
* O tempo de download é medido
* A velocidade é calculada
* O resultado é exibido na tela

---

## 🧠 Como Funciona

O script:

1. Faz o download de um arquivo de teste
2. Mede o tempo total da requisição
3. Obtém o tamanho real do arquivo
4. Calcula a taxa de transferência

Fórmula utilizada:

```
velocidade (Mbps) = (tamanho_em_bytes × 8) / tempo / (1024 × 1024)
```

---

## 🛠️ Tecnologias Utilizadas

* HTML5
* JavaScript (Vanilla JS)
* Fetch API
* Performance API

---

## 📄 Código

```html
<button onclick="testDownload()">Teste de velocidade</button>
<p id="result"></p>

<script>
  async function testDownload() {
    const fileUrl = "https://speed.cloudflare.com/__down?bytes=10000000";
    const startTime = performance.now();

    const response = await fetch(fileUrl, { cache: "no-store" });
    const data = await response.blob();

    const endTime = performance.now();

    const duration = (endTime - startTime) / 1000;
    const fileSizeBytes = data.size;
    const speedMbps = (fileSizeBytes * 8) / duration / (1024 * 1024);

    document.getElementById('result').innerText =
      `Download: ${speedMbps.toFixed(2)} Mbps`;
  }
</script>
```

---

## ⚡ Por Que Cloudflare?

A URL da Cloudflare é ideal para testes porque:

✅ Permite requisições via `fetch()`
✅ Não bloqueia por CORS
✅ Permite definir o tamanho do arquivo

Exemplo:

```
bytes=10000000 → 10MB
bytes=50000000 → 50MB
```

---

## 📈 Melhorias Futuras

Ideias para evoluir o projeto:

* [ ] Teste de Upload
* [ ] Barra de progresso
* [ ] Animação de medição
* [ ] Histórico de testes
* [ ] Interface estilo SpeedTest

---

## 🎯 Objetivo do Projeto

Projeto criado para:

✔ Estudo de JavaScript Assíncrono
✔ Prática com Fetch API
✔ Cálculos de performance
✔ Portfólio GitHub

---

## 👨‍💻 Autor

Desenvolvido por **Edu** 😏

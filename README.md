# atividadeTechWeek
# Diário Algorítmico da Tech Week

**UC:** Algoritmos e Programação.
**Professor:** Montanha. 
**Atividade:** Diário Algorítmico da Tech Week.

---

## Parte 1: Registro das Atividades

### Atividade 1: Google + IBM
* **Título da atividade:** Tech Week XII - Dia 2: Google + IBM 
* **Data e horário:** 16 de setembro de 2026, às 19h00
* **Palestrante:** Marcelo Pereira e Adriana Petendil (Google Cloud)
* **descrição:** Apresentação focada no uso da inteligência artificial generativa no contexto educacional por meio da ferramenta *NotebookLM* do Google. Foi demonstrado como carregar materiais de estudo próprios (PDFs, notas, links) para interagir com a IA. Como a ferramenta consulta estritamente os documentos fornecidos pelo usuário, ela garante um foco restrito que elimina alucinações de respostas e permite gerar resumos ou tirar dúvidas diretamente da fonte.
* **Principal aprendizado:** Compreensão de como afunilar o contexto de um modelo de linguagem reduz alucinações e garante alta precisão no processamento de dados. Além disso, destacou-se a importância da IA como ferramenta de suporte ao estudo para estruturar e correlacionar conteúdos complexos em vez de substituir o raciocínio humano.

---

### Atividade 2: Globo + Oracle
* **Título da atividade:** Tech Week XII - Dia 3: Globo + Oracle 
* **Data e horário:** 17 de setembro de 2026, às 19h00
* **Palestrante:** Mateus, Karen, Priscila e equipe da Academia LED / Globo
* **descrição:** Os palestrantes mostraram os bastidores da aplicação de inteligência artificial e efeitos visuais/VFX no processo de produção de conteúdo da Globo. Foi exemplificado o uso da IA para simulações visuais complexas, como a geração de chamas e fumaça em cenas que envolvem crianças em estúdio (onde o uso de fogo real é proibido por lei), permitindo criar e integrar elementos gráficos sobre a gravação original de forma ágil e segura.
* **Principal aprendizado:** A IA é um poderoso motor de automação e processamento de dados gráficos/computacionais que atua no apoio à tomada de decisão e na segurança da equipe. Ela reduz tempo de execução e custos, dependendo sempre do direcionamento técnico e da validação de profissionais qualificados.

---

## Parte 2: Modelagem da Solução

### Problema Escolhido
**Validação e Automação de Cenas com Efeitos de Fogo Seguros (Inspirado na palestra da Globo):**  
Modelar um algoritmo que analisa os requisitos de segurança de um conjunto de cenas gravadas. Se a cena contiver elementos de risco (como a presença de crianças) e exigir fogo, o sistema aciona a geração de chamas via IA/VFX; caso contrário, autoriza a gravação física tradicional ou sem efeitos especiais. O processo repete a verificação para todas as cenas do episódio.

---

### Entrada:
* `quantidadeCenas`: Número total de cenas a serem processadas no episódio.
* Para cada cena:
  * `temCrianca`: Valor booleano (`true` se houver crianças, `false` se não).
  * `precisaFogo`: Valor booleano (`true` se a cena exige fogo, `false` se não).

---

### Processamento:
1. Inicializar a contagem da cena atual em 1 (`cenaAtual = 1`).
2. **Estrutura de Repetição (`while` / `for`):** Enquanto `cenaAtual <= quantidadeCenas`, executar:
   * Ler os dados de `temCrianca` e `precisaFogo` da cena.
   * **Estrutura de Decisão (`if / else`):**
     * **SE** `precisaFogo == true` **E** `temCrianca == true`:
       * Definir status da cena como: `"Gerar efeito de fogo via IA/VFX em pós-produção (Segurança Confirmada)"`.
     * **SENÃO SE** `precisaFogo == true` **E** `temCrianca == false`:
       * Definir status da cena como: `"Efeito prático permitido sob supervisão de bombeiros"`.
     * **SENÃO:**
       * Definir status da cena como: `"Gravação convencional sem efeitos de fogo"`.
   * Incrementar o contador de cenas (`cenaAtual = cenaAtual + 1`) para evitar laço infinito.

---

### Saída:
* Lista consolidada informando a decisão de produção e o método de execução recomendado para cada uma das cenas analisadas no episódio.

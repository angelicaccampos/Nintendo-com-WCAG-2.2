# Nintendo com WCAG 2.2
Front-end acessível: implementação prática de critérios com os critérios 3.3.3, 3.3.5  WCAG 2.2.

## ✨ Introdução

## 📝 Critérios WCAG 2.2 Implementados

| Critério WCAG 2.2 | Descrição | Nível |
|---------------------|-----------|-------|
| **3.3.3 - Sugestão de erro** | Se um erro de entrada for detectado automaticamente e sugestões de correção forem conhecidas, elas serão fornecidas ao usuário, a menos que isso coloque em risco a segurança ou a finalidade do conteúdo. [WCAG 2.2 - 3.3.3](https://www.w3.org/TR/WCAG22/#error-suggestion)| AA |
| **3.3.5 - Ajuda** | Ajuda contextual está disponível. [WCAG 2.2 - 3.3.5](https://www.w3.org/TR/WCAG22/#help)| AAA |

## 🎯 Importância e Público-Alvo
Ambos os critérios 3.3.3 e 3.3.5 da WCAG 2.2 são fundamentais para criar uma experiência web mais inclusiva, focando em ajudar os usuários a evitar e corrigir erros, e a se autenticar de forma mais fácil e acessível, beneficiando um amplo espectro de pessoas, especialmente aquelas com diversas deficiências.

- Pessoas com deficiências cognitivas: Podem ter dificuldade em entender a natureza de um erro e como corrigi-lo sem orientação clara.
- Pessoas com deficiências visuais: Podem não conseguir identificar visualmente a localização exata do erro ou a forma de corrigi-lo.
- Pessoas com deficiências motoras: Podem se beneficiar da redução do número de tentativas necessárias para corrigir um erro, minimizando movimentos repetitivos.
- Qualquer usuário: Em geral, todos os usuários se beneficiam de sugestões de erro claras, pois isso melhora a experiência e a eficiência na interação com o site.

## 💻 Técnicas de Programação Utilizadas
### Validação de Formulários e Sugestão de Erro (WCAG 2.2 - Critério 3.3.3)
Para tornar a entrada de dados mais robusta e amigável, especialmente em caso de erros, utilizamos as seguintes técnicas:
* **Atributos como `required`, `type="email"`, `type="number"`, `minlength`, `maxlength`, `pattern`:** Esses atributos HTML5 foram empregados diretamente nos campos de entrada (`<input>`) para permitir que o navegador faça uma validação inicial. Isso oferece um feedback imediato e padronizado ao usuário sobre o formato ou preenchimento esperado, antes mesmo de qualquer interação com JavaScript.
* **Mensagens de Erro Claras e Contextuais:** Para além da validação nativa, implementamos JavaScript para fornecer mensagens de erro mais específicas e amigáveis. Em vez de apenas informar "campo inválido", as mensagens dão **sugestões claras de correção** (ex: "O email deve conter '@' e um domínio. Ex: seu.email@dominio.com").
* **Feedback Visual de Erros:** Campos que contêm erros recebem uma **estilização visual** (ex: borda vermelha) para que o usuário identifique rapidamente onde precisa fazer as correções.
* **Associação Semântica com ARIA (`aria-describedby`):** As mensagens de erro são vinculadas semanticamente aos campos de input através do atributo `aria-describedby`. Isso é fundamental para usuários de leitores de tela, que são informados sobre o erro e a sugestão de correção assim que o foco está no campo problemático.
* **Foco Programático:** Em caso de erro, o foco do teclado é direcionado automaticamente para o primeiro campo inválido, otimizando a navegação para usuários de teclado.
* **Regiões ARIA Live (`aria-live="assertive"`):** Utilizamos uma área `aria-live="assertive"` para anunciar mensagens de status e erros gerais do formulário (ex: "Há erros no formulário. Por favor, corrija os campos marcados.") para leitores de tela, garantindo que nenhum erro passe despercebido.

### Autenticação Acessível (WCAG 2.2 - Critério 3.3.5)
Para simplificar e tornar o processo de autenticação mais seguro e acessível, adotamos as seguintes práticas:
* **Atributo `autocomplete`:** Utilizado nos campos de email (`autocomplete="username"`) e senha (`autocomplete="current-password"`). Este atributo auxilia gerenciadores de senhas e navegadores a preencher automaticamente as credenciais, reduzindo a necessidade de digitação manual e memorização de senhas complexas.
* **Liberação do "Copiar e Colar":** O código não impede a funcionalidade padrão de copiar e colar nos campos de input, permitindo que usuários com deficiências motoras ou que dependam de gerenciadores de senhas insiram suas credenciais sem barreiras.

* **Botão "Mostrar Senha":** Adicionamos um botão que permite ao usuário alternar a visibilidade da senha digitada (`type="password"` vs. `type="text"`). Isso é vital para usuários com deficiências cognitivas, dislexia ou dificuldades motoras, que podem precisar revisar o que digitaram para evitar erros.
* **Atributos ARIA para o botão:** O botão "Mostrar Senha" possui os atributos `aria-controls` (apontando para o campo de senha) e `aria-pressed` (indicando se a senha está sendo exibida ou não), comunicando seu propósito e estado de forma clara para tecnologias assistivas.

* **Lista de Requisitos Visível:** Uma lista clara dos requisitos de senha (ex: "Mínimo de 8 caracteres", "Pelo menos uma letra maiúscula") é apresentada diretamente abaixo do campo de senha.
* **Feedback em Tempo Real:** Via JavaScript, cada item da lista de requisitos é atualizado visualmente (ex: **cor verde** para requisito atendido, **vermelho** para não atendido) conforme o usuário digita. Essa **validação visual em tempo real**, combinada com a associação `aria-describedby` ao campo de senha, oferece um guia intuitivo e acessível para a criação de senhas fortes.

## 🚀 Como Rodar o Código
### Requisitos
- Navegador moderno (Google Chrome, Firefox, Edge, etc.).
- Estrutura de arquivos:
``
/assets
├── logo-nitendo.png
├── super-mario-bros-o-filme.jpeg
index.html
``

### Passo a Passo
1. Clone este repositório ou baixe o projeto em seu computador.
2. Garanta que os arquivos estejam organizados conforme a estrutura acima.
3. Abra o arquivo index.html em seu navegador.
4. Navegue pela página e utilize recursos como leitor de tela, navegação por teclado e zoom para testar a acessibilidade.

## 📚 Referências
WORLD WIDE WEB CONSORTIUM W3C. WCAG 2.2 - 3.3.3 Sugestão de Erro. Disponível em: https://www.w3.org/TR/WCAG22/#error-suggestion. Acesso em: 25 de junho de 2025.

WORLD WIDE WEB CONSORTIUM W3C. Understanding WCAG 2.2 - Help. Disponível em: https://www.w3.org/WAI/WCAG22/Understanding/help.html. Acesso em: 25 de junho de 2025.

WORLD WIDE WEB CONSORTIUM W3C. Understanding WCAG 2.2 - Error Suggestion. Disponível em: https://www.w3.org/WAI/WCAG22/Understanding/error-suggestion.html. Acesso em: 25 de junho de 2025.

WORLD WIDE WEB CONSORTIUM W3C. WCAG 2.2 Quick Reference - Error Suggestion. Disponível em: https://www.w3.org/WAI/WCAG22/quickref/#error-suggestion. Acesso em: 25 de junho de 2025.

WORLD WIDE WEB CONSORTIUM W3C. WCAG 2.2 Quick Reference - Redundant Entry. Disponível em: https://www.w3.org/WAI/WCAG22/quickref/#redundant-entry. Acesso em: 25 de junho de 2025.

## 🙋‍♀️ Contribuidores
<table>
  <tr>
    <td align="center">
      <a href="https://github.com/angelicaccampos">
        <img src="https://github.com/angelicaccampos.png" width="100px;" style="border-radius: 50%;" alt="Foto de Angélica Campos"/>
        <br />
        <sub><b>Angélica Campos</b></sub>
      </a>
    </td>
        <td align="center">
      <a href="https://github.com/Felipej3ds">
        <img src="https://avatars.githubusercontent.com/u/173021374?v=4" width="100px;" style="border-radius: 50%;" alt="png"/>
        <br />
        <sub><b>Felipe Júnior Duarte</b></sub>
      </a>
    </td>
        <td align="center">
            <a href="https://github.com/Caio-Antonio">
        <img src="https://avatars.githubusercontent.com/u/126700289?v=4" width="100px;" style="border-radius: 50%;" alt="png"/>
        <br />
        <sub><b>Caio Antonio</b></sub>
      </a>
    </td>
    <td align="center">
            <a href="https://github.com/leticiakrpaiva">
        <img src="https://avatars.githubusercontent.com/u/114038884?v=4" width="100px;" style="border-radius: 50%;" alt="png"/>
        <br />
        <sub><b>Letícia Paiva</b></sub>
      </a>
    </td>


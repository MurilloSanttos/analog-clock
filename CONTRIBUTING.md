# Guia de Contribuição - Relógio Analógico

## 1. 👋 Boas-Vindas

Obrigado pelo seu interesse em contribuir com o projeto **Relógio Analógico**! Este é um projeto open source desenvolvido com HTML, CSS e JavaScript puro, e toda ajuda é muito bem-vinda.

Seja você um desenvolvedor experiente ou está começando, há muitas formas de contribuir:
- 🐛 Reportar bugs
- 💡 Sugerir novas funcionalidades
- 📝 Melhorar documentação
- 🔧 Corrigir issues
- 🎨 Aprimorar o design

## 2. 🚀 Como Contribuir

### Primeiros Passos

1. **Fork do Repositório**
   ```bash
   # Clique no botão 'Fork' no GitHub ou use:
   gh repo fork MurilloSanttos/analog-clock
   ```

2. **Clonar Localmente**
   ```bash
   git clone https://github.com/MurilloSanttos/analog-clock.git
   cd analog-clock
   ```

3. **Configurar Remote Original**
   ```bash
   git remote add upstream https://github.com/MurilloSanttos/analog-clock.git
   git fetch upstream
   ```

### Fluxo de Desenvolvimento

#### Criando uma Branch
```bash
# Sempre crie uma branch descritiva para suas alterações
git checkout -b feature/nome-da-feature
# ou
git checkout -b fix/corrigir-problema-x
# ou
git checkout -b docs/melhorar-documentacao
```

#### Estrutura de Branches Recomendada
- `feature/` - Para novas funcionalidades
- `fix/` - Para correções de bugs
- `docs/` - Para melhorias na documentação
- `style/` - Para mudanças de estilo que não afetam funcionalidade
- `refactor/` - Para refatoração de código

#### Testando Alterações Localmente
```bash
# Usando Python
python -m http.server 8000

# Usando Node.js (se disponível)
npx http-server

# Abra no navegador: http://localhost:8000
```

#### Fazendo Commits
```bash
# Adicione arquivos modificados
git add .

# Faça commit com mensagem descritiva
git commit -m "feat: adicionar tema escuro ao relógio"

# Ou use mensagem multi-linha
git commit -m "feat: implementar alarmes simples

- Adicionar função de alarme com notificação visual
- Implementar interface para configurar horários
- Adicionar feedback sonoro opcional"
```

### Convenção de Commits
Use o padrão **Conventional Commits**:

| Tipo | Descrição |
|------|-----------|
| `feat` | Nova funcionalidade |
| `fix` | Correção de bug |
| `docs` | Mudanças na documentação |
| `style` | Formatação, código CSS |
| `refactor` | Refatoração de código |
| `test` | Adicionar testes |
| `chore` | Tarefas de manutenção |

### Enviando Pull Request

1. **Sincronize com upstream**
   ```bash
   git fetch upstream
   git rebase upstream/main
   ```

2. **Push para seu fork**
   ```bash
   git push origin feature/nome-da-feature
   ```

3. **Crie o Pull Request no GitHub**
   - Use o template de PR fornecido
   - Descreva claramente as mudanças
   - Referencie issues relacionadas (ex: `Fixes #12`)

## 3. 📝 Padrões de Código

### HTML
```html
<!-- Use HTML semântico -->
<section class="clock-container">
  <div class="clock-face">
    <!-- Elementos do relógio -->
  </div>
</section>

<!-- Atributos alt em imagens -->
<img src="icon.png" alt="Ícone do relógio" width="32" height="32">
```

### CSS
```css
/* Use BEM methodology */
.clock {
  /* Estilos base */
}

.clock__face {
  /* Elemento */
}

.clock__hand--hour {
  /* Modificador */
}

/* Variáveis CSS para cores */
:root {
  --primary-color: #2c3e50;
  --secondary-color: #3498db;
}

.clock {
  background-color: var(--primary-color);
}
```

### JavaScript
```javascript
/**
 * Função para atualizar ponteiros do relógio
 * @param {Date} currentTime - Objeto Date com hora atual
 */
function updateClockHands(currentTime) {
  const hours = currentTime.getHours();
  const minutes = currentTime.getMinutes();
  const seconds = currentTime.getSeconds();
  
  // Cálculo dos ângulos
  const hourAngle = (hours % 12) * 30 + minutes * 0.5;
  const minuteAngle = minutes * 6;
  const secondAngle = seconds * 6;
  
  applyRotation('.hour-hand', hourAngle);
  applyRotation('.minute-hand', minuteAngle);
  applyRotation('.second-hand', secondAngle);
}

// Use const/let em vez de var
const CLOCK_CONFIG = {
  updateInterval: 1000,
  smoothTransition: true
};
```

## 4. 🔍 Processo de Revisão de PRs

### O que Esperamos em um PR
- ✅ **Código testado** localmente
- ✅ **Documentação atualizada** (se aplicável)
- ✅ **Seguindo padrões** de código do projeto
- ✅ **Commits organizados** e descritivos
- ✅ **Descrição clara** das mudanças

### Etapas da Revisão

1. **Revisão Inicial** (24-48h)
   - Verificação de conformidade com padrões
   - Testes básicos de funcionalidade

2. **Feedback dos Mantenedores**
   - Comentários no PR
   - Sugestões de melhoria
   - Possíveis requests de changes

3. **Aprovação e Merge**
   - Requer aprovação de pelo menos 1 mantenedor
   - Squash merge para manter histórico limpo
   - Delete da branch após merge

### Status do PR
- 🟡 **Aguardando Revisão** - PR recém-criado
- 🔵 **Em Revisão** - Sendo analisado pelos mantenedores
- 🟠 **Precisa de Ajustes** - Requer mudanças do autor
- 🟢 **Aprovado** - Pronto para merge
- ✅ **Merged** - Incorporado ao projeto

## 5. 🐛 Reportando Problemas

### Criando uma Issue

**Template de Bug Report:**
```markdown
## Descrição do Bug
[Descreva claramente o problema]

## Passos para Reproduzir
1. Vá para '...'
2. Clique em '....'
3. Role até '....'
4. Veja o erro

## Comportamento Esperado
[O que deveria acontecer]

## Comportamento Atual
[O que está acontecendo]

## Screenshots
[Se aplicável, adicione screenshots]

## Ambiente
- Navegador: [ex: Chrome 98, Firefox 97]
- SO: [ex: Windows 11, macOS 12]
- Versão do Projeto: [ex: v1.2.0]

## Informações Adicionais
[Qualquer outra informação relevante]
```

**Template de Feature Request:**
```markdown
## Descrição da Feature
[Descreva a funcionalidade desejada]

## Problema que Resolve
[Qual problema essa feature resolve?]

## Solução Proposta
[Como você imagina que deveria funcionar]

## Alternativas Consideradas
[Outras soluções possíveis]

## Contexto Adicional
[Qualquer informação adicional]
```

### Categorias de Issues
- `bug` - Comportamento inesperado ou erro
- `enhancement` - Melhoria em funcionalidade existente
- `feature` - Nova funcionalidade
- `documentation` - Problemas ou melhorias na docs
- `question` - Dúvidas sobre o projeto

## 6. ⚖️ Códigos e Diretrizes

### Código de Conduta
Todos os contribuidores devem seguir nosso [Código de Conduta](CODE_OF_CONDUCT.md). Relate comportamentos inapropriados para: **murilo.azevedo.d.santos@gmail.com**

### Segurança
Para reportar vulnerabilidades de segurança, consulte nossa [Política de Segurança](SECURITY.md).

### Licença
Ao contribuir, você concorda que suas contribuições serão licenciadas sob a [Licença MIT](LICENSE) do projeto.

## 7. 📞 Contato e Suporte

### Canais de Comunicação
- **📧 E-mail Principal**: murilo.azevedo.d.santos@gmail.com
- **🐛 Issues no GitHub**: Para problemas técnicos e feature requests
- **💬 Discussões**: Use as Discussions do GitHub para dúvidas

### Tempo de Resposta
- **Issues Críticas**: 24-48 horas
- **PRs**: 2-5 dias para revisão inicial
- **Dúvidas Gerais**: 3-7 dias

---

**Precisa de Ajuda?** Não hesite em perguntar! Estamos aqui para ajudar você a contribuir com sucesso. 🚀

*Última atualização: Outubro 2025*

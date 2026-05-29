# 💓 Coração em Partículas

Uma animação 3D interativa e imersiva de um coração feito de partículas com física suave, responsividade total e suporte a gesto de dispositivo. Renderizado em tempo real com Three.js, animado com GSAP e estilizado com Tailwind CSS.

[![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=flat-square&logo=html5&logoColor=white)](https://developer.mozilla.org/en-US/docs/Web/HTML)
[![Three.js](https://img.shields.io/badge/Three.js-000000?style=flat-square&logo=three.js&logoColor=white)](https://threejs.org)
[![GSAP](https://img.shields.io/badge/GSAP-88CE02?style=flat-square&logo=greensock&logoColor=white)](https://greensock.com)
[![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS-38B2AC?style=flat-square&logo=tailwind-css&logoColor=white)](https://tailwindcss.com)
[![License](https://img.shields.io/badge/License-MIT-green.svg?style=flat-square)](LICENSE)

---

## ✨ Características Principais

### 🎨 Visualização Deslumbrante
- **Coração 3D em partículas** renderizado com geometria matemática perfeita
- **Cor rosa/vermelho neon** (#ff2255) com brilho aditivo suave
- **400 partículas** organizadas em forma de coração
- Fundo preto com gradiente radial para profundidade

### 🎬 Animações Fluidas
- **Transições suaves** de partículas aleatórias para forma final
- **Movimento orgânico** com repetição contínua (yoyo animation)
- **Rotação constante** com oscilação natural
- Efeito de **"breathing"** - pulsação delicada na interface

### 🖱️ Interatividade Total
- **Rastreamento de mouse** - partículas respondem ao movimento do cursor
- **Suporte a touch** - funciona perfeitamente em dispositivos móveis
- **Sensor de orientação** - reage a inclinação do dispositivo (gyroscope)
- **Responsividade dinâmica** - se adapta a qualquer tamanho de tela

### 🎭 Design Moderno
- Interface com **efeito glassmorphism** (vidro translúcido)
- **Backdrop blur** com semi-transparência elegante
- Informações sobrepostas não intrusivas
- Mensagens de status e instruções contextualmente posicionadas

---

## 🚀 Como Usar

### 1. Abrir Diretamente
Simplesmente abra o arquivo `love.html` em seu navegador:

```bash
# No Windows
start love.html

# No macOS
open love.html

# No Linux
xdg-open love.html
```

### 2. Usando um Servidor Local (Recomendado)
Para melhor desempenho, sirva através de HTTP:

```bash
# Com Python 3
python -m http.server 8000

# Com Python 2
python -m SimpleHTTPServer 8000

# Com Node.js (http-server)
npx http-server
```

Depois acesse `http://localhost:8000/love.html`

### 3. Integrar em Seu Projeto
Copie o arquivo `love.html` para seu projeto e abra:

```html
<iframe src="love.html" width="100%" height="100%" frameborder="0"></iframe>
```

---

## 🎮 Interação

| Ação | Efeito |
|------|--------|
| **Mover o mouse** | Partículas respondem à posição do cursor |
| **Toque na tela** | Interação tátil funciona em dispositivos móveis |
| **Virar dispositivo** | Sensores de movimento (acelerômetro/giroscópio) controlam rotação |
| **Redimensionar janela** | Animação se adapta automaticamente |

---

## 🛠️ Tecnologias Utilizadas

### Bibliotecas Externas

| Tecnologia | Versão | Propósito |
|------------|--------|----------|
| **Three.js** | r128 | Renderização 3D WebGL |
| **GSAP** | 3.12.2 | Animações avançadas |
| **Tailwind CSS** | Latest | Estilização e layout |

### Recursos Nativos

- **Canvas WebGL** - Renderização de alta performance
- **DeviceOrientation API** - Acesso a sensores de movimento
- **RequestAnimationFrame** - Otimização de renderização
- **WebGL BufferGeometry** - Geometria de partículas otimizada

---

## 📐 Técnica Matemática

### Geração do Coração
O projeto usa a **equação paramétrica do coração** para gerar as posições das partículas:

```javascript
x = 16 * sin(t)³
y = 13 * cos(t) - 5 * cos(2t) - 2 * cos(3t) - cos(4t)
```

Onde `t` varia de 0 a 2π, criando uma forma perfeita de coração.

### Animação de Partículas
- **Estado inicial**: Posições aleatórias no espaço 3D
- **Estado final**: Posições na forma do coração
- **Transição**: 2.5 a 4.5 segundos com easing power3.inOut
- **Repetição**: Ciclo contínuo com yoyo (ida e volta)

---

## 🎯 Estrutura do Arquivo

```
love.html
├── Head
│   ├── Meta tags (charset, viewport)
│   ├── Tailwind CSS (CDN)
│   ├── Three.js (CDN)
│   └── GSAP (CDN)
├── Styles
│   ├── Glass effect
│   ├── Pulse animation
│   └── Float animation
├── HTML
│   ├── Renderização 3D
│   ├── UI informativa
│   └── Instructions overlay
└── JavaScript
    ├── Inicialização de cena 3D
    ├── Geometria de partículas
    ├── Animações GSAP
    ├── Rastreamento de input
    └── Loop de renderização
```

---

## 🎨 Customização

### Alterar Cor do Coração
Procure por esta linha no script e altere o valor hexadecimal:

```javascript
color: 0xff2255,  // Mude para a cor desejada (hex sem #)
```

Exemplos de cores:
- `0xff0000` - Vermelho puro
- `0xff69b4` - Rosa quente
- `0xff1493` - Rosa profundo

### Mudar Quantidade de Partículas
Altere a constante `TOTAL`:

```javascript
const TOTAL = 400;  // Aumente para mais partículas, diminua para menos
```

### Ajustar Velocidade de Animação
Modifique a duração da animação:

```javascript
duration: 2.5 + Math.random() * 2.0,  // Tempo em segundos
```

### Alterar Tamanho das Partículas
Modifique o tamanho no material:

```javascript
size: 0.6,  // Aumentar para partículas maiores
```

---

## 📊 Performance

| Métrica | Valor |
|---------|-------|
| Partículas | 400 |
| FPS alvo | 60 |
| Tamanho do arquivo | ~6.3 KB |
| Dependências externas | 3 CDNs |
| Memória estimada | ~50 MB (com Buffer) |

### Otimizações Aplicadas
- ✅ BufferGeometry para melhor performance
- ✅ PointsMaterial com AdditiveBlending
- ✅ Anti-aliasing adaptativo
- ✅ Pixel ratio limitado a 1.5x para economia
- ✅ RequestAnimationFrame para sincronização

---

## 🌐 Compatibilidade

| Navegador | Status | Notas |
|-----------|--------|-------|
| **Chrome** | ✅ Suportado | Performance excelente |
| **Firefox** | ✅ Suportado | Totalmente compatível |
| **Safari** | ✅ Suportado | Compatível com iOS |
| **Edge** | ✅ Suportado | Baseado em Chromium |
| **Opera** | ✅ Suportado | Sem problemas |

### Requerimentos Mínimos
- Navegador com suporte a WebGL
- ES6+ (2015) ou superior
- 128 MB de RAM
- Aceleração de GPU (recomendada)

---

## 📱 Responsividade

O projeto é 100% responsivo:

```
┌─────────────┐  ┌──────────────┐  ┌───────────────┐
│  Mobile     │  │  Tablet      │  │  Desktop      │
│  (360x640)  │  │  (768x1024)  │  │  (1920x1080)  │
│      ✅     │  │      ✅      │  │      ✅       │
└─────────────┘  └──────────────┘  └───────────────┘
```

---

## 🔧 Troubleshooting

### "WebGL não suportado"
Se receber este erro, seu navegador não tem suporte a WebGL. Solução:
- Atualize para a versão mais recente do navegador
- Habilite aceleração de GPU nas configurações
- Use um navegador moderno (Chrome, Firefox, Safari)

### "Partículas não se movem com mouse"
- Certifique-se de que o JavaScript está habilitado
- Verifique se há erros no console do navegador (F12)
- Recarregue a página

### "Animação travando ou lenta"
- Reduza `TOTAL` de partículas
- Feche abas desnecessárias
- Verifique se há outros processos consumindo recursos
- Tente desabilitar extensões do navegador

### "Sensores não funcionam no mobile"
- Verifique se tem permissão concedida para "Device Orientation"
- Em iOS, abra em modo retrato
- Alguns navegadores requerem HTTPS para acesso a sensores

---

## 💡 Casos de Uso

- 💌 Convite para namorado(a)
- 🎁 Página especial para datas comemorativas
- 💍 Propostas criativas
- 🎵 Fundo de página pessoal/blog
- 🎨 Portfolio criativo
- 🎬 Videoclip ou conteúdo multimedia
- 🎮 Jogo interativo

---

## 🎓 Aprendizados

Este projeto demonstra:

✅ Geometria matemática em gráficos 3D  
✅ Animações com GSAP e Three.js  
✅ Input handling (mouse, touch, sensores)  
✅ WebGL e BufferGeometry  
✅ Responsive design  
✅ Efeitos visuais modernos  

---

## 📝 Licença

Este projeto está licenciado sob a Licença MIT - sinta-se livre para usar, modificar e compartilhar!

---

## 👨‍💻 Autor

**Luis Guigui**
- GitHub: [@luisguigui](https://github.com/luisguigui)
- Projeto: [Coração em Partículas](https://github.com/luisguigui/Coracao-em-particulas)

---

## 🌟 Agradecimentos

- [Three.js](https://threejs.org) - Incrível biblioteca 3D
- [GSAP](https://greensock.com) - Animações de classe mundial
- [Tailwind CSS](https://tailwindcss.com) - Estilização moderna
- Comunidade web criativa

---

## 📞 Feedback

Gostou do projeto? Deixe uma ⭐ no GitHub!

Encontrou um bug? Abra uma [Issue](https://github.com/luisguigui/Coracao-em-particulas/issues)

---

**Desenvolvido com ❤️ em HTML/JavaScript**

*"A beleza está na simplicidade, e a simplicidade está nos detalhes."*

### 🎬 Experimente Agora
Abra `love.html` no seu navegador e sinta a magia! ✨

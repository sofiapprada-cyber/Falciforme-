# 🩸 Falciforme+ 

Sistema integrado de gestão para doentes com Anemia Falciforme

![Version](https://img.shields.io/badge/version-2.0-blue)
![License](https://img.shields.io/badge/license-MIT-green)
![Platform](https://img.shields.io/badge/platform-Web-orange)

## 📋 Índice

- [Sobre o Projeto](#sobre-o-projeto)
- [Funcionalidades](#funcionalidades)
- [Demo](#demo)
- [Tecnologias](#tecnologias)
- [Instalação](#instalação)
- [Estrutura de Ficheiros](#estrutura-de-ficheiros)
- [Como Usar](#como-usar)
- [Credenciais de Teste](#credenciais-de-teste)
- [Capturas de Ecrã](#capturas-de-ecrã)
- [Roadmap](#roadmap)
- [Contribuir](#contribuir)
- [Licença](#licença)
- [Contacto](#contacto)

## 🎯 Sobre o Projeto

**Falciforme+** é uma plataforma web completa para gestão de Anemia Falciforme, composta por dois portais integrados:

- **Portal do Doente**: Para registo diário de sintomas, medicação e acompanhamento pessoal
- **Portal do Profissional de Saúde**: Para monitorização em tempo real e gestão de múltiplos doentes

O sistema foi desenvolvido com foco em:
- ✅ Simplicidade de uso
- ✅ Sincronização automática de dados
- ✅ Alertas inteligentes
- ✅ Responsividade total (desktop, tablet, mobile)
- ✅ Armazenamento local (localStorage)

## ⭐ Funcionalidades

### Portal do Doente 👤

#### 📊 Gestão de Saúde
- Registo de sintomas (dor, febre, cansaço, dificuldade respiratória)
- Controlo de medicação diária (Hidroxiureia, Ácido Fólico)
- Registo de analgésicos SOS (Paracetamol, Ibuprofeno, Metamizol)
- Histórico completo de sintomas e medicação

#### 🩸 Informações de Transfusão
- Aceita/não aceita transfusões
- Data da última transfusão (preenchida automaticamente pelo sistema hospitalar)
- História de reações transfusionais
- Necessidade de medicação pré-transfusão
- Hemoglobina basal

#### 👤 Perfil Completo
- ⚠️ **Alergias medicamentosas** (destaque de segurança)
- 🏥 Outras doenças e condições médicas
- 📧 Email e telefone de contacto
- 📋 Informação pessoal completa

#### 📅 Funcionalidades Adicionais
- Calendário de consultas e urgências
- FAQ sobre Anemia Falciforme
- Interface intuitiva e responsiva

### Portal do Profissional 👨‍⚕️

#### 📈 Dashboard em Tempo Real
- Lista de todos os doentes registados
- Atualização automática a cada 10 segundos
- Indicadores visuais de estado (🟢 🟡 🔴)

#### 🚨 Sistema de Alertas Inteligentes (13 tipos)
1. **Dor Intensa** - Nível > 7/10 nas últimas 48h
2. **Dor Moderada** - Nível 4-6/10 nas últimas 48h
3. **Dor Prolongada** - Mais de 48 horas
4. **Dor Consecutiva** - 2 dias seguidos
5. **Febre** - Nas últimas 48h
6. **Cansaço Intenso** - Forte ou extremo
7. **Cansaço Moderado** - Nas últimas 48h
8. **Dificuldade Respiratória Forte** - Severa
9. **Dificuldade Respiratória Moderada**
10. **Analgésicos Prolongados** - Mais de 48h de uso
11. **Uso Excessivo de Analgésicos** - Mais de 3 tomas/dia
12. **Sem Registo de Medicação** - 7 dias sem registo
13. **Hemoglobina Crítica** - < 6 g/dL

#### 📊 Visualização de Dados do Doente
- **Resumo**: Estatísticas dos últimos 7 dias
- **Perfil**: Informação completa, alergias, transfusões
- **Sintomas**: Histórico detalhado com timeline
- **Medicação**: Adesão e registo de tomas
- **Histórico**: Consultas e urgências
- **Análises**: Resultados laboratoriais com gráficos

#### 🔄 Sincronização Automática
- Dados partilhados via localStorage
- Atualizações em tempo real
- Sem necessidade de backend

## 🚀 Demo

Aceda à demo online: [https://seu-usuario.github.io/falciforme-plus/](https://seu-usuario.github.io/falciforme-plus/)

## 🛠️ Tecnologias

- **HTML5** - Estrutura
- **CSS3** - Estilos e responsividade
- **JavaScript (Vanilla)** - Lógica e funcionalidades
- **LocalStorage** - Armazenamento de dados
- **Responsive Design** - Mobile-first approach

### Sem Dependências Externas
- ✅ Não requer Node.js
- ✅ Não requer npm
- ✅ Não requer servidor
- ✅ Funciona 100% no browser

## 📥 Instalação

### Opção 1: GitHub Pages (Recomendado)

1. Faça fork deste repositório
2. Ative o GitHub Pages nas definições do repositório
3. Aceda através do URL: `https://seu-usuario.github.io/falciforme-plus/`

### Opção 2: Local

1. Clone o repositório:
```bash
git clone https://github.com/seu-usuario/falciforme-plus.git
cd falciforme-plus
```

2. Abra o ficheiro `index.html` no seu browser:
```bash
# No Windows
start index.html

# No Mac
open index.html

# No Linux
xdg-open index.html
```

Ou simplesmente arraste o ficheiro `index.html` para o browser.

## 📁 Estrutura de Ficheiros

```
falciforme-plus/
│
├── index.html                      # Página inicial com escolha de portal
├── app-anemia-falciforme.html     # Portal do Doente
├── app-profissional-saude.html    # Portal do Profissional
└── README.md                       # Este ficheiro
```

## 📖 Como Usar

### 1️⃣ Acesso Inicial
1. Abra `index.html` no browser
2. Escolha o portal desejado:
   - **Portal do Doente** - Para pacientes
   - **Portal do Profissional** - Para médicos/enfermeiros

### 2️⃣ Portal do Doente

#### Primeiro Acesso:
1. Clique em "Criar Nova Conta"
2. Preencha os dados:
   - Nome completo
   - Data de nascimento
   - Género
   - Telefone (opcional)
   - Email
   - Password
3. Após registo, será direcionado para o portal

#### Utilização Diária:
- **Início**: Resumo do dia
- **Sintomas**: Registe dor, febre, cansaço, etc.
- **Medicação**: Marque medicação tomada/não tomada
- **Transfusões**: Preencha informações importantes
- **Calendário**: Veja próximas consultas
- **Perfil**: Atualize alergias e outras doenças

### 3️⃣ Portal do Profissional

#### Primeiro Acesso:
1. Clique em "Criar Conta"
2. Preencha os dados:
   - Nome
   - Especialidade
   - Nº Cédula
   - Instituição
   - Email
   - Password

#### Monitorização:
1. **Dashboard**: Veja lista de doentes e alertas
2. **Clique num doente**: Abre modal com informação completa
3. **Navegue pelos tabs**: Resumo, Perfil, Sintomas, etc.
4. **Alertas**: Veja alertas organizados por prioridade

## 🔐 Credenciais de Teste

### Portal do Doente
```
Email: demo@falciforme.pt
Password: demo123
```

### Portal do Profissional
```
Email: medico@hospital.pt
Password: medico123
```

## 📸 Capturas de Ecrã

### Portal do Doente
- Interface limpa e intuitiva
- Menu inferior com 6 secções
- Formulários simples de preenchimento

### Portal do Profissional
- Dashboard com 2 colunas
- Sistema de alertas visual
- Modal detalhado para cada doente

## 🗺️ Roadmap

### Versão 2.1 (Planeada)
- [ ] Exportação de relatórios em PDF
- [ ] Gráficos de evolução
- [ ] Notificações push
- [ ] Modo escuro

### Versão 3.0 (Futuro)
- [ ] Backend com base de dados real
- [ ] App móvel nativa (iOS/Android)
- [ ] Integração com sistemas hospitalares
- [ ] Telemedicina integrada

## 🤝 Contribuir

Contribuições são muito bem-vindas! Para contribuir:

1. Faça fork do projeto
2. Crie uma branch para a sua feature (`git checkout -b feature/MinhaFeature`)
3. Commit as suas alterações (`git commit -m 'Adiciona MinhaFeature'`)
4. Push para a branch (`git push origin feature/MinhaFeature`)
5. Abra um Pull Request

### Áreas onde precisamos de ajuda:
- 🎨 Design/UI melhorias
- 🐛 Correção de bugs
- 📱 Testes em diferentes dispositivos
- 📝 Documentação
- 🌍 Traduções

## 📄 Licença

Distribuído sob a licença MIT. Veja `LICENSE` para mais informações.

## 👥 Autores

- **Equipa Falciforme+** - *Desenvolvimento inicial*

## 📞 Contacto

- 🌐 Website: [https://github.com/seu-usuario/falciforme-plus](https://github.com/seu-usuario/falciforme-plus)
- 📧 Email: contacto@falciformeplus.pt
- 🐛 Issues: [https://github.com/seu-usuario/falciforme-plus/issues](https://github.com/seu-usuario/falciforme-plus/issues)

## 🙏 Agradecimentos

- A todos os profissionais de saúde que forneceram feedback
- Aos doentes que testaram a plataforma
- À comunidade open-source

## ⚠️ Aviso Legal

Esta aplicação é uma ferramenta de apoio e não substitui a consulta médica. Em caso de emergência, dirija-se imediatamente ao serviço de urgência mais próximo.

---

⭐ Se este projeto foi útil, considere dar uma estrela no GitHub!

**Desenvolvido com ❤️ para a comunidade de Anemia Falciforme**

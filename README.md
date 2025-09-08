# 🚀 App Demo - Projeto de Estudo CI/CD

![Node.js](https://img.shields.io/badge/Node.js-339933?style=for-the-badge&logo=nodedotjs&logoColor=white)
![Express](https://img.shields.io/badge/Express-000000?style=for-the-badge&logo=express&logoColor=white)
![GitHub Actions](https://img.shields.io/badge/GitHub_Actions-2088FF?style=for-the-badge&logo=github-actions&logoColor=white)
![Oracle Cloud](https://img.shields.io/badge/Oracle_Cloud-F80000?style=for-the-badge&logo=oracle&logoColor=white)

## 📚 Sobre o Projeto

Este é um repositório de estudo focado em aprender e implementar práticas de **DevOps** e **CI/CD** (Continuous Integration/Continuous Deployment). O projeto demonstra a configuração completa de um pipeline de deploy automático usando GitHub Actions para uma aplicação Node.js hospedada na Oracle Cloud Infrastructure.

## 🎯 Objetivos de Aprendizado

- ✅ Configurar um servidor web com Node.js e Express
- ✅ Implementar visualização dinâmica com EJS
- ✅ Criar pipeline de CI/CD com GitHub Actions
- ✅ Automatizar deploy via SSH para servidor remoto
- ✅ Configurar notificações via Discord Webhook
- ✅ Gerenciar secrets e variáveis de ambiente
- ✅ Trabalhar com systemd para gerenciamento de serviços

## 🛠️ Tecnologias Utilizadas

### Backend
- **Node.js** - Runtime JavaScript
- **Express** - Framework web minimalista
- **EJS** - Template engine para renderização de views
- **Moment.js** - Manipulação de datas

### DevOps & Infraestrutura
- **GitHub Actions** - Automação de workflows CI/CD
- **Oracle Cloud** - Hospedagem em VM Ubuntu
- **Nginx** - Proxy reverso (configurado no servidor)
- **Systemd** - Gerenciamento de serviço Linux

## 📂 Estrutura do Projeto

```
appdemo1/
├── .github/
│   └── workflows/
│       └── main.yml         # Pipeline de CI/CD
├── views/
│   └── index.ejs           # Template da página principal
├── app.js                  # Aplicação principal Express
├── package.json            # Dependências do projeto
├── package-lock.json       # Lock file das dependências
├── .gitignore             # Arquivos ignorados pelo Git
└── README.md              # Este arquivo
```

## 🚀 Como Executar Localmente

### Pré-requisitos
- Node.js (v14 ou superior)
- npm ou yarn

### Instalação

1. Clone o repositório:
```bash
git clone https://github.com/seu-usuario/appdemo1.git
cd appdemo1
```

2. Instale as dependências:
```bash
npm install
```

3. Execute a aplicação:
```bash
node app.js
```

4. Acesse no navegador:
```
http://localhost:3000
```

## 🔄 Pipeline de Deploy Automático

O projeto utiliza GitHub Actions para automatizar o processo de deploy. O workflow é acionado:

- 🔄 **Push** na branch `master`
- 🔀 **Pull Request** para branch `master`
- 🖱️ **Manualmente** via workflow_dispatch

### Etapas do Deploy

1. **Checkout** - Clona o código do repositório
2. **Configuração SSH** - Prepara chave privada para acesso ao servidor
3. **Criação de Diretório** - Garante que o diretório existe no servidor
4. **Permissões** - Ajusta permissões adequadas
5. **Transferência** - Copia arquivos via SCP
6. **Instalação** - Executa `npm install` no servidor
7. **Restart** - Reinicia o serviço systemd
8. **Notificação** - Envia mensagem ao Discord

## 🔐 Configuração de Secrets

Para o pipeline funcionar, configure os seguintes secrets no GitHub:

| Secret | Descrição |
|--------|-----------|
| `HOST` | IP do servidor (ex: 137.131.250.166) |
| `KEY` | Conteúdo da chave SSH privada |
| `DISCORD_WEBHOOK` | URL do webhook do Discord |

### Como configurar:
1. Vá em **Settings** → **Secrets and variables** → **Actions**
2. Clique em **New repository secret**
3. Adicione cada secret com seu valor correspondente

## 📊 Monitoramento

A aplicação exibe em tempo real:
- 🌐 **IP do Servidor** - Endereço IP da máquina
- 🕐 **Hora Atual** - Timestamp do servidor
- ✅ **Status** - Indicador de servidor online

## 🤝 Contribuindo

Este é um projeto de estudo, mas sugestões e melhorias são bem-vindas! Sinta-se à vontade para:

1. Fazer um Fork do projeto
2. Criar uma branch para sua feature (`git checkout -b feature/AmazingFeature`)
3. Commit suas mudanças (`git commit -m 'Add some AmazingFeature'`)
4. Push para a branch (`git push origin feature/AmazingFeature`)
5. Abrir um Pull Request

## 📝 Licença

Este projeto é de uso educacional e está disponível para livre uso e modificação.

## 🎓 Aprendizados Documentados

### GitHub Actions
- Uso de `secrets` para dados sensíveis
- Execução de comandos SSH remotos
- Transferência de arquivos via SCP
- Integração com webhooks externos

### Servidor Linux
- Configuração de serviços systemd
- Gerenciamento de permissões
- Estrutura de diretórios
- Proxy reverso com Nginx

### Boas Práticas
- Versionamento semântico
- Separação de configurações sensíveis
- Documentação clara e objetiva
- Pipeline automatizado de deploy

## 📞 Contato

Projeto desenvolvido para fins de estudo e aprendizado de DevOps e CI/CD.

---

⭐ **Dica**: Este projeto é ideal para quem está começando com DevOps e quer entender na prática como funciona um pipeline de deploy automático!
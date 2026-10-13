# Plataforma de Indução SIR Motors

Portal em GitHub Pages com navegação institucional e aplicação de autenticação em `app.html`.

## Estado
Código-base do fluxo de registo, perfil, pedidos, aprovação e convites administrativos. **Não está operacional sem configurar e publicar os serviços Firebase.** Os documentos internos não estão alojados neste repositório e não deverão ser publicados no GitHub Pages.

## Preparação
1. Criar projecto Firebase, activar Authentication > Email/Password, Firestore e Functions.
2. Inserir os dados **públicos** do projecto no `firebase-config.js`.
3. Definir domínio autorizado `sirmotors4-questionarios.github.io` em Authentication.
4. Instalar Firebase CLI e executar `firebase deploy --only firestore:rules,functions` num ambiente de administração seguro.
5. Configurar a extensão Firebase **Trigger Email** para a colecção `mail`, com fornecedor SMTP autorizado. Enquanto não estiver configurada, os convites e alertas não serão entregues.
6. Executar `scripts/bootstrap-superadmin.cjs` localmente com credenciais do Firebase Admin SDK protegidas. Primeiro superadministrador: `nbdevelopment@sirmotors.com`. Não guardar credenciais no GitHub.
7. Validar em ambiente de teste o fluxo de confirmação de e-mail, registo, aprovação, convite e privilégios, antes de permitir utilizadores reais.

## Segurança
O site estático em GitHub Pages é **público**. O acesso protegido deve ser aplicado no backend; não confiar em botões ocultos nem no departamento declarado. Não publicar manuais, tokens, listas privadas de colaboradores ou ficheiros de serviço no repositório. As regras em `firestore.rules` bloqueiam acesso directo a dados administrativos e restringem documentos.

## Trabalho pendente
- Configuração Firebase, domínio e serviço de e-mail;
- Activação de convite e permissões com UI completa;
- Armazenamento privado e concessões granulares para manuais;
- Migração dos conteúdos autorizados do Notion;
- Testes de segurança e fluxo ponta a ponta.

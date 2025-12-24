# Valores de Segurança

##  Tríade CIA / CID Original
- **Confidencialidade**: garantir que pessoas não autorizadas não tenham acesso a documentos não autorizados. Exemplos de controles que ajudam a garantir confidencialidade: criptografia, 2FA, *airgaps*, etc.
- **Integridade**: garantir que uma mensagem não tenha seu conteúdo alterado durante o transporte. Exemplos de controles que ajudam a garantir integridade: sistema de controle de acesso, controle de versão, permissões de arquivo, etc.
- **Disponibilidade** (Avaliability): manter o serviço funcionando nos respectivos períodos de tempo pré-decididos. Exemplos de controles que ajudam a garantir disponibilidade: atualizações, backup, etc.

### Outros pilares
- **Não repúdio**: ao realizar algo, ninguém pode dizer que não foi você que fez aquilo. Exemplos de controles que ajudam a garantir não repúdio: geração de logs, proteção de logs, infraestrutura de chave pública (PKI), assinaturas digitais, etc.
- **Privacidade**: direito individual de manter as informações privadas confidenciais.
- **Controle de Acesso**: garantir que somente as pessoas certas tem acesso as coisas certas. Atualmente é orientado pela arquitetura *Zero Trust*.
- **Legalidade**: respeita as leis dos países que atuam, órgãos de controle, boas práticas de mercado, etc.

## AAA
- **A**utentication: Provar que você é quem diz ser.
- **A**utorization: Provar que você tem permissão para acessar aquilo que quer.
- **A**ccounting: Provar que você de fato fez aquilo, ou seja, registro de logs.

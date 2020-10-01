# lives.SacAutoatendimento
Anotações e exemplos de nossa Live com alguns exemplos de Autoatendimento

# Autoatendimento com FAQ

* Criar serviço de terceiro nível em diante
* Criar FAQ, público, em PT_BR
* Associar como "Artigo do Serviço"

# Criar estado Autoatendimento

Ajustar o WasThisArticleHelpful
WasThisArticleHelpful###SelfAnsweredTicketAttributes


# Automação com integração
Criar campo dinamico EmailAdicional
Criar campo dinamico URLArquivo

# Criar Webhook site

webhook.site

tipo de retorno
application/json

conteúdo do retorno:
`{ 
    "FileURL":"https://www.w3.org/WAI/ER/tests/xhtml/testfiles/resources/pdf/dummy.pdf"
}
`

# Criar Web Service
` <xsl:stylesheet version="1.0"
  xmlns:xsl="http://www.w3.org/1999/XSL/Transform">
  <xsl:output omit-xml-declaration="yes" indent="yes"/>
  <xsl:template match="/RootElement">
   <xsl:copy>
       <DynamicField>
           <Name>URLDocumentoOnline</Name>
           <Value><xsl:value-of select="//FileURL" /></Value>
       </DynamicField>
       <Ticket>
           <State>Autoatendimento</State>
       </Ticket>
   </xsl:copy>
  </xsl:template>
 </xsl:stylesheet>
`

# Criar notificação
Disparador, atualização do campo URLArquivo

Email para envio adicional
<OTRS_TICKET_DynamicField_EmailAdicional>

Compor mensagem com esta URL
<OTRS_TICKET_DynamicField_URLArquivo>

Template Unformated


# Para que a próxima tela após criação do chamado seja o próprio ticket, alterar

Ticket::Frontend::CustomerTicketMessage###NextScreenAfterNewTicket

* NÃO ESQUEÇA DE IMPLANTAR


# Trilha de aprendizagem sobre XSLT

https://www.youtube.com/playlist?list=PLRWVfxypDIYRrCQArVoLxWkbr6ZvF2A16

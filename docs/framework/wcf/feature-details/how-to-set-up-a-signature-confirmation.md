---
title: "Как настраивать подтверждение сигнатуры | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "подтверждение сигнатуры"
  - "WCF, безопасность"
ms.assetid: 2424c137-c7c2-4aa9-8d5d-a066e12fefda
caps.latest.revision: 11
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 11
---
# Как настраивать подтверждение сигнатуры
*Подтверждение подписи* — это механизм, позволяющий инициатору сообщения убедиться, что полученный ответ был сформирован в ответ на исходное сообщение отправителя.Подтверждение подписи определено в спецификации WS\-Security 1.1.Если конечная точка поддерживает WS\-Security 1.0, использовать подтверждение подписи нельзя.  
  
 В процедурах ниже показано, как включить подтверждение подписи, используя элемент привязки <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>.Аналогичным образом можно использовать элемент привязки <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>.Эта процедура основывается на базовых шагах, описанных в разделе [Как создавать пользовательскую привязку с использованием элемента SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md).  
  
### Включение подтверждения подписи в коде  
  
1.  Создайте экземпляр класса <xref:System.ServiceModel.Channels.BindingElementCollection>.  
  
2.  Создайте экземпляр класса <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>.  
  
3.  Присвойте свойству <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement.RequireSignatureConfirmation%2A> значение `true`.  
  
4.  Добавьте элемент безопасности в коллекцию элементов привязки.  
  
5.  Создайте пользовательскую привязку, как описано в разделе [Как создавать пользовательскую привязку с использованием элемента SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md).  
  
### Включение подтверждения подписи в конфигурации  
  
1.  Добавьте элемент `<bindings>` в раздел `<customBinding>` файла конфигурации.  
  
2.  Добавьте элемент `<binding>` и присвойте атрибуту имени соответствующее значение.  
  
3.  Добавьте соответствующий элемент кодирования.В приведенном ниже примере добавляется элемент `<TextMessageEncoding>`.  
  
4.  Добавьте дочерний элемент `<security>` и присвойте атрибуту `requireSignatureConfirmation` значение `true`.  
  
5.  \(Необязательно.\)Чтобы включить подтверждение подписи в ходе начальной загрузки, добавьте дочерний элемент [\<secureConversationBootstrap\>](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) и присвойте атрибуту `equireSignatureConfirmation` значение `true`.  
  
6.  Добавьте соответствующий элемент транспорта.В следующем примере добавляется элемент [\<httpTransport\>](../../../../docs/framework/configure-apps/file-schema/wcf/httptransport.md):  
  
    ```  
    <bindings>  
      <customBinding>  
        <binding name="SignatureConfirmationBinding">  
          <security requireSignatureConfirmation="true">  
            <secureConversationBootstrap requireSignatureConfirmation="true" />  
              </security>  
           <textMessageEncoding />  
             <httpTransport />  
        </binding>  
      </customBinding>  
    </bindings>  
    ```  
  
## Пример  
 В приведенном ниже коде создается экземпляр класса <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> и свойству <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement.RequireSignatureConfirmation%2A> присваивается значение `true`.Обратите внимание, что в этом примере не используется элемент `<secureConversationBootstrap>`, показанный в предыдущем примере.В этом примере демонстрируется подтверждение подписи при использовании маркера Windows \(по протоколу Kerberos\).В данном случае подпись клиента возвращается во всех ответах службы и подтверждается клиентом.  
  
 [!code-csharp[c_SignatureConfirmation#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_signatureconfirmation/cs/source.cs#1)]
 [!code-vb[c_SignatureConfirmation#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_signatureconfirmation/vb/source.vb#1)]  
  
## См. также  
 <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>   
 <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>   
 <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateMutualCertificateBindingElement%2A>   
 [Как создавать пользовательскую привязку с использованием элемента SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)   
 [Как создать SecurityBindingElement для заданного режима проверки подлинности](../../../../docs/framework/wcf/feature-details/how-to-create-a-securitybindingelement-for-a-specified-authentication-mode.md)
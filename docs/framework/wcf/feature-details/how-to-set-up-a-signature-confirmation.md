---
title: "Практическое руководство. Настройка подтверждения сигнатуры"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- signature confirmation
- WCF, security
ms.assetid: 2424c137-c7c2-4aa9-8d5d-a066e12fefda
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: fced2ddd16ae244e2ea3d945082f48ffd23302e6
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-set-up-a-signature-confirmation"></a>Практическое руководство. Настройка подтверждения сигнатуры
*Подтверждение подписи* — это механизм для инициатору сообщения убедиться, что полученный ответ был сформирован в ответ на исходное сообщение отправителя. Подтверждение подписи определено в спецификации WS-Security 1.1. Если конечная точка поддерживает WS-Security 1.0, использовать подтверждение подписи нельзя.  
  
 В процедурах ниже показано, как включить подтверждение подписи, используя элемент привязки <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>. Аналогичным образом можно использовать элемент привязки <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>. Процедура базируется на основные шаги, описанные в [как: создайте пользовательские привязки с использованием элемента SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md).  
  
### <a name="to-enable-signature-confirmation-in-code"></a>Включение подтверждения подписи в коде  
  
1.  Создайте экземпляр класса <xref:System.ServiceModel.Channels.BindingElementCollection>.  
  
2.  Создайте экземпляр класса <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> класса.  
  
3.  Присвойте свойству <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement.RequireSignatureConfirmation%2A> значение `true`.  
  
4.  Добавьте элемент безопасности в коллекцию элементов привязки.  
  
5.  Создание пользовательской привязки, как указано в [как: Создание пользовательской привязки с использованием элемента SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md).  
  
### <a name="to-enable-signature-confirmation-in-configuration"></a>Включение подтверждения подписи в конфигурации  
  
1.  Добавьте элемент `<customBinding>` в раздел `<bindings>` файла конфигурации.  
  
2.  Добавьте элемент `<binding>` и присвойте атрибуту имени соответствующее значение.  
  
3.  Добавьте соответствующий элемент кодирования. В следующем примере добавляется элемент `<TextMessageEncoding>`.  
  
4.  Добавьте дочерний элемент `<security>` и присвойте атрибуту `requireSignatureConfirmation` значение `true`.  
  
5.  Необязательно. Включение подтверждения подписи во время начальной загрузки, добавьте [ \<secureConversationBootstrap >](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) дочерний элемент и набор `equireSignatureConfirmation` атрибут `true`.  
  
6.  Добавьте соответствующий элемент транспорта. В следующем примере добавляется [ \<httpTransport >](../../../../docs/framework/configure-apps/file-schema/wcf/httptransport.md):  
  
    ```xml  
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
  
## <a name="example"></a>Пример  
 В приведенном ниже коде создается экземпляр класса <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> и свойству <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement.RequireSignatureConfirmation%2A> присваивается значение `true`. Обратите внимание, что в этом примере не используется элемент `<secureConversationBootstrap>`, показанный в предыдущем примере. В этом примере демонстрируется подтверждение подписи при использовании маркера Windows (по протоколу Kerberos). В данном случае подпись клиента возвращается во всех ответах службы и подтверждается клиентом.  
  
 [!code-csharp[c_SignatureConfirmation#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_signatureconfirmation/cs/source.cs#1)]
 [!code-vb[c_SignatureConfirmation#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_signatureconfirmation/vb/source.vb#1)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>  
 <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>  
 <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateMutualCertificateBindingElement%2A>  
 [Как: Создание пользовательской привязки, с использованием элемента SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)  
 [Как: создание SecurityBindingElement для заданного режима проверки подлинности](../../../../docs/framework/wcf/feature-details/how-to-create-a-securitybindingelement-for-a-specified-authentication-mode.md)

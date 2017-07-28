---
title: "Практическое руководство. Создание подтверждающих учетных данных | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: d0952919-8bb4-4978-926c-9cc108f89806
caps.latest.revision: 9
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 9
---
# Практическое руководство. Создание подтверждающих учетных данных
Некоторые пользовательские схемы безопасности требуют нескольких учетных данных.  Например, служба может потребовать от клиента не только имя пользователя и пароль, но и учетные данные, доказывающие, что возраст клиента старше 18 лет.  Вторые учетные данные являются *вспомогательными учетными данными*.  В этом разделе объясняется, как реализовать эти учетные данные в клиенте [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].  
  
> [!NOTE]
>  Спецификация для поддержки учетных данных является частью спецификации WS\-SecurityPolicy.  [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] [Спецификации безопасности веб\-служб](http://go.microsoft.com/fwlink/?LinkId=88537).  
  
## Вспомогательные маркеры  
 Вкратце, при использовании безопасности сообщения *основные учетные данные* всегда используются для защиты сообщения \(например, сертификат X.509 или билет Kerberos\).  
  
 Как определено в спецификации, привязка безопасности использует *маркеры* для защиты обмена сообщениями.  *Маркер* является представлением учетных данных безопасности.  
  
 Привязка безопасности использует основной маркер, определенный в политике привязки безопасности, для создания подписи.  Эта подпись называется *подпись сообщения*.  
  
 Чтобы расширить утверждения, предоставляемые маркером, связанным с подписью сообщения, можно задать дополнительные маркеры.  
  
## Подтверждение, подпись и шифрование  
 Наличие вспомогательных учетных данных приводит к передаче *вспомогательного маркера* в сообщении.  Спецификация WS\-SecurityPolicy определяет четыре способа прикрепления вспомогательного маркера к сообщению \(см. следующую таблицу\).  
  
|Назначение|Описание|  
|----------------|--------------|  
|Подписанный|Вспомогательный маркер включен в заголовок безопасности и подписан подписью сообщения.|  
|Подтверждающий|*Подтверждающий маркер* подписывает подпись сообщения.|  
|Подписанный и подтверждающий|Подписанные подтверждающие маркеры подписывают весь элемент `ds:Signature`, произведенный из подписи сообщения, и сами подписываются этой подписью сообщения; то есть оба маркера \(маркер, используемый для подписи сообщения, и подписанный подтверждающий маркер\) подписывают друг друга.|  
|Подписанный и шифрующий|Подписанные, зашифрованные вспомогательные маркеры \- это подписанные вспомогательные маркеры, которые шифруются при появлении в `wsse:SecurityHeader`.|  
  
## Программирование вспомогательных учетных данных  
 Чтобы создать службу, использующую вспомогательные маркеры, необходимо создать элемент привязки [\<customBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md).  \([!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] [Как создавать пользовательскую привязку с использованием элемента SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md).\)  
  
 Первым шагом в создании пользовательской привязки является создание элемента привязки безопасности одного из трех следующих типов.  
  
-   <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>  
  
-   <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>  
  
-   <xref:System.ServiceModel.Channels.TransportSecurityBindingElement>  
  
 Все классы наследуются от элемента привязки безопасности <xref:System.ServiceModel.Channels.SecurityBindingElement>, включающего четыре взаимосвязанных свойства.  
  
-   <xref:System.ServiceModel.Channels.SecurityBindingElement.EndpointSupportingTokenParameters%2A>  
  
-   <xref:System.ServiceModel.Channels.SecurityBindingElement.OperationSupportingTokenParameters%2A>  
  
-   <xref:System.ServiceModel.Channels.SecurityBindingElement.OptionalEndpointSupportingTokenParameters%2A>  
  
-   <xref:System.ServiceModel.Channels.SecurityBindingElement.OptionalOperationSupportingTokenParameters%2A>  
  
#### Области  
 Для вспомогательных учетных данных существует две области.  
  
-   *Вспомогательные маркеры конечной точки* поддерживают все операции конечной точки.  Это значит, что учетные данные, представляемые вспомогательным маркером, могут использоваться всякий раз при вызове операций конечной точки.  
  
-   *Вспомогательные маркеры операции* поддерживают только конкретную операцию конечной точки.  
  
 Имена свойств показывают, что вспомогательные учетные данные могут быть обязательными или необязательными.  То есть, если вспомогательные учетные данные имеются, они используются, хотя в этом нет необходимости, так как при отсутствии вспомогательных учетных данных не происходит сбой проверки подлинности.  
  
## Процедуры  
  
#### Создание пользовательской привязки, которая включает вспомогательные учетные данные  
  
1.  Создайте элемент привязки безопасности.  В следующем примере продемонстрировано создание элемента привязки безопасности <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> в режиме проверки подлинности `UserNameForCertificate`.  Воспользуйтесь методом <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateUserNameForCertificateBindingElement%2A>.  
  
2.  Добавьте вспомогательный параметр в коллекцию типов, возвращаемых соответствующим свойством \(`Endorsing`, `Signed`, `SignedEncrypted` или `SignedEndorsed`\).  Типы в пространстве имен <xref:System.ServiceModel.Security.Tokens> включают наиболее часто используемые типы, такие как <xref:System.ServiceModel.Security.Tokens.X509SecurityTokenParameters>.  
  
## Пример  
  
### Описание  
 В следующем примере показано, как создать экземпляр <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> и добавить экземпляр класса <xref:System.ServiceModel.Security.Tokens.KerberosSecurityTokenParameters> в коллекцию, возвращенную свойством Endorsing.  
  
### Код  
 [!code-csharp[c_SupportingCredential#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_supportingcredential/cs/source.cs#1)]  
  
## См. также  
 [Как создавать пользовательскую привязку с использованием элемента SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
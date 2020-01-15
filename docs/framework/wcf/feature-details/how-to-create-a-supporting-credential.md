---
title: Практическое руководство. Создание подтверждающих учетных данных
ms.date: 03/30/2017
ms.assetid: d0952919-8bb4-4978-926c-9cc108f89806
ms.openlocfilehash: 3f33bf5a78c575237ee4bc609a482a81fd30fc53
ms.sourcegitcommit: c01c18755bb7b0f82c7232314ccf7955ea7834db
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/15/2020
ms.locfileid: "75964549"
---
# <a name="how-to-create-a-supporting-credential"></a>Практическое руководство. Создание подтверждающих учетных данных
Некоторые пользовательские схемы безопасности требуют нескольких учетных данных. Например, служба может потребовать от клиента не только имя пользователя и пароль, но и учетные данные, доказывающие, что возраст клиента старше 18 лет. Второй набор учетных данных — это *поддерживающие учетные данные*. В этом разделе объясняется, как реализовать такие учетные данные в клиенте Windows Communication Foundation (WCF).  
  
> [!NOTE]
> Спецификация для поддержки учетных данных является частью спецификации WS-SecurityPolicy. Дополнительные сведения см. в разделе [спецификации WS-Security](https://docs.microsoft.com/previous-versions/dotnet/articles/ms951273(v=msdn.10)).  
  
## <a name="supporting-tokens"></a>Вспомогательные маркеры  
 Вкратце, при использовании безопасности сообщений *основные учетные данные* всегда используются для защиты сообщения (например, сертификат X. 509 или билет Kerberos).  
  
 Как определено спецификацией, привязка безопасности использует *маркеры* для защиты обмена сообщениями. *Маркер* — это представление учетных данных безопасности.  
  
 Привязка безопасности использует основной маркер, определенный в политике привязки безопасности, для создания подписи. Эта подпись называется *подписью сообщения*.  
  
 Чтобы расширить утверждения, предоставляемые маркером, связанным с подписью сообщения, можно задать дополнительные маркеры.  
  
## <a name="endorsing-signing-and-encrypting"></a>Подтверждение, подпись и шифрование  
 В результате поддержки учетных данных создается *поддерживающий маркер* , передаваемый внутри сообщения. Спецификация WS-SecurityPolicy определяет четыре способа прикрепления вспомогательного маркера к сообщению (см. следующую таблицу).  
  
|Цель|Описание|  
|-------------|-----------------|  
|Подписанный|Вспомогательный маркер включен в заголовок безопасности и подписан подписью сообщения.|  
|Подтверждающий|*Токен подтверждающий* подписывает подпись сообщения.|  
|Подписанный и подтверждающий|Подписанные подтверждающие маркеры подписывают весь элемент `ds:Signature`, произведенный из подписи сообщения, и сами подписываются этой подписью сообщения; то есть оба маркера (маркер, используемый для подписи сообщения, и подписанный подтверждающий маркер) подписывают друг друга.|  
|Подписанный и шифрующий|Подписанные, зашифрованные вспомогательные маркеры - это подписанные вспомогательные маркеры, которые шифруются при появлении в `wsse:SecurityHeader`.|  
  
## <a name="programming-supporting-credentials"></a>Программирование вспомогательных учетных данных  
 Чтобы создать службу, использующую вспомогательные токены, необходимо создать [\<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md). (Дополнительные сведения см. в разделе [инструкции. Создание пользовательской привязки с помощью SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md).)  
  
 Первым шагом в создании пользовательской привязки является создание элемента привязки безопасности одного из трех следующих типов.  
  
- <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>  
  
- <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>  
  
- <xref:System.ServiceModel.Channels.TransportSecurityBindingElement>  
  
 Все классы наследуются от элемента привязки безопасности <xref:System.ServiceModel.Channels.SecurityBindingElement>, включающего четыре взаимосвязанных свойства.  
  
- <xref:System.ServiceModel.Channels.SecurityBindingElement.EndpointSupportingTokenParameters%2A>  
  
- <xref:System.ServiceModel.Channels.SecurityBindingElement.OperationSupportingTokenParameters%2A>  
  
- <xref:System.ServiceModel.Channels.SecurityBindingElement.OptionalEndpointSupportingTokenParameters%2A>  
  
- <xref:System.ServiceModel.Channels.SecurityBindingElement.OptionalOperationSupportingTokenParameters%2A>  
  
#### <a name="scopes"></a>Области  
 Для вспомогательных учетных данных существует две области.  
  
- *Конечная точка, поддерживающая маркеры* , поддерживает все операции конечной точки. Это значит, что учетные данные, представляемые вспомогательным маркером, могут использоваться всякий раз при вызове операций конечной точки.  
  
- *Операции, поддерживающие токены* , поддерживают только определенную операцию с конечной точкой.  
  
 Имена свойств показывают, что вспомогательные учетные данные могут быть обязательными или необязательными. То есть, если вспомогательные учетные данные имеются, они используются, хотя в этом нет необходимости, так как при отсутствии вспомогательных учетных данных не происходит сбой проверки подлинности.  
  
## <a name="procedures"></a>Процедуры  
  
#### <a name="to-create-a-custom-binding-that-includes-supporting-credentials"></a>Создание пользовательской привязки, которая включает вспомогательные учетные данные  
  
1. Создайте элемент привязки безопасности. В следующем примере продемонстрировано создание элемента привязки безопасности <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> в режиме проверки подлинности `UserNameForCertificate`. Воспользуйтесь методом <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateUserNameForCertificateBindingElement%2A>.  
  
2. Добавьте вспомогательный параметр в коллекцию типов, возвращаемых соответствующим свойством (`Endorsing`, `Signed`, `SignedEncrypted` или `SignedEndorsed`). Типы в пространстве имен <xref:System.ServiceModel.Security.Tokens> включают наиболее часто используемые типы, такие как <xref:System.ServiceModel.Security.Tokens.X509SecurityTokenParameters>.  
  
## <a name="example"></a>Пример  
  
### <a name="description"></a>Описание  
 В следующем примере показано, как создать экземпляр <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> и добавить экземпляр класса <xref:System.ServiceModel.Security.Tokens.KerberosSecurityTokenParameters> в коллекцию, возвращенную свойством Endorsing.  
  
### <a name="code"></a>Код  
 [!code-csharp[c_SupportingCredential#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_supportingcredential/cs/source.cs#1)]  
  
## <a name="see-also"></a>См. также:

- [Практическое руководство. Создание пользовательской привязки с использованием элемента SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)

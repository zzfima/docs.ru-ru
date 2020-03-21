---
title: Рекомендации по безопасности при использовании WCF
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- best practices [WCF], security
ms.assetid: 3639de41-1fa7-4875-a1d7-f393e4c8bd69
ms.openlocfilehash: c8c0c084ac3b1cf06fc5f2b3df85fa979744e17b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79185422"
---
# <a name="best-practices-for-security-in-wcf"></a>Рекомендации по безопасности при использовании WCF
В следующих разделах приводятся рекомендации по созданию надежных приложений с помощью Windows Communication Foundation (WCF). Дополнительные сведения о безопасности см. в разделах [Вопросы безопасности](../../../../docs/framework/wcf/feature-details/security-considerations-in-wcf.md), [Вопросы безопасности для данных](../../../../docs/framework/wcf/feature-details/security-considerations-for-data.md) и [Вопросы безопасности при использовании метаданных](../../../../docs/framework/wcf/feature-details/security-considerations-with-metadata.md).  
  
## <a name="identify-services-performing-windows-authentication-with-spns"></a>Идентифицируйте службы, проходящие проверку подлинности Windows, с помощью различных SPN.  
 Службы могут идентифицироваться с помощью имен участника-пользователя (UPN) или имен субъекта-службы (SPN). Службы, выполняемые от имени учетных записей компьютера (например, сетевые службы), имеют идентификатор SPN, который совпадает с идентификатором компьютера, на котором они выполняются. Службы, выполняемые от имени учетных записей пользователя, имеют идентификатор UPN, совпадающий с идентификатором пользователя, от имени которого они выполняются, при этом средство `setspn` может использоваться для назначения SPN учетной записи пользователя. Настройка службы, делающая возможной идентификацию службы через SPN, и настройка подключающихся к службе клиентов на использование этого SPN, затрудняют определенные атаки. Это правило действует для привязок, использующих согласование Kerberos или SSPI.  Несмотря на это, клиенты должны указывать SPN в случае, если SSPI возвращается к NTLM.  
  
## <a name="verify-service-identities-in-wsdl"></a>Проверяйте удостоверения службы в WSDL  
 WS-SecurityPolicy позволяет службам публиковать информацию о своих удостоверениях в метаданных. Когда идентификационные данные извлекаются через `svcutil` или с помощью других методов, таких как <xref:System.ServiceModel.Description.WsdlImporter>, эти данные преобразуются в параметры удостоверения для адресов конечных точек служб WCF. Клиенты, которые не подтверждают правильность и допустимость данных удостоверений службы, эффективно выполняют обход проверки подлинности службы. Вредоносная служба может использовать такие клиенты для перенаправления учетных данных и реализации других атак типа "злоумышленник в середине", изменяя заявленное в WSDL удостоверение.  
  
## <a name="use-x509-certificates-instead-of-ntlm"></a>Используйте сертификаты X509 вместо протокола NTLM  
 WCF предоставляет два механизма проверки подлинности одноранговых элементов: сертификаты X509 (используемые одноранговым каналом) и проверку подлинности Windows, при которой согласование SSPI понижается с протокола Kerberos до протокола NTLM.  Проверка подлинности на основании сертификатов с использованием размеров ключа от 1024 битов имеет преимущества по сравнению с проверкой подлинности по протоколу NTLM по следующим причинам:  
  
- возможность взаимной проверки подлинности,  
  
- использование усиленных алгоритмов шифрования и  
  
- затруднение использования перенаправленных учетных данных сертификата X509.  

## <a name="always-revert-after-impersonation"></a>Всегда отменяйте изменения после олицетворения  
 При использовании интерфейсов API, которые разрешают олицетворение клиента, не забудьте вернуться к исходной идентификации. Например, при работе с <xref:System.Security.Principal.WindowsIdentity> и <xref:System.Security.Principal.WindowsImpersonationContext> воспользуйтесь оператором C# `using` или оператором Visual Basic `Using`, как показано в следующем примере кода. Класс <xref:System.Security.Principal.WindowsImpersonationContext> реализует интерфейс <xref:System.IDisposable>, следовательно, среда CLR автоматически возвращается к исходной идентификации после того, как код выводится из блока `using`.  
  
 [!code-csharp[c_SecurityBestPractices#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securitybestpractices/cs/source.cs#1)]
 [!code-vb[c_SecurityBestPractices#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securitybestpractices/vb/source.vb#1)]  
  
## <a name="impersonate-only-as-needed"></a>Используйте олицетворение только при необходимости  
 Метод <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A> класса <xref:System.Security.Principal.WindowsIdentity> позволяет осуществлять строгий контроль над использованием олицетворения. В этом заключается отличие от использования свойства <xref:System.ServiceModel.OperationBehaviorAttribute.Impersonation%2A><xref:System.ServiceModel.OperationBehaviorAttribute>, которое позволяет использовать олицетворение в рамках всей операции. По возможности контролируйте область применения олицетворения с помощью более точного метода <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A>.  
  
## <a name="obtain-metadata-from-trusted-sources"></a>Получайте метаданные из надежных источников  
 Убедитесь в надежности источника метаданных и в том, что метаданные не были злонамеренно искажены. Метаданные, полученные по протоколу HTTP, передаются открытым текстом и могут быть подделаны. Если в службе используются свойства <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpsGetEnabled%2A> и <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpsGetUrl%2A>, для загрузки данных по протоколу HTTPS используйте URL-адрес, предоставленный разработчиком службы.  
  
## <a name="publish-metadata-using-security"></a>Публикуйте метаданные с использованием безопасности  
 Для предотвращения злонамеренного искажения метаданных, опубликованных службой, обеспечьте защиту конечной точки обмена метаданными с помощью безопасности на уровне транспорта или сообщений. Дополнительные сведения см. в разделе [Публикация конечных точек метаданных](../../../../docs/framework/wcf/publishing-metadata-endpoints.md) и [Практическое руководство. Публикация метаданных для службы с использованием кода](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-code.md).  
  
## <a name="ensure-use-of-local-issuer"></a>Разрешите использование локального издателя  
 Если для данной привязки указаны адрес издателя и привязка, локальный издатель не применяется в конечных точках, использующих эту привязку. Клиенты, которые предполагают всегда использовать локальный издатель, должны убедиться, что они не используют такую привязку или что привязка изменена таким образом, что адрес издателя пуст.  
  
## <a name="saml-token-size-quotas"></a>Квоты на размер маркеров SAML  
 Когда маркеры Security Assertion Markup Language (SAML) сериализуются в сообщениях, то, независимо от того, выдаются ли они службой маркеров безопасности (STS) или предоставляются клиентами для служб как часть проверки подлинности, квота на максимальный размер сообщения должна быть достаточно большой, чтобы вместить маркер SAML и другие части сообщения. Как правило, по умолчанию квоты на размер сообщения являются достаточными. Впрочем, если большой размер токена SAML объясняется содержанием в нем сотни утверждений, может потребоваться увеличение квот для выделения места сериализованному токену. Дополнительные сведения о квотах см. в разделе [Вопросы безопасности для данных](../../../../docs/framework/wcf/feature-details/security-considerations-for-data.md).  
  
## <a name="set-securitybindingelementincludetimestamp-to-true-on-custom-bindings"></a>Задайте параметру SecurityBindingElement.IncludeTimestamp значение True в пользовательских привязках  
 При создании пользовательской привязки следует задать параметру <xref:System.ServiceModel.Channels.SecurityBindingElement.IncludeTimestamp%2A> значение `true`. В противном случае, если параметр <xref:System.ServiceModel.Channels.SecurityBindingElement.IncludeTimestamp%2A> имеет значение `false`, а клиент использует асимметричный маркер на основе ключа, например, сертификат Х509, сообщение не будет подписано.  
  
## <a name="see-also"></a>См. также раздел

- [Соображения безопасности](../../../../docs/framework/wcf/feature-details/security-considerations-in-wcf.md)
- [Соображения безопасности для данных](../../../../docs/framework/wcf/feature-details/security-considerations-for-data.md)
- [Вопросы безопасности при использовании метаданных](../../../../docs/framework/wcf/feature-details/security-considerations-with-metadata.md)

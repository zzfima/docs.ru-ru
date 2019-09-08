---
title: Практическое руководство. Использование отдельных сертификатов X.509 для подписывания и шифрования
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF, extensibility
- ClientCredentials class
- ClientCredentialsSecurityTokenManager class
ms.assetid: 0b06ce4e-7835-4d82-8baf-d525c71a0e49
ms.openlocfilehash: e464aff46f311ede1cd629fb459ade9a6e627d59
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796960"
---
# <a name="how-to-use-separate-x509-certificates-for-signing-and-encryption"></a>Практическое руководство. Использование отдельных сертификатов X.509 для подписывания и шифрования

В этом разделе показано, как настроить Windows Communication Foundation (WCF) для использования разных сертификатов для подписи и шифрования сообщений как в клиенте, так и в службе.

Чтобы использовать отдельные сертификаты для подписывания и шифрования, необходимо создать настраиваемые учетные данные клиента или службы (или и то, и другое), так как WCF не предоставляет API для установки нескольких сертификатов клиента или службы. Кроме того, необходимо предоставить диспетчер маркеров безопасности для применения данных нескольких сертификатов и создания соответствующего поставщика маркеров безопасности для заданного использования ключа и указанного направления сообщения.

На представленном ниже рисунке показаны основные используемые классы, классы, от которых они наследуются (показаны стрелкой вверх), и типы возвращаемого значения некоторых методов и свойств.

- `MyClientCredentials` - это пользовательская реализация <xref:System.ServiceModel.Description.ClientCredentials>.

  - Все показанные на рисунке свойства этой реализации возвращают экземпляры <xref:System.Security.Cryptography.X509Certificates.X509Certificate2>.

  - Метод <xref:System.ServiceModel.Description.ClientCredentials.CreateSecurityTokenManager%2A> этой реализации возвращает экземпляр `MyClientCredentialsSecurityTokenManager`.

- `MyClientCredentialsSecurityTokenManager` - это пользовательская реализация <xref:System.ServiceModel.ClientCredentialsSecurityTokenManager>.

  - Метод <xref:System.ServiceModel.ClientCredentialsSecurityTokenManager.CreateSecurityTokenProvider%2A> этой реализации возвращает экземпляр <xref:System.IdentityModel.Selectors.X509SecurityTokenProvider>.

![Диаграмма, показывающая, как используются учетные данные клиента](./media/e4971edd-a59f-4571-b36f-7e6b2f0d610f.gif "e4971edd-a59f-4571-b36f-7e6b2f0d610f")

Дополнительные сведения о пользовательских учетных данных см [. в разделе Пошаговое руководство. Создание настраиваемых учетных данных](walkthrough-creating-custom-client-and-service-credentials.md)клиента и службы.

Кроме того, необходимо создать пользовательское средство проверки идентификации и связать его с элементом привязки безопасности в специальной привязке. Следует также вместо учетных данных по умолчанию использовать пользовательские учетные данные.

На представленном ниже рисунке показаны классы, включенные в специальную привязку, и то, как осуществляется привязка пользовательского средства проверки идентификации. Существует несколько включенных элементов привязки, которые наследуются от <xref:System.ServiceModel.Channels.BindingElement>. <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement> имеет свойство <xref:System.ServiceModel.Channels.LocalClientSecuritySettings>, возвращающее экземпляр <xref:System.ServiceModel.Security.IdentityVerifier>, на основе которого настраивается `MyIdentityVerifier`.

![Диаграмма, на которой показан пользовательский элемент привязки](./media/dddea4a2-0bb4-4921-9bf4-20d4d82c3da5.gif "dddea4a2-0bb4-4921-9bf4-20d4d82c3da5")

Дополнительные сведения о создании пользовательского средства проверки личности см. в разделе как [Практическое руководство. Создайте настраиваемое средство проверки](how-to-create-a-custom-client-identity-verifier.md)удостоверения клиента.

### <a name="to-use-separate-certificates-for-signing-and-encryption"></a>Использование отдельных сертификатов для подписывания и шифрования

1. Определите новый класс учетных данных клиента, который наследуется от класса <xref:System.ServiceModel.Description.ClientCredentials>. Реализуйте четыре новых свойства, чтобы разрешить спецификацию нескольких сертификатов: `ClientSigningCertificate`, `ClientEncryptingCertificate`, `ServiceSigningCertificate` и `ServiceEncryptingCertificate`. Кроме того, переопределите метод <xref:System.ServiceModel.Description.ClientCredentials.CreateSecurityTokenManager%2A> для возврата экземпляра пользовательского класса <xref:System.ServiceModel.ClientCredentialsSecurityTokenManager>, который определяется на следующем шаге.

     [!code-csharp[c_FourCerts#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_fourcerts/cs/source.cs#1)]
     [!code-vb[c_FourCerts#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_fourcerts/vb/source.vb#1)]

2. Определите новый диспетчер маркеров безопасности клиента, который наследуется от класса <xref:System.ServiceModel.ClientCredentialsSecurityTokenManager>. Переопределите метод <xref:System.ServiceModel.ClientCredentialsSecurityTokenManager.CreateSecurityTokenProvider%2A>, чтобы создать соответствующий поставщик маркеров безопасности. Параметр `requirement` (<xref:System.IdentityModel.Selectors.SecurityTokenRequirement>) обеспечивает направление сообщения и использование ключа.

     [!code-csharp[c_FourCerts#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_fourcerts/cs/source.cs#2)]
     [!code-vb[c_FourCerts#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_fourcerts/vb/source.vb#2)]

3. Определите новый класс учетных данных службы, который наследуется от класса <xref:System.ServiceModel.Description.ServiceCredentials>. Реализуйте четыре новых свойства, чтобы разрешить спецификацию нескольких сертификатов: `ClientSigningCertificate`, `ClientEncryptingCertificate`, `ServiceSigningCertificate` и `ServiceEncryptingCertificate`. Кроме того, переопределите метод <xref:System.ServiceModel.Description.ServiceCredentials.CreateSecurityTokenManager%2A> для возврата экземпляра пользовательского класса <xref:System.ServiceModel.Security.ServiceCredentialsSecurityTokenManager>, который определяется на следующем шаге.

     [!code-csharp[c_FourCerts#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_fourcerts/cs/source.cs#3)]
     [!code-vb[c_FourCerts#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_fourcerts/vb/source.vb#3)]

4. Определите новый диспетчер маркеров безопасности службы, который наследуется от класса <xref:System.ServiceModel.Security.ServiceCredentialsSecurityTokenManager>. Переопределите метод <xref:System.ServiceModel.Security.ServiceCredentialsSecurityTokenManager.CreateSecurityTokenProvider%2A> для создания соответствующего поставщика маркеров безопасности при условии переданных в него направления сообщения и использования ключа.

     [!code-csharp[c_FourCerts#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_fourcerts/cs/source.cs#4)]
     [!code-vb[c_FourCerts#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_fourcerts/vb/source.vb#4)]

### <a name="to-use-multiple-certificates-on-the-client"></a>Использование нескольких сертификатов на клиенте

1. Создайте специальную привязку. Элемент привязки безопасности должен работать в дуплексном режиме, чтобы обеспечить наличие разных поставщиков маркеров безопасности для запросов и ответов. Это можно реализовать, например, посредством использования дуплексного транспорта или применения элемента <xref:System.ServiceModel.Channels.CompositeDuplexBindingElement>, как показано в следующем коде. Свяжите пользовательское средство <xref:System.ServiceModel.Security.IdentityVerifier>, которое определяется на следующем шаге, с элементом привязки безопасности. Замените учетные данные клиента по умолчанию на ранее созданные пользовательские учетные данные клиента.

     [!code-csharp[c_FourCerts#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_fourcerts/cs/source.cs#5)]
     [!code-vb[c_FourCerts#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_fourcerts/vb/source.vb#5)]

2. Определите пользовательское средство <xref:System.ServiceModel.Security.IdentityVerifier>. Служба имеет несколько идентификаторов, поскольку для шифрования запроса и подписывания ответа используются разные сертификаты.

    > [!NOTE]
    > В следующем примере предоставленное пользовательское средство проверки идентификации в демонстрационных целях не выполняет никакой проверки идентификации конечных точек. Для рабочего кода так делать не рекомендуется.

     [!code-csharp[c_FourCerts#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_fourcerts/cs/source.cs#6)]
     [!code-vb[c_FourCerts#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_fourcerts/vb/source.vb#6)]

### <a name="to-use-multiple-certificates-on-the-service"></a>Использование нескольких сертификатов в службе

1. Создайте специальную привязку. Элемент привязки безопасности должен работать в дуплексном режиме, чтобы обеспечить наличие разных поставщиков маркеров безопасности для запросов и ответов. Так же как для клиента, используйте дуплексный транспорт или элемент <xref:System.ServiceModel.Channels.CompositeDuplexBindingElement>, как показано в следующем коде. Замените учетные данные службы по умолчанию на ранее созданные пользовательские учетные данные службы.

     [!code-csharp[c_FourCerts#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_fourcerts/cs/source.cs#7)]
     [!code-vb[c_FourCerts#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_fourcerts/vb/source.vb#7)]

## <a name="see-also"></a>См. также

- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Description.ServiceCredentials>
- <xref:System.ServiceModel.ClientCredentialsSecurityTokenManager>
- <xref:System.ServiceModel.Security.ServiceCredentialsSecurityTokenManager>
- <xref:System.ServiceModel.Security.IdentityVerifier>
- [Пошаговое руководство: Создание настраиваемых учетных данных клиента и службы](walkthrough-creating-custom-client-and-service-credentials.md)

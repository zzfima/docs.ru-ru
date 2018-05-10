---
title: 'Как: изменить поставщика служб шифрования для сертификата X.509&#39;s закрытого ключа'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cryptographic provider [WCF], changing
- cryptographic provider [WCF]
ms.assetid: b4254406-272e-4774-bd61-27e39bbb6c12
ms.openlocfilehash: 633e87bca302adc0963e1bf52d2470c9dbae81a5
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
---
# <a name="how-to-change-the-cryptographic-provider-for-an-x509-certificate39s-private-key"></a>Как: изменить поставщика служб шифрования для сертификата X.509&#39;s закрытого ключа
В этом разделе показано, как изменить поставщика служб шифрования, используемый для предоставления закрытый ключ сертификата X.509 и как интегрировать поставщика в инфраструктуру безопасности Windows Communication Foundation (WCF). Дополнительные сведения об использовании сертификатов см. в разделе [работа с сертификатами](../../../../docs/framework/wcf/feature-details/working-with-certificates.md).  
  
 Модель безопасности WCF предоставляет способ вводят новые типы маркеров безопасности, как описано в [как: Создание пользовательского токена](../../../../docs/framework/wcf/extending/how-to-create-a-custom-token.md). Пользовательский маркер также можно использовать для замены существующих типов маркеров, предоставляемых системой.  
  
 В этом разделе описывается замена предоставляемого системой маркера безопасности X.509 пользовательским маркером X.509, что делает возможным иную реализацию закрытого ключа сертификата. Эта возможность оказывается полезной, если фактический закрытый ключ предоставляется другим поставщиком служб шифрования, а не поставщиком служб шифрования Windows по умолчанию. В качестве примера альтернативного поставщика служб шифрования можно назвать аппаратный модуль безопасности, выполняющий все операции шифрования с закрытым ключом и не сохраняющий закрытые ключи в памяти, тем самым повышая уровень безопасности системы.  
  
 Следующий пример используется только в качестве демонстрации. В этом примере не описывается замена поставщика служб шифрования Windows по умолчанию, а показывается, куда можно интегрировать этого поставщика.  
  
## <a name="procedures"></a>Процедуры  
 Каждый маркер безопасности, имеющий связанный ключ или ключи безопасности, должен реализовать свойство <xref:System.IdentityModel.Tokens.SecurityToken.SecurityKeys%2A>, возвращающее коллекцию ключей из экземпляра маркера безопасности. Если маркер является маркером безопасности X.509, коллекция содержит единственный экземпляр класса <xref:System.IdentityModel.Tokens.X509AsymmetricSecurityKey>, представляющего как открытые, так и закрытые ключи, связанные с сертификатом. Для замены поставщика служб шифрования по умолчанию, предоставляющего ключи сертификата, необходимо создать новую реализацию данного класса.  
  
#### <a name="to-create-a-custom-x509-asymmetric-key"></a>Создание пользовательского асимметричного ключа X.509  
  
1.  Определите новый класс, производный от класса <xref:System.IdentityModel.Tokens.X509AsymmetricSecurityKey>.  
  
2.  Переопределите свойство <xref:System.IdentityModel.Tokens.SecurityKey.KeySize%2A>, доступное только для чтения. Это свойство возвращает фактический размер ключа пары ключей сертификата (открытого и закрытого).  
  
3.  Переопределите метод <xref:System.IdentityModel.Tokens.SecurityKey.DecryptKey%2A>. Этот метод вызывается инфраструктурой безопасности WCF для расшифровки симметричного ключа с помощью закрытого ключа сертификата. (Ранее этот ключ был зашифрован с помощью открытого ключа сертификата).  
  
4.  Переопределите метод <xref:System.IdentityModel.Tokens.AsymmetricSecurityKey.GetAsymmetricAlgorithm%2A>. Этот метод вызывается инфраструктурой безопасности WCF для получения экземпляра <xref:System.Security.Cryptography.AsymmetricAlgorithm> класс, представляющий поставщика служб шифрования для закрытого или открытого ключа или сертификата, в зависимости от параметров, переданного методу.  
  
5.  Необязательный. Переопределите метод <xref:System.IdentityModel.Tokens.AsymmetricSecurityKey.GetHashAlgorithmForSignature%2A>. Переопределите этот метод, если требуется иная реализация класса <xref:System.Security.Cryptography.HashAlgorithm>.  
  
6.  Переопределите метод <xref:System.IdentityModel.Tokens.AsymmetricSecurityKey.GetSignatureFormatter%2A>. Этот метод возвращает экземпляр класса <xref:System.Security.Cryptography.AsymmetricSignatureFormatter>, связанного с закрытым ключом сертификата.  
  
7.  Переопределите метод <xref:System.IdentityModel.Tokens.SecurityKey.IsSupportedAlgorithm%2A>. Этот метод используется, чтобы указать, поддерживается ли конкретный алгоритм шифрования данной реализацией ключа безопасности.  
  
     [!code-csharp[c_CustomX509Token#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customx509token/cs/source.cs#1)]
     [!code-vb[c_CustomX509Token#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customx509token/vb/source.vb#1)]  
  
 Ниже показано, как интегрировать X.509 безопасности асимметричного ключа реализацию пользовательского создан в предыдущей процедуре, с инфраструктурой безопасности WCF, чтобы заменить безопасности X.509 системных маркеров.  
  
#### <a name="to-replace-the-system-provided-x509-security-token-with-a-custom-x509-asymmetric-security-key-token"></a>Замена предоставляемого системой маркера безопасности X.509 пользовательским маркером асимметричного ключа безопасности X.509  
  
1.  Создайте пользовательский маркер безопасности X.509, возвращающий пользовательский асимметричный ключ безопасности X.509 вместо предоставляемого системой ключа безопасности, как показано в следующем примере. Дополнительные сведения о пользовательских маркеров безопасности см. в разделе [как: Создание пользовательского токена](../../../../docs/framework/wcf/extending/how-to-create-a-custom-token.md).  
  
     [!code-csharp[c_CustomX509Token#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customx509token/cs/source.cs#2)]
     [!code-vb[c_CustomX509Token#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customx509token/vb/source.vb#2)]  
  
2.  Создайте пользовательский поставщик маркеров безопасности, возвращающий пользовательский маркер безопасности X.509, как показано в примере. Дополнительные сведения о поставщиков маркеров безопасности см. в разделе [как: Создание пользовательского поставщика маркеров безопасности](../../../../docs/framework/wcf/extending/how-to-create-a-custom-security-token-provider.md).  
  
     [!code-csharp[c_CustomX509Token#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customx509token/cs/source.cs#3)]
     [!code-vb[c_CustomX509Token#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customx509token/vb/source.vb#3)]  
  
3.  Если пользовательский ключ безопасности необходимо использовать на стороне инициатора, создайте пользовательский диспетчер маркеров безопасности клиента и пользовательские классы учетных данных клиента, как показано в следующем примере. Дополнительные сведения о пользовательских учетных данных клиента и диспетчеров токена безопасности клиента см. в разделе [Пошаговое руководство: Создание настраиваемых клиентских учетных данных и службы](../../../../docs/framework/wcf/extending/walkthrough-creating-custom-client-and-service-credentials.md).  
  
     [!code-csharp[c_CustomX509Token#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customx509token/cs/source.cs#4)]
     [!code-vb[c_CustomX509Token#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customx509token/vb/source.vb#4)]  
  
     [!code-csharp[c_CustomX509Token#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customx509token/cs/source.cs#6)]
     [!code-vb[c_CustomX509Token#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customx509token/vb/source.vb#6)]  
  
4.  Если пользовательский ключ безопасности необходимо использовать на стороне получателя, создайте пользовательский диспетчер маркеров безопасности службы и пользовательские учетные данные службы, как показано в следующем примере. Дополнительные сведения о пользовательских учетных данных службы и диспетчеры токена безопасности служб см. в разделе [Пошаговое руководство: Создание настраиваемых клиентских учетных данных и службы](../../../../docs/framework/wcf/extending/walkthrough-creating-custom-client-and-service-credentials.md).  
  
     [!code-csharp[c_CustomX509Token#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customx509token/cs/source.cs#5)]
     [!code-vb[c_CustomX509Token#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customx509token/vb/source.vb#5)]  
  
     [!code-csharp[c_CustomX509Token#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customx509token/cs/source.cs#7)]
     [!code-vb[c_CustomX509Token#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customx509token/vb/source.vb#7)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.IdentityModel.Tokens.X509AsymmetricSecurityKey>  
 <xref:System.IdentityModel.Tokens.AsymmetricSecurityKey>  
 <xref:System.IdentityModel.Tokens.SecurityKey>  
 <xref:System.Security.Cryptography.AsymmetricAlgorithm>  
 <xref:System.Security.Cryptography.HashAlgorithm>  
 <xref:System.Security.Cryptography.AsymmetricSignatureFormatter>  
 [Пошаговое руководство. Создание пользовательских учетных данных для клиента и службы](../../../../docs/framework/wcf/extending/walkthrough-creating-custom-client-and-service-credentials.md)  
 [Практическое руководство. Создание пользовательской структуры проверки подлинности маркера безопасности](../../../../docs/framework/wcf/extending/how-to-create-a-custom-security-token-authenticator.md)  
 [Практическое руководство. Создание пользовательского поставщика маркеров безопасности](../../../../docs/framework/wcf/extending/how-to-create-a-custom-security-token-provider.md)  
 [Практическое руководство. Создание пользовательского маркера](../../../../docs/framework/wcf/extending/how-to-create-a-custom-token.md)  
 [Архитектура безопасности](http://msdn.microsoft.com/library/16593476-d36a-408d-808c-ae6fd483e28f)

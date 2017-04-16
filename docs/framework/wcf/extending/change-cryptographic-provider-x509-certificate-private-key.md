---
title: "Практическое руководство. Изменение поставщика служб шифрования для закрытого ключа сертификата X.509 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "поставщик служб шифрования [WCF]"
  - "поставщик служб шифрования [WCF], изменение"
ms.assetid: b4254406-272e-4774-bd61-27e39bbb6c12
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# Практическое руководство. Изменение поставщика служб шифрования для закрытого ключа сертификата X.509
В этом разделе объясняется, как изменить поставщика служб шифрования, предоставляющего закрытый ключ сертификата X.509, и интегрировать поставщика в инфраструктуру безопасности [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].  Дополнительные сведения об использовании сертификатов см. в разделе [Работа с сертификатами](../../../../docs/framework/wcf/feature-details/working-with-certificates.md).  
  
 Инфраструктура безопасности [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] позволяет использовать новые типы маркеров безопасности, как описано в разделе [Как создавать пользовательский маркер](../../../../docs/framework/wcf/extending/how-to-create-a-custom-token.md).  Пользовательский маркер также можно использовать для замены существующих типов маркеров, предоставляемых системой.  
  
 В этом разделе описывается замена предоставляемого системой маркера безопасности X.509 пользовательским маркером X.509, что делает возможным иную реализацию закрытого ключа сертификата.  Эта возможность оказывается полезной, если фактический закрытый ключ предоставляется другим поставщиком служб шифрования, а не поставщиком служб шифрования Windows по умолчанию.  В качестве примера альтернативного поставщика служб шифрования можно назвать аппаратный модуль безопасности, выполняющий все операции шифрования с закрытым ключом и не сохраняющий закрытые ключи в памяти, тем самым повышая уровень безопасности системы.  
  
 Следующий пример используется только в качестве демонстрации.  В этом примере не описывается замена поставщика служб шифрования Windows по умолчанию, а показывается, куда можно интегрировать этого поставщика.  
  
## Процедуры  
 Каждый маркер безопасности, имеющий связанный ключ или ключи безопасности, должен реализовать свойство <xref:System.IdentityModel.Tokens.SecurityToken.SecurityKeys%2A>, возвращающее коллекцию ключей из экземпляра маркера безопасности.  Если маркер является маркером безопасности X.509, коллекция содержит единственный экземпляр класса <xref:System.IdentityModel.Tokens.X509AsymmetricSecurityKey>, представляющего как открытые, так и закрытые ключи, связанные с сертификатом.  Для замены поставщика служб шифрования по умолчанию, предоставляющего ключи сертификата, необходимо создать новую реализацию данного класса.  
  
#### Создание пользовательского асимметричного ключа X.509  
  
1.  Определите новый класс, производный от класса <xref:System.IdentityModel.Tokens.X509AsymmetricSecurityKey>.  
  
2.  Переопределите свойство <xref:System.IdentityModel.Tokens.SecurityKey.KeySize%2A>, доступное только для чтения.  Это свойство возвращает фактический размер ключа пары ключей сертификата \(открытого и закрытого\).  
  
3.  Переопределите метод <xref:System.IdentityModel.Tokens.SecurityKey.DecryptKey%2A>.  Этот метод вызывается инфраструктурой безопасности [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] для расшифровки симметричного ключа с помощью закрытого ключа сертификата.  \(Ранее этот ключ был зашифрован с помощью открытого ключа сертификата\).  
  
4.  Переопределите метод <xref:System.IdentityModel.Tokens.AsymmetricSecurityKey.GetAsymmetricAlgorithm%2A>.  Этот метод вызывается инфраструктурой безопасности [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] для получения экземпляра класса <xref:System.Security.Cryptography.AsymmetricAlgorithm>, представляющего поставщика служб шифрования для закрытого или открытого ключа сертификата \(в зависимости от параметров, переданных методу\).  
  
5.  Необязательно.  Переопределите метод <xref:System.IdentityModel.Tokens.AsymmetricSecurityKey.GetHashAlgorithmForSignature%2A>.  Переопределите этот метод, если требуется иная реализация класса <xref:System.Security.Cryptography.HashAlgorithm>.  
  
6.  Переопределите метод <xref:System.IdentityModel.Tokens.AsymmetricSecurityKey.GetSignatureFormatter%2A>.  Этот метод возвращает экземпляр класса <xref:System.Security.Cryptography.AsymmetricSignatureFormatter>, связанного с закрытым ключом сертификата.  
  
7.  Переопределите метод <xref:System.IdentityModel.Tokens.SecurityKey.IsSupportedAlgorithm%2A>.  Этот метод используется, чтобы указать, поддерживается ли конкретный алгоритм шифрования данной реализацией ключа безопасности.  
  
     [!code-csharp[c_CustomX509Token#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customx509token/cs/source.cs#1)]
     [!code-vb[c_CustomX509Token#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customx509token/vb/source.vb#1)]  
  
 В следующей процедуре показано, как интегрировать реализацию пользовательского асимметричного ключа безопасности X.509, созданного в предыдущей процедуре, в инфраструктуру безопасности [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], чтобы заменить предоставляемый системой маркер безопасности X.509.  
  
#### Замена предоставляемого системой маркера безопасности X.509 пользовательским маркером асимметричного ключа безопасности X.509  
  
1.  Создайте пользовательский маркер безопасности X.509, возвращающий пользовательский асимметричный ключ безопасности X.509 вместо предоставляемого системой ключа безопасности, как показано в следующем примере.  Дополнительные сведения о пользовательских маркерах безопасности см. в разделе [Как создавать пользовательский маркер](../../../../docs/framework/wcf/extending/how-to-create-a-custom-token.md).  
  
     [!code-csharp[c_CustomX509Token#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customx509token/cs/source.cs#2)]
     [!code-vb[c_CustomX509Token#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customx509token/vb/source.vb#2)]  
  
2.  Создайте пользовательский поставщик маркеров безопасности, возвращающий пользовательский маркер безопасности X.509, как показано в примере.  Дополнительные сведения о пользовательских поставщиках маркеров безопасности см. в разделе [Практическое руководство. Создание пользовательского поставщика маркеров безопасности](../../../../docs/framework/wcf/extending/how-to-create-a-custom-security-token-provider.md).  
  
     [!code-csharp[c_CustomX509Token#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customx509token/cs/source.cs#3)]
     [!code-vb[c_CustomX509Token#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customx509token/vb/source.vb#3)]  
  
3.  Если пользовательский ключ безопасности необходимо использовать на стороне инициатора, создайте пользовательский диспетчер маркеров безопасности клиента и пользовательские классы учетных данных клиента, как показано в следующем примере.  Дополнительные сведения о создании пользовательских учетных данных клиента и диспетчеров маркеров безопасности клиента см. в разделе [Пошаговое руководство. Создание пользовательских учетных данных для клиента и службы](../../../../docs/framework/wcf/extending/walkthrough-creating-custom-client-and-service-credentials.md).  
  
     [!code-csharp[c_CustomX509Token#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customx509token/cs/source.cs#4)]
     [!code-vb[c_CustomX509Token#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customx509token/vb/source.vb#4)]  
  
     [!code-csharp[c_CustomX509Token#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customx509token/cs/source.cs#6)]
     [!code-vb[c_CustomX509Token#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customx509token/vb/source.vb#6)]  
  
4.  Если пользовательский ключ безопасности необходимо использовать на стороне получателя, создайте пользовательский диспетчер маркеров безопасности службы и пользовательские учетные данные службы, как показано в следующем примере.  Дополнительные сведения о создании пользовательских учетных данных службы и диспетчеров маркеров безопасности службы см. в разделе [Пошаговое руководство. Создание пользовательских учетных данных для клиента и службы](../../../../docs/framework/wcf/extending/walkthrough-creating-custom-client-and-service-credentials.md).  
  
     [!code-csharp[c_CustomX509Token#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customx509token/cs/source.cs#5)]
     [!code-vb[c_CustomX509Token#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customx509token/vb/source.vb#5)]  
  
     [!code-csharp[c_CustomX509Token#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customx509token/cs/source.cs#7)]
     [!code-vb[c_CustomX509Token#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customx509token/vb/source.vb#7)]  
  
## См. также  
 <xref:System.IdentityModel.Tokens.X509AsymmetricSecurityKey>   
 <xref:System.IdentityModel.Tokens.AsymmetricSecurityKey>   
 <xref:System.IdentityModel.Tokens.SecurityKey>   
 <xref:System.Security.Cryptography.AsymmetricAlgorithm>   
 <xref:System.Security.Cryptography.HashAlgorithm>   
 <xref:System.Security.Cryptography.AsymmetricSignatureFormatter>   
 [Пошаговое руководство. Создание пользовательских учетных данных для клиента и службы](../../../../docs/framework/wcf/extending/walkthrough-creating-custom-client-and-service-credentials.md)   
 [Как создавать пользовательскую структуру проверки подлинности маркера безопасности](../../../../docs/framework/wcf/extending/how-to-create-a-custom-security-token-authenticator.md)   
 [Практическое руководство. Создание пользовательского поставщика маркеров безопасности](../../../../docs/framework/wcf/extending/how-to-create-a-custom-security-token-provider.md)   
 [Как создавать пользовательский маркер](../../../../docs/framework/wcf/extending/how-to-create-a-custom-token.md)   
 [Security Architecture](http://msdn.microsoft.com/ru-ru/16593476-d36a-408d-808c-ae6fd483e28f)
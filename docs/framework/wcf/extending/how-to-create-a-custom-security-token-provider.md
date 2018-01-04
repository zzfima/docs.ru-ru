---
title: "Практическое руководство. Создание пользовательского поставщика маркеров безопасности"
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
helpviewer_keywords: security [WCF], providing credentials
ms.assetid: db8cb478-aa43-478b-bf97-c6489ad7c7fd
caps.latest.revision: "10"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: e776b04c626fac134e2fc9c1b9fd0ae63a50b5d3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-custom-security-token-provider"></a>Практическое руководство. Создание пользовательского поставщика маркеров безопасности
В этом разделе показано, как создавать новые типы маркеров с помощью поставщика пользовательских маркеров безопасности и как интегрировать поставщик с диспетчером пользовательских маркеров безопасности.  
  
> [!NOTE]
>  Поставщик пользовательских маркеров следует создавать, если предоставляемые системой маркеры в пространстве имен <xref:System.IdentityModel.Tokens> не соответствуют требованиям.  
  
 Поставщик маркеров безопасности создает представление маркера безопасности на основании сведений в учетных данных клиента или службы. Чтобы использовать пользовательский поставщик проверки подлинности в [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)], необходимо создать пользовательские реализации учетных данных и диспетчера маркеров безопасности.  
  
 Дополнительные сведения о пользовательских учетных данных и диспетчера маркеров безопасности. в разделе [Пошаговое руководство: Создание настраиваемых клиентских учетных данных и службы](../../../../docs/framework/wcf/extending/walkthrough-creating-custom-client-and-service-credentials.md).  
  
 Дополнительные сведения об учетных данных безопасности маркера manager поставщика классов и проверки подлинности, в разделе [архитектуры безопасности](http://msdn.microsoft.com/en-us/16593476-d36a-408d-808c-ae6fd483e28f).  
  
### <a name="to-create-a-custom-security-token-provider"></a>Создание поставщика пользовательских маркеров безопасности  
  
1.  Определите новый класс, производный от класса <xref:System.IdentityModel.Selectors.SecurityTokenProvider>.  
  
2.  Выполните метод <xref:System.IdentityModel.Selectors.SecurityTokenProvider.GetTokenCore%28System.TimeSpan%29>. Этот метод отвечает за создание и возвращение экземпляра маркера безопасности. В следующем примере создается класс с именем `MySecurityTokenProvider` и переопределяется метод <xref:System.IdentityModel.Selectors.SecurityTokenProvider.GetTokenCore%28System.TimeSpan%29>, чтобы он возвращал экземпляр класса <xref:System.IdentityModel.Tokens.X509SecurityToken>. Конструктору класса требуется экземпляр класса <xref:System.Security.Cryptography.X509Certificates.X509Certificate2>.  
  
     [!code-csharp[c_CustomTokenProvider#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customtokenprovider/cs/source.cs#1)]
     [!code-vb[c_CustomTokenProvider#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customtokenprovider/vb/source.vb#1)]  
  
### <a name="to-integrate-a-custom-security-token-provider-with-a-custom-security-token-manager"></a>Интеграция поставщика пользовательских маркеров безопасности с диспетчером пользовательских маркеров безопасности  
  
1.  Определите новый класс, производный от класса <xref:System.IdentityModel.Selectors.SecurityTokenManager>. (В следующем примере кода создается класс <xref:System.ServiceModel.ClientCredentialsSecurityTokenManager>, наследуемый от класса <xref:System.IdentityModel.Selectors.SecurityTokenManager>.)  
  
2.  Переопределите метод <xref:System.IdentityModel.Selectors.SecurityTokenManager.CreateSecurityTokenProvider%28System.IdentityModel.Selectors.SecurityTokenRequirement%29>, если он еще не переопределен.  
  
     Метод <xref:System.IdentityModel.Selectors.SecurityTokenManager.CreateSecurityTokenProvider%28System.IdentityModel.Selectors.SecurityTokenRequirement%29> отвечает за возврат экземпляра класса <xref:System.IdentityModel.Selectors.SecurityTokenProvider> в соответствии с параметром <xref:System.IdentityModel.Selectors.SecurityTokenRequirement>, переданным методу средой безопасности [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]. Измените метод, чтобы он возвращал реализацию поставщика пользовательских маркеров безопасности (созданную перед этим), когда этот метод вызывается с соответствующим параметром маркера безопасности. Дополнительные сведения о диспетчере маркера безопасности. в разделе [Пошаговое руководство: Создание настраиваемых клиентских учетных данных и службы](../../../../docs/framework/wcf/extending/walkthrough-creating-custom-client-and-service-credentials.md).  
  
3.  Добавьте в метод соответствующие инструкции, чтобы он мог возвращать поставщик пользовательских маркеров безопасности на основании параметра <xref:System.IdentityModel.Selectors.SecurityTokenRequirement>. В следующем примере метод возвращает поставщик пользовательских маркеров безопасности, если выполняются требования маркера. Требования включают маркер безопасности X.509 и направление сообщения (маркер используется для вывода сообщений). Во всех остальных случаях код вызывает базовый класс для поддержки предоставляемого системой поведения для требований других маркеров безопасности.  
  
 [!code-csharp[c_CustomTokenProvider#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customtokenprovider/cs/source.cs#2)]
 [!code-vb[c_CustomTokenProvider#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customtokenprovider/vb/source.vb#2)]  
  
## <a name="example"></a>Пример  
 Ниже показана полная реализация поставщика <xref:System.IdentityModel.Selectors.SecurityTokenProvider>, а также соответствующая реализация диспетчера <xref:System.IdentityModel.Selectors.SecurityTokenManager>.  
  
 [!code-csharp[c_CustomTokenProvider#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customtokenprovider/cs/source.cs#0)]
 [!code-vb[c_CustomTokenProvider#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customtokenprovider/vb/source.vb#0)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.IdentityModel.Selectors.SecurityTokenProvider>  
 <xref:System.IdentityModel.Selectors.SecurityTokenRequirement>  
 <xref:System.IdentityModel.Selectors.SecurityTokenManager>  
 <xref:System.IdentityModel.Tokens.X509SecurityToken>  
 [Пошаговое руководство. Создание пользовательских учетных данных для клиента и службы](../../../../docs/framework/wcf/extending/walkthrough-creating-custom-client-and-service-credentials.md)  
 [Практическое руководство. Создание пользовательской структуры проверки подлинности маркера безопасности](../../../../docs/framework/wcf/extending/how-to-create-a-custom-security-token-authenticator.md)  
 [Архитектура безопасности](http://msdn.microsoft.com/en-us/16593476-d36a-408d-808c-ae6fd483e28f)

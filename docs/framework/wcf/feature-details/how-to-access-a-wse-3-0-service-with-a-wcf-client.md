---
title: Практическое руководство. Обращение к службе WSE 3.0 с помощью клиента WCF
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 1f9bcd9b-8f8f-47fa-8f1e-0d47236eb800
ms.openlocfilehash: 3de4bb4546d3ee20e961ecf5a9d130e8e6c713a8
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2018
ms.locfileid: "50193816"
---
# <a name="how-to-access-a-wse-30-service-with-a-wcf-client"></a>Практическое руководство. Обращение к службе WSE 3.0 с помощью клиента WCF
Клиенты Windows Communication Foundation (WCF) — уровне линий связи совместимы с Web Services Enhancements (WSE) 3.0 для служб Microsoft .NET, если WCF клиенты настроены для использования версии спецификации WS-Addressing от августа 2004 г. Тем не менее, службы WSE 3.0 не поддерживают протокол exchange (MEX) метаданных, поэтому при использовании [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) для создания класса клиента WCF, не применяются параметры безопасности в созданный Клиент WCF. Таким образом, необходимо указать параметры безопасности, служба WSE 3.0 требует после создания клиента WCF.  
  
 Можно применить эти параметры безопасности с помощью пользовательской привязки необходимо принимать во внимание требований службы WSE 3.0 и требований в отношении взаимодействия между клиентом WCF и службой WSE 3.0. Требования в отношении взаимодействия включают использование упомянутой выше спецификации WS-Addressing от августа 2004 г. и предусмотренной в WSE 3.0 защиты сообщений по умолчанию с помощью поля <xref:System.ServiceModel.Security.MessageProtectionOrder.SignBeforeEncrypt>. Защита сообщений по умолчанию для WCF является <xref:System.ServiceModel.Security.MessageProtectionOrder.SignBeforeEncryptAndEncryptSignature>. В этом разделе подробно описано, как создать привязку WCF, которая взаимодействует со службой WSE 3.0. WCF также содержит пример, который включает в себя этой привязки. Дополнительные сведения об этом образце см. в разделе [взаимодействие с веб-служб ASMX](../../../../docs/framework/wcf/samples/interoperating-with-asmx-web-services.md).  
  
### <a name="to-access-a-wse-30-web-service-with-a-wcf-client"></a>Обращение к веб-службе WSE 3.0 с помощью клиента WCF  
  
1.  Запустите [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) создание клиента WCF для WSE 3.0 веб-службы.  
  
     Для службы WSE 3.0 Web создается клиент WCF. Поскольку WSE 3.0 не поддерживает протокол MEX, использовать SvcUtil.exe для извлечения требований безопасности для веб-службы нельзя. Добавить параметры безопасности для клиента должен разработчик приложения.  
  
     Дополнительные сведения о создании клиента WCF, см. в разделе [как: создание клиента](../../../../docs/framework/wcf/how-to-create-a-wcf-client.md).  
  
2.  Создайте класс, представляющий привязку, которая может обмениваться данными с веб-службами WSE 3.0.  
  
     Следующий класс является частью [взаимодействие с WSE](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms752257%28v=vs.90%29) пример:  
  
    1.  Создайте класс, производный от класса <xref:System.ServiceModel.Channels.Binding>.  
  
         В следующем примере кода создается класс с именем `WseHttpBinding`, наследуемый от класса <xref:System.ServiceModel.Channels.Binding>.  
  
         [!code-csharp[c_WCFClientToWSEService#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/wsehttpbinding.cs#1)]
         [!code-vb[c_WCFClientToWSEService#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/wsehttpbinding.vb#1)]  
  
    2.  Добавьте в класс свойства, задающие готовое к использованию утверждение WSE (используемое службой WSE), указывающие, требуются ли производные ключи, используются ли безопасные сеансы, требуется ли подтверждение подписей, а также задающие параметры защиты сообщений. В WSE 3.0 готовое к использованию утверждение задает требования к безопасности для клиентского приложения или веб-службы — аналогично режиму проверки подлинности привязки в WCF.  
  
         В следующем примере кода определяются свойства `SecurityAssertion`, `RequireDerivedKeys`, `EstablishSecurityContext` и `MessageProtectionOrder`, которые задают готовое к использованию утверждение WSE, указывают, требуются ли производные ключи, используются ли безопасные сеансы, требуется ли подтверждение сигнатур, и задают параметры защиты сообщений соответственно.  
  
         [!code-csharp[c_WCFClientToWSEService#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/wsehttpbinding.cs#3)]
         [!code-vb[c_WCFClientToWSEService#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/wsehttpbinding.vb#3)]  
  
    3.  Переопределите метод <xref:System.ServiceModel.Channels.Binding.CreateBindingElements%2A> для задания свойств привязки.  
  
         В следующем примере кода транспорт, кодирование сообщений и параметры защиты сообщений задаются получением значений свойств `SecurityAssertion` и `MessageProtectionOrder`.  
  
         [!code-csharp[c_WCFClientToWSEService#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/wsehttpbinding.cs#2)]
         [!code-vb[c_WCFClientToWSEService#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/wsehttpbinding.vb#2)]  
  
3.  В коде клиентского приложения добавьте код для задания свойств привязки.  
  
     В следующем примере кода указывает, что клиент WCF должна использовать защиту сообщений и проверки подлинности, как определено в WSE 3.0 `AnonymousForCertificate` утверждение готовое к использованию безопасности. Кроме того, требуются безопасные сеансы и производные ключи.  
  
     [!code-csharp[c_WCFClientToWSEService#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/client.cs#4)]
     [!code-vb[c_WCFClientToWSEService#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/client.vb#4)]  
  
## <a name="example"></a>Пример  
 В следующем примере кода определяется пользовательская привязка, предоставляющая свойства, соответствующие свойствам готового к использованию утверждения безопасности WSE 3.0. Эта пользовательская привязка, которая называется `WseHttpBinding`, затем используется для задания свойств привязки для клиента WCF, который взаимодействует с образцом WSSecurityAnonymous WSE 3.0 из учебника.  
  
  
  
## <a name="see-also"></a>См. также  
 <xref:System.ServiceModel.Channels.Binding>  
 [Взаимодействие с WSE](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms752257%28v=vs.90%29)

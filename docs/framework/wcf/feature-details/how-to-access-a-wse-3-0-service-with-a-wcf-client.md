---
title: Практическое руководство. Обращение к службе WSE 3.0 с помощью клиента WCF
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 1f9bcd9b-8f8f-47fa-8f1e-0d47236eb800
caps.latest.revision: 12
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 382762917e790d54dca31158f2b7ffde560c1427
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/30/2018
---
# <a name="how-to-access-a-wse-30-service-with-a-wcf-client"></a>Практическое руководство. Обращение к службе WSE 3.0 с помощью клиента WCF
Клиенты [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] на уровне линий связи совместимы со службами расширений веб-служб (WSE) версии 3.0 для Microsoft .NET, если клиенты [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] настроены на использование спецификации WS-Addressing (версия от августа 2004 г.). Однако WSE 3.0 службы не поддерживают протокол обмена (MEX) метаданные, поэтому при использовании [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) для создания [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] клиентский класс, параметры безопасности не применяются к созданный [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] клиента. Следовательно, необходимо задавать параметры безопасности, которые требует служба WSE 3.0, после формирования клиента [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
 Эти параметры безопасности можно применить путем использования пользовательской привязки для принятия во внимание требований службы WSE 3.0 и требований в отношении взаимодействия между службой WSE 3.0 и клиентом [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]. Требования в отношении взаимодействия включают использование упомянутой выше спецификации WS-Addressing от августа 2004 г. и предусмотренной в WSE 3.0 защиты сообщений по умолчанию с помощью поля <xref:System.ServiceModel.Security.MessageProtectionOrder.SignBeforeEncrypt>. По умолчанию для защиты сообщений в [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] используется поле <xref:System.ServiceModel.Security.MessageProtectionOrder.SignBeforeEncryptAndEncryptSignature>. В этом разделе описывается создание привязки [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], взаимодействующей со службой WSE 3.0. В [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] также содержится образец, включающий в себя эту привязку. Дополнительные сведения об этом образце см. в разделе [взаимодействие с веб-службами ASMX](../../../../docs/framework/wcf/samples/interoperating-with-asmx-web-services.md).  
  
### <a name="to-access-a-wse-30-web-service-with-a-wcf-client"></a>Обращение к веб-службе WSE 3.0 с помощью клиента WCF  
  
1.  Запустите [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) для создания [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] клиента для службы WSE 3.0 Web.  
  
     Для веб-службы WSE 3.0 создается клиент [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]. Поскольку WSE 3.0 не поддерживает протокол MEX, использовать SvcUtil.exe для извлечения требований безопасности для веб-службы нельзя. Добавить параметры безопасности для клиента должен разработчик приложения.  
  
     Дополнительные сведения о создании [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] клиента, в разделе [как: создание клиента](../../../../docs/framework/wcf/how-to-create-a-wcf-client.md).  
  
2.  Создайте класс, представляющий привязку, которая может обмениваться данными с веб-службами WSE 3.0.  
  
     Следующий класс является частью [взаимодействия с WSE](http://msdn.microsoft.com/library/f6816861-96a0-45f9-8736-8e4e82cd3a41) образца:  
  
    1.  Создайте класс, производный от класса <xref:System.ServiceModel.Channels.Binding>.  
  
         В следующем примере кода создается класс с именем `WseHttpBinding`, наследуемый от класса <xref:System.ServiceModel.Channels.Binding>.  
  
         [!code-csharp[c_WCFClientToWSEService#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/wsehttpbinding.cs#1)]
         [!code-vb[c_WCFClientToWSEService#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/wsehttpbinding.vb#1)]  
  
    2.  Добавьте в класс свойства, задающие готовое к использованию утверждение WSE (используемое службой WSE), указывающие, требуются ли производные ключи, используются ли безопасные сеансы, требуется ли подтверждение подписей, а также задающие параметры защиты сообщений. В WSE 3.0 готовое к использованию утверждение задает требования безопасности для клиента или веб-службы, подобно режиму проверки подлинности привязки в [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
         В следующем примере кода определяются свойства `SecurityAssertion`, `RequireDerivedKeys`, `EstablishSecurityContext` и `MessageProtectionOrder`, которые задают готовое к использованию утверждение WSE, указывают, требуются ли производные ключи, используются ли безопасные сеансы, требуется ли подтверждение сигнатур, и задают параметры защиты сообщений соответственно.  
  
         [!code-csharp[c_WCFClientToWSEService#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/wsehttpbinding.cs#3)]
         [!code-vb[c_WCFClientToWSEService#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/wsehttpbinding.vb#3)]  
  
    3.  Переопределите метод <xref:System.ServiceModel.Channels.Binding.CreateBindingElements%2A> для задания свойств привязки.  
  
         В следующем примере кода транспорт, кодирование сообщений и параметры защиты сообщений задаются получением значений свойств `SecurityAssertion` и `MessageProtectionOrder`.  
  
         [!code-csharp[c_WCFClientToWSEService#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/wsehttpbinding.cs#2)]
         [!code-vb[c_WCFClientToWSEService#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/wsehttpbinding.vb#2)]  
  
3.  В коде клиентского приложения добавьте код для задания свойств привязки.  
  
     В следующем примере кода указывается, что клиент [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] должен использовать защиту сообщений и проверку подлинности в соответствии с готовым к использованию утверждением безопасности WSE 3.0 `AnonymousForCertificate`. Кроме того, требуются безопасные сеансы и производные ключи.  
  
     [!code-csharp[c_WCFClientToWSEService#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/client.cs#4)]
     [!code-vb[c_WCFClientToWSEService#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/client.vb#4)]  
  
## <a name="example"></a>Пример  
 В следующем примере кода определяется пользовательская привязка, предоставляющая свойства, соответствующие свойствам готового к использованию утверждения безопасности WSE 3.0. Эта пользовательская привязка (с именем `WseHttpBinding`) затем используется для задания свойств привязки для клиента [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], который обменивается данными с образцом WSSecurityAnonymous WSE 3.0 из учебника.  
  
  
  
## <a name="see-also"></a>См. также  
 <xref:System.ServiceModel.Channels.Binding>  
 [Взаимодействие с WSE](http://msdn.microsoft.com/library/f6816861-96a0-45f9-8736-8e4e82cd3a41)

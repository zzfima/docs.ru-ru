---
title: Практическое руководство. Обращение к службе WSE 3.0 с помощью клиента WCF
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 1f9bcd9b-8f8f-47fa-8f1e-0d47236eb800
ms.openlocfilehash: 54d795858b85bd72a01f619b3603c9927df655d5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-access-a-wse-30-service-with-a-wcf-client"></a>Практическое руководство. Обращение к службе WSE 3.0 с помощью клиента WCF
Клиенты Windows Communication Foundation (WCF) совместимы транспортного уровня с Web Services Enhancements (WSE) 3.0 для служб Microsoft .NET при настройке клиентов WCF для использования версии спецификации WS-Addressing августа 2004 г. Однако WSE 3.0 службы не поддерживают протокол обмена (MEX) метаданные, поэтому при использовании [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) для создания класса клиента WCF, параметры безопасности не применяются к созданным Клиент WCF. Таким образом, необходимо указать параметры безопасности, службе WSE 3.0 требуется после создания клиента WCF.  
  
 Эти параметры безопасности можно применить с помощью пользовательской привязки для принятия во внимание требований службы WSE 3.0 и требований в отношении взаимодействия между службой WSE 3.0 и клиентом WCF. Требования в отношении взаимодействия включают использование упомянутой выше спецификации WS-Addressing от августа 2004 г. и предусмотренной в WSE 3.0 защиты сообщений по умолчанию с помощью поля <xref:System.ServiceModel.Security.MessageProtectionOrder.SignBeforeEncrypt>. Защита сообщений по умолчанию, для WCF <xref:System.ServiceModel.Security.MessageProtectionOrder.SignBeforeEncryptAndEncryptSignature>. В этом разделе описывается создание привязки WCF, который может взаимодействовать со службой WSE 3.0. WCF также содержится образец, включающий в себя этой привязки. Дополнительные сведения об этом образце см. в разделе [взаимодействие с веб-службами ASMX](../../../../docs/framework/wcf/samples/interoperating-with-asmx-web-services.md).  
  
### <a name="to-access-a-wse-30-web-service-with-a-wcf-client"></a>Обращение к веб-службе WSE 3.0 с помощью клиента WCF  
  
1.  Запустите [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) для создания клиента WCF для службы WSE 3.0 Web.  
  
     Для службы WSE 3.0 Web создается клиент WCF. Поскольку WSE 3.0 не поддерживает протокол MEX, использовать SvcUtil.exe для извлечения требований безопасности для веб-службы нельзя. Добавить параметры безопасности для клиента должен разработчик приложения.  
  
     Дополнительные сведения о создании WCF-клиента см. в разделе [как: создание клиента](../../../../docs/framework/wcf/how-to-create-a-wcf-client.md).  
  
2.  Создайте класс, представляющий привязку, которая может обмениваться данными с веб-службами WSE 3.0.  
  
     Следующий класс является частью [взаимодействия с WSE](http://msdn.microsoft.com/library/f6816861-96a0-45f9-8736-8e4e82cd3a41) образца:  
  
    1.  Создайте класс, производный от класса <xref:System.ServiceModel.Channels.Binding>.  
  
         В следующем примере кода создается класс с именем `WseHttpBinding`, наследуемый от класса <xref:System.ServiceModel.Channels.Binding>.  
  
         [!code-csharp[c_WCFClientToWSEService#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/wsehttpbinding.cs#1)]
         [!code-vb[c_WCFClientToWSEService#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/wsehttpbinding.vb#1)]  
  
    2.  Добавьте в класс свойства, задающие готовое к использованию утверждение WSE (используемое службой WSE), указывающие, требуются ли производные ключи, используются ли безопасные сеансы, требуется ли подтверждение подписей, а также задающие параметры защиты сообщений. В WSE 3.0 готовое к использованию утверждение задает требования безопасности для клиента или веб-службы, подобно режиму проверки подлинности привязки в WCF.  
  
         В следующем примере кода определяются свойства `SecurityAssertion`, `RequireDerivedKeys`, `EstablishSecurityContext` и `MessageProtectionOrder`, которые задают готовое к использованию утверждение WSE, указывают, требуются ли производные ключи, используются ли безопасные сеансы, требуется ли подтверждение сигнатур, и задают параметры защиты сообщений соответственно.  
  
         [!code-csharp[c_WCFClientToWSEService#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/wsehttpbinding.cs#3)]
         [!code-vb[c_WCFClientToWSEService#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/wsehttpbinding.vb#3)]  
  
    3.  Переопределите метод <xref:System.ServiceModel.Channels.Binding.CreateBindingElements%2A> для задания свойств привязки.  
  
         В следующем примере кода транспорт, кодирование сообщений и параметры защиты сообщений задаются получением значений свойств `SecurityAssertion` и `MessageProtectionOrder`.  
  
         [!code-csharp[c_WCFClientToWSEService#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/wsehttpbinding.cs#2)]
         [!code-vb[c_WCFClientToWSEService#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/wsehttpbinding.vb#2)]  
  
3.  В коде клиентского приложения добавьте код для задания свойств привязки.  
  
     В следующем примере кода указывает, что клиент WCF необходимо использовать защиту сообщений и проверки подлинности в соответствии с определением WSE 3.0 `AnonymousForCertificate` использованию утверждением безопасности. Кроме того, требуются безопасные сеансы и производные ключи.  
  
     [!code-csharp[c_WCFClientToWSEService#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/client.cs#4)]
     [!code-vb[c_WCFClientToWSEService#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/client.vb#4)]  
  
## <a name="example"></a>Пример  
 В следующем примере кода определяется пользовательская привязка, предоставляющая свойства, соответствующие свойствам готового к использованию утверждения безопасности WSE 3.0. Эта пользовательская привязка, которая называется `WseHttpBinding`, используется для задания свойств привязки для клиента WCF, который обменивается данными с образцом Wssecurityanonymous WSE 3.0.  
  
  
  
## <a name="see-also"></a>См. также  
 <xref:System.ServiceModel.Channels.Binding>  
 [Взаимодействие с WSE](http://msdn.microsoft.com/library/f6816861-96a0-45f9-8736-8e4e82cd3a41)

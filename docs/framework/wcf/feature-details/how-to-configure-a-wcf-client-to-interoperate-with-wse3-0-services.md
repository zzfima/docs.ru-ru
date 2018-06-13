---
title: Практическое руководство. Настройка клиента WCF для взаимодействия со службами WSE 3.0
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 3dadd7f1-d207-4ea5-a73b-3e8aa44407f8
ms.openlocfilehash: e30403f9c97f31e93c22a9658ffb74d4d02a49ec
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33490647"
---
# <a name="how-to-configure-a-wcf-client-to-interoperate-with-wse30-services"></a>Практическое руководство. Настройка клиента WCF для взаимодействия со службами WSE 3.0
Клиенты Windows Communication Foundation (WCF) находятся транспортного уровня совместимости с веб-служб версии 3.0 для служб Microsoft .NET (WSE), когда WCF клиенты настроены для использования версии спецификации WS-Addressing августа 2004 г.  
  
### <a name="to-configure-a-wcf-client-to-interoperate-with-a-wse-30-web-service"></a>Настройка клиента WCF для взаимодействия с веб-службой WSE 3.0  
  
1.  Запустите [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) для создания клиента WCF для службы WSE 3.0 Web.  
  
     Для веб-службы WSE создается класс клиента WCF.  
  
     Дополнительные сведения о создании WCF-клиента см. в разделе [как: создание клиента](../../../../docs/framework/wcf/how-to-create-a-wcf-client.md).  
  
2.  Создайте класс, представляющий привязку, которая может обмениваться данными с веб-службами WSE 3.0.  
  
     Следующий класс является частью [взаимодействия с WSE](http://msdn.microsoft.com/library/f6816861-96a0-45f9-8736-8e4e82cd3a41) образца.  
  
    1.  Создайте класс, производный от класса <xref:System.ServiceModel.Channels.Binding>.  
  
         В следующем примере кода создается класс с именем `WseHttpBinding`, наследуемый от класса <xref:System.ServiceModel.Channels.Binding>.  
  
         [!code-csharp[c_WCFClientToWSEService#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/wsehttpbinding.cs#1)]
         [!code-vb[c_WCFClientToWSEService#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/wsehttpbinding.vb#1)]  
  
    2.  Добавьте в класс свойства, задающие готовое к использованию утверждение WSE, требуются ли производные ключи, используются ли безопасные сеансы, требуется ли подтверждение подписей, и параметры защиты сообщений.  
  
         В следующем примере кода определяется `SecurityAssertion,``RequireDerivedKeys, EstablishSecurityContext, MessageProtectionOrder` свойства, задающие готовое к использованию утверждение WSE, требуются ли производные ключи, используются ли безопасные сеансы, требуются ли подтверждение подписей и параметры защиты сообщений соответственно.  
  
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
 В следующем примере кода определяется пользовательская привязка, предоставляющая свойства, соответствующие свойствам готового к использованию утверждения безопасности WSE 3.0. Пользовательские привязки, который называется `WseHttpBinding`, используется для задания свойств привязки для клиента WCF.  
  
  
[!code-csharp[c_WCFClientToWSEService#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/client.cs#0)]
[!code-vb[c_WCFClientToWSEService#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/client.vb#0)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.ServiceModel.Channels.Binding>  
 [Взаимодействие с WSE](http://msdn.microsoft.com/library/f6816861-96a0-45f9-8736-8e4e82cd3a41)

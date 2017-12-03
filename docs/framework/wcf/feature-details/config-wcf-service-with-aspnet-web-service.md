---
title: "Практическое руководство. Настройка службы WCF для взаимодействия с клиентами веб-службы ASP.NET"
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
ms.assetid: 48e1cd90-de80-4d6c-846e-631878955762
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 7ed4bf8e86e727505d48e85bb55a88452217c76b
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-configure-wcf-service-to-interoperate-with-aspnet-web-service-clients"></a>Практическое руководство. Настройка службы WCF для взаимодействия с клиентами веб-службы ASP.NET
Для настройки конечной точки службы [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] таким образом, чтобы она могла взаимодействовать с клиентами веб-службы [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)], используйте в качестве типа привязки для конечной точки вашей службы тип <xref:System.ServiceModel.BasicHttpBinding?displayProperty=nameWithType>.  
  
 В привязке можно дополнительно включить поддержку протокола HTTPS и проверку подлинности клиента на транспортном уровне. Клиенты веб-службы [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] не поддерживают кодирование сообщений MTOM, поэтому для свойства <xref:System.ServiceModel.BasicHttpBinding.MessageEncoding%2A?displayProperty=nameWithType> следует сохранить значение по умолчанию, т. е. <xref:System.ServiceModel.WSMessageEncoding.Text?displayProperty=nameWithType>. Клиенты веб-служб ASP.Net не поддерживают WS-Security, поэтому для <xref:System.ServiceModel.BasicHttpBinding.Security%2A?displayProperty=nameWithType> должно быть задано значение <xref:System.ServiceModel.BasicHttpSecurityMode.Transport>.  
  
 Чтобы сделать метаданные для [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] службу, доступную [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] веб-инструменты создания прокси-сервера службы (т. е [инструмент языка описания веб-служб (Wsdl.exe)](http://go.microsoft.com/fwlink/?LinkId=73833), [(средство обнаружения веб-служб DISCO.exe)](http://go.microsoft.com/fwlink/?LinkId=73834)и возможность добавить веб-ссылку в Visual Studio), должны предоставлять конечную точку метаданных HTTP/GET.  
  
### <a name="to-add-a-wcf-endpoint-that-is-compatible-with-aspnet-web-service-clients-in-code"></a>Добавление конечной точки WCF, совместимой с клиентами веб-службы ASP.NET, в код  
  
1.  Создайте новый экземпляр класса <xref:System.ServiceModel.BasicHttpBinding>.  
  
2.  Если требуется, включите безопасность транспортного уровня для привязки этой конечной точки службы, задав для привязки режим безопасности <xref:System.ServiceModel.BasicHttpSecurityMode.Transport>. Дополнительные сведения см. в разделе [безопасность транспорта](../../../../docs/framework/wcf/feature-details/transport-security.md).  
  
3.  Добавьте новую конечную точку приложения в узел службы, используя созданный экземпляр привязки. Дополнительные сведения о том, как добавить конечную точку службы в коде см. в разделе [как: создать конечную точку службы в коде](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-code.md).  
  
4.  Включите конечную точку метаданных HTTP/GET для своей службы. Дополнительные сведения см. [как: публикация метаданных для службы с помощью кода](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-code.md).  
  
### <a name="to-add-a-wcf-endpoint-that-is-compatible-with-aspnet-web-service-clients-in-a-configuration-file"></a>Добавление конечной точки WCF, совместимой с клиентами веб-службы ASP.NET, в файл конфигурации  
  
1.  Создайте новую конфигурацию привязки <xref:System.ServiceModel.BasicHttpBinding>. Дополнительные сведения см. в разделе [как: Укажите привязку службы в конфигурации](../../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md).  
  
2.  Если требуется, включите безопасность транспортного уровня для конфигурации привязки этой конечной точки службы, задав для привязки режим безопасности <xref:System.ServiceModel.BasicHttpSecurityMode.Transport>. Дополнительные сведения см. в разделе [безопасность транспорта](../../../../docs/framework/wcf/feature-details/transport-security.md).  
  
3.  Настройте новую конечную точку приложения для службы, используя созданную конфигурацию привязки. Дополнительные сведения о том, как добавить конечную точку службы в файле конфигурации см. в разделе [как: создать конечную точку службы в конфигурации](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-configuration.md).  
  
4.  Включите конечную точку метаданных HTTP/GET для своей службы. Дополнительные сведения см. [как: публикация метаданных для службы с помощью файла конфигурации](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md).  
  
## <a name="example"></a>Пример  
 В следующем примере кода показано, как добавить конечную точку [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], совместимую с клиентами веб-службы [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)], в код или в файлы конфигурации.  
  
 [!code-csharp[C_HowTo-WCFServiceAndASMXClient#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto-wcfserviceandasmxclient/cs/program.cs#0)] 
 [!code-vb[C_HowTo-WCFServiceAndASMXClient#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto-wcfserviceandasmxclient/vb/program.vb#0)] 
 [!code-xml[C_HowTo-WCFServiceAndASMXClient#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto-wcfserviceandasmxclient/common/app.config#1)]     
  
## <a name="see-also"></a>См. также  
 [Как: создать конечную точку службы в коде](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-code.md)  
 [Как: публикация метаданных для службы в коде](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-code.md)  
 [Практическое руководство. Указание привязки службы в конфигурации](../../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md)  
 [Как: создать конечную точку службы в конфигурации](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-configuration.md)  
 [Как: публикация метаданных для службы с помощью файла конфигурации](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)  
 [Безопасность транспорта](../../../../docs/framework/wcf/feature-details/transport-security.md)  
 [Использование метаданных](../../../../docs/framework/wcf/feature-details/using-metadata.md)

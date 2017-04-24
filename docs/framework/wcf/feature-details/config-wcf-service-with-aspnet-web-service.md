---
title: "Практическое руководство. Настройка службы WCF для взаимодействия с клиентами веб-службы ASP.NET | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 48e1cd90-de80-4d6c-846e-631878955762
caps.latest.revision: 11
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 11
---
# Практическое руководство. Настройка службы WCF для взаимодействия с клиентами веб-службы ASP.NET
Настройка [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] конечной точки службы с [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] клиентами веб-службы, используйте <xref:System.ServiceModel.BasicHttpBinding?displayProperty=fullName> с типом привязки для конечной точки службы.  
  
 В привязке можно дополнительно включить поддержку протокола HTTPS и проверку подлинности клиента на транспортном уровне. [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]Клиенты веб-службы не поддерживают кодирование сообщений MTOM, поэтому <xref:System.ServiceModel.BasicHttpBinding.MessageEncoding%2A?displayProperty=fullName> свойство следует оставить значение по умолчанию, который является <xref:System.ServiceModel.WSMessageEncoding?displayProperty=fullName>. Клиенты веб-службы ASP.Net не поддерживают WS-Security, поэтому <xref:System.ServiceModel.BasicHttpBinding.Security%2A?displayProperty=fullName> должно быть присвоено <xref:System.ServiceModel.BasicHttpSecurityMode>.  
  
 Чтобы сделать метаданные [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] служба доступна для [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] средства создания прокси-сервера службы веб-(то есть, [инструмент языка описания веб-служб (Wsdl.exe)](http://go.microsoft.com/fwlink/?LinkId=73833), [инструмент обнаружения веб-служб (Disco.exe)](http://go.microsoft.com/fwlink/?LinkId=73834)и функции Add Web Reference в Visual Studio), должны предоставлять конечную точку метаданных HTTP/GET.  
  
### <a name="to-add-a-wcf-endpoint-that-is-compatible-with-aspnet-web-service-clients-in-code"></a>Добавление конечной точки WCF, совместимой с клиентами веб-службы ASP.NET, в код  
  
1.  Создайте новый <xref:System.ServiceModel.BasicHttpBinding> экземпляра  
  
2.  При необходимости включить режим безопасности транспорта для привязки этой конечной точки службы, установив режим безопасности для привязки к <xref:System.ServiceModel.BasicHttpSecurityMode>. Дополнительные сведения см. в разделе [безопасность транспорта](../../../../docs/framework/wcf/feature-details/transport-security.md).  
  
3.  Добавьте новую конечную точку приложения в узел службы, используя созданный экземпляр привязки. Дополнительные сведения о том, как добавить конечную точку службы в коде см. в разделе [Практическое руководство: Создание конечной точки службы в коде](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-code.md).  
  
4.  Включите конечную точку метаданных HTTP/GET для своей службы. Дополнительные сведения см. [как: публикация метаданных для службы с помощью кода](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-code.md).  
  
### <a name="to-add-a-wcf-endpoint-that-is-compatible-with-aspnet-web-service-clients-in-a-configuration-file"></a>Добавление конечной точки WCF, совместимой с клиентами веб-службы ASP.NET, в файл конфигурации  
  
1.  Создайте новый <xref:System.ServiceModel.BasicHttpBinding> конфигурации привязки. Дополнительные сведения см. в разделе [как: Укажите привязку службы в конфигурации](../../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md).  
  
2.  При необходимости включить режим безопасности транспорта для данной конфигурации привязки конечной точки службы, установив режим безопасности для привязки к <xref:System.ServiceModel.BasicHttpSecurityMode>. Дополнительные сведения см. в разделе [безопасность транспорта](../../../../docs/framework/wcf/feature-details/transport-security.md).  
  
3.  Настройте новую конечную точку приложения для службы, используя созданную конфигурацию привязки. Дополнительные сведения о том, как добавить конечную точку службы в файле конфигурации см. в разделе [Практическое руководство: Создание конечной точки службы в конфигурации](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-configuration.md).  
  
4.  Включите конечную точку метаданных HTTP/GET для своей службы. Дополнительные сведения см. [как: публикация метаданных для службы с помощью файла конфигурации](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md).  
  
## <a name="example"></a>Пример  
 В следующем примере кода показано, как добавить конечную точку [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], совместимую с клиентами веб-службы [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)], в код или в файлы конфигурации.  
  
 [!code-csharp[C_HowTo-WCFServiceAndASMXClient#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto-wcfserviceandasmxclient/cs/program.cs#0)]
 [!code-vb[C_HowTo-WCFServiceAndASMXClient#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto-wcfserviceandasmxclient/vb/program.vb#0)]  
  
 <!-- TODO: review snippet reference [!code[C_HowTo-WCFServiceAndASMXClient#1](../../../../samples/snippets/common/VS_Snippets_CFX/c_howto-wcfserviceandasmxclient/common/app.config#1)]  -->  
  
## <a name="see-also"></a>См. также  
 [Практическое руководство: Создание конечной точки службы в коде](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-code.md)   
 [Практическое руководство: публикация метаданных для службы с помощью кода](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-code.md)   
 [Практическое руководство: задание привязки службы в конфигурации](../../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md)   
 [Практическое руководство: Создание конечной точки службы в конфигурации](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-configuration.md)   
 [Практическое руководство: публикация метаданных для службы с помощью файла конфигурации](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)   
 [Безопасность транспорта](../../../../docs/framework/wcf/feature-details/transport-security.md)   
 [Использование метаданных](../../../../docs/framework/wcf/feature-details/using-metadata.md)
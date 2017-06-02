---
title: "Создание служб, поддерживающих взаимодействие с базовым профилем WS-I 1.1 | Microsoft Docs"
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
  - "конфигурация [WCF], службы, поддерживающие взаимодействие"
ms.assetid: 91b70a21-8f5c-4679-808c-2ed5fa6b2013
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# Создание служб, поддерживающих взаимодействие с базовым профилем WS-I 1.1
Для настройки конечной точки службы [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] таким образом, чтобы она могла взаимодействовать с клиентами веб-службы [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)], необходимо:  
  
-   Используйте <xref:System.ServiceModel.BasicHttpBinding?displayProperty=fullName> с типом привязки для конечной точки службы.  
  
-   не использовать возможности обратного вызова и сеансового контракта и не управлять поведением транзакций на конечной точке службы.  
  
 В привязке можно дополнительно включить поддержку протокола HTTPS и проверку подлинности клиента на транспортном уровне.  
  
 Следующие функции <xref:System.ServiceModel.BasicHttpBinding> класса требуются функциональные возможности WS-I Basic Profile 1.1:  
  
-   Кодирование сообщения подсистемы оптимизации передачи (MTOM) сообщений контролируется <xref:System.ServiceModel.BasicHttpBinding.MessageEncoding%2A?displayProperty=fullName> свойство. Это свойство следует оставить значение по умолчанию, который является <xref:System.ServiceModel.WSMessageEncoding?displayProperty=fullName> не использовать MTOM.  
  
-   Безопасность сообщения управляется <xref:System.ServiceModel.BasicHttpBinding.Security%2A?displayProperty=fullName> значение обеспечивает поддержку WS-Security, совместимую с WS-I Basic Security Profile 1.0. Это свойство следует оставить значение по умолчанию, который является <xref:System.ServiceModel.SecurityMode?displayProperty=fullName> не использовать WS-Security.  
  
 Чтобы сделать метаданные [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] служба доступна для [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)], используйте средства создания клиентских веб-служб: [инструмент языка описания веб-служб (Wsdl.exe)](http://msdn.microsoft.com/ru-ru/b9210348-8bc2-4367-8c91-d1a04b403e88), [инструмент обнаружения веб-служб (Disco.exe)](http://msdn.microsoft.com/ru-ru/acd88078-c581-42bc-94ca-6633e2851979)и `Add Web Reference` компонентов в [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)]; необходимо включить публикацию метаданных. [!INCLUDE[crdefault](../../../includes/crdefault-md.md)][Публикация конечных точек метаданных](../../../docs/framework/wcf/publishing-metadata-endpoints.md).  
  
## <a name="example"></a>Пример  
  
### <a name="description"></a>Описание  
 В следующем примере кода показано, как добавить конечную точку [!INCLUDE[indigo2](../../../includes/indigo2-md.md)], совместимую с клиентами веб-службы [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)], в код или в файлы конфигурации.  
  
### <a name="code"></a>Код  
 [!code-csharp[C_HowTo-WCFServiceAndASMXClient#0](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto-wcfserviceandasmxclient/cs/program.cs#0)]
 [!code-vb[C_HowTo-WCFServiceAndASMXClient#0](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto-wcfserviceandasmxclient/vb/program.vb#0)]  
  
 <!-- TODO: review snippet reference [!code[C_HowTo-WCFServiceAndASMXClient#1](../../../samples/snippets/common/VS_Snippets_CFX/c_howto-wcfserviceandasmxclient/common/app.config#1)]  -->  
  
## <a name="see-also"></a>См. также  
 [Взаимодействие с веб-служб ASP.NET](../../../docs/framework/wcf/feature-details/interop-with-aspnet-web-services.md)
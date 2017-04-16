---
title: "Задание поведения клиента во время выполнения | Microsoft Docs"
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
  - "поведения [WCF], предусмотренных в системе клиента"
ms.assetid: d16d3405-be70-4edb-8f62-b5f614ddeca5
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# Задание поведения клиента во время выполнения
Клиенты [!INCLUDE[indigo1](../../../includes/indigo1-md.md)], как и службы [!INCLUDE[indigo1](../../../includes/indigo1-md.md)], можно настроить для изменения поведения среды выполнения в соответствии с особенностями клиентского приложения. Для задания поведения среды выполнения клиента существует три атрибута. Объекты обратного вызова дуплексного клиента могут использовать <xref:System.ServiceModel.CallbackBehaviorAttribute> и <xref:System.ServiceModel.Description.CallbackDebugBehavior> атрибуты для изменения их поведения во время выполнения. Атрибут, <xref:System.ServiceModel.Description.ClientViaBehavior>, может использоваться для разделения логического назначения и непосредственного назначения сети. Более того, типы обратного вызова дуплексного клиента могут использовать некоторые поведения на стороне службы. [!INCLUDE[crdefault](../../../includes/crdefault-md.md)][Указание поведения службы во время выполнения](../../../docs/framework/wcf/specifying-service-run-time-behavior.md).  
  
## <a name="using-the-callbackbehaviorattribute"></a>Использование атрибута CallbackBehaviorAttribute  
 Можно настроить или расширить поведение выполнения реализации контракта обратного вызова в клиентском приложении с помощью <xref:System.ServiceModel.CallbackBehaviorAttribute> класса. Этот атрибут выполняет те же функции для класса обратного вызова как <xref:System.ServiceModel.ServiceBehaviorAttribute> класса, за исключением экземпляров, поведения и параметров транзакции.  
  
 <xref:System.ServiceModel.CallbackBehaviorAttribute> класс должен быть применен к класса, реализующего контракт обратного вызова. Если применяется к реализации контракта недуплексные <xref:System.InvalidOperationException> исключения во время выполнения. В следующем примере кода показано <xref:System.ServiceModel.CallbackBehaviorAttribute> класса для объекта обратного вызова, который использует <xref:System.Threading.SynchronizationContext> объекта для определения потока, который требуется маршалировать, <xref:System.ServiceModel.CallbackBehaviorAttribute.ValidateMustUnderstand%2A> для принудительной проверки сообщений и <xref:System.ServiceModel.CallbackBehaviorAttribute.IncludeExceptionDetailInFaults%2A> для возврата исключений как <xref:System.ServiceModel.FaultException> объектов службы для целей отладки.  
  
 [!code-csharp[CallbackBehaviorAttribute#3](../../../samples/snippets/csharp/VS_Snippets_CFX/callbackbehaviorattribute/cs/client.cs#3)]
 [!code-vb[CallbackBehaviorAttribute#3](../../../samples/snippets/visualbasic/VS_Snippets_CFX/callbackbehaviorattribute/vb/client.vb#3)]  
  
## <a name="using-callbackdebugbehavior-to-enable-the-flow-of-managed-exception-information"></a>Использование поведения CallbackDebugBehavior для разрешения потока сведений об управляемых исключениях.  
 Можно включить поток сведений об управляемых исключениях в объект обратного вызова клиента обратно к службе для отладки, задав <xref:System.ServiceModel.Description.CallbackDebugBehavior.IncludeExceptionDetailInFaults%2A> свойства `true` программно или из конфигурации приложения файла.  
  
 Возвращение службам сведений об управляемых исключениях может представлять угрозу безопасности, потому что данные об исключениях предоставляют информацию о внутренней реализации клиента, которой могут воспользоваться неавторизованные службы. Кроме того хотя <xref:System.ServiceModel.Description.CallbackDebugBehavior> свойства также можно сделать программно, его можно легко забыть отключить <xref:System.ServiceModel.Description.CallbackDebugBehavior.IncludeExceptionDetailInFaults%2A> при развертывании.  
  
 Вследствие указанных проблем с безопасностью настоятельно рекомендуется делать следующее.  
  
-   Использовать файл конфигурации приложения для задания значения <xref:System.ServiceModel.Description.CallbackDebugBehavior.IncludeExceptionDetailInFaults%2A> свойства `true`.  
  
-   Это следует делать только в контролируемых сценариях отладки.  
  
 В следующем примере кода показан файл конфигурации клиента, который предписывает [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] возвращать сведения об управляемом исключении из объекта обратного вызова клиента в сообщениях SOAP.  
  
 [!code[SCA.CallbackContract#4](../../../samples/snippets/common/VS_Snippets_CFX/sca.callbackcontract/common/client.exe.config#4)]
 [!code-csharp[SCA.CallbackContract#4](../../../samples/snippets/csharp/VS_Snippets_CFX/sca.callbackcontract/cs/client.exe.config#4)]
 [!code-vb[SCA.CallbackContract#4](../../../samples/snippets/visualbasic/VS_Snippets_CFX/sca.callbackcontract/vb/client.exe.config#4)]  
  
## <a name="using-the-clientviabehavior-behavior"></a>Использование поведения ClientViaBehavior  
 Можно использовать <xref:System.ServiceModel.Description.ClientViaBehavior> поведение, чтобы указать универсальный код ресурса, для которого необходимо создать канал транспорта. Используйте это поведение, если непосредственное назначение сети не является предназначенным средством обработки сообщения. Благодаря этому возможны диалоги с несколькими участками передачи, если точно не известно, знает ли вызывающее приложение конечную точку назначения, или заголовок назначения `Via` не является адресом.  
  
## <a name="see-also"></a>См. также  
 [Указание поведения службы во время выполнения](../../../docs/framework/wcf/specifying-service-run-time-behavior.md)
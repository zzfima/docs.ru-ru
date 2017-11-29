---
title: "Задание поведения клиента во время выполнения"
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
helpviewer_keywords: behaviors [WCF], system-provided client
ms.assetid: d16d3405-be70-4edb-8f62-b5f614ddeca5
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 3aebab3799af562d958eb8e3e83380e734fe9268
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="specifying-client-run-time-behavior"></a>Задание поведения клиента во время выполнения
Клиенты [!INCLUDE[indigo1](../../../includes/indigo1-md.md)], как и службы [!INCLUDE[indigo1](../../../includes/indigo1-md.md)], можно настроить для изменения поведения среды выполнения в соответствии с особенностями клиентского приложения. Для задания поведения среды выполнения клиента существует три атрибута. Объекты обратного вызова дуплексного клиента могут использовать атрибуты <xref:System.ServiceModel.CallbackBehaviorAttribute> и <xref:System.ServiceModel.Description.CallbackDebugBehavior> для изменения своего поведения в среде выполнения. Атрибут <xref:System.ServiceModel.Description.ClientViaBehavior> можно использовать для разделения логического назначения и непосредственного назначения сети. Более того, типы обратного вызова дуплексного клиента могут использовать некоторые поведения на стороне службы. [!INCLUDE[crdefault](../../../includes/crdefault-md.md)][Указание поведения службы во время выполнения](../../../docs/framework/wcf/specifying-service-run-time-behavior.md).  
  
## <a name="using-the-callbackbehaviorattribute"></a>Использование атрибута CallbackBehaviorAttribute  
 Настроить или расширить поведение выполнения реализации контракта обратного вызова в клиентском приложении можно с помощью класса <xref:System.ServiceModel.CallbackBehaviorAttribute>. Функция, выполняемая этим атрибутом для класса обратного вызова, аналогична функции, выполняемой им для класса <xref:System.ServiceModel.ServiceBehaviorAttribute>, за исключением поведения при создании экземпляров и параметров транзакции.  
  
 Необходимо применить класс <xref:System.ServiceModel.CallbackBehaviorAttribute> к классу, реализующему контракт обратного вызова. Если класс применяется к реализации недуплексного контракта, во время выполнения создается исключение <xref:System.InvalidOperationException>. В следующем примере кода показан класс <xref:System.ServiceModel.CallbackBehaviorAttribute> в объекте обратного вызова, в котором используются объект <xref:System.Threading.SynchronizationContext> для определения потока, в который требуется маршалировать, свойство <xref:System.ServiceModel.CallbackBehaviorAttribute.ValidateMustUnderstand%2A> для принудительной проверки сообщений и свойство <xref:System.ServiceModel.CallbackBehaviorAttribute.IncludeExceptionDetailInFaults%2A> для возврата исключений службе в виде объектов <xref:System.ServiceModel.FaultException> в целях отладки.  
  
 [!code-csharp[CallbackBehaviorAttribute#3](../../../samples/snippets/csharp/VS_Snippets_CFX/callbackbehaviorattribute/cs/client.cs#3)]
 [!code-vb[CallbackBehaviorAttribute#3](../../../samples/snippets/visualbasic/VS_Snippets_CFX/callbackbehaviorattribute/vb/client.vb#3)]  
  
## <a name="using-callbackdebugbehavior-to-enable-the-flow-of-managed-exception-information"></a>Использование поведения CallbackDebugBehavior для разрешения потока сведений об управляемых исключениях.  
 Чтобы разрешить поток сведений об управляемых исключениях в объекте обратного вызова клиента обратно к службе в целях отладки, необходимо задать свойству <xref:System.ServiceModel.Description.CallbackDebugBehavior.IncludeExceptionDetailInFaults%2A> значение `true` программно или из файла конфигурации приложения.  
  
 Возвращение службам сведений об управляемых исключениях может представлять угрозу безопасности, потому что данные об исключениях предоставляют информацию о внутренней реализации клиента, которой могут воспользоваться неавторизованные службы. Кроме того, хотя свойства <xref:System.ServiceModel.Description.CallbackDebugBehavior> также могут настраиваться программно, <xref:System.ServiceModel.Description.CallbackDebugBehavior.IncludeExceptionDetailInFaults%2A> легко забыть отключить при развертывании.  
  
 Вследствие указанных проблем с безопасностью настоятельно рекомендуется делать следующее.  
  
-   Файл конфигурации приложения может использоваться для присвоения свойству <xref:System.ServiceModel.Description.CallbackDebugBehavior.IncludeExceptionDetailInFaults%2A> значения `true`.  
  
-   Это следует делать только в контролируемых сценариях отладки.  
  
 В следующем примере кода показан файл конфигурации клиента, который предписывает [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] возвращать сведения об управляемом исключении из объекта обратного вызова клиента в сообщениях SOAP.  
  
 [!code-xml[SCA.CallbackContract#4](../../../samples/snippets/csharp/VS_Snippets_CFX/sca.callbackcontract/cs/client.exe.config#4)]  
 
## <a name="using-the-clientviabehavior-behavior"></a>Использование поведения ClientViaBehavior  
 Для задания универсального кода ресурса (URI), для которого должен быть создан транспортный канал, можно использовать поведение <xref:System.ServiceModel.Description.ClientViaBehavior>. Используйте это поведение, если непосредственное назначение сети не является предназначенным средством обработки сообщения. Благодаря этому возможны диалоги с несколькими участками передачи, если точно не известно, знает ли вызывающее приложение конечную точку назначения, или заголовок назначения `Via` не является адресом.  
  
## <a name="see-also"></a>См. также  
 [Указание поведения службы во время выполнения](../../../docs/framework/wcf/specifying-service-run-time-behavior.md)

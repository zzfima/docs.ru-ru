---
title: Задание поведения клиента во время выполнения
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- behaviors [WCF], system-provided client
ms.assetid: d16d3405-be70-4edb-8f62-b5f614ddeca5
ms.openlocfilehash: 2f6879f5e46e62db29e482444d55680d39dd8ccc
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54587181"
---
# <a name="specifying-client-run-time-behavior"></a>Задание поведения клиента во время выполнения
Клиенты Windows Communication Foundation (WCF), такие как службы Windows Communication Foundation (WCF), можно настроить для изменения поведения времени выполнения в соответствии с клиентским приложением. Для задания поведения среды выполнения клиента существует три атрибута. Объекты обратного вызова дуплексного клиента могут использовать атрибуты <xref:System.ServiceModel.CallbackBehaviorAttribute> и <xref:System.ServiceModel.Description.CallbackDebugBehavior> для изменения своего поведения в среде выполнения. Атрибут <xref:System.ServiceModel.Description.ClientViaBehavior> можно использовать для разделения логического назначения и непосредственного назначения сети. Более того, типы обратного вызова дуплексного клиента могут использовать некоторые поведения на стороне службы. Дополнительные сведения см. в разделе [указание поведения службы во время выполнения](../../../docs/framework/wcf/specifying-service-run-time-behavior.md).  
  
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
  
 В следующем примере кода показан клиент, файл конфигурации, который указывает, что WCF для возврата сведений об управляемых исключениях из клиента объект обратного вызова в сообщениях SOAP.  
  
 [!code-xml[SCA.CallbackContract#4](../../../samples/snippets/csharp/VS_Snippets_CFX/sca.callbackcontract/cs/client.exe.config#4)]  
 
## <a name="using-the-clientviabehavior-behavior"></a>Использование поведения ClientViaBehavior  
 Для задания универсального кода ресурса (URI), для которого должен быть создан транспортный канал, можно использовать поведение <xref:System.ServiceModel.Description.ClientViaBehavior>. Используйте это поведение, если непосредственное назначение сети не является предназначенным средством обработки сообщения. Благодаря этому возможны диалоги с несколькими участками передачи, если точно не известно, знает ли вызывающее приложение конечную точку назначения, или заголовок назначения `Via` не является адресом.  
  
## <a name="see-also"></a>См. также
- [Указание поведения службы во время выполнения](../../../docs/framework/wcf/specifying-service-run-time-behavior.md)

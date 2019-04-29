---
title: Обработка неупорядоченных сообщений
ms.date: 03/30/2017
ms.assetid: 33fc62a5-5d59-461c-a37a-0e1b51ac763d
ms.openlocfilehash: 4e1864b25a4dbe8192cd5c692c75645bebbb92d2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61701246"
---
# <a name="out-of-order-message-processing"></a>Обработка неупорядоченных сообщений
Службы рабочих процессов могут зависеть от порядка отправки сообщений. Служба рабочих процессов содержит одно или несколько действий <xref:System.ServiceModel.Activities.Receive>. Каждое из этих действий <xref:System.ServiceModel.Activities.Receive> рассчитано на определенное сообщение. Поскольку доставка данных не гарантируется, отправляемые клиентами сообщения могут задерживаться и доставляться в порядке, на который служба рабочих процессов не рассчитана. Реализация службы рабочих процессов, которая не требует отправки сообщений в определенном порядке, обычно осуществляется с использованием параллельных действий. В результате усложнения протокола приложения рабочий процесс также слишком быстро становится сложным.  Из неупорядоченные сообщения, обработке функции в Windows Communication Foundation (WCF) позволяет создавать такой рабочий процесс исключив сложности реализации вложенных параллельных действий. Обработка сообщений из неупорядоченные поддерживается только каналами, поддерживающими <xref:System.ServiceModel.Channels.ReceiveContext> например привязок WCF MSMQ.  
  
## <a name="enabling-out-of-order-message-processing"></a>Реализация обработки внеочередных сообщений  
 Чтобы включить обработку внеочередных сообщений, в WorkflowService установите свойство <xref:System.ServiceModel.Activities.WorkflowService.AllowBufferedReceive%2A> в значение `true`. В следующем примере кода показана установка свойства <xref:System.ServiceModel.Activities.WorkflowService.AllowBufferedReceive%2A> в коде.  
  
```csharp  
// Code: Opt-in to Buffered Receive processing...  
WorkflowService service = new WorkflowService  
{  
    Name="MyService",  
    Body = workflow,  
    AllowBufferedReceive = true  
};  
```  
  
 Можно также применить атрибут `AllowBufferedReceive` к службе рабочих процессов в XAML, как показано в следующем примере.  
  
```xaml  
// Xaml: Opt-in to Buffered Receive processing...  
<WorkflowService AllowBufferedReceive="True">  
   <!--the actual children activities -->  
</Sequence>  
```  
  
## <a name="see-also"></a>См. также

- <xref:System.ServiceModel.Channels.ReceiveContext>
- [Службы рабочих процессов](../../../../docs/framework/wcf/feature-details/workflow-services.md)
- [Очереди и надежные сеансы](../../../../docs/framework/wcf/feature-details/queues-and-reliable-sessions.md)

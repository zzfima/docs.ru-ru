---
title: Практическое руководство. Асинхронный вызов операций службы WCF
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 0face17f-43ca-417b-9b33-737c0fc360df
ms.openlocfilehash: 5eae08ab6b8dee5ebece66a1c41c87ebab3387bc
ms.sourcegitcommit: c01c18755bb7b0f82c7232314ccf7955ea7834db
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/15/2020
ms.locfileid: "75963279"
---
# <a name="how-to-call-wcf-service-operations-asynchronously"></a>Практическое руководство. Асинхронный вызов операций службы WCF

В этой статье описывается, как клиент может асинхронно получить доступ к операции службы. Служба в этой статье реализует интерфейс `ICalculator`. Клиент может асинхронно вызывать операции этого интерфейса с помощью управляемой событиями модели асинхронного вызова. (Дополнительные сведения о модели асинхронного вызова на основе событий см. [в разделе многопоточное программирование с асинхронной моделью, основанной на событиях](../../../standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)). Пример, демонстрирующий асинхронную реализацию операции в службе, см. [в разделе как реализовать асинхронную операцию службы](../how-to-implement-an-asynchronous-service-operation.md). Дополнительные сведения о синхронных и асинхронных операциях см. в разделе [синхронные и асинхронные операции](../synchronous-and-asynchronous-operations.md).  
  
> [!NOTE]
> Управляемая событиями модель асинхронных вызовов не поддерживается при использовании класса <xref:System.ServiceModel.ChannelFactory%601>. Дополнительные сведения о выполнении асинхронных вызовов с помощью <xref:System.ServiceModel.ChannelFactory%601>см. в разделе [инструкции. асинхронное вызов операций с помощью фабрики каналов](../../../../docs/framework/wcf/feature-details/how-to-call-operations-asynchronously-using-a-channel-factory.md).  
  
## <a name="procedure"></a>Процедура .  
  
#### <a name="to-call-wcf-service-operations-asynchronously"></a>Асинхронный вызов операций службы WCF  
  
1. Запустите средство [служебной программы метаданных ServiceModel (Svcutil. exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) с параметрами команды `/async` и `/tcv:Version35`, как показано в следующей команде.  
  
    ```console
    svcutil /n:http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples http://localhost:8000/servicemodelsamples/service/mex /a /tcv:Version35  
    ```  
  
     В дополнение к синхронным и стандартным асинхронным операциям на основе делегата, клиентский класс WCF, содержащий:  
  
    - Два <`operationName`>`Async` операции для использования с асинхронным вызовом на основе событий. Например:  
  
         [!code-csharp[EventAsync#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/generatedclient.cs#1)]
         [!code-vb[EventAsync#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/generatedclient.vb#1)]  
  
    - Операции завершенных событий в форме <`operationName`>`Completed` для использования с асинхронным вызовом на основе событий. Например:  
  
         [!code-csharp[EventAsync#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/generatedclient.cs#2)]
         [!code-vb[EventAsync#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/generatedclient.vb#2)]  
  
    - <xref:System.EventArgs?displayProperty=nameWithType> типы для каждой операции (формы <`operationName`>`CompletedEventArgs`) для использования с методом асинхронного вызова на основе событий. Например:  
  
         [!code-csharp[EventAsync#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/generatedclient.cs#3)]
         [!code-vb[EventAsync#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/generatedclient.vb#3)]  
  
2. В вызывающем приложении создайте метод обратного вызова, вызываемый после завершения асинхронной операции, как показано в следующем примере кода.  
  
     [!code-csharp[EventAsync#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/client.cs#4)]
     [!code-vb[EventAsync#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/client.vb#4)]  
  
3. Перед вызовом операции используйте новый универсальный <xref:System.EventHandler%601?displayProperty=nameWithType> типа <`operationName`>`EventArgs`, чтобы добавить метод обработчика (созданный на предыдущем шаге) в событие <`operationName`>`Completed`. Затем вызовите метод <`operationName`>`Async`. Например:  
  
     [!code-csharp[EventAsync#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/client.cs#5)]
     [!code-vb[EventAsync#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/client.vb#5)]  
  
## <a name="example"></a>Пример  
  
> [!NOTE]
> Согласно правилам разработки для асинхронной модели на основе событий, если возвращается несколько значений, одно значение возвращается как свойство `Result`, а остальные возвращаются как свойства объекта <xref:System.EventArgs>. Одним из результатов этого является то, что если клиент импортирует метаданные с использованием параметров асинхронных команд на основе событий и операция возвращает более одного значения, объект <xref:System.EventArgs> по умолчанию возвращает одно значение как свойство `Result`, а остальные являются свойствами объекта <xref:System.EventArgs>. Если требуется получать объект сообщения как свойство `Result`, чтобы возвращаемые значения были свойствами этого объекта, используйте параметр команды `/messageContract`. При этом формируется сигнатура, которая возвращает ответное сообщение как свойство `Result` объекта <xref:System.EventArgs>. Все внутренние возвращаемые значения тогда будут свойствами объекта ответного сообщения.  
  
 [!code-csharp[EventAsync#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/client.cs#6)]
 [!code-vb[EventAsync#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/client.vb#6)]  
  
## <a name="see-also"></a>См. также:

- [Практическое руководство. Асинхронная реализация операции службы](../../../../docs/framework/wcf/how-to-implement-an-asynchronous-service-operation.md)

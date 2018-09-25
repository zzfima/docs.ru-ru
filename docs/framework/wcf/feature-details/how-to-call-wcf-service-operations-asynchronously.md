---
title: Практическое руководство. Асинхронный вызов операций службы WCF
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 0face17f-43ca-417b-9b33-737c0fc360df
ms.openlocfilehash: 90e00e4264ff808151c9e1c58fdaf290765620c8
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2018
ms.locfileid: "46711354"
---
# <a name="how-to-call-wcf-service-operations-asynchronously"></a>Практическое руководство. Асинхронный вызов операций службы WCF
В этом разделе описано, каким образом клиент может асинхронно обратиться к операции службы. Служба в этом разделе реализует интерфейс `ICalculator`. Клиент может асинхронно вызывать операции этого интерфейса с помощью управляемой событиями модели асинхронного вызова. (Дополнительные сведения об управляемой событиями модели асинхронного вызова см. в разделе [многопоточное программирование с использованием асинхронной модели на основе событий](https://go.microsoft.com/fwlink/?LinkId=248184)). Пример, в котором демонстрируется реализация асинхронной операции в службе, см. в разделе [как: реализация асинхронной операции службы](../../../../docs/framework/wcf/how-to-implement-an-asynchronous-service-operation.md). Дополнительные сведения о синхронных и асинхронных операциях см. в разделе [синхронные и асинхронные операции](../../../../docs/framework/wcf/synchronous-and-asynchronous-operations.md).  
  
> [!NOTE]
>  Управляемая событиями модель асинхронных вызовов не поддерживается при использовании класса <xref:System.ServiceModel.ChannelFactory%601>. Сведения об асинхронных вызовах с использованием <xref:System.ServiceModel.ChannelFactory%601>, см. в разделе [как: вызов операции асинхронно с помощью фабрики каналов](../../../../docs/framework/wcf/feature-details/how-to-call-operations-asynchronously-using-a-channel-factory.md).  
  
## <a name="procedure"></a>Процедура  
  
#### <a name="to-call-wcf-service-operations-asynchronously"></a>Асинхронный вызов операций службы WCF  
  
1.  Запустите [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) средство с обоими `/async` и `/tcv:Version35` параметрами командной строки как показано в следующей команде.  
  
    ```  
    svcutil /n:http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples http://localhost:8000/servicemodelsamples/service/mex /a /tcv:Version35  
    ```  
  
     Это приводит к возникновению ошибки, помимо синхронной операции и стандартной делегатов асинхронными операциями, класс клиента WCF, который содержит:  
  
    -   Два <`operationName` > `Async` операций для использования с основанной на событиях асинхронных вызовами. Пример:  
  
         [!code-csharp[EventAsync#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/generatedclient.cs#1)]
         [!code-vb[EventAsync#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/generatedclient.vb#1)]  
  
    -   События с завершенными операциями в форме <`operationName` > `Completed` для использования с основанной на событиях асинхронных вызовами. Пример:  
  
         [!code-csharp[EventAsync#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/generatedclient.cs#2)]
         [!code-vb[EventAsync#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/generatedclient.vb#2)]  
  
    -   <xref:System.EventArgs?displayProperty=nameWithType> типы для каждой операции (в формате <`operationName`>`CompletedEventArgs`) для использования с основанной на событиях асинхронных вызовами. Пример:  
  
         [!code-csharp[EventAsync#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/generatedclient.cs#3)]
         [!code-vb[EventAsync#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/generatedclient.vb#3)]  
  
2.  В вызывающем приложении создайте метод обратного вызова, вызываемый после завершения асинхронной операции, как показано в следующем примере кода.  
  
     [!code-csharp[EventAsync#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/client.cs#4)]
     [!code-vb[EventAsync#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/client.vb#4)]  
  
3.  Перед вызовом операции используйте новый универсальный <xref:System.EventHandler%601?displayProperty=nameWithType> типа <`operationName` > `EventArgs` добавляемый метод обработчика (созданный на предыдущем шаге) <`operationName` > `Completed` событий. Затем вызовите <`operationName` > `Async` метод. Пример:  
  
     [!code-csharp[EventAsync#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/client.cs#5)]
     [!code-vb[EventAsync#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/client.vb#5)]  
  
## <a name="example"></a>Пример  
  
> [!NOTE]
>  Согласно правилам разработки для асинхронной модели на основе событий, если возвращается несколько значений, одно значение возвращается как свойство `Result`, а остальные возвращаются как свойства объекта <xref:System.EventArgs>. Одним из результатов этого является то, что если клиент импортирует метаданные с использованием параметров асинхронных команд на основе событий и операция возвращает более одного значения, объект <xref:System.EventArgs> по умолчанию возвращает одно значение как свойство `Result`, а остальные являются свойствами объекта <xref:System.EventArgs>. Если требуется получать объект сообщения как свойство `Result`, чтобы возвращаемые значения были свойствами этого объекта, используйте параметр команды `/messageContract`. При этом формируется сигнатура, которая возвращает ответное сообщение как свойство `Result` объекта <xref:System.EventArgs>. Все внутренние возвращаемые значения тогда будут свойствами объекта ответного сообщения.  
  
 [!code-csharp[EventAsync#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/client.cs#6)]
 [!code-vb[EventAsync#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/client.vb#6)]  
  
## <a name="see-also"></a>См. также  
 [Практическое руководство. Асинхронная реализация операции службы](../../../../docs/framework/wcf/how-to-implement-an-asynchronous-service-operation.md)

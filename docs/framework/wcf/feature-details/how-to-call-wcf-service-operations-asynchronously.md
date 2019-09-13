---
title: Практическое руководство. Асинхронный вызов операций службы WCF
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 0face17f-43ca-417b-9b33-737c0fc360df
ms.openlocfilehash: 2c0a6f1477ceec5471c22fa3e46d85f5856b298e
ms.sourcegitcommit: 5ae5a1a9520b8b8b6164ad728d396717f30edafc
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/11/2019
ms.locfileid: "70895061"
---
# <a name="how-to-call-wcf-service-operations-asynchronously"></a>Практическое руководство. Асинхронный вызов операций службы WCF
В этом разделе описано, каким образом клиент может асинхронно обратиться к операции службы. Служба в этом разделе реализует интерфейс `ICalculator`. Клиент может асинхронно вызывать операции этого интерфейса с помощью управляемой событиями модели асинхронного вызова. (Дополнительные сведения о модели асинхронного вызова на основе событий см. [в разделе многопоточное программирование с асинхронной моделью, основанной на событиях](https://go.microsoft.com/fwlink/?LinkId=248184)). Пример, демонстрирующий асинхронную реализацию операции в службе, см. в разделе [как Реализуйте асинхронную операцию](../../../../docs/framework/wcf/how-to-implement-an-asynchronous-service-operation.md)службы. Дополнительные сведения о синхронных и асинхронных операциях см. в разделе [синхронные и асинхронные операции](../../../../docs/framework/wcf/synchronous-and-asynchronous-operations.md).  
  
> [!NOTE]
> Управляемая событиями модель асинхронных вызовов не поддерживается при использовании класса <xref:System.ServiceModel.ChannelFactory%601>. Дополнительные сведения о выполнении асинхронных вызовов с <xref:System.ServiceModel.ChannelFactory%601>помощью см [. в разделе как Асинхронно вызывайте операции с помощью фабрики](../../../../docs/framework/wcf/feature-details/how-to-call-operations-asynchronously-using-a-channel-factory.md)каналов.  
  
## <a name="procedure"></a>Процедура  
  
#### <a name="to-call-wcf-service-operations-asynchronously"></a>Асинхронный вызов операций службы WCF  
  
1. Запустите средство [служебной программы метаданных ServiceModel (Svcutil. exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) вместе с `/async` параметрами `/tcv:Version35` команды и, как показано в следующей команде.  
  
    ```console
    svcutil /n:http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples http://localhost:8000/servicemodelsamples/service/mex /a /tcv:Version35  
    ```  
  
     В дополнение к синхронным и стандартным асинхронным операциям на основе делегата, клиентский класс WCF, содержащий:  
  
    - Две операции`operationName` <>дляиспользованияс методомасинхронноговызованаосновесобытий`Async` . Например:  
  
         [!code-csharp[EventAsync#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/generatedclient.cs#1)]
         [!code-vb[EventAsync#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/generatedclient.vb#1)]  
  
    - Операции завершенных событий в форме <`operationName` > `Completed` для использования с асинхронным вызовом на основе событий. Например:  
  
         [!code-csharp[EventAsync#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/generatedclient.cs#2)]
         [!code-vb[EventAsync#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/generatedclient.vb#2)]  
  
    - <xref:System.EventArgs?displayProperty=nameWithType>типы для каждой операции (формы <`operationName`>`CompletedEventArgs`) для использования с методом асинхронного вызова на основе событий. Например:  
  
         [!code-csharp[EventAsync#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/generatedclient.cs#3)]
         [!code-vb[EventAsync#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/generatedclient.vb#3)]  
  
2. В вызывающем приложении создайте метод обратного вызова, вызываемый после завершения асинхронной операции, как показано в следующем примере кода.  
  
     [!code-csharp[EventAsync#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/client.cs#4)]
     [!code-vb[EventAsync#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/client.vb#4)]  
  
3. Перед <xref:System.EventHandler%601?displayProperty=nameWithType> вызовом операции используйте новый универсальный тип <`operationName` > `EventArgs` , чтобы добавить метод обработчика (созданный на предыдущем шаге) к событию <`operationName`. > `Completed` Затем вызовите метод`operationName` <> `Async` . Например:  
  
     [!code-csharp[EventAsync#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/client.cs#5)]
     [!code-vb[EventAsync#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/client.vb#5)]  
  
## <a name="example"></a>Пример  
  
> [!NOTE]
> Согласно правилам разработки для асинхронной модели на основе событий, если возвращается несколько значений, одно значение возвращается как свойство `Result`, а остальные возвращаются как свойства объекта <xref:System.EventArgs>. Одним из результатов этого является то, что если клиент импортирует метаданные с использованием параметров асинхронных команд на основе событий и операция возвращает более одного значения, объект <xref:System.EventArgs> по умолчанию возвращает одно значение как свойство `Result`, а остальные являются свойствами объекта <xref:System.EventArgs>. Если требуется получать объект сообщения как свойство `Result`, чтобы возвращаемые значения были свойствами этого объекта, используйте параметр команды `/messageContract`. При этом формируется сигнатура, которая возвращает ответное сообщение как свойство `Result` объекта <xref:System.EventArgs>. Все внутренние возвращаемые значения тогда будут свойствами объекта ответного сообщения.  
  
 [!code-csharp[EventAsync#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/client.cs#6)]
 [!code-vb[EventAsync#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/client.vb#6)]  
  
## <a name="see-also"></a>См. также

- [Практическое руководство. Реализация асинхронной операции службы](../../../../docs/framework/wcf/how-to-implement-an-asynchronous-service-operation.md)

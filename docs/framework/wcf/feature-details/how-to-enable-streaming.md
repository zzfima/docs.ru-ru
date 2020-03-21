---
title: Практическое руководство. Включение потоковой передачи
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 6ca2cf4b-c7a1-49d8-a79b-843a90556ba4
ms.openlocfilehash: 1d1eaa1ebf41ef86478dda795b3b199239cd37b4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184932"
---
# <a name="how-to-enable-streaming"></a>Практическое руководство. Включение потоковой передачи
Фонд связи Windows (WCF) может отправлять сообщения с помощью буферизированных или потоковых переводов. По умолчанию используется режим буферизованной передачи, в случае которого сообщение должно быть доставлено полностью, прежде чем получатель сможет его прочитать. При использовании режима потоковой передачи получатель может начать обработку сообщения до того, как оно будет доставлено полностью. Режим потоковой передачи полезно использовать при большой длине передаваемых данных, которые могут обрабатываться последовательно. Режим потоковой передачи также может быть полезен, когда размер сообщения слишком велик для выполнения полной буферизации.  
  
 Для включения потоковой передачи необходимо соответствующим образом определить контракт операции `OperationContract` и включить потоковую передачу на транспортном уровне.  
  
### <a name="to-stream-data"></a>Потоковая передача данных  
  
1. Для выполнения потоковой передачи контракт операции `OperationContract` для службы должен удовлетворять двум требованиям.  
  
    1. Параметр, в котором содержатся данные для потоковой передачи, должен быть единственным в методе. Например, если требуется выполнить потоковую передачу входного сообщения, операция должна иметь точно один входной параметр. Аналогично, если требуется выполнить потоковую передачу выходного сообщения, операция должна иметь точно один выходной параметр или возвращать значение.  
  
    2. Параметр и возвращаемое значение должны принадлежать по крайней мере к одному из следующих типов: <xref:System.IO.Stream>, <xref:System.ServiceModel.Channels.Message> или <xref:System.Xml.Serialization.IXmlSerializable>.  
  
     Ниже приведен пример контракта для потоковой передачи данных.  
  
     [!code-csharp[c_HowTo_EnableStreaming#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_enablestreaming/cs/service.cs#1)]
     [!code-vb[c_HowTo_EnableStreaming#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_enablestreaming/vb/service.vb#1)]  
  
     Операция `GetStream` получает часть буферизованных входных данных в качестве строки (`string`), которая является буферизованной, и возвращает объект `Stream`, который является потоковым. И наоборот, `UploadStream` принимает объект `Stream` (потоковый) и возвращает объект `bool` (буферизованный). `EchoStream` принимает и возвращает объект `Stream` и является примером операции, в которой как входное, так и выходное сообщения являются потоковыми. Наконец, `GetReversedStream` не принимает никакие данные и возвращает объект `Stream` (потоковый).  
  
2. Потоковая передача должна быть включена в привязке. Задаваемое свойство `TransferMode` может принимать одно из следующих значений.  
  
    1. `Buffered`,  
  
    2. `Streamed`. Обеспечивает потоковую передачу в обоих направлениях.  
  
    3. `StreamedRequest`. Обеспечивает только потоковую передачу запроса.  
  
    4. `StreamedResponse`. Обеспечивает только потоковую передачу ответа.  
  
     `BasicHttpBinding` предоставляет свойство `TransferMode` в привязке, как делают `NetTcpBinding` и `NetNamedPipeBinding`. Свойство `TransferMode` можно также задать в элементе привязки транспорта и использовать в пользовательской привязке.  
  
     В следующих примерах показано, как задать свойство `TransferMode` с помощью кода и путем изменения файла конфигурации. В обоих примерах для свойства `maxReceivedMessageSize` задается значение 64 МБ, определяющее максимальный размер принимаемых сообщений. По умолчанию для свойства `maxReceivedMessageSize` задано значение 64 КБ, которое обычно слишком мало для сценариев потоковой передачи. Это параметр квоты необходимо задавать в соответствии с максимальным размером сообщений, получение которых ожидается приложением. Также обратите внимание, что свойство `maxBufferSize` контролирует максимальный размер буферизуемых данных; для него требуется задать соответствующее значение.  
  
    1. В следующем фрагменте конфигурации из примера показано задание для свойства `TransferMode` значения потоковой передачи в привязке `basicHttpBinding` и пользовательской привязке HTTP.  
  
         [!code-xml[c_HowTo_EnableStreaming#103](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_enablestreaming/common/app.config#103)]
  
    2. В следующем фрагменте кода показано задание для свойства `TransferMode` значения потоковой передачи в привязке `basicHttpBinding` и пользовательской привязке HTTP.  
  
         [!code-csharp[c_HowTo_EnableStreaming_code#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_enablestreaming_code/cs/c_howto_enablestreaming_code.cs#2)]
         [!code-vb[c_HowTo_EnableStreaming_code#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_enablestreaming_code/vb/c_howto_enablestreaming_code.vb#2)]  
  
    3. В следующем фрагменте кода показано задание для свойства `TransferMode` значения потоковой передачи в пользовательской привязке TCP.  
  
         [!code-csharp[c_HowTo_EnableStreaming_code#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_enablestreaming_code/cs/c_howto_enablestreaming_code.cs#3)]
         [!code-vb[c_HowTo_EnableStreaming_code#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_enablestreaming_code/vb/c_howto_enablestreaming_code.vb#3)]  
  
3. Операции `GetStream`, `UploadStream` и `EchoStream` выполняют передачу данных непосредственно из файла или сохранение полученных данных непосредственно в файл. Следующий код относится к `GetStream`.  
  
     [!code-csharp[c_HowTo_EnableStreaming#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_enablestreaming/cs/service.cs#4)]
     [!code-vb[c_HowTo_EnableStreaming#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_enablestreaming/vb/service.vb#4)]  
  
### <a name="writing-a-custom-stream"></a>Создание пользовательского потока  
  
1. Для специальной обработки каждого фрагмента потока данных во время его отправки или получения необходимо создать производный класс на основе класса <xref:System.IO.Stream>. В следующем примере кода пользовательского потока используется метод `GetReversedStream` и класс `ReverseStream`.  
  
     Метод `GetReversedStream` создает и возвращает новый экземпляр класса `ReverseStream`. Фактическая обработка происходит, когда система считывает данные из объекта `ReverseStream`. Метод `ReverseStream.Read` считывает фрагмент байтов из исходного файла, обращает их, а затем возвращает байты, представленные в обратном порядке. Этот метод не обращает все содержимое файла; он обращает один фрагмент байтов за раз. В этом примере показано, как можно выполнить потоковую обработку во время чтения или записи содержимого из потока.  
  
     [!code-csharp[c_HowTo_EnableStreaming#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_enablestreaming/cs/service.cs#2)]
     [!code-vb[c_HowTo_EnableStreaming#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_enablestreaming/vb/service.vb#2)]  
  
## <a name="see-also"></a>См. также раздел

- [Большие данные и потоковая передача](../../../../docs/framework/wcf/feature-details/large-data-and-streaming.md)
- [Поток](../../../../docs/framework/wcf/samples/stream.md)

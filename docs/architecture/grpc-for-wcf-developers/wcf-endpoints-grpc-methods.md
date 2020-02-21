---
title: Конечные точки WCF и методы gRPC — gRPC для разработчиков WCF
description: Сравнение конечных точек WCF, объявленных с атрибутами ServiceContract и OperationContract, и методами gRPC, объявленными в protobuf
ms.date: 09/02/2019
ms.openlocfilehash: 1bc6ecbc73bfc0a58393e4c28672b897ed6f2f15
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/20/2020
ms.locfileid: "77503432"
---
# <a name="wcf-endpoints-and-grpc-methods"></a>Конечные точки WCF и методы gRPC

В Windows Communication Foundation (WCF) при написании кода приложения используется один из следующих методов.

- Код приложения записывается в класс и оформляются методы с помощью атрибута [OperationContract](xref:System.ServiceModel.OperationContractAttribute) .
- Вы объявляете интерфейс для службы и добавляете в интерфейс атрибуты [OperationContract](xref:System.ServiceModel.OperationContractAttribute) .

Например, WCF, эквивалентная службе `greet.proto` Гритер, может быть написана следующим образом:

```csharp
[ServiceContract]
public interface IGreeterService
{
    [OperationContract]
    string SayHello(string name);
}
```

В главе 3 показано, что определения сообщений protobuf используются для создания классов данных. Объявления служб и методов используются для создания базовых классов, наследуемых от, для реализации службы. Вы просто объявляете методы для реализации в файле `.proto`, и компилятор создает базовый класс с виртуальными методами, которые необходимо переопределить.

## <a name="operationcontract-properties"></a>Свойства OperationContract

Атрибут [OperationContract](xref:System.ServiceModel.OperationContractAttribute) имеет свойства для управления и уточнения его работы. методы gRPC не предлагают этот тип элемента управления. В следующей таблице перечислены эти `OperationContract` свойства и описано, как заданные ими функции являются (или нет) обработаны с помощью в gRPC:

| Свойство `OperationContract` | gRPC                                             |
| ---------------------------- | ------------------------------------------------ |
| <xref:System.ServiceModel.OperationContractAttribute.Action>             | URI идентифицирует операцию. gRPC использует имя `package`, `service`и `rpc` из файла `.proto`. |
| <xref:System.ServiceModel.OperationContractAttribute.AsyncPattern>       | Все методы службы gRPC возвращают `Task` объекты. |
| <xref:System.ServiceModel.OperationContractAttribute.IsInitiating>       | См. абзац после этой таблицы. |
| <xref:System.ServiceModel.OperationContractAttribute.IsOneWay>           | Односторонние методы gRPC возвращают `Empty` результаты или используют потоковую передачу клиента. |
| <xref:System.ServiceModel.OperationContractAttribute.IsTerminating>      | См. абзац после этой таблицы. |
| <xref:System.ServiceModel.OperationContractAttribute.Name>               | Это свойство связано с SOAP и не имеет смысла в gRPC. |
| <xref:System.ServiceModel.OperationContractAttribute.ProtectionLevel>    | Шифрование сообщений отсутствует. Сетевое шифрование обрабатывается на транспортном уровне (TLS через HTTP/2). |
| <xref:System.ServiceModel.OperationContractAttribute.ReplyAction>        | Это свойство связано с SOAP и не имеет смысла в gRPC. |

Свойство `IsInitiating` позволяет указать, что метод в [ServiceContract](xref:System.ServiceModel.ServiceContractAttribute) не может быть первым методом, вызванным как часть сеанса. Свойство `IsTerminating` заставляет сервер закрыть сеанс после вызова операции (или клиента, если свойство используется в клиенте обратного вызова). В gRPC потоки создаются с помощью отдельных методов и закрываются явным образом. См. раздел [потоковая передача gRPC](rpc-types.md#grpc-streaming).

Дополнительные сведения о безопасности и шифровании gRPC см. в [главе 6](security.md).

>[!div class="step-by-step"]
>[Назад](wcf-services-to-grpc-comparison.md)
>[Вперед](wcf-bindings.md)

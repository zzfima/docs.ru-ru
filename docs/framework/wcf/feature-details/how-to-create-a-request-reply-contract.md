---
title: Практическое руководство. Создание контракта типа "запрос-ответ"
ms.date: 03/30/2017
ms.assetid: 801d90da-3d45-4284-9c9f-56c8aadb4060
ms.openlocfilehash: 793f7214f8319e87c3e344990577841fc029bc55
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79185033"
---
# <a name="how-to-create-a-request-reply-contract"></a>Практическое руководство. Создание контракта типа "запрос-ответ"
Контракт «запрос-ответ» указывает метод, который возвращает ответ. Необходима отправка ответа и его корреляция запросу согласно условиям этого контракта. Даже если метод не возвращает ответ (`void` в C# или `Sub` в Visual Basic), инфраструктура создает и отправляет вызывающему объекту пустое сообщение. Чтобы запретить отправку пустого ответного сообщения, используйте для операции односторонний контракт.  
  
### <a name="to-create-a-request-reply-contract"></a>Создание контракта типа запрос-ответ  
  
1. Создайте интерфейс на любом языке программирования.  
  
2. Примените атрибут <xref:System.ServiceModel.ServiceContractAttribute> к интерфейсу.  
  
3. Примените атрибут <xref:System.ServiceModel.OperationContractAttribute> к каждому методу, который могут вызывать клиенты.  
  
4. Необязательный параметр. Установите свойство <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A> в значение `true`, чтобы избежать отправки пустого ответного сообщения. По умолчанию все операции используют контракты «запрос-ответ».  
  
## <a name="example"></a>Пример  
 В следующем примере определяется контракт для службы калькулятора, предоставляющей методы `Add` и `Subtract`. Метод `Multiply` не является частью контракта, поскольку он не отмечен классом <xref:System.ServiceModel.OperationContractAttribute>, а потому недоступен клиентам.  
  
```csharp
using System.ServiceModel;

[ServiceContract]
public interface ICalculator
{
    [OperationContract]
    // It would be equivalent to write explicitly:
    // [OperationContract(IsOneWay=false)]
    int Add(int a, int b);

    [OperationContract]
    int Subtract(int a, int b);

    int Multiply(int a, int b)
}
```
  
- Для получения дополнительной информации <xref:System.ServiceModel.OperationContractAttribute> <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A> о том, как указать операционные контракты, см.  
  
- Применение атрибутов <xref:System.ServiceModel.ServiceContractAttribute> и <xref:System.ServiceModel.OperationContractAttribute> вызывает автоматическое создание определений контракта службы в документе WSDL после развертывания службы. Документ загружается путем добавления `?wsdl` к базовому адресу HTTP для службы, Например `http://microsoft/CalculatorService?wsdl`.  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.ServiceModel.OperationContractAttribute>
- [Разработка контрактов службы](../../../../docs/framework/wcf/designing-service-contracts.md)
- [Практическое руководство. Создание дуплексного контракта](../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md)

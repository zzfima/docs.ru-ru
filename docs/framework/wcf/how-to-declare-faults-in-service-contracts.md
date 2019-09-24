---
title: Практическое руководство. Объявление сбоев в контрактах служб
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e8da98e7-d22f-4f60-ac82-3fb0928a353f
ms.openlocfilehash: 2de14a76fd2ce8ad656c2b64f5f9e5b17d81eebc
ms.sourcegitcommit: 56f1d1203d0075a461a10a301459d3aa452f4f47
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2019
ms.locfileid: "71216862"
---
# <a name="how-to-declare-faults-in-service-contracts"></a>Практическое руководство. Объявление сбоев в контрактах служб

В управляемом коде исключения создаются в случае возникновения ошибки. Однако в приложениях Windows Communication Foundation (WCF) контракты служб указывают, какие сведения об ошибке возвращаются клиентам, объявляя ошибки SOAP в контракте службы. Общие сведения о связи между исключениями и сбоями см. [в разделе Указание и обработка ошибок в контрактах и службах](specifying-and-handling-faults-in-contracts-and-services.md).

## <a name="create-a-service-contract-that-specifies-a-soap-fault"></a>Создайте контракт службы, в котором определяется ошибка SOAP

1. Создайте контракт службы, который содержит как минимум одну операцию. Пример см. в статье [Практическое руководство. Определите контракт](how-to-define-a-wcf-service-contract.md)службы.

2. Выберите операцию, которая задает условие ошибки, о которой предполагается уведомить клиентов. Сведения о том, какие условия ошибок по высоте возвращают ошибки SOAP клиентам, см. в разделе [Указание и обработка ошибок в контрактах и службах](specifying-and-handling-faults-in-contracts-and-services.md).

3. Примените атрибут <xref:System.ServiceModel.FaultContractAttribute?displayProperty=nameWithType> к выбранной операции и передайте в конструктор сериализуемый тип ошибки. Дополнительные сведения о создании и использовании сериализуемых типов см. [в разделе указание передача данных в контрактах служб](./feature-details/specifying-data-transfer-in-service-contracts.md). В следующем примере показано, как указать, что операция `SampleMethod` может возвращать `GreetingFault`.

     [!code-csharp[FaultContractAttribute#4](~/samples/snippets/csharp/VS_Snippets_CFX/faultcontractattribute/cs/services.cs#4)]
     [!code-vb[FaultContractAttribute#4](~/samples/snippets/visualbasic/VS_Snippets_CFX/faultcontractattribute/vb/services.vb#4)]

4. Повторите шаги 2 и 3 для всех операций контракта, которые могут передавать клиентам условия ошибок.

## <a name="implementing-an-operation-to-return-a-specified-soap-fault"></a>Реализация операции, возвращающей заданную ошибку SOAP
 После задания операции, возвращающей конкретную ошибку SOAP (например, как в описанной выше процедуре) для передачи условия ошибки вызывающему приложения, необходимо реализовать соответствующую спецификацию.

### <a name="throw-the-specified-soap-fault-in-the-operation"></a>Создайте заданную ошибку SOAP в операции

1. Когда в операции возникает условие ошибки, задаваемое атрибутом <xref:System.ServiceModel.FaultContractAttribute>, создайте новое исключение <xref:System.ServiceModel.FaultException%601?displayProperty=nameWithType>, где заданная ошибка SOAP является параметром типа. В следующих примерах кода демонстрируется, как создать ошибку `GreetingFault` в методе `SampleMethod`, показанном в описанной выше процедуре и в следующем разделе Code.

     [!code-csharp[FaultContractAttribute#5](~/samples/snippets/csharp/VS_Snippets_CFX/faultcontractattribute/cs/services.cs#5)]
     [!code-vb[FaultContractAttribute#5](~/samples/snippets/visualbasic/VS_Snippets_CFX/faultcontractattribute/vb/services.vb#5)]

## <a name="example"></a>Пример

В следующем примере кода показана реализация одной операции, которая задает ошибку `GreetingFault` для операции `SampleMethod`.

[!code-csharp[FaultContractAttribute#1](~/samples/snippets/csharp/VS_Snippets_CFX/faultcontractattribute/cs/services.cs#1)]
[!code-vb[FaultContractAttribute#1](~/samples/snippets/visualbasic/VS_Snippets_CFX/faultcontractattribute/vb/services.vb#1)]

## <a name="see-also"></a>См. также

- <xref:System.ServiceModel.FaultContractAttribute?displayProperty=nameWithType>
- <xref:System.ServiceModel.FaultException%601?displayProperty=nameWithType>

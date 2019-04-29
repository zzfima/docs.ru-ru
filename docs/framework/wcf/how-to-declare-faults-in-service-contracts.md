---
title: Практическое руководство. Объявление сбоев в контрактах служб
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e8da98e7-d22f-4f60-ac82-3fb0928a353f
ms.openlocfilehash: 0e173f71201d5f98a04d2ad922469e4ff6666681
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61929289"
---
# <a name="how-to-declare-faults-in-service-contracts"></a>Практическое руководство. Объявление сбоев в контрактах служб
В управляемом коде исключения создаются в случае возникновения ошибки. В приложениях Windows Communication Foundation (WCF) Однако контракты службы укажите, какие сведения об ошибке возвращается клиентам объявляются ошибки SOAP в контракте службы. Общие сведения о связи между исключениями и ошибками, см. в разделе [задание и обработка сбоев в контрактах и службах](../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md).  
  
### <a name="create-a-service-contract-that-specifies-a-soap-fault"></a>Создайте контракт службы, в котором определяется ошибка SOAP  
  
1. Создайте контракт службы, который содержит как минимум одну операцию. Пример см. в статье [Практическое руководство. Определите контракт службы](../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md).  
  
2. Выберите операцию, которая задает условие ошибки, о которой предполагается уведомить клиентов. Чтобы решить, какие ошибки соответствуют возврату ошибок SOAP клиентам, см. в разделе [задание и обработка сбоев в контрактах и службах](../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md).  
  
3. Примените атрибут <xref:System.ServiceModel.FaultContractAttribute?displayProperty=nameWithType> к выбранной операции и передайте в конструктор сериализуемый тип ошибки. Дополнительные сведения о создании и использовании сериализуемых типов см. в разделе [Specifying Data Transfer in Service Contracts](../../../docs/framework/wcf/feature-details/specifying-data-transfer-in-service-contracts.md). В следующем примере показано, как указать, что операция `SampleMethod` может возвращать `GreetingFault`.  
  
     [!code-csharp[FaultContractAttribute#4](../../../samples/snippets/csharp/VS_Snippets_CFX/faultcontractattribute/cs/services.cs#4)]
     [!code-vb[FaultContractAttribute#4](../../../samples/snippets/visualbasic/VS_Snippets_CFX/faultcontractattribute/vb/services.vb#4)]  
  
4. Повторите шаги 2 и 3 для всех операций контракта, которые могут передавать клиентам условия ошибок.  
  
## <a name="implementing-an-operation-to-return-a-specified-soap-fault"></a>Реализация операции, возвращающей заданную ошибку SOAP  
 После задания операции, возвращающей конкретную ошибку SOAP (например, как в описанной выше процедуре) для передачи условия ошибки вызывающему приложения, необходимо реализовать соответствующую спецификацию.  
  
#### <a name="throw-the-specified-soap-fault-in-the-operation"></a>Создайте заданную ошибку SOAP в операции  
  
1. Когда в операции возникает условие ошибки, задаваемое атрибутом <xref:System.ServiceModel.FaultContractAttribute>, создайте новое исключение <xref:System.ServiceModel.FaultException%601?displayProperty=nameWithType>, где заданная ошибка SOAP является параметром типа. В следующих примерах кода демонстрируется, как создать ошибку `GreetingFault` в методе `SampleMethod`, показанном в описанной выше процедуре и в следующем разделе Code.  
  
     [!code-csharp[FaultContractAttribute#5](../../../samples/snippets/csharp/VS_Snippets_CFX/faultcontractattribute/cs/services.cs#5)]
     [!code-vb[FaultContractAttribute#5](../../../samples/snippets/visualbasic/VS_Snippets_CFX/faultcontractattribute/vb/services.vb#5)]  
  
## <a name="example"></a>Пример  
 В следующем примере кода показана реализация одной операции, которая задает ошибку `GreetingFault` для операции `SampleMethod`.  
  
 [!code-csharp[FaultContractAttribute#1](../../../samples/snippets/csharp/VS_Snippets_CFX/faultcontractattribute/cs/services.cs#1)]
 [!code-vb[FaultContractAttribute#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/faultcontractattribute/vb/services.vb#1)]  
  
## <a name="see-also"></a>См. также

- <xref:System.ServiceModel.FaultContractAttribute?displayProperty=nameWithType>
- <xref:System.ServiceModel.FaultException%601?displayProperty=nameWithType>

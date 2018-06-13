---
title: Практическое руководство. Объявление сбоев в контрактах служб
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e8da98e7-d22f-4f60-ac82-3fb0928a353f
ms.openlocfilehash: 142ad26702f0732bc5103e29d5a44bc57ab37625
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33500240"
---
# <a name="how-to-declare-faults-in-service-contracts"></a>Практическое руководство. Объявление сбоев в контрактах служб
В управляемом коде исключения создаются в случае возникновения ошибки. В приложениях Windows Communication Foundation (WCF) Однако контракты служб указывают, какие сведения об ошибке возвращаются клиенту объявляются ошибки SOAP в контракте службы. Общие сведения о связи между исключений и ошибок в разделе [указание и обработка сбоев в контрактах и службах](../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md).  
  
### <a name="create-a-service-contract-that-specifies-a-soap-fault"></a>Создайте контракт службы, в котором определяется ошибка SOAP  
  
1.  Создайте контракт службы, который содержит как минимум одну операцию. Пример см. в разделе [как: определение контракта службы](../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md).  
  
2.  Выберите операцию, которая задает условие ошибки, о которой предполагается уведомить клиентов. Чтобы решить, какие состояния ошибки justify, возвращая ошибок SOAP клиентам, в разделе [указание и обработка сбоев в контрактах и службах](../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md).  
  
3.  Примените атрибут <xref:System.ServiceModel.FaultContractAttribute?displayProperty=nameWithType> к выбранной операции и передайте в конструктор сериализуемый тип ошибки. Дополнительные сведения о создании и использовании сериализуемых типов см. в разделе [указание входящий трафик передачи данных в контрактах служб](../../../docs/framework/wcf/feature-details/specifying-data-transfer-in-service-contracts.md). В следующем примере показано, как указать, что операция `SampleMethod` может возвращать `GreetingFault`.  
  
     [!code-csharp[FaultContractAttribute#4](../../../samples/snippets/csharp/VS_Snippets_CFX/faultcontractattribute/cs/services.cs#4)]
     [!code-vb[FaultContractAttribute#4](../../../samples/snippets/visualbasic/VS_Snippets_CFX/faultcontractattribute/vb/services.vb#4)]  
  
4.  Повторите шаги 2 и 3 для всех операций контракта, которые могут передавать клиентам условия ошибок.  
  
## <a name="implementing-an-operation-to-return-a-specified-soap-fault"></a>Реализация операции, возвращающей заданную ошибку SOAP  
 После задания операции, возвращающей конкретную ошибку SOAP (например, как в описанной выше процедуре) для передачи условия ошибки вызывающему приложения, необходимо реализовать соответствующую спецификацию.  
  
#### <a name="throw-the-specified-soap-fault-in-the-operation"></a>Создайте заданную ошибку SOAP в операции  
  
1.  Когда в операции возникает условие ошибки, задаваемое атрибутом <xref:System.ServiceModel.FaultContractAttribute>, создайте новое исключение <xref:System.ServiceModel.FaultException%601?displayProperty=nameWithType>, где заданная ошибка SOAP является параметром типа. В следующих примерах кода демонстрируется, как создать ошибку `GreetingFault` в методе `SampleMethod`, показанном в описанной выше процедуре и в следующем разделе Code.  
  
     [!code-csharp[FaultContractAttribute#5](../../../samples/snippets/csharp/VS_Snippets_CFX/faultcontractattribute/cs/services.cs#5)]
     [!code-vb[FaultContractAttribute#5](../../../samples/snippets/visualbasic/VS_Snippets_CFX/faultcontractattribute/vb/services.vb#5)]  
  
## <a name="example"></a>Пример  
 В следующем примере кода показана реализация одной операции, которая задает ошибку `GreetingFault` для операции `SampleMethod`.  
  
 [!code-csharp[FaultContractAttribute#1](../../../samples/snippets/csharp/VS_Snippets_CFX/faultcontractattribute/cs/services.cs#1)]
 [!code-vb[FaultContractAttribute#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/faultcontractattribute/vb/services.vb#1)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.ServiceModel.FaultContractAttribute?displayProperty=nameWithType>  
 <xref:System.ServiceModel.FaultException%601?displayProperty=nameWithType>

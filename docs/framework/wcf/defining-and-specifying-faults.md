---
title: Определение и задание сбоев
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- handling faults [WCF], specifying
- handling faults [WCF], defining
ms.assetid: c00c84f1-962d-46a7-b07f-ebc4f80fbfc1
ms.openlocfilehash: 99e0c22a66eb1d839f1594cf53373a74fc3dd02d
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
ms.locfileid: "33806878"
---
# <a name="defining-and-specifying-faults"></a>Определение и задание сбоев
Ошибки SOAP передают сведения об ошибке от службы клиенту и, в дуплексном случае, от клиента службе совместимым способом. В этом разделе описано, как и когда можно определить содержимое пользовательских ошибок и задать операции, которые могут возвратить это содержимое. Дополнительные сведения о том, как служба или дуплексный клиент могут отправлять такие ошибки и как клиент или служба приложение обрабатывает эти ошибки см. в разделе [отправка и получение ошибки](../../../docs/framework/wcf/sending-and-receiving-faults.md). Общие сведения для обработки ошибок в приложениях Windows Communication Foundation (WCF) см. в разделе [указание и обработка сбоев в контрактах и службах](../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md).  
  
## <a name="overview"></a>Обзор  
 Объявленные ошибки SOAP - это ошибки, в которых в операции имеется атрибут <xref:System.ServiceModel.FaultContractAttribute?displayProperty=nameWithType>, указывающий пользовательский тип ошибки SOAP. Необъявленные ошибки SOAP - это ошибки, не указанные в контракте операции. Изучение этого раздела поможет определять такие состояния ошибки и создать для своей службы контракт ошибок, который может использоваться клиентами для правильной обработки состояния ошибки при уведомлении о пользовательской ошибке SOAP. Необходимо решить следующие основные задачи (порядок имеет значение):  
  
1.  Определить состояния ошибки, о которых должен знать клиент службы;  
  
2.  Определить пользовательское содержимое ошибок SOAP для этих состояний ошибки;  
  
3.  Отметить операции, чтобы создаваемые ими определенные ошибки SOAP предоставлялись клиентам в формате WSDL.  
  
### <a name="defining-error-conditions-that-clients-should-know-about"></a>Определение состояний ошибки, о которых должен знать клиент  
 Ошибки SOAP - это общедоступные сообщения, содержащие сведения об ошибке определенной операции. Так как они описаны вместе с другими сообщениями операций в WSDL, клиенты знают о них и, следовательно, готовы обрабатывать такие ошибки при вызове операции. Однако, так как службы WCF написаны в управляемом коде, выбор состояний ошибки в управляемом коде должны быть преобразованы в ошибки и возвращается клиенту предоставляет возможность отделить ошибки и сбои службы от формального ошибки диалога у клиента.  
  
 Например, в следующем примере кода показана операция, которая принимает два целых числа и возвращает другое целое число. Здесь может быть создано несколько исключений, поэтому при разработке контракта ошибок нужно определить, какие состояния ошибки важны для клиента. В этом случае служба должна обнаруживать исключение <xref:System.DivideByZeroException?displayProperty=nameWithType>.  
  
```csharp  
[ServiceContract]  
public class CalculatorService  
{  
    [OperationContract]   
    int Divide(int a, int b)  
    {  
      if (b==0) throw new Exception("Division by zero!");  
      return a/b;  
    }  
}  
```  
  
```vb  
<ServiceContract> _  
Public Class CalculatorService  
    <OperationContract]> _  
    Public Function Divide(ByVal a As Integer, ByVal b As Integer) _  
       As Integer  
      If (b==0) Then   
            Throw New Exception("Division by zero!")  
      Return a/b  
    End Function  
End Class  
```  
  
 В данном примере операция может вернуть пользовательскую ошибку SOAP о делении на ноль, пользовательскую ошибку, связанную с математическими операциями, но содержащую сведения о делении на ноль, несколько ошибок для различных ситуаций с ошибками или не возвращать ошибок SOAP.  
  
### <a name="define-the-content-of-error-conditions"></a>Определение содержимого состояний ошибки  
 Если установлено, что состояние ошибки может вернуть полезную пользовательскую ошибку SOAP, необходимо определить содержимое этой ошибки и убедиться, что структура содержимого сериализуется. В примере кода в предыдущем разделе показана ошибка, связанную с операцией `Divide`, но если в службе `Calculator` содержатся другие операции, одна пользовательская ошибка SOAP может сообщать клиенту обо всех состояниях ошибки калькулятора, включая `Divide`. В следующем коде показан пример создания пользовательской ошибки SOAP, `MathFault`, которая может сообщать об ошибках, произошедших при любых математических операциях, включая `Divide`. Класс может задавать операцию (свойство `Operation`) и значение, описывающее проблему (свойство `ProblemType`), но при этом класс и эти свойства должны быть сериализуемы, чтобы их можно было передать клиенту в пользовательской ошибке SOAP. Чтобы обеспечить максимальный уровень сериализуемости типа и его свойств, а также максимальный уровень взаимодействия, используются атрибуты <xref:System.Runtime.Serialization.DataContractAttribute?displayProperty=nameWithType> и <xref:System.Runtime.Serialization.DataMemberAttribute?displayProperty=nameWithType>.  
  
 [!code-csharp[Faults#2](../../../samples/snippets/csharp/VS_Snippets_CFX/faults/cs/service.cs#2)]
 [!code-vb[Faults#2](../../../samples/snippets/visualbasic/VS_Snippets_CFX/faults/vb/service.vb#2)]  
  
 Дополнительные сведения о том, как обеспечить данных может быть сериализован см. в разделе [указание входящий трафик передачи данных в контрактах служб](../../../docs/framework/wcf/feature-details/specifying-data-transfer-in-service-contracts.md). Список сериализации технической поддержки, <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> предоставляет, см. [типы, поддерживаемые сериализатором контракта данных](../../../docs/framework/wcf/feature-details/types-supported-by-the-data-contract-serializer.md).  
  
### <a name="mark-operations-to-establish-the-fault-contract"></a>Разметка операций для установления контракта ошибок  
 После определения сериализуемой структуры данных, которая возвращается как часть пользовательской ошибки SOAP, нужно отметить контракт операции, как создающий ошибку SOAP этого типа. Для этого следует использовать атрибут <xref:System.ServiceModel.FaultContractAttribute?displayProperty=nameWithType> и передать тип созданного пользовательского типа данных. В следующем примере кода показано, как с помощью атрибута <xref:System.ServiceModel.FaultContractAttribute> указать, что операция `Divide` может возвращать ошибку SOAP типа `MathFault`. Другие математические операции теперь тоже могут указывать, что могут вернуть ошибку `MathFault`.  
  
 [!code-csharp[Faults#1](../../../samples/snippets/csharp/VS_Snippets_CFX/faults/cs/service.cs#1)]
 [!code-vb[Faults#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/faults/vb/service.vb#1)]  
  
 Операция может указывать, что возвращает несколько пользовательских ошибок, если она отмечена несколькими атрибутами <xref:System.ServiceModel.FaultContractAttribute>.  
  
 Следующий шаг для реализации контракта ошибок в реализации операции, описанную в разделе [отправка и получение ошибки](../../../docs/framework/wcf/sending-and-receiving-faults.md).  
  
#### <a name="soap-wsdl-and-interoperability-considerations"></a>Вопросы SOAP, WSDL и взаимодействия  
 В некоторых ситуациях, особенно при взаимодействиях с другими платформами, может быть важно контролировать представление ошибки в сообщении SOAP или способ ее описания в метаданных WSDL.  
  
 Атрибут <xref:System.ServiceModel.FaultContractAttribute> содержит свойство <xref:System.ServiceModel.FaultContractAttribute.Name%2A>, позволяющее контролировать имя элемента ошибки WSDL, которое создается в метаданных этой ошибки.  
  
 В соответствии со стандартом SOAP для ошибки могут указываться атрибуты `Action`, `Code` и `Reason`. `Action` контролируется свойством <xref:System.ServiceModel.FaultContractAttribute.Action%2A>. Свойства <xref:System.ServiceModel.FaultException.Code%2A> и<xref:System.ServiceModel.FaultException.Reason%2A> - свойства класса <xref:System.ServiceModel.FaultException?displayProperty=nameWithType>, родительского класса универсального класса <xref:System.ServiceModel.FaultException%601?displayProperty=nameWithType>. Свойство `Code` включает член <xref:System.ServiceModel.FaultCode.SubCode%2A>.  
  
 Существуют некоторые ограничения доступа к службам, создающим ошибки. WCF поддерживает только ошибки с типами сведений, описанными в схеме и совместимыми с контрактами данных. Например как упоминалось выше, WCF не поддерживает ошибки, использующие в типах сведений атрибуты XML, а также ошибки с более чем один элемент верхнего уровня в области сведений.  
  
## <a name="see-also"></a>См. также  
 <xref:System.ServiceModel.FaultContractAttribute>  
 <xref:System.Runtime.Serialization.DataContractAttribute>  
 <xref:System.Runtime.Serialization.DataMemberAttribute>  
 [Указание и обработка сбоев в контрактах и службах](../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md)  
 [Сбои при отправке и получении](../../../docs/framework/wcf/sending-and-receiving-faults.md)  
 [Практическое руководство. Объявление сбоев в контрактах служб](../../../docs/framework/wcf/how-to-declare-faults-in-service-contracts.md)  
 [Основные сведения об уровне защиты](../../../docs/framework/wcf/understanding-protection-level.md)  
 [Практическое руководство. Установка свойства ProtectionLevel](../../../docs/framework/wcf/how-to-set-the-protectionlevel-property.md)  
 [Задание передачи данных в контрактах служб](../../../docs/framework/wcf/feature-details/specifying-data-transfer-in-service-contracts.md)

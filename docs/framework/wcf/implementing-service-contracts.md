---
title: Реализация контрактов служб
ms.date: 03/30/2017
helpviewer_keywords:
- implementing service contracts [WCF]
ms.assetid: aefb6f56-47e3-4f24-ab0a-9bc07bf9885f
ms.openlocfilehash: aefe146a8941d98d7d9138e4ece83c330c967034
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184005"
---
# <a name="implementing-service-contracts"></a>Реализация контрактов служб
Служба - это класс, который предоставляет клиентам имеющиеся функциональные возможности в одной или нескольких конечных точках. Чтобы создать службу, напишите класс, который реализует контракт Фонда связи Windows (WCF). Это можно сделать одним из двух способов. Во-первых, можно определить контракт отдельно в качестве интерфейса, а затем создать класс, реализующий этот интерфейс. Во-вторых, можно непосредственно создать класс и контракт, разместив атрибут <xref:System.ServiceModel.ServiceContractAttribute> в самом классе, а атрибут <xref:System.ServiceModel.OperationContractAttribute> - в методах, доступных клиентам службы.  
  
## <a name="creating-a-service-class"></a>Создание класса службы  
 Ниже приведен пример службы, реализующей отдельно определенный контракт `IMath`.  
  
```csharp  
// Define the IMath contract.  
[ServiceContract]  
public interface IMath  
{  
    [OperationContract]
    double Add(double A, double B);  
  
    [OperationContract]  
    double Multiply (double A, double B);  
}  
  
// Implement the IMath contract in the MathService class.  
public class MathService : IMath  
{  
    public double Add (double A, double B) { return A + B; }  
    public double Multiply (double A, double B) { return A * B; }  
}  
```  
  
 Кроме того, контракт может непосредственно предоставляться службой. Ниже приведен пример класса службы, который определяет и реализует контракт `MathService`.  
  
```csharp  
// Define the MathService contract directly on the service class.  
[ServiceContract]  
class MathService  
{  
    [OperationContract]  
    public double Add(double A, double B) { return A + B; }  
    [OperationContract]  
    private double Multiply (double A, double B) { return A * B; }  
}  
```  
  
 Обратите внимание, что описанные службы предоставляют разные контракты, так как имена контрактов различаются. В первом случае предоставленный контракт называется "`IMath`", а во втором - "`MathService`".  
  
 Некоторые свойства (такие как параллелизм и создание экземпляров) можно задать на уровне реализации службы и операции. Для получения дополнительной [информации](designing-and-implementing-services.md)см.  
  
 После реализации контракта службы необходимо создать для службы одну или более конечных точек. Для получения дополнительной [Endpoint Creation Overview](endpoint-creation-overview.md)информации см. Для получения дополнительной информации о том, как запустить службу, [см.](hosting-services.md)  
  
## <a name="see-also"></a>См. также раздел

- [Проектирование и реализация служб](designing-and-implementing-services.md)
- [Практическое руководство. Создание службы с помощью класса контракта](./feature-details/how-to-create-a-wcf-contract-with-a-class.md)
- [Практическое руководство. Создание службы с помощью интерфейса контракта](./feature-details/how-to-create-a-service-with-a-contract-interface.md)
- [Указание поведения службы во время выполнения](specifying-service-run-time-behavior.md)

---
title: DeliveryRequirementsAttribute
ms.date: 03/30/2017
ms.assetid: 40c5435c-a325-4cf8-9dd0-d6e24b4a56a3
ms.openlocfilehash: 7bfc03299fffc8070a7d8a4b3885706ea861bdf6
ms.sourcegitcommit: 9bd8f213b50f0e1a73e03bd1e840c917fbd6d20a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/26/2018
ms.locfileid: "50042900"
---
# <a name="deliveryrequirementsattribute"></a>DeliveryRequirementsAttribute
DeliveryRequirementsAttribute  
  
## <a name="syntax"></a>Синтаксис  
  
```csharp
class DeliveryRequirementsAttribute : Behavior  
{  
  string QueuedDeliveryRequirements;  
  boolean RequireOrderedDelivery;  
  string TargetContract;  
};  
```  
  
## <a name="methods"></a>Методы  
 Класс DeliveryRequirementsAttribute не определяет никаких методов.  
  
## <a name="properties"></a>Свойства  
 Класс DeliveryRequirementsAttribute имеет следующие свойства.  
  
### <a name="queueddeliveryrequirements"></a>QueuedDeliveryRequirements  
 Тип данных: string  
  
 Тип доступа: только для чтения  
  
 Указывает, поддерживает ли привязка для службы контракты.  
  
### <a name="requireordereddelivery"></a>RequireOrderedDelivery  
 Тип данных: boolean  
  
 Тип доступа: только для чтения  
  
 Указывает, поддерживает ли привязка упорядоченные сообщения.  
  
### <a name="targetcontract"></a>TargetContract  
 Тип данных: string  
  
 Тип доступа: только для чтения  
  
 Контракт, к которому оно применимо.  
  
## <a name="requirements"></a>Требования  
  
|MOF|Объявлено в файле Servicemodel.mof.|  
|---------|-----------------------------------|  
|Пространство имен|Определено в root\ServiceModel.|  
  
## <a name="see-also"></a>См. также  
 <xref:System.ServiceModel.DeliveryRequirementsAttribute>

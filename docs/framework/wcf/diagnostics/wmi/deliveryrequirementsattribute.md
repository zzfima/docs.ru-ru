---
title: DeliveryRequirementsAttribute
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 40c5435c-a325-4cf8-9dd0-d6e24b4a56a3
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e297bfc0499ea3ee8d3dd8395165ca22b2baa1de
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="deliveryrequirementsattribute"></a>DeliveryRequirementsAttribute
DeliveryRequirementsAttribute  
  
## <a name="syntax"></a>Синтаксис  
  
```  
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

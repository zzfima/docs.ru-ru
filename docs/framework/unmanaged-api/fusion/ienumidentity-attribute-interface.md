---
title: "Интерфейс IEnumIDENTITY_ATTRIBUTE"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IEnumIDENTITY_ATTRIBUTE
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IEnumIDENTITY_ATTRIBUTE
helpviewer_keywords:
- IEnumIDENTITY_ATTRIBUTE interface [.NET Framework fusion]
ms.assetid: c2ec2748-e9ae-4e1b-80db-6fcec5cb81a1
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: fc77f2106f5063b8db25f375c354a15f9f936e78
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="ienumidentityattribute-interface"></a>Интерфейс IEnumIDENTITY_ATTRIBUTE
Служит в качестве перечислителя для атрибутов объекта кода в текущей области.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание:|  
|------------|-----------------|  
|`IEnumIDENTITY_ATTRIBUTE::Clone`|Получает указатель интерфейса на новый `IEnumIDENTITY_ATTRIBUTE` , содержащий те же элементы, как это `IEnumIDENTITY_ATTRIBUTE`.|  
|`IEnumIDENTITY_ATTRIBUTE::CurrentIntoBuffer`|Записывает данные, содержащиеся в элементах этого `IEnumIDENTITY_ATTRIBUTE` для указанного буфера данных.|  
|`IEnumIDENTITY_ATTRIBUTE::Next`|Возвращает заданное число атрибутов, начиная с текущей позиции.|  
|`IEnumIDENTITY_ATTRIBUTE::Reset`|Перемещает указатель на начало `IEnumIDENTITY_ATTRIBUTE`.|  
|`IEnumIDENTITY_ATTRIBUTE::Skip`|Перемещает указатель инструкций вперед на указанное число элементов, начиная с текущей позиции.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** Isolation.h  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейсы Fusion](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)

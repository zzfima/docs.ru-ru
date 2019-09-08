---
title: Интерфейс IEnumIDENTITY_ATTRIBUTE
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: dbb3ac150ebfe9fe3698427d8bb2bfb3e3347c07
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796467"
---
# <a name="ienumidentity_attribute-interface"></a>Интерфейс IEnumIDENTITY_ATTRIBUTE
Служит в качестве перечислителя для атрибутов объекта Code в текущей области.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|`IEnumIDENTITY_ATTRIBUTE::Clone`|Возвращает указатель интерфейса на новый `IEnumIDENTITY_ATTRIBUTE` объект, содержащий те же элементы, что и этот `IEnumIDENTITY_ATTRIBUTE`объект.|  
|`IEnumIDENTITY_ATTRIBUTE::CurrentIntoBuffer`|Записывает данные, содержащиеся в элементах `IEnumIDENTITY_ATTRIBUTE` этого объекта, в указанный буфер данных.|  
|`IEnumIDENTITY_ATTRIBUTE::Next`|Возвращает указанное число атрибутов, начиная с текущей позиции.|  
|`IEnumIDENTITY_ATTRIBUTE::Reset`|Перемещает указатель инструкций в начало `IEnumIDENTITY_ATTRIBUTE`.|  
|`IEnumIDENTITY_ATTRIBUTE::Skip`|Перемещает указатель инструкции вперед на указанное число элементов, начиная с текущей позиции.|  
  
## <a name="requirements"></a>Требования  
 **Платформ** См. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок.** Изоляция. h  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейсы Fusion](fusion-interfaces.md)

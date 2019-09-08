---
title: Интерфейс IEnumReferenceIdentity
ms.date: 03/30/2017
api_name:
- IEnumReferenceIdentity
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IEnumReferenceIdentity
helpviewer_keywords:
- IEnumReferenceIdentity interface [.NET Framework fusion]
ms.assetid: a17b3155-7216-4e16-8c9f-abce21f549e7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4c5d4bc1fa82f7623168050f4ee36f0ea3cd171e
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796441"
---
# <a name="ienumreferenceidentity-interface"></a>Интерфейс IEnumReferenceIdentity
Служит в качестве перечислителя для коллекции `IReferenceIdentity` объектов.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|`IEnumReferenceIdentity::Clone`|Возвращает указатель интерфейса на новый `IEnumReferenceIdentity` объект, содержащий те же элементы, что и этот `IEnumReferenceIdentity`объект.|  
|`IEnumReferenceIdentity::Next`|Возвращает указанное число `IReferenceIdentity` объектов, начиная с текущей позиции.|  
|`IEnumReferenceIdentity::Reset`|Перемещает указатель инструкций в начало `IEnumReferenceIdentity`.|  
|`IEnumReferenceIdentity::Skip`|Перемещает указатель инструкции вперед на указанное число элементов, начиная с текущей позиции.|  
  
## <a name="requirements"></a>Требования  
 **Платформ** См. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок.** Изоляция. h  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейсы Fusion](fusion-interfaces.md)
- [Интерфейс IReferenceIdentity](ireferenceidentity-interface.md)

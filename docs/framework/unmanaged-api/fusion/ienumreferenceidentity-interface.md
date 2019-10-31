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
ms.openlocfilehash: 1305b9ebe3cd87ba002ee87610ff309d015a44e6
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131745"
---
# <a name="ienumreferenceidentity-interface"></a>Интерфейс IEnumReferenceIdentity
Служит перечислителем для коллекции объектов `IReferenceIdentity`.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|`IEnumReferenceIdentity::Clone`|Возвращает указатель интерфейса на новый `IEnumReferenceIdentity`, содержащий те же элементы, что и этот `IEnumReferenceIdentity`.|  
|`IEnumReferenceIdentity::Next`|Возвращает указанное число объектов `IReferenceIdentity`, начиная с текущей позиции.|  
|`IEnumReferenceIdentity::Reset`|Перемещает указатель инструкции в начало этого `IEnumReferenceIdentity`.|  
|`IEnumReferenceIdentity::Skip`|Перемещает указатель инструкции вперед на указанное число элементов, начиная с текущей позиции.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** Изоляция. h  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейсы Fusion](fusion-interfaces.md)
- [Интерфейс IReferenceIdentity](ireferenceidentity-interface.md)

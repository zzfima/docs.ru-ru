---
title: Интерфейс IReferenceIdentity
ms.date: 03/30/2017
api_name:
- IReferenceIdentity
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IReferenceIdentity
helpviewer_keywords:
- IReferenceIdentity interface [.NET Framework fusion]
ms.assetid: 9180ac5a-7019-4716-9f83-8a91d157239a
topic_type:
- apiref
ms.openlocfilehash: 8f6a117d1e2fe76c271b0b014e6079370c8b4fe4
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127064"
---
# <a name="ireferenceidentity-interface"></a>Интерфейс IReferenceIdentity
Представляет ссылку на уникальную сигнатуру объекта кода.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|`IReferenceIdentity::Clone`|Получает указатель интерфейса на новый экземпляр `IReferenceIdentity`, идентичный этому `IReferenceIdentity`, за исключением изменения указанного атрибута.|  
|`IReferenceIdentity::EnumAttributes`|Возвращает указатель интерфейса на экземпляр `IEnumIDENTITY_ATTRIBUTE`, содержащий атрибуты, связанные с этим `IReferenceIdentity`.|  
|`IReferenceIdentity::GetAttribute`|Возвращает значение атрибута в указанном пространстве имен с указанным именем.|  
|`IReferenceIdentity::SetAttribute`|Задает для атрибута, имеющего указанное пространство имен и указанное имя, указанное значение.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** Изоляция. h  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейсы Fusion](fusion-interfaces.md)
- [Интерфейс IEnumIDENTITY_ATTRIBUTE](ienumidentity-attribute-interface.md)

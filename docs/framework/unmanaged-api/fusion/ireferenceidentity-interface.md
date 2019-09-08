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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2bb151d7c77104d8e24acefaac2e1f109b67f168
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796354"
---
# <a name="ireferenceidentity-interface"></a>Интерфейс IReferenceIdentity
Представляет ссылку на уникальную сигнатуру объекта кода.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|`IReferenceIdentity::Clone`|Возвращает указатель интерфейса на новый `IReferenceIdentity` экземпляр, идентичный этому `IReferenceIdentity`, за исключением изменения указанного атрибута.|  
|`IReferenceIdentity::EnumAttributes`|Возвращает указатель интерфейса на `IEnumIDENTITY_ATTRIBUTE` экземпляр, содержащий атрибуты, связанные с этим. `IReferenceIdentity`|  
|`IReferenceIdentity::GetAttribute`|Возвращает значение атрибута в указанном пространстве имен с указанным именем.|  
|`IReferenceIdentity::SetAttribute`|Задает для атрибута, имеющего указанное пространство имен и указанное имя, указанное значение.|  
  
## <a name="requirements"></a>Требования  
 **Платформ** См. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок.** Изоляция. h  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейсы Fusion](fusion-interfaces.md)
- [Интерфейс IEnumIDENTITY_ATTRIBUTE](ienumidentity-attribute-interface.md)

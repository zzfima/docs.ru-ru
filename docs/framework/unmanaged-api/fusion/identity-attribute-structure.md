---
title: Структура IDENTITY_ATTRIBUTE
ms.date: 03/30/2017
api_name:
- IDENTITY_ATTRIBUTE
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IDENTITY_ATTRIBUTE
helpviewer_keywords:
- IDENTITY_ATTRIBUTE structure [.NET Framework fusion]
ms.assetid: 1ee7c434-9681-4fa8-badd-652cb1a9742b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e0bcabb32d50b236d42a555c073b50ba3a234dde
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796487"
---
# <a name="identity_attribute-structure"></a>Структура IDENTITY_ATTRIBUTE
Содержит сведения об атрибутах метаданных для экземпляра [идефинитионидентити](idefinitionidentity-interface.md) .  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef struct _IDENTITY_ATTRIBUTE {  
    LPCWSTR  pszNamespace;  
    LPCWSTR  pszName;  
    LPCWSTR  pszValue;  
} IDENTITY_ATTRIBUTE;  
```  
  
## <a name="members"></a>Участники  
  
|Член|Описание|  
|------------|-----------------|  
|`pszNamespace`|Указатель на строку символов, завершающуюся нулем, которая содержит пространство имен, в котором находится атрибут.|  
|`pszName`|Указатель на строку символов, завершающуюся нулем, которая содержит имя атрибута.|  
|`pszValue`|Указатель на строку символов, завершающуюся нулем, которая содержит значение атрибута.|  
  
## <a name="remarks"></a>Примечания  
 `IDENTITY_ATTRIBUTE` Структура содержит три указателя на строки символов, заканчивающиеся нулем. Эти три строки описывают один атрибут.  
  
 Экземпляр `IDENTITY_ATTRIBUTE` структуры связан с экземпляром структуры [IDENTITY_ATTRIBUTE_BLOB](identity-attribute-blob-structure.md) . Структура содержит фактические строки, а соответствующая `IDENTITY_ATTRIBUTE_BLOB` структура перечисляет смещения для `IDENTITY_ATTRIBUTE` трех строк, перечисленных в структуре. `IDENTITY_ATTRIBUTE`  
  
## <a name="requirements"></a>Требования  
 **Платформ** См. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок.** Изоляция. h  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IDefinitionIdentity](idefinitionidentity-interface.md)
- [Структура IDENTITY_ATTRIBUTE_BLOB](identity-attribute-blob-structure.md)
- [Структуры Fusion](fusion-structures.md)

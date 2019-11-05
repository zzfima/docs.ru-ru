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
ms.openlocfilehash: 8b7edf1cc642228c4a79c855b51727264f31741c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73107985"
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
  
## <a name="members"></a>Члены  
  
|Член|Описание|  
|------------|-----------------|  
|`pszNamespace`|Указатель на строку символов, завершающуюся нулем, которая содержит пространство имен, в котором находится атрибут.|  
|`pszName`|Указатель на строку символов, завершающуюся нулем, которая содержит имя атрибута.|  
|`pszValue`|Указатель на строку символов, завершающуюся нулем, которая содержит значение атрибута.|  
  
## <a name="remarks"></a>Заметки  
 Структура `IDENTITY_ATTRIBUTE` содержит три указателя на строки символов, заканчивающиеся символом NULL. Эти три строки описывают один атрибут.  
  
 Экземпляр структуры `IDENTITY_ATTRIBUTE` связан с экземпляром структуры [IDENTITY_ATTRIBUTE_BLOB](identity-attribute-blob-structure.md) . Структура `IDENTITY_ATTRIBUTE` содержит фактические строки, а соответствующая структура `IDENTITY_ATTRIBUTE_BLOB` перечисляет смещения для трех строк, перечисленных в структуре `IDENTITY_ATTRIBUTE`.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** Изоляция. h  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IDefinitionIdentity](idefinitionidentity-interface.md)
- [Структура IDENTITY_ATTRIBUTE_BLOB](identity-attribute-blob-structure.md)
- [Структуры Fusion](fusion-structures.md)

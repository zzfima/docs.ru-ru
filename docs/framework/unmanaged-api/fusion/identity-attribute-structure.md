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
ms.openlocfilehash: de1646cdbc11369b43a821d8b762879d1df7ed2e
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67751538"
---
# <a name="identityattribute-structure"></a>Структура IDENTITY_ATTRIBUTE
Содержит сведения об атрибутах метаданных о [IDefinitionIdentity](../../../../docs/framework/unmanaged-api/fusion/idefinitionidentity-interface.md) экземпляра.  
  
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
|`pszNamespace`|Указатель на строку символов с завершающим нулем, содержащая пространство имен к которому принадлежит атрибут.|  
|`pszName`|Указатель на строку символов с завершающим нулем, которая содержит имя атрибута.|  
|`pszValue`|Указатель на строку символов с завершающим нулем, которая содержит значение атрибута.|  
  
## <a name="remarks"></a>Примечания  
 `IDENTITY_ATTRIBUTE` Структура содержит три указатели на строки символов с завершающим нулем. Эти три строки описывают один атрибут.  
  
 Экземпляр `IDENTITY_ATTRIBUTE` структура связан с экземпляром [IDENTITY_ATTRIBUTE_BLOB](../../../../docs/framework/unmanaged-api/fusion/identity-attribute-blob-structure.md) структуры. `IDENTITY_ATTRIBUTE` Структура содержит фактические строки и соответствующий `IDENTITY_ATTRIBUTE_BLOB` структура перечислены смещения до трех строк в `IDENTITY_ATTRIBUTE` структуры.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** Isolation.h  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IDefinitionIdentity](../../../../docs/framework/unmanaged-api/fusion/idefinitionidentity-interface.md)
- [Структура IDENTITY_ATTRIBUTE_BLOB](../../../../docs/framework/unmanaged-api/fusion/identity-attribute-blob-structure.md)
- [Структуры Fusion](../../../../docs/framework/unmanaged-api/fusion/fusion-structures.md)

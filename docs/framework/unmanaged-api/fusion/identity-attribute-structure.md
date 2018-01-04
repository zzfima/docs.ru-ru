---
title: "Структура IDENTITY_ATTRIBUTE"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IDENTITY_ATTRIBUTE
api_location: fusion.dll
api_type: COM
f1_keywords: IDENTITY_ATTRIBUTE
helpviewer_keywords: IDENTITY_ATTRIBUTE structure [.NET Framework fusion]
ms.assetid: 1ee7c434-9681-4fa8-badd-652cb1a9742b
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2c0d09bf4c24f977a490f946cbc35b2b3f53dfc3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="identityattribute-structure"></a>Структура IDENTITY_ATTRIBUTE
Содержит сведения об атрибутах метаданных о [IDefinitionIdentity](../../../../docs/framework/unmanaged-api/fusion/idefinitionidentity-interface.md) экземпляра.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
typedef struct _IDENTITY_ATTRIBUTE {  
    LPCWSTR  pszNamespace;  
    LPCWSTR  pszName;  
    LPCWSTR  pszValue;  
} IDENTITY_ATTRIBUTE;  
```  
  
## <a name="members"></a>Участники  
  
|Член|Описание:|  
|------------|-----------------|  
|`pszNamespace`|Указатель на завершающуюся значением null строка, содержащая пространство имен к которому принадлежит атрибут.|  
|`pszName`|Указатель на завершающуюся значением null строка, содержащая имя атрибута.|  
|`pszValue`|Указатель на завершающуюся значением null строка, содержащая значение атрибута.|  
  
## <a name="remarks"></a>Примечания  
 `IDENTITY_ATTRIBUTE` Структура содержит три указатели на строки символом null. Эти три строки описывают один атрибут.  
  
 Экземпляр `IDENTITY_ATTRIBUTE` структуры связан с экземпляром [IDENTITY_ATTRIBUTE_BLOB](../../../../docs/framework/unmanaged-api/fusion/identity-attribute-blob-structure.md) структуры. `IDENTITY_ATTRIBUTE` Структура содержит фактические строки и соответствующий `IDENTITY_ATTRIBUTE_BLOB` структуры перечислены смещения до трех строк в `IDENTITY_ATTRIBUTE` структуры.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** Isolation.h  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейс IDefinitionIdentity](../../../../docs/framework/unmanaged-api/fusion/idefinitionidentity-interface.md)  
 [Структура IDENTITY_ATTRIBUTE_BLOB](../../../../docs/framework/unmanaged-api/fusion/identity-attribute-blob-structure.md)  
 [Структуры Fusion](../../../../docs/framework/unmanaged-api/fusion/fusion-structures.md)

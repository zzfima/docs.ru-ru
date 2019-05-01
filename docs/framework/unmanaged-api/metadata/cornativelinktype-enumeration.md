---
title: Перечисление CorNativeLinkType
ms.date: 03/30/2017
api_name:
- CorNativeLinkType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorNativeLinkType
helpviewer_keywords:
- CorNativeLinkType enumeration [.NET Framework metadata]
ms.assetid: 4f86ff37-2dab-4e64-819a-76b3bfe828ff
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 66d650adb39a9c7dade0936ec671ae5a8b4aeecd
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62045478"
---
# <a name="cornativelinktype-enumeration"></a>Перечисление CorNativeLinkType
Предоставляет значения, указывающие тип, связанный в машинном коде.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
typedef enum   
{  
    nltNone       = 1,  
    nltAnsi       = 2,  
    nltUnicode    = 3,  
    nltAuto       = 4,  
    nltOle        = 5,  
    nltMaxValue   = 7  
} CorNativeLinkType;  
```  
  
## <a name="members"></a>Участники  
  
|Член|Описание|  
|------------|-----------------|  
|`nltNone`|Указывает, что не указан ни один из ключевых слов.|  
|`nltAnsi`|Указывает, что ключевое слово в формате ANSI.|  
|`nltUnicode`|Указывает, что указан Unicode-ключевое слово|  
|`nltAuto`|Указывает, что ключевое слово auto.|  
|`nltOle`|Указывает, что ключевое слово OLE.|  
|`nltMaxValue`|Не используется.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** Cor.h  
  
 **Библиотека:** Включена как ресурс в MsCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Перечисления метаданных](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)

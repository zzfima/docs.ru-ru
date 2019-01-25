---
title: Перечисление CorMethodSemanticsAttr
ms.date: 03/30/2017
api_name:
- CorMethodSemanticsAttr
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorMethodSemanticsAttr
helpviewer_keywords:
- CorMethodSemanticsAttr enumeration [.NET Framework metadata]
ms.assetid: ca2af325-eb9d-4a91-90e4-267e45b98611
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f888c39160e52e550d07f58b9c5bcd11fd625658
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54564085"
---
# <a name="cormethodsemanticsattr-enumeration"></a>Перечисление CorMethodSemanticsAttr
Содержит значения, описывающие связь между методом и соответствующим свойством или событием.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
typedef enum CorMethodSemanticsAttr {  
  
    msSetter    =   0x0001,  
    msGetter    =   0x0002,  
    msOther     =   0x0004,  
    msAddOn     =   0x0008,  
    msRemoveOn  =   0x0010,  
    msFire      =   0x0020,  
  
} CorMethodSemanticsAttr;  
```  
  
## <a name="members"></a>Участники  
  
|Член|Описание:|  
|------------|-----------------|  
|`msSetter`|Указывает, что метод вызывается `set` метод доступа для свойства.|  
|`msGetter`|Указывает, что метод вызывается `get` метод доступа для свойства.|  
|`msOther`|Указывает, что метод имеет отношение к свойство или событие, отличные от определенных здесь.|  
|`msAddOn`|Указывает, что этот метод добавляет методы обработчика для события.|  
|`msRemoveOn`|Указывает, что метод удаляет методы обработчика для события.|  
|`msFire`|Указывает, что метод вызывает событие.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorHdr.h  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также
- [Перечисления метаданных](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)

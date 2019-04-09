---
title: Перечисление CorSetENC
ms.date: 03/30/2017
api_name:
- CorSetENC
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorSetENC
helpviewer_keywords:
- CorSetENC enumeration [.NET Framework metadata]
ms.assetid: fe4150e8-071d-43fb-8e06-c3c616dbeed2
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1fd903cb4a9ce664b7a1c958a3fef0c639d6845d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59122321"
---
# <a name="corsetenc-enumeration"></a>Перечисление CorSetENC
Содержит значения, используемые для оказания влияния на поведение во время создания метаданных.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
typedef enum CorSetENC {  
  
    MDSetENCOn                  = 0x00000001,  
    MDSetENCOff                 = 0x00000002,  
  
    MDUpdateENC                 = 0x00000001,  
    MDUpdateFull                = 0x00000002,  
    MDUpdateExtension           = 0x00000003,  
    MDUpdateIncremental         = 0x00000004,  
    MDUpdateDelta               = 0x00000005,  
    MDUpdateMask                = 0x00000007  
  
} CorSetENC;  
```  
  
## <a name="members"></a>Участники  
  
|Член|Описание|  
|------------|-----------------|  
|`MDSetENCOn`|Является устаревшей.|  
|`MDSetENCOff`|Является устаревшей.|  
|`MDUpdateENC`|Указывает, что в то время как метаданные могут быть обновлены, невозможно переместить маркеры.|  
|`MDUpdateFull`|Указывает, что маркеры можно переместить во время обновления.|  
|`MDUpdateExtension`|Указывает, что обновления могут состоять только из добавлений. Маркеры не могут быть перемещены.|  
|`MDUpdateIncremental`|Указывает добавочной компиляции.|  
|`MDUpdateDelta`|Указывает, что только измененные метаданные должны сохраняться.|  
|`MDUpdateMask`|Включает в себя `MDUpdateENC`, `MDUpdateFull` и `MDUpdateIncremental`.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorHdr.h  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Перечисления метаданных](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)

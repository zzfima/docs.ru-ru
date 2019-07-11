---
title: Перечисление CorDebugMappingResult
ms.date: 03/30/2017
api_name:
- CorDebugMappingResult
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugMappingResult
helpviewer_keywords:
- CorDebugMappingResult enumeration [.NET Framework debugging]
ms.assetid: 701281dd-2936-45c8-a1f0-3bf7332b093b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c2042d0936359a85d203375c42be0d8a096f004e
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67739761"
---
# <a name="cordebugmappingresult-enumeration"></a>Перечисление CorDebugMappingResult
Предоставляет сведения о том, как было получено значение указателя инструкций.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef enum CorDebugMappingResult {  
    MAPPING_PROLOG              = 0x1,  
    MAPPING_EPILOG              = 0x2,  
    MAPPING_NO_INFO             = 0x4,  
    MAPPING_UNMAPPED_ADDRESS    = 0x8,  
    MAPPING_EXACT               = 0x10,  
    MAPPING_APPROXIMATE         = 0x20,  
} CorDebugMappingResult;  
```  
  
## <a name="members"></a>Участники  
  
|Член|Описание|  
|------------|-----------------|  
|`MAPPING_PROLOG`|Машинный код находится в прологе, поэтому значение IP-адреса равно 0.|  
|`MAPPING_EPILOG`|Машинный код находится в эпилоге, поэтому значение IP-адреса — адрес последней инструкции метода.|  
|`MAPPING_NO_INFO`|Нет сведений о сопоставлении для метода, поэтому значение IP-адреса — 0.|  
|`MAPPING_UNMAPPED_ADDRESS`|Несмотря на то, что есть сведения о сопоставлении для метода, текущий адрес не может быть сопоставлен код на промежуточном языке (MSIL). IP-адреса значение 0.|  
|`MAPPING_EXACT`|Метод сопоставляет ровно кода MSIL, либо была выполнена интерпретация кадра, поэтому значение IP-адреса является точным.|  
|`MAPPING_APPROXIMATE`|Метод успешно сопоставлен, но значение IP-адреса может быть приблизительным.|  
  
## <a name="remarks"></a>Примечания  
 Можно использовать [ICorDebugILFrame::GetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getip-method.md) метод для получения значения указателя инструкций.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Перечисления отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)

---
title: Перечисление CorDebugDecodeEventFlagsWindows
ms.date: 03/30/2017
api_name:
- CorDebugDecodeEventFlagsWindows
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: aa6cf962-30ae-4cfd-8895-826deeb46a54
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2d4e006a03db5b16de93dfd07ec7b964db4bfc1d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59207738"
---
# <a name="cordebugdecodeeventflagswindows-enumeration"></a>Перечисление CorDebugDecodeEventFlagsWindows
Предоставляет дополнительную информацию о событиях отладки на платформе Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
typedef enum CorDebugDecodeEventFlagsWindows {  
    IS_FIRST_CHANCE = 1,  
} CorDebugDecodeEventFlagsWindows;  
```  
  
## <a name="members"></a>Участники  
  
|Член|Описание|  
|------------|-----------------|  
|`IS_FIRST_CHANCE`|Указывает, что событие отладки является первичным исключением.|  
  
## <a name="remarks"></a>Примечания  
 [ICorDebugProcess6::DecodeEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-decodeevent-method.md) метод включает `dwFlags` параметра, предоставляющий дополнительные сведения о событии отладки, и значение которого зависит от целевой архитектуры. Перечисление `CorDebugDecodeEventFlagsWindows` можно использовать с событиями отладки на платформе Windows.  
  
> [!NOTE]
>  Это перечисление предназначено для использования только в сценариях отладки .NET Native.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>См. также

- [Перечисления отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)

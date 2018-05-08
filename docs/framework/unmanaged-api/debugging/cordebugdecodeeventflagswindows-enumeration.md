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
ms.openlocfilehash: fa8bbcf4d8e5aadee6a4250d23842187d6c2af09
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
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
 [ICorDebugProcess6::DecodeEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-decodeevent-method.md) метод включает `dwFlags` параметра, предоставляющий дополнительные сведения о событии отладки и, значение которого зависит от целевой архитектуры. Перечисление `CorDebugDecodeEventFlagsWindows` можно использовать с событиями отладки на платформе Windows.  
  
> [!NOTE]
>  Это перечисление предназначено для использования только в сценариях отладки .NET Native.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Перечисления отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)

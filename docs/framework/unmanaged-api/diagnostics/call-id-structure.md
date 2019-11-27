---
title: Структура CALL_ID
ms.date: 03/30/2017
api_name:
- CALL_ID
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- CALL_ID
helpviewer_keywords:
- CALL_ID structure [.NET Framework debugging]
ms.assetid: bfd46324-afec-4782-9c18-586d81fb4740
topic_type:
- apiref
ms.openlocfilehash: 8c606f67766334800444f39b115d90f65ecca13d
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448594"
---
# <a name="call_id-structure"></a>Структура CALL_ID
Предоставляет сведения отладчику о вызываемой функции. Дополнительные сведения см. в интерфейсе [INotifySink2](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md) .  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef struct tagCALL_ID  
{  
    LPCOLESTR       szMachine;  
    DWORD           dwPid;  
    USER_THREAD     *pUserThread;  
    STACK_ADDRESS   addrStackPointer;  
    LPCOLESTR       szEntryPoint;  
    LPCOLESTR       szDestinationMachine;  
} CALL_ID;  
```  
  
## <a name="members"></a>Члены  
  
|Член|Описание|  
|------------|-----------------|  
|`szMachine`|Идентифицирует компьютер, выполняющий вызов.|  
|`dwPid`|Идентифицирует процессор компьютера.|  
|`pUserThread`|Идентифицирует поток, который исполняет вызов.|  
|`addrStackPointer`|Задает адрес стека вызовов.|  
|`szEntryPoint`|Задает адрес вызова.|  
|`szDestinationMachine`|Определяет компьютер, который будет выполнять вызов.|  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** ProtocolNotify2. idl  
  
## <a name="see-also"></a>См. также:

- [Интерфейс INotifySink2](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md)
- [Структуры хранилища символов диагностики](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-structures.md)

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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2823c018ff22607052cb9a298f69dbd0c4fe2c23
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67769501"
---
# <a name="callid-structure"></a>Структура CALL_ID
Сведения о функции, которая вызывается отладчиком. См. в разделе [INotifySink2](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md) интерфейс Дополнительные сведения.  
  
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
  
## <a name="members"></a>Участники  
  
|Член|Описание|  
|------------|-----------------|  
|`szMachine`|Определяет, выполняет вызов машину.|  
|`dwPid`|Определяет процессор компьютера.|  
|`pUserThread`|Определяет поток, который выполняет вызов.|  
|`addrStackPointer`|Указывает адрес стека вызовов.|  
|`szEntryPoint`|Указывает адрес вызова.|  
|`szDestinationMachine`|Определяет, будет исполнен в машину.|  
  
## <a name="requirements"></a>Требования  
 **Заголовок.** ProtocolNotify2.idl  
  
## <a name="see-also"></a>См. также

- [Интерфейс INotifySink2](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md)
- [Структуры хранилища символов диагностики](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-structures.md)

---
title: Метод ICorDebugMDA::GetName
ms.date: 03/30/2017
api_name:
- ICorDebugMDA.GetName
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugMDA::GetName
helpviewer_keywords:
- ICorDebugMDA::GetName method [.NET Framework debugging]
- GetName method, ICorDebugMDA interface [.NET Framework debugging]
ms.assetid: 885bf5e8-00b7-4cd7-9d8d-e720d47918c4
topic_type:
- apiref
ms.openlocfilehash: 1b19ce5e9f795fd9ff4dd15e10256a150063a314
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73128046"
---
# <a name="icordebugmdagetname-method"></a>Метод ICorDebugMDA::GetName
Возвращает строку, содержащую имя помощника по отладке управляемого кода (MDA), представленного [ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetName (  
    [in] ULONG32   cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]  
        WCHAR      szName[]  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `cchName`  
 [in] Размер массива `szName`.  
  
 `pcchName`  
 заполняет Указатель на длину имени.  
  
 `szName`  
 заполняет Массив, в котором сохраняется имя.  
  
## <a name="remarks"></a>Заметки  
 Имена MDA являются уникальными значениями. Метод `GetName` является удобной альтернативой производительности для получения XML-потока и извлечения имени из потока на основе схемы.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md)
- [Диагностика ошибок посредством помощников по отладке управляемого кода](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)

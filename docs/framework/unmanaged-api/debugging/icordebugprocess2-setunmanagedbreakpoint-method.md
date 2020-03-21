---
title: Метод ICorDebugProcess2::SetUnmanagedBreakpoint
ms.date: 03/30/2017
api_name:
- ICorDebugProcess2.SetUnmanagedBreakpoint
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess2::SetUnmanagedBreakpoint
helpviewer_keywords:
- ICorDebugProcess2::SetUnmanagedBreakpoint method [.NET Framework debugging]
- SetUnmanagedBreakpoint method [.NET Framework debugging]
ms.assetid: 93829d15-d942-4e2d-b7a4-dfc9d7fb96be
topic_type:
- apiref
ms.openlocfilehash: fb8b8f3e29c141e91587a4d0cdc81cdabccdbc9e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178649"
---
# <a name="icordebugprocess2setunmanagedbreakpoint-method"></a>Метод ICorDebugProcess2::SetUnmanagedBreakpoint
Устанавливает неуправляемую точку разрыва в указанном смещении родного изображения.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT SetUnmanagedBreakpoint (  
    [in]  CORDB_ADDRESS    address,  
    [in]  ULONG32          bufsize,  
    [out, size_is(bufsize), length_is(*bufLen)]
        BYTE               buffer[],  
    [out] ULONG32          *bufLen  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `address`  
 (в) Объект, `CORDB_ADDRESS` опознававательный смещение родного изображения.  
  
 `bufsize`  
 (в) Размер массива, `buffer` в байтах.  
  
 `buffer`  
 (ваут) Массив, содержащий opcode, который заменяется точкой разрыва.  
  
 `bufLen`  
 (ваут) Указатель на количество байтов, `buffer` возвращенных в массиве.  
  
## <a name="remarks"></a>Remarks  
 Если смещение изображения нативного изображения находится в пределах общего времени выполнения языка (CLR), точка разрыва будет проигнорирована. Это позволяет CLR избежать отправки внеполосной точки разрыва, когда точка разрыва устанавливается отладчиком.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]

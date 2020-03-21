---
title: Метод ICorDebugProcess::ReadMemory
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.ReadMemory
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::ReadMemory
helpviewer_keywords:
- ReadMemory method [.NET Framework debugging]
- ICorDebugProcess::ReadMemory method [.NET Framework debugging]
ms.assetid: 28e4b2f6-9589-445c-be24-24a3306795e7
topic_type:
- apiref
ms.openlocfilehash: 383e3f8990a1f355c94ff5e9f9daa69bdbdd97bb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178652"
---
# <a name="icordebugprocessreadmemory-method"></a>Метод ICorDebugProcess::ReadMemory
Читает указанную область памяти для этого процесса.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT ReadMemory(  
    [in]  CORDB_ADDRESS address,
    [in]  DWORD size,  
    [out, size_is(size), length_is(size)] BYTE buffer[],  
    [out] SIZE_T *read);  
```  
  
## <a name="parameters"></a>Параметры  
 `address`  
 (в) Значение, `CORDB_ADDRESS` опоглавивававаев базовое адрес прочитанной памяти.  
  
 `size`  
 (в) Количество байтов, которые можно считывать по памяти.  
  
 `buffer`  
 (ваут) Буфер, который получает содержимое памяти.  
  
 `read`  
 (ваут) Указатель на количество байтов, переведенных в указанный буфер.  
  
## <a name="remarks"></a>Remarks  
 Метод `ReadMemory` в первую очередь предназначен для использования межопомнейной отладки для проверки областей памяти, которые используются неуправляемой частью отладки. Этот метод также может быть использован для чтения промежуточных языков Microsoft (MSIL) код и родной JIT-компилированный код.  
  
 Любые управляемые точки разрыва будут удалены `buffer` из данных, которые возвращаются в параметре. Никакие корректировки не будут внесены для родных брейк-пойнтов, установленных [ICorDebugProcess2::SetUnmanagedBreakpoint.](icordebugprocess2-setunmanagedbreakpoint-method.md)  
  
 Кэширование памяти процесса не выполняется.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]

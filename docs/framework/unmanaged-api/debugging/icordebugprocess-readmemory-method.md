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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a0063e33a6a7861815ebb9d9eb3dabec64dd4b9d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugprocessreadmemory-method"></a>Метод ICorDebugProcess::ReadMemory
Считывает заданную область памяти для этого процесса.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT ReadMemory(  
    [in]  CORDB_ADDRESS address,   
    [in]  DWORD size,  
    [out, size_is(size), length_is(size)] BYTE buffer[],  
    [out] SIZE_T *read);  
```  
  
#### <a name="parameters"></a>Параметры  
 `address`  
 [in] Объект `CORDB_ADDRESS` значение, указывающее базовый адрес в памяти для чтения.  
  
 `size`  
 [in] Число байтов, считываемых из памяти.  
  
 `buffer`  
 [out] Буфер, получающий содержимое памяти.  
  
 `read`  
 [out] Указатель на число байтов, переданных в указанный буфер.  
  
## <a name="remarks"></a>Примечания  
 `ReadMemory` Метод в основном предназначен для использования при отладке взаимодействия для проверки областей памяти, используемых неуправляемой частью отлаживаемого кода. Этот метод может также использоваться для чтения код на промежуточном языке (MSIL) и собственного JIT-скомпилированный код.  
  
 Будут удалены все точки останова управляемого кода из данных, возвращаемых в `buffer` параметра. Каких-либо корректировок станет собственного точек останова, установленных [ICorDebugProcess2::SetUnmanagedBreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setunmanagedbreakpoint-method.md).  
  
 Кэширование памяти процесса не выполняется.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]

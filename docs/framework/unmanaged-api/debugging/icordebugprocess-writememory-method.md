---
title: Метод ICorDebugProcess::WriteMemory
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.WriteMemory
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::WriteMemory
helpviewer_keywords:
- ICorDebugProcess::WriteMemory method [.NET Framework debugging]
- WriteMemory method [.NET Framework debugging]
ms.assetid: d5c07d86-045d-4391-893b-0bcd2959f90e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4599bf310a0b819bc662b90a5a86e87ac27c37b1
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67737016"
---
# <a name="icordebugprocesswritememory-method"></a>Метод ICorDebugProcess::WriteMemory
Записывает данные в область памяти, в этом процессе.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT WriteMemory(  
    [in]  CORDB_ADDRESS address,  
    [in]  DWORD size,  
    [in, size_is(size)] BYTE buffer[],  
    [out] SIZE_T *written);  
```  
  
## <a name="parameters"></a>Параметры  
 `address`  
 [in] Объект `CORDB_ADDRESS` записывается значение, базовый адрес области памяти для данных. Прежде чем происходит передача данных, система проверяет, область памяти указанного размера, начиная с базового адреса, доступного для записи. Если он недоступен, происходит сбой метода.  
  
 `size`  
 [in] Число байтов для записи в область памяти.  
  
 `buffer`  
 [in] Буфер, содержащий записываемые данные.  
  
 `written`  
 [out] Указатель на переменную, которая получает число байтов, записанных в область памяти, в этом процессе. Если `written` имеет значение NULL, этот параметр учитывается.  
  
## <a name="remarks"></a>Примечания  
 Данные автоматически записываются за любыми точками останова. В платформе .NET Framework версии 2.0 машинные отладчики не следует использовать этот метод для вставки точки останова в потоке инструкций. Используйте [ICorDebugProcess2::SetUnmanagedBreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setunmanagedbreakpoint-method.md) вместо этого.  
  
 `WriteMemory` Метод должен использоваться только за пределами управляемого кода. Этот метод может привести к повреждению среды выполнения при неправильном.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]

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
ms.openlocfilehash: eaf5b9980d55b0efb473b4631a8c052b013d0796
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137259"
---
# <a name="icordebugprocesswritememory-method"></a>Метод ICorDebugProcess::WriteMemory
Записывает данные в область памяти в этом процессе.  
  
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
 окне `CORDB_ADDRESS` значение, являющееся базовым адресом области памяти, в которую записываются данные. Перед передачей данных система проверяет, что область памяти указанного размера, начиная с базового адреса, доступна для записи. Если он недоступен, метод завершается ошибкой.  
  
 `size`  
 окне Число байтов, записываемых в область памяти.  
  
 `buffer`  
 окне Буфер, содержащий записываемые данные.  
  
 `written`  
 заполняет Указатель на переменную, которая получает число байтов, записанных в область памяти в этом процессе. Если `written` имеет значение NULL, этот параметр игнорируется.  
  
## <a name="remarks"></a>Заметки  
 Данные автоматически записываются за любые точки останова. В .NET Framework версии 2,0 отладчики машинного кода не должны использовать этот метод для вставки точек останова в поток инструкций. Вместо этого используйте [ICorDebugProcess2:: сетунманажедбреакпоинт](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setunmanagedbreakpoint-method.md) .  
  
 Метод `WriteMemory` следует использовать только за пределами управляемого кода. Этот метод может повредить среду выполнения при неправильном использовании.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]

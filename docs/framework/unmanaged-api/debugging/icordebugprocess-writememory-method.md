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
ms.openlocfilehash: 6da4c282c7f969a406a657d1e30dd6120a32b4e3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33420912"
---
# <a name="icordebugprocesswritememory-method"></a>Метод ICorDebugProcess::WriteMemory
Записывает данные в область памяти в данном процессе.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT WriteMemory(  
    [in]  CORDB_ADDRESS address,  
    [in]  DWORD size,  
    [in, size_is(size)] BYTE buffer[],  
    [out] SIZE_T *written);  
```  
  
#### <a name="parameters"></a>Параметры  
 `address`  
 [in] Объект `CORDB_ADDRESS` записывается значение, базовый адрес области памяти для данных. Прежде чем произойдет передача данных, система проверяет, область памяти указанного размера, начиная с базового адреса, доступен для записи. Если он недоступен, произойдет ошибка.  
  
 `size`  
 [in] Число байтов для записи в область памяти.  
  
 `buffer`  
 [in] Буфер, содержащий записываемые данные.  
  
 `written`  
 [out] Указатель на переменную, которая получает число байтов, записанных в область памяти, в этом процессе. Если `written` имеет значение NULL, этот параметр учитывается.  
  
## <a name="remarks"></a>Примечания  
 Данные автоматически записываются за любыми точками останова. В платформе .NET Framework версии 2.0 машинные отладчики не следует использовать этот метод для вставки точки останова в поток инструкций. Используйте [ICorDebugProcess2::SetUnmanagedBreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setunmanagedbreakpoint-method.md) вместо него.  
  
 `WriteMemory` Метод должен использоваться только за пределами управляемого кода. Этот метод может привести к повреждению среды выполнения при неправильном.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]

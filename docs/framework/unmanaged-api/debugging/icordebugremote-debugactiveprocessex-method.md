---
title: Метод ICorDebugRemote::DebugActiveProcessEx
ms.date: 03/30/2017
api_name:
- ICorDebugRemote.DebugActiveProcessEx
api_location:
- CorDebug.dll
api_type:
- COM
f1_keywords:
- ICorDebugRemoteTarget::DebugActiveProcessEx
helpviewer_keywords:
- ICorDebugRemote::DebugActiveProcessEx method [.NET Framework debugging]
- DebugActiveProcessEx method, ICorDebugRemote interface [.NET Framework debugging]
ms.assetid: b0df5c5d-9a2e-47bf-894c-6f8a9fe24a1f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 13371d15c8b29f9ef93cc4af87acf85029404644
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67744764"
---
# <a name="icordebugremotedebugactiveprocessex-method"></a>Метод ICorDebugRemote::DebugActiveProcessEx
Запускает процесс на удаленном компьютере в режиме отладки.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT DebugActiveProcessEx (  
    [in]  ICorDebugRemoteTarget *   pRemoteTarget,  
    [in]  DWORD                     dwProcessId,  
    [in]  BOOL                      fWin32Attach,  
    [out] ICorDebugProcess **       ppProcess  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `pRemoteTarget`  
 [in] Указатель на [интерфейс ICorDebugRemoteTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-interface.md). Этот параметр используется для определения компьютера, на котором выполняется процесс.  
  
 `id`  
 [in] Идентификатор процесса, к которому отладчик должен быть связан.  
  
 `win32Attach`  
 [in] `true` Если отладчик должен вести себя как отладчик Win32 для процесса и отправки неуправляемых обратных вызовов; в противном случае `false`.  
  
 `ppProcess`  
 [out] Указатель на адрес объекта «ICorDebugProcess», представляющий процесс, к которому присоединен отладчик.  
  
## <a name="return-value"></a>Возвращаемое значение  
 S_OK  
 Успешно подключен к процессу на удаленном компьютере.  
  
 E_FAIL (или другие коды возврата E_)  
 Не удалось присоединиться к процессу на удаленном компьютере.  
  
## <a name="remarks"></a>Примечания  
 Отладка в смешанном режиме не поддерживается в Silverlight.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:** 4.5, 4, 3.5 С ПАКЕТОМ ОБНОВЛЕНИЯ 1  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorDebugRemote](../../../../docs/framework/unmanaged-api/debugging/icordebugremote-interface.md)
- [Интерфейс ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)

- [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

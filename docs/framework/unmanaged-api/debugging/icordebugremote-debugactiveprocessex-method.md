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
ms.openlocfilehash: b78bff2994cefc6c35a4bd59133338392c3a1b24
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791972"
---
# <a name="icordebugremotedebugactiveprocessex-method"></a>Метод ICorDebugRemote::DebugActiveProcessEx
Запускает процесс на удаленном компьютере в отладчике.  
  
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
 окне Указатель на [интерфейс ICorDebugRemoteTarget](icordebugremotetarget-interface.md). Этот параметр используется для определения компьютера, на котором выполняется процесс.  
  
 `id`  
 окне Идентификатор процесса, к которому должен быть присоединен отладчик.  
  
 `win32Attach`  
 [in] `true`, если отладчик должен вести себя в качестве отладчика Win32 для процесса и передать неуправляемые обратные вызовы; в противном случае `false`.  
  
 `ppProcess`  
 заполняет Указатель на адрес объекта "ICorDebugProcess", который представляет процесс, к которому присоединен отладчик.  
  
## <a name="return-value"></a>Возвращаемое значение  
 S_OK  
 Успешно присоединен к процессу на удаленном компьютере.  
  
 E_FAIL (или другие коды возврата E_)  
 Не удалось присоединиться к процессу на удаленном компьютере.  
  
## <a name="remarks"></a>Заметки  
 Отладка в смешанном режиме не поддерживается в Silverlight.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:** 4,5, 4, 3,5 SP1  
  
## <a name="see-also"></a>См. также:

- [Интерфейс ICorDebugRemote](icordebugremote-interface.md)
- [Интерфейс ICorDebug](icordebug-interface.md)

- [Интерфейсы отладки](debugging-interfaces.md)

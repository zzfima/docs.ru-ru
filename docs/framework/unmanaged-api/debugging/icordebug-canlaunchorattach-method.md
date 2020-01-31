---
title: Метод ICorDebug::CanLaunchOrAttach
ms.date: 03/30/2017
api_name:
- ICorDebug.CanLaunchOrAttach
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebug::CanLaunchOrAttach
helpviewer_keywords:
- ICorDebug::CanLaunchOrAttach method [.NET Framework debugging]
- CanLaunchOrAttach method [.NET Framework debugging]
ms.assetid: ca7723db-7c07-4cdd-bd92-fba34928b623
topic_type:
- apiref
ms.openlocfilehash: 28b9fb5a25981e5e37a5f1bbb797baeac45e0028
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793575"
---
# <a name="icordebugcanlaunchorattach-method"></a>Метод ICorDebug::CanLaunchOrAttach
Возвращает значение HRESULT, указывающее, возможен ли запуск нового процесса или присоединение к указанному существующему процессу в контексте текущего компьютера и конфигурации среды выполнения.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT CanLaunchOrAttach (  
    [in] DWORD      dwProcessId,  
    [in] BOOL       win32DebuggingEnabled  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `dwProcessId`  
 окне Идентификатор существующего процесса.  
  
 `win32DebuggingEnabled`  
 окне Передайте `true`, если планируется запуск с отладкой Win32, или для подключения с включенной отладкой Win32. в противном случае передайте `false`.  
  
## <a name="return-value"></a>Возвращаемое значение  
 S_OK, если службы отладки определяют, что можно запустить новый процесс или присоединиться к заданному процессу, учитывая сведения о текущем компьютере и конфигурации среды выполнения. Возможные значения HRESULT:  
  
- S_OK  
  
- CORDBG_E_DEBUGGING_NOT_POSSIBLE  
  
- CORDBG_E_KERNEL_DEBUGGER_PRESENT  
  
- CORDBG_E_KERNEL_DEBUGGER_ENABLED  
  
## <a name="remarks"></a>Заметки  
 Этот метод является исключительно информационным. Интерфейс не будет останавливаться при запуске или присоединении к процессу независимо от значения, возвращаемого `CanLaunchOrAttach`.  
  
 Если вы планируете запустить отладчик с включенной отладкой Win32 или присоединиться с включенной отладкой Win32, передайте `true` для `win32DebuggingEnabled`. Значение HRESULT, возвращаемое `CanLaunchOrAttach`, может отличаться при использовании этого параметра.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Интерфейс ICorDebug](icordebug-interface.md)

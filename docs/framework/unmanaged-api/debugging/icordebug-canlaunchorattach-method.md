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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b768c8f7880a2317d1b72878657158e839b731f3
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54569733"
---
# <a name="icordebugcanlaunchorattach-method"></a>Метод ICorDebug::CanLaunchOrAttach
Возвращает значение HRESULT, указывающее, возможна ли запуск нового процесса или вложение указанным существующий процесс в контексте текущей конфигурации компьютера и среды выполнения.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT CanLaunchOrAttach (  
    [in] DWORD      dwProcessId,  
    [in] BOOL       win32DebuggingEnabled  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `dwProcessId`  
 [in] Идентификатор существующего процесса.  
  
 `win32DebuggingEnabled`  
 [in] Передайте `true` Если вы планируете запустить в режиме отладки Win32 или для присоединения с помощью Win32 отладка включена; в противном случае передайте `false`.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Значение S_OK, если службы отладки выяснилось, что запуск нового процесса или вложение в данный процесс можно, учитывая сведения о текущей конфигурации компьютера и среды выполнения. Ниже приведены возможные значения HRESULT.  
  
-   S_OK  
  
-   CORDBG_E_DEBUGGING_NOT_POSSIBLE  
  
-   CORDBG_E_KERNEL_DEBUGGER_PRESENT  
  
-   CORDBG_E_KERNEL_DEBUGGER_ENABLED  
  
## <a name="remarks"></a>Примечания  
 Этот метод носит исключительно информационный характер. Интерфейс не помешает вам запуск или присоединение к процессу, независимо от значения, возвращенные `CanLaunchOrAttach`.  
  
 Если вы планируете запустить в режиме отладки Win32 или присоединить с включенной отладкой Win32, передайте `true` для `win32DebuggingEnabled`. Значение HRESULT, возвращаемые `CanLaunchOrAttach` могут отличаться, если вы используете этот параметр.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также
- [Интерфейс ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)

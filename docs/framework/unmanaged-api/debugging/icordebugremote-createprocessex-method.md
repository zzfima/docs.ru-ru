---
title: Метод ICorDebugRemote::CreateProcessEx
ms.date: 03/30/2017
api_name:
- ICorDebugRemote.CreateProcessEx
api_location:
- CorDebug.dll
api_type:
- COM
f1_keywords:
- ICorDebugRemoteTarget::CreateProcessEx
helpviewer_keywords:
- CreateProcessEx method, ICorDebugRemote interface [.NET Framework debugging]
- ICorDebugRemote::CreateProcessEx method [.NET Framework debugging]
ms.assetid: 41af93c7-e448-4251-8d4d-413d38c635f2
topic_type:
- apiref
ms.openlocfilehash: cfec84483d387630623f77c176c668171303dd0f
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791980"
---
# <a name="icordebugremotecreateprocessex-method"></a>Метод ICorDebugRemote::CreateProcessEx
Запускает процесс на удаленном компьютере в отладчике.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT CreateProcessEx (  
    [in]  ICorDebugRemoteTarget*      pRemoteTarget,  
    [in]  LPCWSTR                     lpApplicationName,  
    [in]  LPWSTR                      lpCommandLine,  
    [in]  LPSECURITY_ATTRIBUTES       lpProcessAttributes,  
    [in]  LPSECURITY_ATTRIBUTES       lpThreadAttributes,  
    [in]  BOOL                        bInheritHandles,  
    [in]  DWORD                       dwCreationFlags,  
    [in]  PVOID                       lpEnvironment,  
    [in]  LPCWSTR                     lpCurrentDirectory,  
    [in]  LPSTARTUPINFOW              lpStartupInfo,  
    [in]  LPPROCESS_INFORMATION       lpProcessInformation,  
    [in]  CorDebugCreateProcessFlags  debuggingFlags,  
    [out] ICorDebugProcess**          ppProcess  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `pRemoteTarget`  
 окне Указатель на [интерфейс ICorDebugRemoteTarget](icordebugremotetarget-interface.md). Используется для определения удаленного компьютера, на котором будет запущен процесс.  
  
 `lpApplicationName`  
 окне Указатель на строку, завершающуюся нулем, которая указывает модуль, выполняемый запущенным процессом. Модуль выполняется в контексте безопасности вызывающего процесса.  
  
 `lpCommandLine`  
 окне Указатель на строку, завершающуюся нулем, которая указывает командную строку, выполняемую запущенным процессом.  
  
 `lpProcessAttributes`  
 окне Не используется для удаленной отладки.  
  
 `lpThreadAttributes`  
 окне Не используется для удаленной отладки.  
  
 `bInheritHandles`  
 окне Не используется для удаленной отладки.  
  
 `dwCreationFlags`  
 окне Не используется для удаленной отладки.  
  
 `lpEnvironment`  
 окне Указатель на блок среды для нового процесса.  
  
 `lpCurrentDirectory`  
 окне Указатель на строку, завершающуюся нулем, которая указывает полный путь к текущему каталогу для процесса. Если этот параметр имеет значение null, то новый процесс будет иметь тот же текущий диск и каталог, что и вызывающий процесс.  
  
 `lpStartupInfo`  
 окне Не используется для удаленной отладки.  
  
 `lpProcessInformation`  
 окне Не используется для удаленной отладки.  
  
 `debuggingFlags`  
 окне Не используется для удаленной отладки.  
  
 `ppProcess`  
 заполняет Указатель на адрес объекта "ICorDebugProcess Interface", который представляет процесс.  
  
## <a name="return-value"></a>Возвращаемое значение  
 S_OK  
 Процесс успешно запущен на удаленном компьютере и для отладки возвращен "Интерфейс ICorDebugProcess".  
  
 E_FAIL (или другие коды возврата E_)  
 Не удалось запустить процесс на удаленном компьютере и вернуть для отладки "Интерфейс ICorDebugProcess".  
  
## <a name="remarks"></a>Заметки  
 Отладка в смешанном режиме не поддерживается в Silverlight.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug. idl  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:** 4,5, 4, 3,5 SP1  
  
## <a name="see-also"></a>См. также:

- [Интерфейс ICorDebugRemote](icordebugremote-interface.md)
- [Интерфейс ICorDebug](icordebug-interface.md)

- [Интерфейсы отладки](debugging-interfaces.md)

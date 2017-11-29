---
title: "Метод ICorDebugRemote::CreateProcessEx"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugRemote.CreateProcessEx
api_location: CorDebug.dll
api_type: COM
f1_keywords: ICorDebugRemoteTarget::CreateProcessEx
helpviewer_keywords:
- CreateProcessEx method, ICorDebugRemote interface [.NET Framework debugging]
- ICorDebugRemote::CreateProcessEx method [.NET Framework debugging]
ms.assetid: 41af93c7-e448-4251-8d4d-413d38c635f2
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 00709ffe4695ea0b56982cb60df15c2991b49d4e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugremotecreateprocessex-method"></a>Метод ICorDebugRemote::CreateProcessEx
Запускает процесс на удаленном компьютере в отладчике.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
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
  
#### <a name="parameters"></a>Параметры  
 `pRemoteTarget`  
 [in] Указатель на [интерфейс ICorDebugRemoteTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-interface.md). Используется для определения удаленного компьютера, на котором будет запускаться процесс.  
  
 `lpApplicationName`  
 [in] Указатель на строку символом null, указывающее модуль должен быть исполнен запущенного процесса. Модуль выполняется в контексте безопасности вызывающего процесса.  
  
 `lpCommandLine`  
 [in] Указатель символом null строку, которая определяет командную строку для выполнения запущенного процесса.  
  
 `lpProcessAttributes`  
 [in] Не используется для удаленной отладки.  
  
 `lpThreadAttributes`  
 [in] Не используется для удаленной отладки.  
  
 `bInheritHandles`  
 [in] Не используется для удаленной отладки.  
  
 `dwCreationFlags`  
 [in] Не используется для удаленной отладки.  
  
 `lpEnvironment`  
 [in] Указатель на блок среды для нового процесса.  
  
 `lpCurrentDirectory`  
 [in] Указатель на завершающуюся значением null строка, указывающая полный путь к текущему каталогу для процесса. Если этот параметр имеет значение null, новый процесс будет диск и каталог как вызывающий процесс.  
  
 `lpStartupInfo`  
 [in] Не используется для удаленной отладки.  
  
 `lpProcessInformation`  
 [in] Не используется для удаленной отладки.  
  
 `debuggingFlags`  
 [in] Не используется для удаленной отладки.  
  
 `ppProcess`  
 [out] Указатель на адрес объекта «Интерфейс ICorDebugProcess», который представляет процесс.  
  
## <a name="return-value"></a>Возвращаемое значение  
 S_OK  
 Успешный запуск процесса на удаленном компьютере и возвращаемый «ICorDebugProcess интерфейс» для отладки.  
  
 E_FAIL (или другие коды возврата E_)  
 Не удалось запустить процесс на удаленном компьютере и возврата «Интерфейс ICorDebugProcess» отладки.  
  
## <a name="remarks"></a>Примечания  
 Отладка в смешанном режиме не поддерживается в Silverlight.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:** 4.5, 4, 3.5 с пакетом обновления 1  
  
## <a name="see-also"></a>См. также  
 [Интерфейс ICorDebugRemote](../../../../docs/framework/unmanaged-api/debugging/icordebugremote-interface.md)  
 [ICorDebug-интерфейс](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)  
    
 [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

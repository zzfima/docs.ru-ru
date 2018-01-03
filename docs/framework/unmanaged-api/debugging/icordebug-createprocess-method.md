---
title: "Метод ICorDebug::CreateProcess"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebug.CreateProcess
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebug::CreateProcess
helpviewer_keywords:
- ICorDebug::CreateProcess method [.NET Framework debugging]
- CreateProcess method, ICorDebugProcess interface [.NET Framework debugging]
ms.assetid: b6128694-11ed-46e7-bd4e-49ea1914c46a
topic_type: apiref
caps.latest.revision: "21"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 16e45f3bad92914ce8c7fb0044534789a7a28b2e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugcreateprocess-method"></a>Метод ICorDebug::CreateProcess
Запускает процесс и основной поток под контролем отладчика.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT CreateProcess (  
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
    [out] ICorDebugProcess            **ppProcess  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `lpApplicationName`  
 [in] Указатель на строку символом null, указывающее модуль должен быть исполнен запущенного процесса. Модуль выполняется в контексте безопасности вызывающего процесса.  
  
 `lpCommandLine`  
 [in] Указатель символом null строку, которая определяет командную строку для выполнения запущенного процесса. Имя приложения (например, «SomeApp.exe») должны быть первыми аргументами.  
  
 `lpProcessAttributes`  
 [in] Указатель на объект Win32 `SECURITY_ATTRIBUTES` структура, которая задает дескриптор безопасности для процесса. Если `lpProcessAttributes` имеет значение null, процесс получает дескриптор безопасности по умолчанию.  
  
 `lpThreadAttributes`  
 [in] Указатель на объект Win32 `SECURITY_ATTRIBUTES` структура, которая задает дескриптор безопасности для основного потока процесса. Если `lpThreadAttributes` имеет значение null, поток получает дескриптор безопасности по умолчанию.  
  
 `bInheritHandles`  
 [in] Значение `true` для указания, что каждого наследуемые дескриптора в вызывающий процесс наследуется запущенного процесса, или `false` для указания, что маркеры не наследуются. Унаследованные дескрипторы имеют те же права значение и доступа, что и исходные дескрипторы.  
  
 `dwCreationFlags`  
 [in] Побитовое сочетание [флаги создания проекта Win32](http://go.microsoft.com/fwlink/?linkid=69981) управляют класс приоритета и поведение запущенного процесса.  
  
 `lpEnvironment`  
 [in] Указатель на блок среды для нового процесса.  
  
 `lpCurrentDirectory`  
 [in] Указатель на завершающуюся значением null строка, указывающая полный путь к текущему каталогу для процесса. Если этот параметр имеет значение null, новый процесс будет диск и каталог как вызывающий процесс.  
  
 `lpStartupInfo`  
 [in] Указатель на объект Win32 `STARTUPINFOW` структуру, которая определяет окно станции, рабочий стол, стандартные дескрипторы и внешний вид главного окна для запущенного процесса.  
  
 `lpProcessInformation`  
 [in] Указатель на объект Win32 `PROCESS_INFORMATION` структура, которая задает идентификационные сведения о процессе, который будет запущен.  
  
 `debuggingFlags`  
 [in] Значение перечисления CorDebugCreateProcessFlags, которое указывает параметры отладки.  
  
 `ppProcess`  
 [out] Указатель на адрес объекта ICorDebugProcess, который представляет процесс.  
  
## <a name="remarks"></a>Примечания  
 Параметры этого метода — это отличается от Win32 `CreateProcess` метод.  
  
 Чтобы неуправляемой отладки в смешанном режиме, установите `dwCreationFlags` для DEBUG_PROCESS &#124; DEBUG_ONLY_THIS_PROCESS. Если вы хотите использовать только управляемую отладку, не задавайте эти флаги.  
  
 Если отладчик и процесс отладки (вложенный процесс) совместно использовать единую консоль, и при отладке взаимодействия, то возможна вложенный процесс может заблокировать консоль и остановить событие отладки. Затем отладчик заблокирует любые попытки использовать консоль. Чтобы избежать этой проблемы, установите флаг CREATE_NEW_CONSOLE `dwCreationFlags` параметра.  
  
 Отладка взаимодействия не поддерживается на платформах Win9x и не x86, например основе AMD64 и IA-64-разрядных платформах.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейс ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)

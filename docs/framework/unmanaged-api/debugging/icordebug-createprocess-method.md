---
title: Метод ICorDebug::CreateProcess
ms.date: 03/30/2017
api_name:
- ICorDebug.CreateProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebug::CreateProcess
helpviewer_keywords:
- ICorDebug::CreateProcess method [.NET Framework debugging]
- CreateProcess method, ICorDebugProcess interface [.NET Framework debugging]
ms.assetid: b6128694-11ed-46e7-bd4e-49ea1914c46a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 795392bc50d4b7c5eeb82b98230a52156f273f15
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59187373"
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
  
## <a name="parameters"></a>Параметры  
 `lpApplicationName`  
 [in] Указатель на заканчивающуюся нулем строку, которая задает имя этого модуля, который будет выполнен задачей запуск процесса. Модуль выполняется в контексте безопасности вызывающего процесса.  
  
 `lpCommandLine`  
 [in] Указатель на заканчивающуюся нулем строку, который определяет командную строку, который будет выполнен задачей запуск процесса. Имя приложения (например, «SomeApp.exe») должен быть первым аргументом.  
  
 `lpProcessAttributes`  
 [in] Указатель на Win32 `SECURITY_ATTRIBUTES` структуру, которая определяет дескриптор безопасности для процесса. Если `lpProcessAttributes` имеет значение null, процесс получает дескриптор безопасности по умолчанию.  
  
 `lpThreadAttributes`  
 [in] Указатель на Win32 `SECURITY_ATTRIBUTES` структура, которая задает дескриптор безопасности для основного потока этого процесса. Если `lpThreadAttributes` имеет значение null, поток получает дескриптор безопасности по умолчанию.  
  
 `bInheritHandles`  
 [in] Значение `true` для указания, что запущенный процесс, наследуют каждого наследуемого дескриптора в вызывающий процесс или `false` для указания, что маркеры не наследуются. Унаследованные дескрипторы имеют те же права значение и доступа, что и исходные дескрипторы.  
  
 `dwCreationFlags`  
 [in] Побитовое сочетание [флаги создания Win32](https://go.microsoft.com/fwlink/?linkid=69981) управления с приоритетом и поведение запуск процесса.  
  
 `lpEnvironment`  
 [in] Указатель на блок среды для нового процесса.  
  
 `lpCurrentDirectory`  
 [in] Указатель на заканчивающуюся нулем строку, которая указывает полный путь к текущему каталогу процесса. Если этот параметр имеет значение null, новый процесс будет иметь диск и каталог как вызывающий процесс.  
  
 `lpStartupInfo`  
 [in] Указатель на Win32 `STARTUPINFOW` структура, задающая оконной станции, рабочий стол, стандартные дескрипторы и внешний вид главного окна для запуск процесса.  
  
 `lpProcessInformation`  
 [in] Указатель на Win32 `PROCESS_INFORMATION` структура, задающая идентификационную информацию о для запуска процесса.  
  
 `debuggingFlags`  
 [in] Значение перечисления CorDebugCreateProcessFlags, которое указывает параметры отладки.  
  
 `ppProcess`  
 [out] Указатель на адрес объекта ICorDebugProcess, представляющий процесс.  
  
## <a name="remarks"></a>Примечания  
 Параметры этого метода являются те же Win32 `CreateProcess` метод.  
  
 Чтобы включить неуправляемой отладки в смешанном режиме, задайте `dwCreationFlags` для DEBUG_PROCESS &#124; DEBUG_ONLY_THIS_PROCESS. Если вы хотите использовать только управляемой отладки, не устанавливайте эти флаги.  
  
 Если отладчик и процесс отладки (вложенный процесс) совместно использовать единую консоль, и при отладке взаимодействия, возможна вложенный процесс может заблокировать консоль и остановить событие отладки. Отладчик будет блокироваться любая попытка использовать консоль. Чтобы избежать этой проблемы, установите флаг CREATE_NEW_CONSOLE `dwCreationFlags` параметра.  
  
 Отладки взаимодействия не поддерживается в операционных системах Win9x и не — x86 платформ, таких как основе AMD64 и IA-64-разрядных платформах.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)

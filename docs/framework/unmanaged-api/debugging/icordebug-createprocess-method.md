---
title: Метод ICorDebug::CreateProcess
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: reference
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
caps.latest.revision: 21
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 16e45f3bad92914ce8c7fb0044534789a7a28b2e
ms.sourcegitcommit: b750a8e3979749b214e7e10c82efb0a0524dfcb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/10/2018
---
# <a name="icordebugcreateprocess-method"></a><span data-ttu-id="3f1f8-102">Метод ICorDebug::CreateProcess</span><span class="sxs-lookup"><span data-stu-id="3f1f8-102">ICorDebug::CreateProcess Method</span></span>
<span data-ttu-id="3f1f8-103">Запускает процесс и основной поток под контролем отладчика.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-103">Launches a process and its primary thread under the control of the debugger.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3f1f8-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3f1f8-104">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="3f1f8-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="3f1f8-105">Parameters</span></span>  
 `lpApplicationName`  
 <span data-ttu-id="3f1f8-106">[in] Указатель на строку символом null, указывающее модуль должен быть исполнен запущенного процесса.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-106">[in] Pointer to a null-terminated string that specifies the module to be executed by the launched process.</span></span> <span data-ttu-id="3f1f8-107">Модуль выполняется в контексте безопасности вызывающего процесса.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-107">The module is executed in the security context of the calling process.</span></span>  
  
 `lpCommandLine`  
 <span data-ttu-id="3f1f8-108">[in] Указатель символом null строку, которая определяет командную строку для выполнения запущенного процесса.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-108">[in] Pointer to a null-terminated string that specifies the command line to be executed by the launched process.</span></span> <span data-ttu-id="3f1f8-109">Имя приложения (например, «SomeApp.exe») должны быть первыми аргументами.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-109">The application name (for example, "SomeApp.exe") must be the first argument.</span></span>  
  
 `lpProcessAttributes`  
 <span data-ttu-id="3f1f8-110">[in] Указатель на объект Win32 `SECURITY_ATTRIBUTES` структура, которая задает дескриптор безопасности для процесса.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-110">[in] Pointer to a Win32 `SECURITY_ATTRIBUTES` structure that specifies the security descriptor for the process.</span></span> <span data-ttu-id="3f1f8-111">Если `lpProcessAttributes` имеет значение null, процесс получает дескриптор безопасности по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-111">If `lpProcessAttributes` is null, the process gets a default security descriptor.</span></span>  
  
 `lpThreadAttributes`  
 <span data-ttu-id="3f1f8-112">[in] Указатель на объект Win32 `SECURITY_ATTRIBUTES` структура, которая задает дескриптор безопасности для основного потока процесса.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-112">[in] Pointer to a Win32 `SECURITY_ATTRIBUTES` structure that specifies the security descriptor for the primary thread of the process.</span></span> <span data-ttu-id="3f1f8-113">Если `lpThreadAttributes` имеет значение null, поток получает дескриптор безопасности по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-113">If `lpThreadAttributes` is null, the thread gets a default security descriptor.</span></span>  
  
 `bInheritHandles`  
 <span data-ttu-id="3f1f8-114">[in] Значение `true` для указания, что каждого наследуемые дескриптора в вызывающий процесс наследуется запущенного процесса, или `false` для указания, что маркеры не наследуются.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-114">[in] Set to `true` to indicate that each inheritable handle in the calling process is inherited by the launched process, or `false` to indicate that the handles are not inherited.</span></span> <span data-ttu-id="3f1f8-115">Унаследованные дескрипторы имеют те же права значение и доступа, что и исходные дескрипторы.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-115">The inherited handles have the same value and access rights as the original handles.</span></span>  
  
 `dwCreationFlags`  
 <span data-ttu-id="3f1f8-116">[in] Побитовое сочетание [флаги создания проекта Win32](http://go.microsoft.com/fwlink/?linkid=69981) управляют класс приоритета и поведение запущенного процесса.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-116">[in] A bitwise combination of the [Win32 Process Creation Flags](http://go.microsoft.com/fwlink/?linkid=69981) that control the priority class and the behavior of the launched process.</span></span>  
  
 `lpEnvironment`  
 <span data-ttu-id="3f1f8-117">[in] Указатель на блок среды для нового процесса.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-117">[in] Pointer to an environment block for the new process.</span></span>  
  
 `lpCurrentDirectory`  
 <span data-ttu-id="3f1f8-118">[in] Указатель на завершающуюся значением null строка, указывающая полный путь к текущему каталогу для процесса.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-118">[in] Pointer to a null-terminated string that specifies the full path to the current directory for the process.</span></span> <span data-ttu-id="3f1f8-119">Если этот параметр имеет значение null, новый процесс будет диск и каталог как вызывающий процесс.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-119">If this parameter is null, the new process will have the same current drive and directory as the calling process.</span></span>  
  
 `lpStartupInfo`  
 <span data-ttu-id="3f1f8-120">[in] Указатель на объект Win32 `STARTUPINFOW` структуру, которая определяет окно станции, рабочий стол, стандартные дескрипторы и внешний вид главного окна для запущенного процесса.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-120">[in] Pointer to a Win32 `STARTUPINFOW` structure that specifies the window station, desktop, standard handles, and appearance of the main window for the launched process.</span></span>  
  
 `lpProcessInformation`  
 <span data-ttu-id="3f1f8-121">[in] Указатель на объект Win32 `PROCESS_INFORMATION` структура, которая задает идентификационные сведения о процессе, который будет запущен.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-121">[in] Pointer to a Win32 `PROCESS_INFORMATION` structure that specifies the identification information about the process to be launched.</span></span>  
  
 `debuggingFlags`  
 <span data-ttu-id="3f1f8-122">[in] Значение перечисления CorDebugCreateProcessFlags, которое указывает параметры отладки.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-122">[in] A value of the CorDebugCreateProcessFlags enumeration that specifies the debugging options.</span></span>  
  
 `ppProcess`  
 <span data-ttu-id="3f1f8-123">[out] Указатель на адрес объекта ICorDebugProcess, который представляет процесс.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-123">[out] A pointer to the address of a ICorDebugProcess object that represents the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3f1f8-124">Примечания</span><span class="sxs-lookup"><span data-stu-id="3f1f8-124">Remarks</span></span>  
 <span data-ttu-id="3f1f8-125">Параметры этого метода — это отличается от Win32 `CreateProcess` метод.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-125">The parameters of this method are the same as those of the Win32 `CreateProcess` method.</span></span>  
  
 <span data-ttu-id="3f1f8-126">Чтобы неуправляемой отладки в смешанном режиме, установите `dwCreationFlags` для DEBUG_PROCESS &#124; DEBUG_ONLY_THIS_PROCESS.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-126">To enable unmanaged mixed-mode debugging, set `dwCreationFlags` to DEBUG_PROCESS &#124; DEBUG_ONLY_THIS_PROCESS.</span></span> <span data-ttu-id="3f1f8-127">Если вы хотите использовать только управляемую отладку, не задавайте эти флаги.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-127">If you want to use only managed debugging, do not set these flags.</span></span>  
  
 <span data-ttu-id="3f1f8-128">Если отладчик и процесс отладки (вложенный процесс) совместно использовать единую консоль, и при отладке взаимодействия, то возможна вложенный процесс может заблокировать консоль и остановить событие отладки.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-128">If the debugger and the process to be debugged (the attached process) share a single console, and if interop debugging is used, it is possible for the attached process to hold console locks and stop at a debug event.</span></span> <span data-ttu-id="3f1f8-129">Затем отладчик заблокирует любые попытки использовать консоль.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-129">The debugger will then block any attempt to use the console.</span></span> <span data-ttu-id="3f1f8-130">Чтобы избежать этой проблемы, установите флаг CREATE_NEW_CONSOLE `dwCreationFlags` параметра.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-130">To avoid this problem, set the CREATE_NEW_CONSOLE flag in the `dwCreationFlags` parameter.</span></span>  
  
 <span data-ttu-id="3f1f8-131">Отладка взаимодействия не поддерживается на платформах Win9x и не x86, например основе AMD64 и IA-64-разрядных платформах.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-131">Interop debugging is not supported on Win9x and non-x86 platforms such as IA-64-based and AMD64-based platforms.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3f1f8-132">Требования</span><span class="sxs-lookup"><span data-stu-id="3f1f8-132">Requirements</span></span>  
 <span data-ttu-id="3f1f8-133">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3f1f8-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3f1f8-134">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3f1f8-134">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3f1f8-135">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3f1f8-135">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3f1f8-136">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3f1f8-136">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f1f8-137">См. также</span><span class="sxs-lookup"><span data-stu-id="3f1f8-137">See Also</span></span>  
 [<span data-ttu-id="3f1f8-138">Интерфейс ICorDebug</span><span class="sxs-lookup"><span data-stu-id="3f1f8-138">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)

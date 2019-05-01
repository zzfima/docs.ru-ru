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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61989525"
---
# <a name="icordebugcreateprocess-method"></a><span data-ttu-id="a50e0-102">Метод ICorDebug::CreateProcess</span><span class="sxs-lookup"><span data-stu-id="a50e0-102">ICorDebug::CreateProcess Method</span></span>
<span data-ttu-id="a50e0-103">Запускает процесс и основной поток под контролем отладчика.</span><span class="sxs-lookup"><span data-stu-id="a50e0-103">Launches a process and its primary thread under the control of the debugger.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a50e0-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a50e0-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="a50e0-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="a50e0-105">Parameters</span></span>  
 `lpApplicationName`  
 <span data-ttu-id="a50e0-106">[in] Указатель на заканчивающуюся нулем строку, которая задает имя этого модуля, который будет выполнен задачей запуск процесса.</span><span class="sxs-lookup"><span data-stu-id="a50e0-106">[in] Pointer to a null-terminated string that specifies the module to be executed by the launched process.</span></span> <span data-ttu-id="a50e0-107">Модуль выполняется в контексте безопасности вызывающего процесса.</span><span class="sxs-lookup"><span data-stu-id="a50e0-107">The module is executed in the security context of the calling process.</span></span>  
  
 `lpCommandLine`  
 <span data-ttu-id="a50e0-108">[in] Указатель на заканчивающуюся нулем строку, который определяет командную строку, который будет выполнен задачей запуск процесса.</span><span class="sxs-lookup"><span data-stu-id="a50e0-108">[in] Pointer to a null-terminated string that specifies the command line to be executed by the launched process.</span></span> <span data-ttu-id="a50e0-109">Имя приложения (например, «SomeApp.exe») должен быть первым аргументом.</span><span class="sxs-lookup"><span data-stu-id="a50e0-109">The application name (for example, "SomeApp.exe") must be the first argument.</span></span>  
  
 `lpProcessAttributes`  
 <span data-ttu-id="a50e0-110">[in] Указатель на Win32 `SECURITY_ATTRIBUTES` структуру, которая определяет дескриптор безопасности для процесса.</span><span class="sxs-lookup"><span data-stu-id="a50e0-110">[in] Pointer to a Win32 `SECURITY_ATTRIBUTES` structure that specifies the security descriptor for the process.</span></span> <span data-ttu-id="a50e0-111">Если `lpProcessAttributes` имеет значение null, процесс получает дескриптор безопасности по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="a50e0-111">If `lpProcessAttributes` is null, the process gets a default security descriptor.</span></span>  
  
 `lpThreadAttributes`  
 <span data-ttu-id="a50e0-112">[in] Указатель на Win32 `SECURITY_ATTRIBUTES` структура, которая задает дескриптор безопасности для основного потока этого процесса.</span><span class="sxs-lookup"><span data-stu-id="a50e0-112">[in] Pointer to a Win32 `SECURITY_ATTRIBUTES` structure that specifies the security descriptor for the primary thread of the process.</span></span> <span data-ttu-id="a50e0-113">Если `lpThreadAttributes` имеет значение null, поток получает дескриптор безопасности по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="a50e0-113">If `lpThreadAttributes` is null, the thread gets a default security descriptor.</span></span>  
  
 `bInheritHandles`  
 <span data-ttu-id="a50e0-114">[in] Значение `true` для указания, что запущенный процесс, наследуют каждого наследуемого дескриптора в вызывающий процесс или `false` для указания, что маркеры не наследуются.</span><span class="sxs-lookup"><span data-stu-id="a50e0-114">[in] Set to `true` to indicate that each inheritable handle in the calling process is inherited by the launched process, or `false` to indicate that the handles are not inherited.</span></span> <span data-ttu-id="a50e0-115">Унаследованные дескрипторы имеют те же права значение и доступа, что и исходные дескрипторы.</span><span class="sxs-lookup"><span data-stu-id="a50e0-115">The inherited handles have the same value and access rights as the original handles.</span></span>  
  
 `dwCreationFlags`  
 <span data-ttu-id="a50e0-116">[in] Побитовое сочетание [флаги создания Win32](https://go.microsoft.com/fwlink/?linkid=69981) управления с приоритетом и поведение запуск процесса.</span><span class="sxs-lookup"><span data-stu-id="a50e0-116">[in] A bitwise combination of the [Win32 Process Creation Flags](https://go.microsoft.com/fwlink/?linkid=69981) that control the priority class and the behavior of the launched process.</span></span>  
  
 `lpEnvironment`  
 <span data-ttu-id="a50e0-117">[in] Указатель на блок среды для нового процесса.</span><span class="sxs-lookup"><span data-stu-id="a50e0-117">[in] Pointer to an environment block for the new process.</span></span>  
  
 `lpCurrentDirectory`  
 <span data-ttu-id="a50e0-118">[in] Указатель на заканчивающуюся нулем строку, которая указывает полный путь к текущему каталогу процесса.</span><span class="sxs-lookup"><span data-stu-id="a50e0-118">[in] Pointer to a null-terminated string that specifies the full path to the current directory for the process.</span></span> <span data-ttu-id="a50e0-119">Если этот параметр имеет значение null, новый процесс будет иметь диск и каталог как вызывающий процесс.</span><span class="sxs-lookup"><span data-stu-id="a50e0-119">If this parameter is null, the new process will have the same current drive and directory as the calling process.</span></span>  
  
 `lpStartupInfo`  
 <span data-ttu-id="a50e0-120">[in] Указатель на Win32 `STARTUPINFOW` структура, задающая оконной станции, рабочий стол, стандартные дескрипторы и внешний вид главного окна для запуск процесса.</span><span class="sxs-lookup"><span data-stu-id="a50e0-120">[in] Pointer to a Win32 `STARTUPINFOW` structure that specifies the window station, desktop, standard handles, and appearance of the main window for the launched process.</span></span>  
  
 `lpProcessInformation`  
 <span data-ttu-id="a50e0-121">[in] Указатель на Win32 `PROCESS_INFORMATION` структура, задающая идентификационную информацию о для запуска процесса.</span><span class="sxs-lookup"><span data-stu-id="a50e0-121">[in] Pointer to a Win32 `PROCESS_INFORMATION` structure that specifies the identification information about the process to be launched.</span></span>  
  
 `debuggingFlags`  
 <span data-ttu-id="a50e0-122">[in] Значение перечисления CorDebugCreateProcessFlags, которое указывает параметры отладки.</span><span class="sxs-lookup"><span data-stu-id="a50e0-122">[in] A value of the CorDebugCreateProcessFlags enumeration that specifies the debugging options.</span></span>  
  
 `ppProcess`  
 <span data-ttu-id="a50e0-123">[out] Указатель на адрес объекта ICorDebugProcess, представляющий процесс.</span><span class="sxs-lookup"><span data-stu-id="a50e0-123">[out] A pointer to the address of a ICorDebugProcess object that represents the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a50e0-124">Примечания</span><span class="sxs-lookup"><span data-stu-id="a50e0-124">Remarks</span></span>  
 <span data-ttu-id="a50e0-125">Параметры этого метода являются те же Win32 `CreateProcess` метод.</span><span class="sxs-lookup"><span data-stu-id="a50e0-125">The parameters of this method are the same as those of the Win32 `CreateProcess` method.</span></span>  
  
 <span data-ttu-id="a50e0-126">Чтобы включить неуправляемой отладки в смешанном режиме, задайте `dwCreationFlags` для DEBUG_PROCESS &#124; DEBUG_ONLY_THIS_PROCESS.</span><span class="sxs-lookup"><span data-stu-id="a50e0-126">To enable unmanaged mixed-mode debugging, set `dwCreationFlags` to DEBUG_PROCESS &#124; DEBUG_ONLY_THIS_PROCESS.</span></span> <span data-ttu-id="a50e0-127">Если вы хотите использовать только управляемой отладки, не устанавливайте эти флаги.</span><span class="sxs-lookup"><span data-stu-id="a50e0-127">If you want to use only managed debugging, do not set these flags.</span></span>  
  
 <span data-ttu-id="a50e0-128">Если отладчик и процесс отладки (вложенный процесс) совместно использовать единую консоль, и при отладке взаимодействия, возможна вложенный процесс может заблокировать консоль и остановить событие отладки.</span><span class="sxs-lookup"><span data-stu-id="a50e0-128">If the debugger and the process to be debugged (the attached process) share a single console, and if interop debugging is used, it is possible for the attached process to hold console locks and stop at a debug event.</span></span> <span data-ttu-id="a50e0-129">Отладчик будет блокироваться любая попытка использовать консоль.</span><span class="sxs-lookup"><span data-stu-id="a50e0-129">The debugger will then block any attempt to use the console.</span></span> <span data-ttu-id="a50e0-130">Чтобы избежать этой проблемы, установите флаг CREATE_NEW_CONSOLE `dwCreationFlags` параметра.</span><span class="sxs-lookup"><span data-stu-id="a50e0-130">To avoid this problem, set the CREATE_NEW_CONSOLE flag in the `dwCreationFlags` parameter.</span></span>  
  
 <span data-ttu-id="a50e0-131">Отладки взаимодействия не поддерживается в операционных системах Win9x и не — x86 платформ, таких как основе AMD64 и IA-64-разрядных платформах.</span><span class="sxs-lookup"><span data-stu-id="a50e0-131">Interop debugging is not supported on Win9x and non-x86 platforms such as IA-64-based and AMD64-based platforms.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a50e0-132">Требования</span><span class="sxs-lookup"><span data-stu-id="a50e0-132">Requirements</span></span>  
 <span data-ttu-id="a50e0-133">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a50e0-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a50e0-134">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a50e0-134">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a50e0-135">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a50e0-135">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a50e0-136">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a50e0-136">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a50e0-137">См. также</span><span class="sxs-lookup"><span data-stu-id="a50e0-137">See also</span></span>

- [<span data-ttu-id="a50e0-138">Интерфейс ICorDebug</span><span class="sxs-lookup"><span data-stu-id="a50e0-138">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)

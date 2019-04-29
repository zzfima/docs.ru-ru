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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a38812803127857281f9766fa3ed551971ec0330
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61782789"
---
# <a name="icordebugremotecreateprocessex-method"></a><span data-ttu-id="7cf2e-102">Метод ICorDebugRemote::CreateProcessEx</span><span class="sxs-lookup"><span data-stu-id="7cf2e-102">ICorDebugRemote::CreateProcessEx Method</span></span>
<span data-ttu-id="7cf2e-103">Запускает процесс на удаленном компьютере в режиме отладки.</span><span class="sxs-lookup"><span data-stu-id="7cf2e-103">Launches a process on a remote machine under the debugger.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7cf2e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7cf2e-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="7cf2e-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="7cf2e-105">Parameters</span></span>  
 `pRemoteTarget`  
 <span data-ttu-id="7cf2e-106">[in] Указатель на [интерфейс ICorDebugRemoteTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-interface.md).</span><span class="sxs-lookup"><span data-stu-id="7cf2e-106">[in] Pointer to an [ICorDebugRemoteTarget Interface](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-interface.md).</span></span> <span data-ttu-id="7cf2e-107">Используется для определения удаленного компьютера, на котором будет запущен процесс.</span><span class="sxs-lookup"><span data-stu-id="7cf2e-107">Used to determine the remote machine on which the process will be launched.</span></span>  
  
 `lpApplicationName`  
 <span data-ttu-id="7cf2e-108">[in] Указатель на заканчивающуюся нулем строку, которая задает имя этого модуля, который будет выполнен задачей запуск процесса.</span><span class="sxs-lookup"><span data-stu-id="7cf2e-108">[in] Pointer to a null-terminated string that specifies the module to be executed by the launched process.</span></span> <span data-ttu-id="7cf2e-109">Модуль выполняется в контексте безопасности вызывающего процесса.</span><span class="sxs-lookup"><span data-stu-id="7cf2e-109">The module is executed in the security context of the calling process.</span></span>  
  
 `lpCommandLine`  
 <span data-ttu-id="7cf2e-110">[in] Указатель на заканчивающуюся нулем строку, который определяет командную строку, который будет выполнен задачей запуск процесса.</span><span class="sxs-lookup"><span data-stu-id="7cf2e-110">[in] Pointer to a null-terminated string that specifies the command line to be executed by the launched process.</span></span>  
  
 `lpProcessAttributes`  
 <span data-ttu-id="7cf2e-111">[in] Не используется для удаленной отладки.</span><span class="sxs-lookup"><span data-stu-id="7cf2e-111">[in] Unused for remote debugging.</span></span>  
  
 `lpThreadAttributes`  
 <span data-ttu-id="7cf2e-112">[in] Не используется для удаленной отладки.</span><span class="sxs-lookup"><span data-stu-id="7cf2e-112">[in] Unused for remote debugging.</span></span>  
  
 `bInheritHandles`  
 <span data-ttu-id="7cf2e-113">[in] Не используется для удаленной отладки.</span><span class="sxs-lookup"><span data-stu-id="7cf2e-113">[in] Unused for remote debugging.</span></span>  
  
 `dwCreationFlags`  
 <span data-ttu-id="7cf2e-114">[in] Не используется для удаленной отладки.</span><span class="sxs-lookup"><span data-stu-id="7cf2e-114">[in] Unused for remote debugging.</span></span>  
  
 `lpEnvironment`  
 <span data-ttu-id="7cf2e-115">[in] Указатель на блок среды для нового процесса.</span><span class="sxs-lookup"><span data-stu-id="7cf2e-115">[in] Pointer to an environment block for the new process.</span></span>  
  
 `lpCurrentDirectory`  
 <span data-ttu-id="7cf2e-116">[in] Указатель на заканчивающуюся нулем строку, которая указывает полный путь к текущему каталогу процесса.</span><span class="sxs-lookup"><span data-stu-id="7cf2e-116">[in] Pointer to a null-terminated string that specifies the full path to the current directory for the process.</span></span> <span data-ttu-id="7cf2e-117">Если этот параметр имеет значение null, новый процесс будет иметь диск и каталог как вызывающий процесс.</span><span class="sxs-lookup"><span data-stu-id="7cf2e-117">If this parameter is null, the new process will have the same current drive and directory as the calling process.</span></span>  
  
 `lpStartupInfo`  
 <span data-ttu-id="7cf2e-118">[in] Не используется для удаленной отладки.</span><span class="sxs-lookup"><span data-stu-id="7cf2e-118">[in] Unused for remote debugging.</span></span>  
  
 `lpProcessInformation`  
 <span data-ttu-id="7cf2e-119">[in] Не используется для удаленной отладки.</span><span class="sxs-lookup"><span data-stu-id="7cf2e-119">[in] Unused for remote debugging.</span></span>  
  
 `debuggingFlags`  
 <span data-ttu-id="7cf2e-120">[in] Не используется для удаленной отладки.</span><span class="sxs-lookup"><span data-stu-id="7cf2e-120">[in] Unused for remote debugging.</span></span>  
  
 `ppProcess`  
 <span data-ttu-id="7cf2e-121">[out] Указатель на адрес объекта «Интерфейс ICorDebugProcess», который представляет процесс.</span><span class="sxs-lookup"><span data-stu-id="7cf2e-121">[out] A pointer to the address of a"ICorDebugProcess Interface" object that represents the process.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7cf2e-122">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="7cf2e-122">Return Value</span></span>  
 <span data-ttu-id="7cf2e-123">S_OK</span><span class="sxs-lookup"><span data-stu-id="7cf2e-123">S_OK</span></span>  
 <span data-ttu-id="7cf2e-124">Успешно запущено в процессе на удаленном компьютере и возвращаемый «ICorDebugProcess интерфейс» для отладки.</span><span class="sxs-lookup"><span data-stu-id="7cf2e-124">Successfully launched the process on the remote machine and returned an "ICorDebugProcess Interface" for debugging.</span></span>  
  
 <span data-ttu-id="7cf2e-125">E_FAIL (или другие коды возврата E_)</span><span class="sxs-lookup"><span data-stu-id="7cf2e-125">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="7cf2e-126">Не удалось запустить процесс на удаленном компьютере и возврата «Интерфейс ICorDebugProcess» отладки.</span><span class="sxs-lookup"><span data-stu-id="7cf2e-126">Unable to launch the process on the remote machine and return an "ICorDebugProcess Interface" for debugging.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7cf2e-127">Примечания</span><span class="sxs-lookup"><span data-stu-id="7cf2e-127">Remarks</span></span>  
 <span data-ttu-id="7cf2e-128">Отладка в смешанном режиме не поддерживается в Silverlight.</span><span class="sxs-lookup"><span data-stu-id="7cf2e-128">Mixed-mode debugging is not supported in Silverlight.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7cf2e-129">Требования</span><span class="sxs-lookup"><span data-stu-id="7cf2e-129">Requirements</span></span>  
 <span data-ttu-id="7cf2e-130">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7cf2e-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7cf2e-131">**Заголовок.** CorDebug.idl</span><span class="sxs-lookup"><span data-stu-id="7cf2e-131">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="7cf2e-132">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7cf2e-132">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7cf2e-133">**Версии платформы .NET framework:** 4.5, 4, 3.5 С ПАКЕТОМ ОБНОВЛЕНИЯ 1</span><span class="sxs-lookup"><span data-stu-id="7cf2e-133">**.NET Framework Versions:** 4.5, 4, 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7cf2e-134">См. также</span><span class="sxs-lookup"><span data-stu-id="7cf2e-134">See also</span></span>

- [<span data-ttu-id="7cf2e-135">Интерфейс ICorDebugRemote</span><span class="sxs-lookup"><span data-stu-id="7cf2e-135">ICorDebugRemote Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugremote-interface.md)
- [<span data-ttu-id="7cf2e-136">Интерфейс ICorDebug</span><span class="sxs-lookup"><span data-stu-id="7cf2e-136">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)

- [<span data-ttu-id="7cf2e-137">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="7cf2e-137">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

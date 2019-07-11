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
ms.openlocfilehash: d05384af8201fae8cf81650d38c99a5c44e6bd16
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67744775"
---
# <a name="icordebugremotecreateprocessex-method"></a><span data-ttu-id="0cd7c-102">Метод ICorDebugRemote::CreateProcessEx</span><span class="sxs-lookup"><span data-stu-id="0cd7c-102">ICorDebugRemote::CreateProcessEx Method</span></span>
<span data-ttu-id="0cd7c-103">Запускает процесс на удаленном компьютере в режиме отладки.</span><span class="sxs-lookup"><span data-stu-id="0cd7c-103">Launches a process on a remote machine under the debugger.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0cd7c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0cd7c-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="0cd7c-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="0cd7c-105">Parameters</span></span>  
 `pRemoteTarget`  
 <span data-ttu-id="0cd7c-106">[in] Указатель на [интерфейс ICorDebugRemoteTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-interface.md).</span><span class="sxs-lookup"><span data-stu-id="0cd7c-106">[in] Pointer to an [ICorDebugRemoteTarget Interface](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-interface.md).</span></span> <span data-ttu-id="0cd7c-107">Используется для определения удаленного компьютера, на котором будет запущен процесс.</span><span class="sxs-lookup"><span data-stu-id="0cd7c-107">Used to determine the remote machine on which the process will be launched.</span></span>  
  
 `lpApplicationName`  
 <span data-ttu-id="0cd7c-108">[in] Указатель на заканчивающуюся нулем строку, которая задает имя этого модуля, который будет выполнен задачей запуск процесса.</span><span class="sxs-lookup"><span data-stu-id="0cd7c-108">[in] Pointer to a null-terminated string that specifies the module to be executed by the launched process.</span></span> <span data-ttu-id="0cd7c-109">Модуль выполняется в контексте безопасности вызывающего процесса.</span><span class="sxs-lookup"><span data-stu-id="0cd7c-109">The module is executed in the security context of the calling process.</span></span>  
  
 `lpCommandLine`  
 <span data-ttu-id="0cd7c-110">[in] Указатель на заканчивающуюся нулем строку, который определяет командную строку, который будет выполнен задачей запуск процесса.</span><span class="sxs-lookup"><span data-stu-id="0cd7c-110">[in] Pointer to a null-terminated string that specifies the command line to be executed by the launched process.</span></span>  
  
 `lpProcessAttributes`  
 <span data-ttu-id="0cd7c-111">[in] Не используется для удаленной отладки.</span><span class="sxs-lookup"><span data-stu-id="0cd7c-111">[in] Unused for remote debugging.</span></span>  
  
 `lpThreadAttributes`  
 <span data-ttu-id="0cd7c-112">[in] Не используется для удаленной отладки.</span><span class="sxs-lookup"><span data-stu-id="0cd7c-112">[in] Unused for remote debugging.</span></span>  
  
 `bInheritHandles`  
 <span data-ttu-id="0cd7c-113">[in] Не используется для удаленной отладки.</span><span class="sxs-lookup"><span data-stu-id="0cd7c-113">[in] Unused for remote debugging.</span></span>  
  
 `dwCreationFlags`  
 <span data-ttu-id="0cd7c-114">[in] Не используется для удаленной отладки.</span><span class="sxs-lookup"><span data-stu-id="0cd7c-114">[in] Unused for remote debugging.</span></span>  
  
 `lpEnvironment`  
 <span data-ttu-id="0cd7c-115">[in] Указатель на блок среды для нового процесса.</span><span class="sxs-lookup"><span data-stu-id="0cd7c-115">[in] Pointer to an environment block for the new process.</span></span>  
  
 `lpCurrentDirectory`  
 <span data-ttu-id="0cd7c-116">[in] Указатель на заканчивающуюся нулем строку, которая указывает полный путь к текущему каталогу процесса.</span><span class="sxs-lookup"><span data-stu-id="0cd7c-116">[in] Pointer to a null-terminated string that specifies the full path to the current directory for the process.</span></span> <span data-ttu-id="0cd7c-117">Если этот параметр имеет значение null, новый процесс будет иметь диск и каталог как вызывающий процесс.</span><span class="sxs-lookup"><span data-stu-id="0cd7c-117">If this parameter is null, the new process will have the same current drive and directory as the calling process.</span></span>  
  
 `lpStartupInfo`  
 <span data-ttu-id="0cd7c-118">[in] Не используется для удаленной отладки.</span><span class="sxs-lookup"><span data-stu-id="0cd7c-118">[in] Unused for remote debugging.</span></span>  
  
 `lpProcessInformation`  
 <span data-ttu-id="0cd7c-119">[in] Не используется для удаленной отладки.</span><span class="sxs-lookup"><span data-stu-id="0cd7c-119">[in] Unused for remote debugging.</span></span>  
  
 `debuggingFlags`  
 <span data-ttu-id="0cd7c-120">[in] Не используется для удаленной отладки.</span><span class="sxs-lookup"><span data-stu-id="0cd7c-120">[in] Unused for remote debugging.</span></span>  
  
 `ppProcess`  
 <span data-ttu-id="0cd7c-121">[out] Указатель на адрес объекта «Интерфейс ICorDebugProcess», который представляет процесс.</span><span class="sxs-lookup"><span data-stu-id="0cd7c-121">[out] A pointer to the address of a"ICorDebugProcess Interface" object that represents the process.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0cd7c-122">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="0cd7c-122">Return Value</span></span>  
 <span data-ttu-id="0cd7c-123">S_OK</span><span class="sxs-lookup"><span data-stu-id="0cd7c-123">S_OK</span></span>  
 <span data-ttu-id="0cd7c-124">Успешно запущено в процессе на удаленном компьютере и возвращаемый «ICorDebugProcess интерфейс» для отладки.</span><span class="sxs-lookup"><span data-stu-id="0cd7c-124">Successfully launched the process on the remote machine and returned an "ICorDebugProcess Interface" for debugging.</span></span>  
  
 <span data-ttu-id="0cd7c-125">E_FAIL (или другие коды возврата E_)</span><span class="sxs-lookup"><span data-stu-id="0cd7c-125">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="0cd7c-126">Не удалось запустить процесс на удаленном компьютере и возврата «Интерфейс ICorDebugProcess» отладки.</span><span class="sxs-lookup"><span data-stu-id="0cd7c-126">Unable to launch the process on the remote machine and return an "ICorDebugProcess Interface" for debugging.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0cd7c-127">Примечания</span><span class="sxs-lookup"><span data-stu-id="0cd7c-127">Remarks</span></span>  
 <span data-ttu-id="0cd7c-128">Отладка в смешанном режиме не поддерживается в Silverlight.</span><span class="sxs-lookup"><span data-stu-id="0cd7c-128">Mixed-mode debugging is not supported in Silverlight.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0cd7c-129">Требования</span><span class="sxs-lookup"><span data-stu-id="0cd7c-129">Requirements</span></span>  
 <span data-ttu-id="0cd7c-130">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0cd7c-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0cd7c-131">**Заголовок.** CorDebug.idl</span><span class="sxs-lookup"><span data-stu-id="0cd7c-131">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="0cd7c-132">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0cd7c-132">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0cd7c-133">**Версии платформы .NET framework:** 4.5, 4, 3.5 С ПАКЕТОМ ОБНОВЛЕНИЯ 1</span><span class="sxs-lookup"><span data-stu-id="0cd7c-133">**.NET Framework Versions:** 4.5, 4, 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0cd7c-134">См. также</span><span class="sxs-lookup"><span data-stu-id="0cd7c-134">See also</span></span>

- [<span data-ttu-id="0cd7c-135">Интерфейс ICorDebugRemote</span><span class="sxs-lookup"><span data-stu-id="0cd7c-135">ICorDebugRemote Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugremote-interface.md)
- [<span data-ttu-id="0cd7c-136">Интерфейс ICorDebug</span><span class="sxs-lookup"><span data-stu-id="0cd7c-136">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)

- [<span data-ttu-id="0cd7c-137">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="0cd7c-137">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

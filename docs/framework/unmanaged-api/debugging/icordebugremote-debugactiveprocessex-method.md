---
title: Метод ICorDebugRemote::DebugActiveProcessEx
ms.date: 03/30/2017
api_name:
- ICorDebugRemote.DebugActiveProcessEx
api_location:
- CorDebug.dll
api_type:
- COM
f1_keywords:
- ICorDebugRemoteTarget::DebugActiveProcessEx
helpviewer_keywords:
- ICorDebugRemote::DebugActiveProcessEx method [.NET Framework debugging]
- DebugActiveProcessEx method, ICorDebugRemote interface [.NET Framework debugging]
ms.assetid: b0df5c5d-9a2e-47bf-894c-6f8a9fe24a1f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: eb085cc486c307a308258709f4c58619597bc202
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54608392"
---
# <a name="icordebugremotedebugactiveprocessex-method"></a><span data-ttu-id="bfe9c-102">Метод ICorDebugRemote::DebugActiveProcessEx</span><span class="sxs-lookup"><span data-stu-id="bfe9c-102">ICorDebugRemote::DebugActiveProcessEx Method</span></span>
<span data-ttu-id="bfe9c-103">Запускает процесс на удаленном компьютере в режиме отладки.</span><span class="sxs-lookup"><span data-stu-id="bfe9c-103">Launches a process on a remote machine under the debugger.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bfe9c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bfe9c-104">Syntax</span></span>  
  
```  
HRESULT DebugActiveProcessEx (  
    [in]  ICorDebugRemoteTarget *   pRemoteTarget,  
    [in]  DWORD                     dwProcessId,  
    [in]  BOOL                      fWin32Attach,  
    [out] ICorDebugProcess **       ppProcess  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="bfe9c-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="bfe9c-105">Parameters</span></span>  
 `pRemoteTarget`  
 <span data-ttu-id="bfe9c-106">[in] Указатель на [интерфейс ICorDebugRemoteTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-interface.md).</span><span class="sxs-lookup"><span data-stu-id="bfe9c-106">[in] Pointer to an [ICorDebugRemoteTarget Interface](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-interface.md).</span></span> <span data-ttu-id="bfe9c-107">Этот параметр используется для определения компьютера, на котором выполняется процесс.</span><span class="sxs-lookup"><span data-stu-id="bfe9c-107">This parameter is used to determine the machine on which the process is running.</span></span>  
  
 `id`  
 <span data-ttu-id="bfe9c-108">[in] Идентификатор процесса, к которому отладчик должен быть связан.</span><span class="sxs-lookup"><span data-stu-id="bfe9c-108">[in] The ID of the process to which the debugger is to be attached.</span></span>  
  
 `win32Attach`  
 <span data-ttu-id="bfe9c-109">[in] `true` Если отладчик должен вести себя как отладчик Win32 для процесса и отправки неуправляемых обратных вызовов; в противном случае `false`.</span><span class="sxs-lookup"><span data-stu-id="bfe9c-109">[in] `true` if the debugger should behave as the Win32 debugger for the process and dispatch the unmanaged callbacks; otherwise, `false`.</span></span>  
  
 `ppProcess`  
 <span data-ttu-id="bfe9c-110">[out] Указатель на адрес объекта «ICorDebugProcess», представляющий процесс, к которому присоединен отладчик.</span><span class="sxs-lookup"><span data-stu-id="bfe9c-110">[out] A pointer to the address of an "ICorDebugProcess" object that represents the process to which the debugger has been attached.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bfe9c-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="bfe9c-111">Return Value</span></span>  
 <span data-ttu-id="bfe9c-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="bfe9c-112">S_OK</span></span>  
 <span data-ttu-id="bfe9c-113">Успешно подключен к процессу на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="bfe9c-113">Successfully attached to the process on the remote machine.</span></span>  
  
 <span data-ttu-id="bfe9c-114">E_FAIL (или другие коды возврата E_)</span><span class="sxs-lookup"><span data-stu-id="bfe9c-114">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="bfe9c-115">Не удалось присоединиться к процессу на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="bfe9c-115">Unable to attach to the process on the remote machine.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bfe9c-116">Примечания</span><span class="sxs-lookup"><span data-stu-id="bfe9c-116">Remarks</span></span>  
 <span data-ttu-id="bfe9c-117">Отладка в смешанном режиме не поддерживается в Silverlight.</span><span class="sxs-lookup"><span data-stu-id="bfe9c-117">Mixed-mode debugging is not supported in Silverlight.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bfe9c-118">Требования</span><span class="sxs-lookup"><span data-stu-id="bfe9c-118">Requirements</span></span>  
 <span data-ttu-id="bfe9c-119">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bfe9c-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bfe9c-120">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bfe9c-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bfe9c-121">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bfe9c-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bfe9c-122">**Версии платформы .NET framework:** 4.5, 4, 3.5 С ПАКЕТОМ ОБНОВЛЕНИЯ 1</span><span class="sxs-lookup"><span data-stu-id="bfe9c-122">**.NET Framework Versions:** 4.5, 4, 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bfe9c-123">См. также</span><span class="sxs-lookup"><span data-stu-id="bfe9c-123">See also</span></span>
- [<span data-ttu-id="bfe9c-124">Интерфейс ICorDebugRemote</span><span class="sxs-lookup"><span data-stu-id="bfe9c-124">ICorDebugRemote Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugremote-interface.md)
- [<span data-ttu-id="bfe9c-125">Интерфейс ICorDebug</span><span class="sxs-lookup"><span data-stu-id="bfe9c-125">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)

- [<span data-ttu-id="bfe9c-126">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="bfe9c-126">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

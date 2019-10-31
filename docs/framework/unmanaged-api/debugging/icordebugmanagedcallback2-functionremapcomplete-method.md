---
title: Метод ICorDebugManagedCallback2::FunctionRemapComplete
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback2.FunctionRemapComplete
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback2::FunctionRemapComplete
helpviewer_keywords:
- FunctionRemapComplete method [.NET Framework debugging]
- ICorDebugManagedCallback2::FunctionRemapComplete method [.NET Framework debugging]
ms.assetid: 5396c4c3-4ec3-4e3a-a38d-d65b21f0a2fc
topic_type:
- apiref
ms.openlocfilehash: 6e048d03e54d4f97cd45935906ea4e4744468db9
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131518"
---
# <a name="icordebugmanagedcallback2functionremapcomplete-method"></a><span data-ttu-id="259ca-102">Метод ICorDebugManagedCallback2::FunctionRemapComplete</span><span class="sxs-lookup"><span data-stu-id="259ca-102">ICorDebugManagedCallback2::FunctionRemapComplete Method</span></span>
<span data-ttu-id="259ca-103">Уведомляет отладчик о том, что выполнение кода переключено на новую версию измененной функции.</span><span class="sxs-lookup"><span data-stu-id="259ca-103">Notifies the debugger that code execution has switched to a new version of an edited function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="259ca-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="259ca-104">Syntax</span></span>  
  
```cpp  
HRESULT FunctionRemapComplete (  
    [in] ICorDebugAppDomain   *pAppDomain,  
    [in] ICorDebugThread      *pThread,  
    [in] ICorDebugFunction    *pFunction  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="259ca-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="259ca-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="259ca-106">окне Указатель на объект ICorDebugAppDomain, представляющий домен приложения, содержащий измененную функцию.</span><span class="sxs-lookup"><span data-stu-id="259ca-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the edited function.</span></span>  
  
 `pThread`  
 <span data-ttu-id="259ca-107">окне Указатель на объект ICorDebugThread, представляющий поток, в котором была обнаружена точка останова сопоставления.</span><span class="sxs-lookup"><span data-stu-id="259ca-107">[in] A pointer to an ICorDebugThread object that represents the thread on which the remap breakpoint was encountered.</span></span>  
  
 `pFunction`  
 <span data-ttu-id="259ca-108">окне Указатель на объект ICorDebugFunction, представляющий версию функции, выполняемой в данный момент в потоке.</span><span class="sxs-lookup"><span data-stu-id="259ca-108">[in] A pointer to an ICorDebugFunction object that represents the version of the function currently running on the thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="259ca-109">Заметки</span><span class="sxs-lookup"><span data-stu-id="259ca-109">Remarks</span></span>  
 <span data-ttu-id="259ca-110">Этот обратный вызов дает возможность отладчику повторно создавать все ранее существовавшие пошаговые шаги.</span><span class="sxs-lookup"><span data-stu-id="259ca-110">This callback gives the debugger an opportunity to recreate any steppers that previously existed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="259ca-111">Требования</span><span class="sxs-lookup"><span data-stu-id="259ca-111">Requirements</span></span>  
 <span data-ttu-id="259ca-112">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="259ca-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="259ca-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="259ca-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="259ca-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="259ca-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="259ca-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="259ca-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="259ca-116">См. также</span><span class="sxs-lookup"><span data-stu-id="259ca-116">See also</span></span>

- [<span data-ttu-id="259ca-117">Интерфейс ICorDebugManagedCallback2</span><span class="sxs-lookup"><span data-stu-id="259ca-117">ICorDebugManagedCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)
- [<span data-ttu-id="259ca-118">Интерфейс ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="259ca-118">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)

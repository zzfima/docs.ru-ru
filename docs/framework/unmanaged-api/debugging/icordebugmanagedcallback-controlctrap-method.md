---
title: Метод ICorDebugManagedCallback::ControlCTrap
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.ControlCTrap
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::ControlCTrap
helpviewer_keywords:
- ICorDebugManagedCallback::ControlCTrap method [.NET Framework debugging]
- ControlCTrap method [.NET Framework debugging]
ms.assetid: 0500854e-2121-43d9-a028-64312da35258
topic_type:
- apiref
ms.openlocfilehash: da35db8a943fda5fb3fbf4126684bb9cb7243001
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137431"
---
# <a name="icordebugmanagedcallbackcontrolctrap-method"></a><span data-ttu-id="9cff2-102">Метод ICorDebugManagedCallback::ControlCTrap</span><span class="sxs-lookup"><span data-stu-id="9cff2-102">ICorDebugManagedCallback::ControlCTrap Method</span></span>
<span data-ttu-id="9cff2-103">Уведомляет отладчик о том, что в отлаживаемом процессе выполняется перехват CTRL + C.</span><span class="sxs-lookup"><span data-stu-id="9cff2-103">Notifies the debugger that a CTRL+C is trapped in the process that is being debugged.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9cff2-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9cff2-104">Syntax</span></span>  
  
```cpp  
HRESULT ControlCTrap (  
    [in] ICorDebugProcess *pProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9cff2-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="9cff2-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="9cff2-106">окне Указатель на объект ICorDebugProcess, представляющий процесс, в котором выполняется перехват CTRL + C.</span><span class="sxs-lookup"><span data-stu-id="9cff2-106">[in] A pointer to an ICorDebugProcess object that represents the process in which the CTRL+C is trapped.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9cff2-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="9cff2-107">Return Value</span></span>  
  
|<span data-ttu-id="9cff2-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9cff2-108">HRESULT</span></span>|<span data-ttu-id="9cff2-109">Описание</span><span class="sxs-lookup"><span data-stu-id="9cff2-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9cff2-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="9cff2-110">S_OK</span></span>|<span data-ttu-id="9cff2-111">Отладчик будет выполнять обработку ловушек CTRL + C.</span><span class="sxs-lookup"><span data-stu-id="9cff2-111">The debugger will handle the CTRL+C trap.</span></span>|  
|<span data-ttu-id="9cff2-112">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="9cff2-112">S_FALSE</span></span>|<span data-ttu-id="9cff2-113">Отладчик не будет выполнять обработку ловушек CTRL + C.</span><span class="sxs-lookup"><span data-stu-id="9cff2-113">The debugger will not handle the CTRL+C trap.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9cff2-114">Заметки</span><span class="sxs-lookup"><span data-stu-id="9cff2-114">Remarks</span></span>  
 <span data-ttu-id="9cff2-115">Все домены приложений в рамках процесса останавливаются для этого обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="9cff2-115">All application domains within the process are stopped for this callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9cff2-116">Требования</span><span class="sxs-lookup"><span data-stu-id="9cff2-116">Requirements</span></span>  
 <span data-ttu-id="9cff2-117">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9cff2-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9cff2-118">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9cff2-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9cff2-119">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9cff2-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9cff2-120">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9cff2-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9cff2-121">См. также</span><span class="sxs-lookup"><span data-stu-id="9cff2-121">See also</span></span>

- [<span data-ttu-id="9cff2-122">Интерфейс ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="9cff2-122">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)

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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7f4794fb0383435f828626497036ad3458df2173
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59204995"
---
# <a name="icordebugmanagedcallbackcontrolctrap-method"></a><span data-ttu-id="76f07-102">Метод ICorDebugManagedCallback::ControlCTrap</span><span class="sxs-lookup"><span data-stu-id="76f07-102">ICorDebugManagedCallback::ControlCTrap Method</span></span>
<span data-ttu-id="76f07-103">Уведомляет отладчик о том, что сочетание клавиш CTRL + C, представленные в отлаживаемом процессе.</span><span class="sxs-lookup"><span data-stu-id="76f07-103">Notifies the debugger that a CTRL+C is trapped in the process that is being debugged.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="76f07-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="76f07-104">Syntax</span></span>  
  
```  
HRESULT ControlCTrap (  
    [in] ICorDebugProcess *pProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="76f07-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="76f07-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="76f07-106">[in] Указатель на объект ICorDebugProcess, представляющий процесс, в котором перехватывается CTRL + C.</span><span class="sxs-lookup"><span data-stu-id="76f07-106">[in] A pointer to an ICorDebugProcess object that represents the process in which the CTRL+C is trapped.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="76f07-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="76f07-107">Return Value</span></span>  
  
|<span data-ttu-id="76f07-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="76f07-108">HRESULT</span></span>|<span data-ttu-id="76f07-109">Описание</span><span class="sxs-lookup"><span data-stu-id="76f07-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="76f07-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="76f07-110">S_OK</span></span>|<span data-ttu-id="76f07-111">Отладчик будет обрабатывать нажатие клавиши CTRL + C.</span><span class="sxs-lookup"><span data-stu-id="76f07-111">The debugger will handle the CTRL+C trap.</span></span>|  
|<span data-ttu-id="76f07-112">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="76f07-112">S_FALSE</span></span>|<span data-ttu-id="76f07-113">Отладчик не будет обрабатывать нажатие CTRL + C.</span><span class="sxs-lookup"><span data-stu-id="76f07-113">The debugger will not handle the CTRL+C trap.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="76f07-114">Примечания</span><span class="sxs-lookup"><span data-stu-id="76f07-114">Remarks</span></span>  
 <span data-ttu-id="76f07-115">Все домены приложений в рамках процесса остановлены для этого обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="76f07-115">All application domains within the process are stopped for this callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="76f07-116">Требования</span><span class="sxs-lookup"><span data-stu-id="76f07-116">Requirements</span></span>  
 <span data-ttu-id="76f07-117">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="76f07-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="76f07-118">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="76f07-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="76f07-119">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="76f07-119">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="76f07-120">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="76f07-120">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="76f07-121">См. также</span><span class="sxs-lookup"><span data-stu-id="76f07-121">See also</span></span>

- [<span data-ttu-id="76f07-122">Интерфейс ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="76f07-122">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)

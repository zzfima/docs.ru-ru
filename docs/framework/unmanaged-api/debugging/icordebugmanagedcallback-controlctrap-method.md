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
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59204995"
---
# <a name="icordebugmanagedcallbackcontrolctrap-method"></a><span data-ttu-id="9cf0b-102">Метод ICorDebugManagedCallback::ControlCTrap</span><span class="sxs-lookup"><span data-stu-id="9cf0b-102">ICorDebugManagedCallback::ControlCTrap Method</span></span>
<span data-ttu-id="9cf0b-103">Уведомляет отладчик о том, что сочетание клавиш CTRL + C, представленные в отлаживаемом процессе.</span><span class="sxs-lookup"><span data-stu-id="9cf0b-103">Notifies the debugger that a CTRL+C is trapped in the process that is being debugged.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9cf0b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9cf0b-104">Syntax</span></span>  
  
```  
HRESULT ControlCTrap (  
    [in] ICorDebugProcess *pProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9cf0b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="9cf0b-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="9cf0b-106">[in] Указатель на объект ICorDebugProcess, представляющий процесс, в котором перехватывается CTRL + C.</span><span class="sxs-lookup"><span data-stu-id="9cf0b-106">[in] A pointer to an ICorDebugProcess object that represents the process in which the CTRL+C is trapped.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9cf0b-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="9cf0b-107">Return Value</span></span>  
  
|<span data-ttu-id="9cf0b-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9cf0b-108">HRESULT</span></span>|<span data-ttu-id="9cf0b-109">Описание</span><span class="sxs-lookup"><span data-stu-id="9cf0b-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9cf0b-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="9cf0b-110">S_OK</span></span>|<span data-ttu-id="9cf0b-111">Отладчик будет обрабатывать нажатие клавиши CTRL + C.</span><span class="sxs-lookup"><span data-stu-id="9cf0b-111">The debugger will handle the CTRL+C trap.</span></span>|  
|<span data-ttu-id="9cf0b-112">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="9cf0b-112">S_FALSE</span></span>|<span data-ttu-id="9cf0b-113">Отладчик не будет обрабатывать нажатие CTRL + C.</span><span class="sxs-lookup"><span data-stu-id="9cf0b-113">The debugger will not handle the CTRL+C trap.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9cf0b-114">Примечания</span><span class="sxs-lookup"><span data-stu-id="9cf0b-114">Remarks</span></span>  
 <span data-ttu-id="9cf0b-115">Все домены приложений в рамках процесса остановлены для этого обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="9cf0b-115">All application domains within the process are stopped for this callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9cf0b-116">Требования</span><span class="sxs-lookup"><span data-stu-id="9cf0b-116">Requirements</span></span>  
 <span data-ttu-id="9cf0b-117">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9cf0b-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9cf0b-118">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9cf0b-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9cf0b-119">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9cf0b-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9cf0b-120">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9cf0b-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9cf0b-121">См. также</span><span class="sxs-lookup"><span data-stu-id="9cf0b-121">See also</span></span>

- [<span data-ttu-id="9cf0b-122">Интерфейс ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="9cf0b-122">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)

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
ms.openlocfilehash: 63f7bf8c09480b9ce2cfb8eb8dc66e4a6133ef8f
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76777490"
---
# <a name="icordebugmanagedcallbackcontrolctrap-method"></a><span data-ttu-id="1a92b-102">Метод ICorDebugManagedCallback::ControlCTrap</span><span class="sxs-lookup"><span data-stu-id="1a92b-102">ICorDebugManagedCallback::ControlCTrap Method</span></span>
<span data-ttu-id="1a92b-103">Уведомляет отладчик о том, что в отлаживаемом процессе выполняется перехват CTRL + C.</span><span class="sxs-lookup"><span data-stu-id="1a92b-103">Notifies the debugger that a CTRL+C is trapped in the process that is being debugged.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1a92b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1a92b-104">Syntax</span></span>  
  
```cpp  
HRESULT ControlCTrap (  
    [in] ICorDebugProcess *pProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1a92b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="1a92b-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="1a92b-106">окне Указатель на объект ICorDebugProcess, представляющий процесс, в котором выполняется перехват CTRL + C.</span><span class="sxs-lookup"><span data-stu-id="1a92b-106">[in] A pointer to an ICorDebugProcess object that represents the process in which the CTRL+C is trapped.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1a92b-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="1a92b-107">Return Value</span></span>  
  
|<span data-ttu-id="1a92b-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="1a92b-108">HRESULT</span></span>|<span data-ttu-id="1a92b-109">Описание</span><span class="sxs-lookup"><span data-stu-id="1a92b-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="1a92b-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="1a92b-110">S_OK</span></span>|<span data-ttu-id="1a92b-111">Отладчик будет выполнять обработку ловушек CTRL + C.</span><span class="sxs-lookup"><span data-stu-id="1a92b-111">The debugger will handle the CTRL+C trap.</span></span>|  
|<span data-ttu-id="1a92b-112">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="1a92b-112">S_FALSE</span></span>|<span data-ttu-id="1a92b-113">Отладчик не будет выполнять обработку ловушек CTRL + C.</span><span class="sxs-lookup"><span data-stu-id="1a92b-113">The debugger will not handle the CTRL+C trap.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1a92b-114">Заметки</span><span class="sxs-lookup"><span data-stu-id="1a92b-114">Remarks</span></span>  
 <span data-ttu-id="1a92b-115">Все домены приложений в рамках процесса останавливаются для этого обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="1a92b-115">All application domains within the process are stopped for this callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1a92b-116">Требования</span><span class="sxs-lookup"><span data-stu-id="1a92b-116">Requirements</span></span>  
 <span data-ttu-id="1a92b-117">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1a92b-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1a92b-118">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1a92b-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1a92b-119">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1a92b-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1a92b-120">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1a92b-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a92b-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="1a92b-121">See also</span></span>

- [<span data-ttu-id="1a92b-122">Интерфейс ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="1a92b-122">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)

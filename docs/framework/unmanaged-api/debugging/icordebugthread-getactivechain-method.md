---
title: Метод ICorDebugThread::GetActiveChain
ms.date: 03/30/2017
api_name:
- ICorDebugThread.GetActiveChain
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetActiveChain
helpviewer_keywords:
- ICorDebugThread::GetActiveChain method [.NET Framework debugging]
- GetActiveChain method [.NET Framework debugging]
ms.assetid: f50de1f7-40ef-4949-b542-1d9a61f7bfef
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9030319ca12aafcf452e3ecd816fc269f0abfc0e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugthreadgetactivechain-method"></a><span data-ttu-id="d23dd-102">Метод ICorDebugThread::GetActiveChain</span><span class="sxs-lookup"><span data-stu-id="d23dd-102">ICorDebugThread::GetActiveChain Method</span></span>
<span data-ttu-id="d23dd-103">Получает указатель интерфейса активной (последней) цепи стека для этого объекта ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="d23dd-103">Gets an interface pointer to the active (most recent) stack chain on this ICorDebugThread object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d23dd-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d23dd-104">Syntax</span></span>  
  
```  
HRESULT GetActiveChain (  
    [out] ICorDebugChain **ppChain  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d23dd-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="d23dd-105">Parameters</span></span>  
 `ppChain`  
 <span data-ttu-id="d23dd-106">[out] Указатель на адрес объекта ICorDebugChain, который представляет цепочка стека.</span><span class="sxs-lookup"><span data-stu-id="d23dd-106">[out] A pointer to the address of an ICorDebugChain object that represents the stack chain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d23dd-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="d23dd-107">Remarks</span></span>  
 <span data-ttu-id="d23dd-108">`ppChain` Параметр имеет значение null, если нет цепочка стека в данный момент активна.</span><span class="sxs-lookup"><span data-stu-id="d23dd-108">The `ppChain` parameter is null if no stack chain is currently active.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d23dd-109">Требования</span><span class="sxs-lookup"><span data-stu-id="d23dd-109">Requirements</span></span>  
 <span data-ttu-id="d23dd-110">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d23dd-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d23dd-111">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d23dd-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d23dd-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d23dd-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d23dd-113">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d23dd-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

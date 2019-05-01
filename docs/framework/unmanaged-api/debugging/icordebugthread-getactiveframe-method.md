---
title: Метод ICorDebugThread::GetActiveFrame
ms.date: 03/30/2017
api_name:
- ICorDebugThread.GetActiveFrame
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetActiveFrame
helpviewer_keywords:
- ICorDebugThread::GetActiveFrame method [.NET Framework debugging]
- GetActiveFrame method, ICorDebugThread interface [.NET Framework debugging]
ms.assetid: 8d6d3a1a-fef6-4f2f-a22c-3bdd30d70e07
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 051491173bbcef3d87d9a3dbe854eece46c49e0d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61994062"
---
# <a name="icordebugthreadgetactiveframe-method"></a><span data-ttu-id="8f0e8-102">Метод ICorDebugThread::GetActiveFrame</span><span class="sxs-lookup"><span data-stu-id="8f0e8-102">ICorDebugThread::GetActiveFrame Method</span></span>
<span data-ttu-id="8f0e8-103">Получает указатель интерфейса на этот объект ICorDebugThread активного кадра (последней).</span><span class="sxs-lookup"><span data-stu-id="8f0e8-103">Gets an interface pointer to the active (most recent) frame on this ICorDebugThread object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8f0e8-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8f0e8-104">Syntax</span></span>  
  
```  
HRESULT GetActiveFrame (  
    [out] ICorDebugFrame   **ppFrame  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8f0e8-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="8f0e8-105">Parameters</span></span>  
 `ppFrame`  
 <span data-ttu-id="8f0e8-106">[out] Указатель на адрес объекта интерфейса ICorDebugFrame, представляющий кадр.</span><span class="sxs-lookup"><span data-stu-id="8f0e8-106">[out] A pointer to the address of an ICorDebugFrame interface object that represents a frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8f0e8-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="8f0e8-107">Remarks</span></span>  
 <span data-ttu-id="8f0e8-108">`ppFrame` Параметр имеет значение null, если не рамка в данный момент активна.</span><span class="sxs-lookup"><span data-stu-id="8f0e8-108">The `ppFrame` parameter is null if no frame is currently active.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8f0e8-109">Требования</span><span class="sxs-lookup"><span data-stu-id="8f0e8-109">Requirements</span></span>  
 <span data-ttu-id="8f0e8-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8f0e8-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8f0e8-111">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8f0e8-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8f0e8-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8f0e8-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8f0e8-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8f0e8-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

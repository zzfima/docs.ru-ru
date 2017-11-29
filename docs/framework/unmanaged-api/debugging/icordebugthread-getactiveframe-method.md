---
title: "Метод ICorDebugThread::GetActiveFrame"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugThread.GetActiveFrame
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugThread::GetActiveFrame
helpviewer_keywords:
- ICorDebugThread::GetActiveFrame method [.NET Framework debugging]
- GetActiveFrame method, ICorDebugThread interface [.NET Framework debugging]
ms.assetid: 8d6d3a1a-fef6-4f2f-a22c-3bdd30d70e07
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: f8b5d9d42b7c3f7827ce938fdd3dffe57b00142c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugthreadgetactiveframe-method"></a><span data-ttu-id="361e0-102">Метод ICorDebugThread::GetActiveFrame</span><span class="sxs-lookup"><span data-stu-id="361e0-102">ICorDebugThread::GetActiveFrame Method</span></span>
<span data-ttu-id="361e0-103">Получает указатель интерфейса на этот объект ICorDebugThread активного кадра (последней).</span><span class="sxs-lookup"><span data-stu-id="361e0-103">Gets an interface pointer to the active (most recent) frame on this ICorDebugThread object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="361e0-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="361e0-104">Syntax</span></span>  
  
```  
HRESULT GetActiveFrame (  
    [out] ICorDebugFrame   **ppFrame  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="361e0-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="361e0-105">Parameters</span></span>  
 `ppFrame`  
 <span data-ttu-id="361e0-106">[out] Указатель на адрес объекта интерфейса ICorDebugFrame, который представляет кадр.</span><span class="sxs-lookup"><span data-stu-id="361e0-106">[out] A pointer to the address of an ICorDebugFrame interface object that represents a frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="361e0-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="361e0-107">Remarks</span></span>  
 <span data-ttu-id="361e0-108">`ppFrame` Параметр имеет значение null, если нет рамка в данный момент активна.</span><span class="sxs-lookup"><span data-stu-id="361e0-108">The `ppFrame` parameter is null if no frame is currently active.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="361e0-109">Требования</span><span class="sxs-lookup"><span data-stu-id="361e0-109">Requirements</span></span>  
 <span data-ttu-id="361e0-110">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="361e0-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="361e0-111">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="361e0-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="361e0-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="361e0-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="361e0-113">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="361e0-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

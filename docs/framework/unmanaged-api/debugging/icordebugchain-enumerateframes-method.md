---
title: "Метод ICorDebugChain::EnumerateFrames"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorDebugChain.EnumerateFrames
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain::EnumerateFrames method
helpviewer_keywords:
- EnumerateFrames method [.NET Framework debugging]
- ICorDebugChain::EnumerateFrames method [.NET Framework debugging]
ms.assetid: 9fcefa98-750d-4168-8915-8173a43accf2
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: d9df99c239568948c04f61ca4ec5e2b9207930f8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugchainenumerateframes-method"></a><span data-ttu-id="966b7-102">Метод ICorDebugChain::EnumerateFrames</span><span class="sxs-lookup"><span data-stu-id="966b7-102">ICorDebugChain::EnumerateFrames Method</span></span>
<span data-ttu-id="966b7-103">Возвращает перечислитель, содержащий все управляемые фреймы стека в цепочке, начиная с последнего кадра.</span><span class="sxs-lookup"><span data-stu-id="966b7-103">Gets an enumerator that contains all the managed stack frames in the chain, starting with the most recent frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="966b7-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="966b7-104">Syntax</span></span>  
  
```  
HRESULT EnumerateFrames (  
    [out] ICorDebugFrameEnum **ppFrames  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="966b7-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="966b7-105">Parameters</span></span>  
 `ppFrames`  
 <span data-ttu-id="966b7-106">[out] Указатель на адрес объекта ICorDebugFrameEnum, который является перечислителем для кадров стека.</span><span class="sxs-lookup"><span data-stu-id="966b7-106">[out] A pointer to the address of an ICorDebugFrameEnum object that is the enumerator for the stack frames.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="966b7-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="966b7-107">Remarks</span></span>  
 <span data-ttu-id="966b7-108">Цепь представляет физический стек вызова для потока.</span><span class="sxs-lookup"><span data-stu-id="966b7-108">The chain represents the physical call stack for the thread.</span></span>  
  
 <span data-ttu-id="966b7-109">`EnumerateFrames` Метод должен вызываться только для управляемых цепочек.</span><span class="sxs-lookup"><span data-stu-id="966b7-109">The `EnumerateFrames` method should be called only for managed chains.</span></span> <span data-ttu-id="966b7-110">API отладки не предоставляет методы для получения кадров, содержащихся в неуправляемых цепочки.</span><span class="sxs-lookup"><span data-stu-id="966b7-110">The debugging API does not provide methods for obtaining frames contained in unmanaged chains.</span></span> <span data-ttu-id="966b7-111">Отладчик должен использовать другие средства для получения этих сведений.</span><span class="sxs-lookup"><span data-stu-id="966b7-111">The debugger must use other means to obtain this information.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="966b7-112">Требования</span><span class="sxs-lookup"><span data-stu-id="966b7-112">Requirements</span></span>  
 <span data-ttu-id="966b7-113">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="966b7-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="966b7-114">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="966b7-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="966b7-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="966b7-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="966b7-116">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="966b7-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

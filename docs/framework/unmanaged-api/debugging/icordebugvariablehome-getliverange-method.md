---
title: "Метод IcorDebugVariableHome::GetLiveRange"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
api_name:
- ICorDebugVariableHome.GetLiveRange
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHome::GetLiveRange
helpviewer_keywords:
- ICorDebugVariableHome::GetLiveRange method [.NET Framework debugging]
- GetLiveRange method, ICorDebugVariableFrame interface [.NET Framework debugging]
ms.assetid: 87277e1a-1595-4729-9e25-d1c3ac18ce5f
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 1bb86921be3398e6e9653838c1aec6b40ca86469
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugvariablehomegetliverange-method"></a><span data-ttu-id="eefb8-102">Метод IcorDebugVariableHome::GetLiveRange</span><span class="sxs-lookup"><span data-stu-id="eefb8-102">IcorDebugVariableHome::GetLiveRange Method</span></span>
<span data-ttu-id="eefb8-103">Получает собственный диапазон, по которому эта переменная является динамической.</span><span class="sxs-lookup"><span data-stu-id="eefb8-103">Gets the native range over which this variable is live.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eefb8-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="eefb8-104">Syntax</span></span>  
  
```  
HRESULT GetLiveRange(  
    [out] ULONG32* pStartOffset,  
    [out] ULONG32 *pEndOffset  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="eefb8-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="eefb8-105">Parameters</span></span>  
 `pStartOffset`  
 <span data-ttu-id="eefb8-106">[out] Логический смещение, когда переменная является первой динамическая.</span><span class="sxs-lookup"><span data-stu-id="eefb8-106">[out] The logical offset at which the variable is first live.</span></span>  
  
 `pEndOffset`  
 <span data-ttu-id="eefb8-107">[out] Логический смещение сразу после запятой, когда переменная является последней динамическая.</span><span class="sxs-lookup"><span data-stu-id="eefb8-107">[out] The logical offset immediately after the point at which the variable is last live.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eefb8-108">Требования</span><span class="sxs-lookup"><span data-stu-id="eefb8-108">Requirements</span></span>  
 <span data-ttu-id="eefb8-109">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="eefb8-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eefb8-110">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="eefb8-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="eefb8-111">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="eefb8-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="eefb8-112">**Версии платформы .NET framework:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eefb8-112">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eefb8-113">См. также</span><span class="sxs-lookup"><span data-stu-id="eefb8-113">See Also</span></span>  
 [<span data-ttu-id="eefb8-114">Интерфейс ICorDebugVariableHome</span><span class="sxs-lookup"><span data-stu-id="eefb8-114">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)

---
title: Метод IcorDebugVariableHome::GetLiveRange
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7e2c9e981f431bb87df61a71389abf3d42a6a507
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59123816"
---
# <a name="icordebugvariablehomegetliverange-method"></a><span data-ttu-id="c0d77-102">Метод IcorDebugVariableHome::GetLiveRange</span><span class="sxs-lookup"><span data-stu-id="c0d77-102">IcorDebugVariableHome::GetLiveRange Method</span></span>
<span data-ttu-id="c0d77-103">Получает собственный диапазон, по которому эта переменная является динамической.</span><span class="sxs-lookup"><span data-stu-id="c0d77-103">Gets the native range over which this variable is live.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c0d77-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c0d77-104">Syntax</span></span>  
  
```  
HRESULT GetLiveRange(  
    [out] ULONG32* pStartOffset,  
    [out] ULONG32 *pEndOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c0d77-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c0d77-105">Parameters</span></span>  
 `pStartOffset`  
 <span data-ttu-id="c0d77-106">[out] Логические смещение, по которому переменная является первой динамическую.</span><span class="sxs-lookup"><span data-stu-id="c0d77-106">[out] The logical offset at which the variable is first live.</span></span>  
  
 `pEndOffset`  
 <span data-ttu-id="c0d77-107">[out] Логические смещение сразу же после запятой, по которому переменная является последним live.</span><span class="sxs-lookup"><span data-stu-id="c0d77-107">[out] The logical offset immediately after the point at which the variable is last live.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c0d77-108">Требования</span><span class="sxs-lookup"><span data-stu-id="c0d77-108">Requirements</span></span>  
 <span data-ttu-id="c0d77-109">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c0d77-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c0d77-110">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c0d77-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c0d77-111">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c0d77-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c0d77-112">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c0d77-112">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0d77-113">См. также</span><span class="sxs-lookup"><span data-stu-id="c0d77-113">See also</span></span>

- [<span data-ttu-id="c0d77-114">Интерфейс ICorDebugVariableHome</span><span class="sxs-lookup"><span data-stu-id="c0d77-114">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)

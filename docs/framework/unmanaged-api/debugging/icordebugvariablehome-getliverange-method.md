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
ms.openlocfilehash: c0f9c586a9e95fc2e57c4956601f6dce2b988159
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33423069"
---
# <a name="icordebugvariablehomegetliverange-method"></a><span data-ttu-id="7d1ea-102">Метод IcorDebugVariableHome::GetLiveRange</span><span class="sxs-lookup"><span data-stu-id="7d1ea-102">IcorDebugVariableHome::GetLiveRange Method</span></span>
<span data-ttu-id="7d1ea-103">Получает собственный диапазон, по которому эта переменная является динамической.</span><span class="sxs-lookup"><span data-stu-id="7d1ea-103">Gets the native range over which this variable is live.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7d1ea-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7d1ea-104">Syntax</span></span>  
  
```  
HRESULT GetLiveRange(  
    [out] ULONG32* pStartOffset,  
    [out] ULONG32 *pEndOffset  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7d1ea-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="7d1ea-105">Parameters</span></span>  
 `pStartOffset`  
 <span data-ttu-id="7d1ea-106">[out] Логический смещение, когда переменная является первой динамическая.</span><span class="sxs-lookup"><span data-stu-id="7d1ea-106">[out] The logical offset at which the variable is first live.</span></span>  
  
 `pEndOffset`  
 <span data-ttu-id="7d1ea-107">[out] Логический смещение сразу после запятой, когда переменная является последней динамическая.</span><span class="sxs-lookup"><span data-stu-id="7d1ea-107">[out] The logical offset immediately after the point at which the variable is last live.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7d1ea-108">Требования</span><span class="sxs-lookup"><span data-stu-id="7d1ea-108">Requirements</span></span>  
 <span data-ttu-id="7d1ea-109">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7d1ea-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7d1ea-110">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7d1ea-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7d1ea-111">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7d1ea-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7d1ea-112">**Версии платформы .NET framework:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7d1ea-112">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d1ea-113">См. также</span><span class="sxs-lookup"><span data-stu-id="7d1ea-113">See Also</span></span>  
 [<span data-ttu-id="7d1ea-114">Интерфейс ICorDebugVariableHome</span><span class="sxs-lookup"><span data-stu-id="7d1ea-114">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)

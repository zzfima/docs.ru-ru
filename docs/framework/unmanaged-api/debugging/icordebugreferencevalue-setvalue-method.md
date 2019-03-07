---
title: Метод ICorDebugReferenceValue::SetValue
ms.date: 03/30/2017
api_name:
- ICorDebugReferenceValue.SetValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugReferenceValue::SetValue
helpviewer_keywords:
- SetValue method, ICorDebugReferenceValue interface [.NET Framework debugging]
- ICorDebugReferenceValue::SetValue method [.NET Framework debugging]
ms.assetid: 3d3f6eec-d772-401f-a028-1a2ecdc31e95
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 59ef7bf8f17e79c9ae7b80dd314a5afce7fa9584
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57474180"
---
# <a name="icordebugreferencevaluesetvalue-method"></a><span data-ttu-id="ec268-102">Метод ICorDebugReferenceValue::SetValue</span><span class="sxs-lookup"><span data-stu-id="ec268-102">ICorDebugReferenceValue::SetValue Method</span></span>
<span data-ttu-id="ec268-103">Задает адрес указанной области памяти.</span><span class="sxs-lookup"><span data-stu-id="ec268-103">Sets the specified memory address.</span></span> <span data-ttu-id="ec268-104">То есть этот метод задает этот ICorDebugReferenceValue для указания на объект.</span><span class="sxs-lookup"><span data-stu-id="ec268-104">That is, this method sets this ICorDebugReferenceValue to point to an object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ec268-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ec268-105">Syntax</span></span>  
  
```  
HRESULT SetValue (  
    [in] CORDB_ADDRESS    value  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ec268-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="ec268-106">Parameters</span></span>  
 `value`  
 <span data-ttu-id="ec268-107">[in] Объект `CORDB_ADDRESS` значение, указывающее адрес объекта, к которому `ICorDebugReferenceValue` точек.</span><span class="sxs-lookup"><span data-stu-id="ec268-107">[in] A `CORDB_ADDRESS` value that specifies the address of the object to which this `ICorDebugReferenceValue` points.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ec268-108">Требования</span><span class="sxs-lookup"><span data-stu-id="ec268-108">Requirements</span></span>  
 <span data-ttu-id="ec268-109">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ec268-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ec268-110">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ec268-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ec268-111">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ec268-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ec268-112">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ec268-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

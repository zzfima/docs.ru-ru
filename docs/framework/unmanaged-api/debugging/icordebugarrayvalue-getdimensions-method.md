---
title: "Метод ICorDebugArrayValue::GetDimensions"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugArrayValue.GetDimensions
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugArrayValue::GetDimensions
helpviewer_keywords:
- ICorDebugArrayValue::GetDimensions method [.NET Framework debugging]
- GetDimensions method [.NET Framework debugging]
ms.assetid: 6c116592-134b-4ef2-a319-680e92d013aa
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1769969d411d66417d2b2df7ddc9f810bd7f48ad
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugarrayvaluegetdimensions-method"></a><span data-ttu-id="9c7d7-102">Метод ICorDebugArrayValue::GetDimensions</span><span class="sxs-lookup"><span data-stu-id="9c7d7-102">ICorDebugArrayValue::GetDimensions Method</span></span>
<span data-ttu-id="9c7d7-103">Возвращает количество элементов в каждом измерении этого массива.</span><span class="sxs-lookup"><span data-stu-id="9c7d7-103">Gets the number of elements in each dimension of this array.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9c7d7-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9c7d7-104">Syntax</span></span>  
  
```  
HRESULT GetDimensions (  
    [in] ULONG32         cdim,  
    [out, size_is(cdim), length_is(cdim)]   
        ULONG32          dims[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9c7d7-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="9c7d7-105">Parameters</span></span>  
 `cdim`  
 <span data-ttu-id="9c7d7-106">[in] Число измерений противном.</span><span class="sxs-lookup"><span data-stu-id="9c7d7-106">[in] The number of dimensions of this ICorDebugArrayValue object.</span></span>  
  
 <span data-ttu-id="9c7d7-107">Этот параметр также имеет размер `dims` массива, так как его размер равен числу измерений `ICorDebugArrayValue` объекта.</span><span class="sxs-lookup"><span data-stu-id="9c7d7-107">This value is also the size of the `dims` array because its size is equal to the number of dimensions of the `ICorDebugArrayValue` object.</span></span>  
  
 `dims`  
 <span data-ttu-id="9c7d7-108">[out] Массив целых чисел, каждое из которых задает количество элементов измерения в этом `ICorDebugArrayValue` объекта.</span><span class="sxs-lookup"><span data-stu-id="9c7d7-108">[out] An array of integers, each of which specifies the number of elements in a dimension in this `ICorDebugArrayValue` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9c7d7-109">Требования</span><span class="sxs-lookup"><span data-stu-id="9c7d7-109">Requirements</span></span>  
 <span data-ttu-id="9c7d7-110">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9c7d7-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9c7d7-111">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9c7d7-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9c7d7-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9c7d7-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9c7d7-113">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9c7d7-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

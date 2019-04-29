---
title: Метод ICorDebugArrayValue::GetDimensions
ms.date: 03/30/2017
api_name:
- ICorDebugArrayValue.GetDimensions
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugArrayValue::GetDimensions
helpviewer_keywords:
- ICorDebugArrayValue::GetDimensions method [.NET Framework debugging]
- GetDimensions method [.NET Framework debugging]
ms.assetid: 6c116592-134b-4ef2-a319-680e92d013aa
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a52075f33d594787c516f84b65b3319991380907
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61645699"
---
# <a name="icordebugarrayvaluegetdimensions-method"></a><span data-ttu-id="0fcbe-102">Метод ICorDebugArrayValue::GetDimensions</span><span class="sxs-lookup"><span data-stu-id="0fcbe-102">ICorDebugArrayValue::GetDimensions Method</span></span>
<span data-ttu-id="0fcbe-103">Получает число элементов в каждом измерении этого массива.</span><span class="sxs-lookup"><span data-stu-id="0fcbe-103">Gets the number of elements in each dimension of this array.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0fcbe-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0fcbe-104">Syntax</span></span>  
  
```  
HRESULT GetDimensions (  
    [in] ULONG32         cdim,  
    [out, size_is(cdim), length_is(cdim)]   
        ULONG32          dims[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0fcbe-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="0fcbe-105">Parameters</span></span>  
 `cdim`  
 <span data-ttu-id="0fcbe-106">[in] Число измерений противном.</span><span class="sxs-lookup"><span data-stu-id="0fcbe-106">[in] The number of dimensions of this ICorDebugArrayValue object.</span></span>  
  
 <span data-ttu-id="0fcbe-107">Этот параметр также имеет размер `dims` массива, так как его размер равен числу измерений `ICorDebugArrayValue` объекта.</span><span class="sxs-lookup"><span data-stu-id="0fcbe-107">This value is also the size of the `dims` array because its size is equal to the number of dimensions of the `ICorDebugArrayValue` object.</span></span>  
  
 `dims`  
 <span data-ttu-id="0fcbe-108">[out] Массив целых чисел, каждое из которых указывает количество элементов в измерении в это `ICorDebugArrayValue` объекта.</span><span class="sxs-lookup"><span data-stu-id="0fcbe-108">[out] An array of integers, each of which specifies the number of elements in a dimension in this `ICorDebugArrayValue` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0fcbe-109">Требования</span><span class="sxs-lookup"><span data-stu-id="0fcbe-109">Requirements</span></span>  
 <span data-ttu-id="0fcbe-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0fcbe-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0fcbe-111">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0fcbe-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0fcbe-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0fcbe-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0fcbe-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0fcbe-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

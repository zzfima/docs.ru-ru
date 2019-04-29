---
title: Метод ICorDebugArrayValue::HasBaseIndicies
ms.date: 03/30/2017
api_name:
- ICorDebugArrayValue.HasBaseIndicies
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugArrayValue::HasBaseIndicies
helpviewer_keywords:
- HasBaseIndicies method [.NET Framework debugging]
- ICorDebugArrayValue::HasBaseIndicies method [.NET Framework debugging]
ms.assetid: aa26df07-e0a6-4608-bdef-d4afafec89aa
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 49f5ed8b24d81ba8f32a9fe0ad7488693718bde9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61645673"
---
# <a name="icordebugarrayvaluehasbaseindicies-method"></a><span data-ttu-id="51c3c-102">Метод ICorDebugArrayValue::HasBaseIndicies</span><span class="sxs-lookup"><span data-stu-id="51c3c-102">ICorDebugArrayValue::HasBaseIndicies Method</span></span>
<span data-ttu-id="51c3c-103">Получает значение, указывающее, имеют ли все измерения массива базовый индекс ненулевое значение.</span><span class="sxs-lookup"><span data-stu-id="51c3c-103">Gets a value that indicates whether any dimensions of this array have a base index of non-zero.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="51c3c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="51c3c-104">Syntax</span></span>  
  
```  
HRESULT HasBaseIndicies (  
    [out] BOOL    *pbHasBaseIndicies  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="51c3c-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="51c3c-105">Parameters</span></span>  
 `pbHasBaseIndicies`  
 <span data-ttu-id="51c3c-106">[out] Указатель на логическое значение, которое является `true` Если одно или несколько измерений этого `ICorDebugArrayValue` объект имеет базовый индекс ненулевое значение; в противном случае логическое значение равно `false`.</span><span class="sxs-lookup"><span data-stu-id="51c3c-106">[out] A pointer to a Boolean value that is `true` if one or more dimensions of this `ICorDebugArrayValue` object have a base index of non-zero; otherwise, the Boolean value is `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="51c3c-107">Требования</span><span class="sxs-lookup"><span data-stu-id="51c3c-107">Requirements</span></span>  
 <span data-ttu-id="51c3c-108">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="51c3c-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="51c3c-109">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="51c3c-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="51c3c-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="51c3c-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="51c3c-111">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="51c3c-111">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>

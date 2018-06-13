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
ms.openlocfilehash: 574df434360dfab644a4c937dac46ebc3871a53a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33399514"
---
# <a name="icordebugarrayvaluehasbaseindicies-method"></a><span data-ttu-id="46df9-102">Метод ICorDebugArrayValue::HasBaseIndicies</span><span class="sxs-lookup"><span data-stu-id="46df9-102">ICorDebugArrayValue::HasBaseIndicies Method</span></span>
<span data-ttu-id="46df9-103">Возвращает значение, указывающее, имеют ли все измерения массива базовый индекс ненулевое значение.</span><span class="sxs-lookup"><span data-stu-id="46df9-103">Gets a value that indicates whether any dimensions of this array have a base index of non-zero.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="46df9-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="46df9-104">Syntax</span></span>  
  
```  
HRESULT HasBaseIndicies (  
    [out] BOOL    *pbHasBaseIndicies  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="46df9-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="46df9-105">Parameters</span></span>  
 `pbHasBaseIndicies`  
 <span data-ttu-id="46df9-106">[out] Указатель на значение типа Boolean, `true` Если одно или несколько измерений этого `ICorDebugArrayValue` объект имеет базовый индекс не равно нулю; в противном случае — логическое значение, которое `false`.</span><span class="sxs-lookup"><span data-stu-id="46df9-106">[out] A pointer to a Boolean value that is `true` if one or more dimensions of this `ICorDebugArrayValue` object have a base index of non-zero; otherwise, the Boolean value is `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="46df9-107">Требования</span><span class="sxs-lookup"><span data-stu-id="46df9-107">Requirements</span></span>  
 <span data-ttu-id="46df9-108">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="46df9-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="46df9-109">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="46df9-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="46df9-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="46df9-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="46df9-111">**Версии платформы .NET framework:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="46df9-111">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>

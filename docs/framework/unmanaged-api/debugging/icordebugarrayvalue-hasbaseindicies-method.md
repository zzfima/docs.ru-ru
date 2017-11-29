---
title: "Метод ICorDebugArrayValue::HasBaseIndicies"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugArrayValue.HasBaseIndicies
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugArrayValue::HasBaseIndicies
helpviewer_keywords:
- HasBaseIndicies method [.NET Framework debugging]
- ICorDebugArrayValue::HasBaseIndicies method [.NET Framework debugging]
ms.assetid: aa26df07-e0a6-4608-bdef-d4afafec89aa
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 256429bfed350181aa13ee2c119eb5c9541ce231
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugarrayvaluehasbaseindicies-method"></a><span data-ttu-id="17931-102">Метод ICorDebugArrayValue::HasBaseIndicies</span><span class="sxs-lookup"><span data-stu-id="17931-102">ICorDebugArrayValue::HasBaseIndicies Method</span></span>
<span data-ttu-id="17931-103">Возвращает значение, указывающее, имеют ли все измерения массива базовый индекс ненулевое значение.</span><span class="sxs-lookup"><span data-stu-id="17931-103">Gets a value that indicates whether any dimensions of this array have a base index of non-zero.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="17931-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="17931-104">Syntax</span></span>  
  
```  
HRESULT HasBaseIndicies (  
    [out] BOOL    *pbHasBaseIndicies  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="17931-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="17931-105">Parameters</span></span>  
 `pbHasBaseIndicies`  
 <span data-ttu-id="17931-106">[out] Указатель на значение типа Boolean, `true` Если одно или несколько измерений этого `ICorDebugArrayValue` объект имеет базовый индекс не равно нулю; в противном случае — логическое значение, которое `false`.</span><span class="sxs-lookup"><span data-stu-id="17931-106">[out] A pointer to a Boolean value that is `true` if one or more dimensions of this `ICorDebugArrayValue` object have a base index of non-zero; otherwise, the Boolean value is `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="17931-107">Требования</span><span class="sxs-lookup"><span data-stu-id="17931-107">Requirements</span></span>  
 <span data-ttu-id="17931-108">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="17931-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="17931-109">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="17931-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="17931-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="17931-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="17931-111">**Версии платформы .NET framework:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="17931-111">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>

---
title: Метод ICorDebugReferenceValue::IsNull
ms.date: 03/30/2017
api_name:
- ICorDebugReferenceValue.IsNull
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugReferenceValue::IsNull
helpviewer_keywords:
- IsNull method, ICorDebugReferenceValue interface [.NET Framework debugging]
- ICorDebugReferenceValue::IsNull method [.NET Framework debugging]
ms.assetid: 99e8c8d7-a1c0-47c8-9dbd-03e0b2bcb4d5
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2c82c72350931bf3aed8ec6699cd0af834798e92
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugreferencevalueisnull-method"></a><span data-ttu-id="51f5e-102">Метод ICorDebugReferenceValue::IsNull</span><span class="sxs-lookup"><span data-stu-id="51f5e-102">ICorDebugReferenceValue::IsNull Method</span></span>
<span data-ttu-id="51f5e-103">Получает значение, указывающее, является ли этот ICorDebugReferenceValue значение null, в этом случае `ICorDebugReferenceValue` не указывает на объект.</span><span class="sxs-lookup"><span data-stu-id="51f5e-103">Gets a value that indicates whether this ICorDebugReferenceValue is a null value, in which case the `ICorDebugReferenceValue` does not point to an object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="51f5e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="51f5e-104">Syntax</span></span>  
  
```  
HRESULT IsNull (  
    [out] BOOL   *pbNull  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="51f5e-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="51f5e-105">Parameters</span></span>  
 `pbNull`  
 <span data-ttu-id="51f5e-106">[out] Указатель на значение типа Boolean, `true` при этом `ICorDebugReferenceValue` объекта null, в противном случае — `pbNull` — `false`.</span><span class="sxs-lookup"><span data-stu-id="51f5e-106">[out] A pointer to a Boolean value that is `true` if this `ICorDebugReferenceValue` object is null; otherwise, `pbNull` is `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="51f5e-107">Требования</span><span class="sxs-lookup"><span data-stu-id="51f5e-107">Requirements</span></span>  
 <span data-ttu-id="51f5e-108">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="51f5e-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="51f5e-109">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="51f5e-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="51f5e-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="51f5e-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="51f5e-111">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="51f5e-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

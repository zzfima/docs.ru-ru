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
ms.openlocfilehash: 972df4613255dc1b71801e02d387a735dfc632c0
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57477261"
---
# <a name="icordebugreferencevalueisnull-method"></a><span data-ttu-id="47518-102">Метод ICorDebugReferenceValue::IsNull</span><span class="sxs-lookup"><span data-stu-id="47518-102">ICorDebugReferenceValue::IsNull Method</span></span>
<span data-ttu-id="47518-103">Получает значение, указывающее, является ли этот ICorDebugReferenceValue значение null, в этом случае `ICorDebugReferenceValue` не указывает на объект.</span><span class="sxs-lookup"><span data-stu-id="47518-103">Gets a value that indicates whether this ICorDebugReferenceValue is a null value, in which case the `ICorDebugReferenceValue` does not point to an object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="47518-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="47518-104">Syntax</span></span>  
  
```  
HRESULT IsNull (  
    [out] BOOL   *pbNull  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="47518-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="47518-105">Parameters</span></span>  
 `pbNull`  
 <span data-ttu-id="47518-106">[out] Указатель на логическое значение, которое является `true` Если `ICorDebugReferenceValue` объект null; в противном случае `pbNull` является `false`.</span><span class="sxs-lookup"><span data-stu-id="47518-106">[out] A pointer to a Boolean value that is `true` if this `ICorDebugReferenceValue` object is null; otherwise, `pbNull` is `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="47518-107">Требования</span><span class="sxs-lookup"><span data-stu-id="47518-107">Requirements</span></span>  
 <span data-ttu-id="47518-108">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="47518-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="47518-109">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="47518-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="47518-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="47518-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="47518-111">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="47518-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

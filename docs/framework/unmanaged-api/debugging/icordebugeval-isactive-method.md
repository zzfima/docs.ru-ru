---
title: Метод ICorDebugEval::IsActive
ms.date: 03/30/2017
api_name:
- ICorDebugEval.IsActive
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval::IsActive
helpviewer_keywords:
- IsActive method, ICorDebugEval interface [.NET Framework debugging]
- ICorDebugEval::IsActive method [.NET Framework debugging]
ms.assetid: bf2bba24-d278-43bd-b1c5-35680e748d3e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0d992ea86b3221af222bb01f1985fe277cea5a2c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61989004"
---
# <a name="icordebugevalisactive-method"></a><span data-ttu-id="30ecb-102">Метод ICorDebugEval::IsActive</span><span class="sxs-lookup"><span data-stu-id="30ecb-102">ICorDebugEval::IsActive Method</span></span>
<span data-ttu-id="30ecb-103">Получает значение, указывающее, является ли этот объект ICorDebugEval в данный момент.</span><span class="sxs-lookup"><span data-stu-id="30ecb-103">Gets a value that indicates whether this ICorDebugEval object is currently executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="30ecb-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="30ecb-104">Syntax</span></span>  
  
```  
HRESULT IsActive (  
    [out] BOOL              *pbActive  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="30ecb-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="30ecb-105">Parameters</span></span>  
 `pbActive`  
 <span data-ttu-id="30ecb-106">[out] Указатель на значение, указывающее, активна ли эта оценка.</span><span class="sxs-lookup"><span data-stu-id="30ecb-106">[out] Pointer to a value that indicates whether this evaluation is active.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="30ecb-107">Требования</span><span class="sxs-lookup"><span data-stu-id="30ecb-107">Requirements</span></span>  
 <span data-ttu-id="30ecb-108">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="30ecb-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="30ecb-109">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="30ecb-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="30ecb-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="30ecb-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="30ecb-111">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="30ecb-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

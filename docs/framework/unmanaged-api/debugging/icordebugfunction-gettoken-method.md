---
title: Метод ICorDebugFunction::GetToken
ms.date: 03/30/2017
api_name:
- ICorDebugFunction.GetToken
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction::GetToken
helpviewer_keywords:
- ICorDebugFunction::GetToken method [.NET Framework debugging]
- GetToken method, ICorDebugFunction interface [.NET Framework debugging]
ms.assetid: c6bbf479-062e-48e9-9c70-0f92e293e36a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e56c8eba49260eba9e3e0ca7e9ab4c7cfcd3261f
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57471944"
---
# <a name="icordebugfunctiongettoken-method"></a><span data-ttu-id="b4250-102">Метод ICorDebugFunction::GetToken</span><span class="sxs-lookup"><span data-stu-id="b4250-102">ICorDebugFunction::GetToken Method</span></span>
<span data-ttu-id="b4250-103">Получает маркер метаданных для этой функции.</span><span class="sxs-lookup"><span data-stu-id="b4250-103">Gets the metadata token for this function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b4250-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b4250-104">Syntax</span></span>  
  
```  
HRESULT GetToken (  
    [out] mdMethodDef *pMethodDef  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b4250-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="b4250-105">Parameters</span></span>  
 `pMethodDef`  
 <span data-ttu-id="b4250-106">[out] Указатель на `mdMethodDef` маркер, который ссылается на метаданные для этой функции.</span><span class="sxs-lookup"><span data-stu-id="b4250-106">[out] A pointer to an `mdMethodDef` token that references the metadata for this function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b4250-107">Требования</span><span class="sxs-lookup"><span data-stu-id="b4250-107">Requirements</span></span>  
 <span data-ttu-id="b4250-108">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b4250-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b4250-109">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b4250-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b4250-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b4250-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b4250-111">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b4250-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

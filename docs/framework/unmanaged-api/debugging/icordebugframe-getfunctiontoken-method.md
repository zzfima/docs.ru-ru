---
title: Метод ICorDebugFrame::GetFunctionToken
ms.date: 03/30/2017
api_name:
- ICorDebugFrame.GetFunctionToken
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrame::GetFunctionToken
helpviewer_keywords:
- ICorDebugFrame::GetFunctionToken method [.NET Framework debugging]
- GetFunctionToken method [.NET Framework debugging]
ms.assetid: a46925b3-3bf8-404f-9f30-a86ae41032c1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 156c16f73916d2b4efa1c1b3541a772fb43dd470
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57497565"
---
# <a name="icordebugframegetfunctiontoken-method"></a><span data-ttu-id="a61e1-102">Метод ICorDebugFrame::GetFunctionToken</span><span class="sxs-lookup"><span data-stu-id="a61e1-102">ICorDebugFrame::GetFunctionToken Method</span></span>
<span data-ttu-id="a61e1-103">Получает маркер метаданных для функции, которая содержит код, связанный с данным кадром стека.</span><span class="sxs-lookup"><span data-stu-id="a61e1-103">Gets the metadata token for the function that contains the code associated with this stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a61e1-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a61e1-104">Syntax</span></span>  
  
```  
HRESULT GetFunctionToken (  
    [out] mdMethodDef        *pToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a61e1-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="a61e1-105">Parameters</span></span>  
 `pToken`  
 <span data-ttu-id="a61e1-106">[out] Указатель на `mdMethodDef` маркер, который ссылается на метаданные для функции.</span><span class="sxs-lookup"><span data-stu-id="a61e1-106">[out] A pointer to an `mdMethodDef` token that references the metadata for the function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a61e1-107">Требования</span><span class="sxs-lookup"><span data-stu-id="a61e1-107">Requirements</span></span>  
 <span data-ttu-id="a61e1-108">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a61e1-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a61e1-109">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a61e1-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a61e1-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a61e1-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a61e1-111">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a61e1-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

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
ms.openlocfilehash: e7821022e6966dbdea90d57b6899f09b2ed1964e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73090529"
---
# <a name="icordebugframegetfunctiontoken-method"></a><span data-ttu-id="dbaf2-102">Метод ICorDebugFrame::GetFunctionToken</span><span class="sxs-lookup"><span data-stu-id="dbaf2-102">ICorDebugFrame::GetFunctionToken Method</span></span>
<span data-ttu-id="dbaf2-103">Возвращает маркер метаданных для функции, которая содержит код, связанный с этим кадром стека.</span><span class="sxs-lookup"><span data-stu-id="dbaf2-103">Gets the metadata token for the function that contains the code associated with this stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dbaf2-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="dbaf2-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFunctionToken (  
    [out] mdMethodDef        *pToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dbaf2-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="dbaf2-105">Parameters</span></span>  
 `pToken`  
 <span data-ttu-id="dbaf2-106">заполняет Указатель на маркер `mdMethodDef`, который ссылается на метаданные функции.</span><span class="sxs-lookup"><span data-stu-id="dbaf2-106">[out] A pointer to an `mdMethodDef` token that references the metadata for the function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dbaf2-107">Требования</span><span class="sxs-lookup"><span data-stu-id="dbaf2-107">Requirements</span></span>  
 <span data-ttu-id="dbaf2-108">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dbaf2-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dbaf2-109">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="dbaf2-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="dbaf2-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dbaf2-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dbaf2-111">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dbaf2-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

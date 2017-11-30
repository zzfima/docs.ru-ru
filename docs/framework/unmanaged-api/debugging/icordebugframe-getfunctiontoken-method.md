---
title: "Метод ICorDebugFrame::GetFunctionToken"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugFrame.GetFunctionToken
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugFrame::GetFunctionToken
helpviewer_keywords:
- ICorDebugFrame::GetFunctionToken method [.NET Framework debugging]
- GetFunctionToken method [.NET Framework debugging]
ms.assetid: a46925b3-3bf8-404f-9f30-a86ae41032c1
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d7a3e4300c32a32fd76f253d34581f53e4afd95e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugframegetfunctiontoken-method"></a><span data-ttu-id="6d7fd-102">Метод ICorDebugFrame::GetFunctionToken</span><span class="sxs-lookup"><span data-stu-id="6d7fd-102">ICorDebugFrame::GetFunctionToken Method</span></span>
<span data-ttu-id="6d7fd-103">Получает маркер метаданных для функции, которая содержит код, связанный с данным кадром стека.</span><span class="sxs-lookup"><span data-stu-id="6d7fd-103">Gets the metadata token for the function that contains the code associated with this stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6d7fd-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6d7fd-104">Syntax</span></span>  
  
```  
HRESULT GetFunctionToken (  
    [out] mdMethodDef        *pToken  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6d7fd-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="6d7fd-105">Parameters</span></span>  
 `pToken`  
 <span data-ttu-id="6d7fd-106">[out] Указатель на `mdMethodDef` маркер, который ссылается на метаданные для функции.</span><span class="sxs-lookup"><span data-stu-id="6d7fd-106">[out] A pointer to an `mdMethodDef` token that references the metadata for the function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6d7fd-107">Требования</span><span class="sxs-lookup"><span data-stu-id="6d7fd-107">Requirements</span></span>  
 <span data-ttu-id="6d7fd-108">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6d7fd-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6d7fd-109">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6d7fd-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6d7fd-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6d7fd-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6d7fd-111">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6d7fd-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

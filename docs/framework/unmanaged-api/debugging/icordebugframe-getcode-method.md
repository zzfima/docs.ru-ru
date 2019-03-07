---
title: Метод ICorDebugFrame::GetCode
ms.date: 03/30/2017
api_name:
- ICorDebugFrame.GetCode
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrame::GetCode
helpviewer_keywords:
- GetCode method, ICorDebugFrame interface [.NET Framework debugging]
- ICorDebugFrame::GetCode method [.NET Framework debugging]
ms.assetid: fbaa0794-a031-4015-8beb-2749e47ac340
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e7a4e8c6fa91ee43c33fe0f99d50bd4b1af4a0fd
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57481200"
---
# <a name="icordebugframegetcode-method"></a><span data-ttu-id="a5900-102">Метод ICorDebugFrame::GetCode</span><span class="sxs-lookup"><span data-stu-id="a5900-102">ICorDebugFrame::GetCode Method</span></span>
<span data-ttu-id="a5900-103">Возвращает указатель на код, связанный с данным кадром стека.</span><span class="sxs-lookup"><span data-stu-id="a5900-103">Gets a pointer to the code associated with this stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a5900-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a5900-104">Syntax</span></span>  
  
```  
HRESULT GetCode (  
    [out] ICorDebugCode      **ppCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a5900-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="a5900-105">Parameters</span></span>  
 `ppCode`  
 <span data-ttu-id="a5900-106">[out] Указатель на адрес объекта ICorDebugCode, представляющее код, связанный с данным кадром.</span><span class="sxs-lookup"><span data-stu-id="a5900-106">[out] A pointer to the address of an ICorDebugCode object that represents the code associated with this frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a5900-107">Требования</span><span class="sxs-lookup"><span data-stu-id="a5900-107">Requirements</span></span>  
 <span data-ttu-id="a5900-108">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a5900-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a5900-109">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a5900-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a5900-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a5900-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a5900-111">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a5900-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

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
ms.openlocfilehash: ca64e392b930ed57691f05ae771bbaf305df8eb3
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67754073"
---
# <a name="icordebugframegetcode-method"></a><span data-ttu-id="549fd-102">Метод ICorDebugFrame::GetCode</span><span class="sxs-lookup"><span data-stu-id="549fd-102">ICorDebugFrame::GetCode Method</span></span>
<span data-ttu-id="549fd-103">Возвращает указатель на код, связанный с данным кадром стека.</span><span class="sxs-lookup"><span data-stu-id="549fd-103">Gets a pointer to the code associated with this stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="549fd-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="549fd-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCode (  
    [out] ICorDebugCode      **ppCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="549fd-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="549fd-105">Parameters</span></span>  
 `ppCode`  
 <span data-ttu-id="549fd-106">[out] Указатель на адрес объекта ICorDebugCode, представляющее код, связанный с данным кадром.</span><span class="sxs-lookup"><span data-stu-id="549fd-106">[out] A pointer to the address of an ICorDebugCode object that represents the code associated with this frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="549fd-107">Требования</span><span class="sxs-lookup"><span data-stu-id="549fd-107">Requirements</span></span>  
 <span data-ttu-id="549fd-108">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="549fd-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="549fd-109">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="549fd-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="549fd-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="549fd-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="549fd-111">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="549fd-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

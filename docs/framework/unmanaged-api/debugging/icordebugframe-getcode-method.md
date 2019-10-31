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
ms.openlocfilehash: 9a4f533c0ab817d800c2d35b7d64c7aee78faaea
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121171"
---
# <a name="icordebugframegetcode-method"></a><span data-ttu-id="61e0a-102">Метод ICorDebugFrame::GetCode</span><span class="sxs-lookup"><span data-stu-id="61e0a-102">ICorDebugFrame::GetCode Method</span></span>
<span data-ttu-id="61e0a-103">Возвращает указатель на код, связанный с этим кадром стека.</span><span class="sxs-lookup"><span data-stu-id="61e0a-103">Gets a pointer to the code associated with this stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="61e0a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="61e0a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCode (  
    [out] ICorDebugCode      **ppCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="61e0a-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="61e0a-105">Parameters</span></span>  
 `ppCode`  
 <span data-ttu-id="61e0a-106">заполняет Указатель на адрес объекта ICorDebugCode, представляющий код, связанный с этим кадром.</span><span class="sxs-lookup"><span data-stu-id="61e0a-106">[out] A pointer to the address of an ICorDebugCode object that represents the code associated with this frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="61e0a-107">Требования</span><span class="sxs-lookup"><span data-stu-id="61e0a-107">Requirements</span></span>  
 <span data-ttu-id="61e0a-108">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="61e0a-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="61e0a-109">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="61e0a-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="61e0a-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="61e0a-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="61e0a-111">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="61e0a-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

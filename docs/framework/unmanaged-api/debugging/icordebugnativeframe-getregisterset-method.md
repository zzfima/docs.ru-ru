---
title: Метод ICorDebugNativeFrame::GetRegisterSet
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame.GetRegisterSet
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame::GetRegisterSet
helpviewer_keywords:
- ICorDebugNativeFrame::GetRegisterSet method [.NET Framework debugging]
- GetRegisterSet method, ICorDebugNativeFrame interface [.NET Framework debugging]
ms.assetid: 6f309b5f-5556-4f1e-b1dd-4fe97fc81d01
topic_type:
- apiref
ms.openlocfilehash: ac7601f89c125cecbfbd212118420a800f495742
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73096815"
---
# <a name="icordebugnativeframegetregisterset-method"></a><span data-ttu-id="ba4ea-102">Метод ICorDebugNativeFrame::GetRegisterSet</span><span class="sxs-lookup"><span data-stu-id="ba4ea-102">ICorDebugNativeFrame::GetRegisterSet Method</span></span>
<span data-ttu-id="ba4ea-103">Возвращает набор регистров для этого кадра стека.</span><span class="sxs-lookup"><span data-stu-id="ba4ea-103">Gets the register set for this stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ba4ea-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ba4ea-104">Syntax</span></span>  
  
```cpp  
HRESULT GetRegisterSet (  
    [out] ICorDebugRegisterSet **ppRegisters  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ba4ea-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="ba4ea-105">Parameters</span></span>  
 `ppRegisters`  
 <span data-ttu-id="ba4ea-106">заполняет Указатель на адрес объекта [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) , который представляет набор регистров для данного кадра стека.</span><span class="sxs-lookup"><span data-stu-id="ba4ea-106">[out] A pointer to the address of an [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) object that represents the register set for this stack frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ba4ea-107">Требования</span><span class="sxs-lookup"><span data-stu-id="ba4ea-107">Requirements</span></span>  
 <span data-ttu-id="ba4ea-108">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ba4ea-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ba4ea-109">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ba4ea-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ba4ea-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ba4ea-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ba4ea-111">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ba4ea-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba4ea-112">См. также</span><span class="sxs-lookup"><span data-stu-id="ba4ea-112">See also</span></span>

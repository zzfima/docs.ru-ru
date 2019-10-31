---
title: Метод ICorDebugChain::GetActiveFrame
ms.date: 03/30/2017
api_name:
- ICorDebugChain.GetActiveFrame
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain::GetActiveFrame
helpviewer_keywords:
- ICorDebugChain::GetActiveFrame method [.NET Framework debugging]
- GetActiveFrame method, ICorDebugChain interface [.NET Framework debugging]
ms.assetid: 36887017-670b-4f21-b406-8fab956f84a3
topic_type:
- apiref
ms.openlocfilehash: 03cb1556ee971124ed4c591f38d9f892fc7df7b0
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73192147"
---
# <a name="icordebugchaingetactiveframe-method"></a><span data-ttu-id="568e2-102">Метод ICorDebugChain::GetActiveFrame</span><span class="sxs-lookup"><span data-stu-id="568e2-102">ICorDebugChain::GetActiveFrame Method</span></span>
<span data-ttu-id="568e2-103">Возвращает активный (то есть самый последний) кадр в цепочке.</span><span class="sxs-lookup"><span data-stu-id="568e2-103">Gets the active (that is, most recent) frame on the chain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="568e2-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="568e2-104">Syntax</span></span>  
  
```cpp  
HRESULT GetActiveFrame (  
    [out] ICorDebugFrame   **ppFrame  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="568e2-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="568e2-105">Parameters</span></span>  
 `ppFrame`  
 <span data-ttu-id="568e2-106">заполняет Указатель на адрес объекта ICorDebugFrame, который представляет активный (то есть самый последний) кадр в цепочке.</span><span class="sxs-lookup"><span data-stu-id="568e2-106">[out] A pointer to the address of an ICorDebugFrame object that represents the active (that is, most recent) frame on the chain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="568e2-107">Заметки</span><span class="sxs-lookup"><span data-stu-id="568e2-107">Remarks</span></span>  
 <span data-ttu-id="568e2-108">Если управляемый фрейм стека недоступен, `ppFrame` имеет значение null.</span><span class="sxs-lookup"><span data-stu-id="568e2-108">If no managed stack frame is available, `ppFrame` is set to null.</span></span>  
  
 <span data-ttu-id="568e2-109">Если активный кадр недоступен, вызов будет выполнен, а `ppFrame` будет иметь значение null.</span><span class="sxs-lookup"><span data-stu-id="568e2-109">If the active frame is not available, the call will succeed and `ppFrame` will be null.</span></span> <span data-ttu-id="568e2-110">Активные фреймы не будут доступны для цепочек, инициированных из-за CHAIN_ENTER_UNMANAGED, и для некоторых цепочек, инициированных из-за CHAIN_CLASS_INIT.</span><span class="sxs-lookup"><span data-stu-id="568e2-110">Active frames will not be available for chains initiated due to CHAIN_ENTER_UNMANAGED, and for some chains initiated due to CHAIN_CLASS_INIT.</span></span> <span data-ttu-id="568e2-111">См. раздел перечисление Кордебугчаинреасон.</span><span class="sxs-lookup"><span data-stu-id="568e2-111">See the CorDebugChainReason enumeration.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="568e2-112">Требования</span><span class="sxs-lookup"><span data-stu-id="568e2-112">Requirements</span></span>  
 <span data-ttu-id="568e2-113">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="568e2-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="568e2-114">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="568e2-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="568e2-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="568e2-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="568e2-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="568e2-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

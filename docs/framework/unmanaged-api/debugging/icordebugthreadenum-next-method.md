---
title: Метод ICorDebugThreadEnum::Next
ms.date: 03/30/2017
api_name:
- ICorDebugThreadEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThreadEnum::Next
helpviewer_keywords:
- ICorDebugThreadEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugThreadEnum interface [.NET Framework debugging]
ms.assetid: f967c93d-9a7f-4aaf-99a1-a1317899ff3f
topic_type:
- apiref
ms.openlocfilehash: 0c455706b0d644d2444e9fbdf49c5a5d4f5295a9
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122390"
---
# <a name="icordebugthreadenumnext-method"></a><span data-ttu-id="e17d1-102">Метод ICorDebugThreadEnum::Next</span><span class="sxs-lookup"><span data-stu-id="e17d1-102">ICorDebugThreadEnum::Next Method</span></span>
<span data-ttu-id="e17d1-103">Возвращает число указанных экземпляров ICorDebugThread из перечисления, начиная с текущей позиции.</span><span class="sxs-lookup"><span data-stu-id="e17d1-103">Gets the number of specified ICorDebugThread instances from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e17d1-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e17d1-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugThread *threads[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e17d1-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="e17d1-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="e17d1-106">окне Число извлекаемых экземпляров `ICorDebugThread`.</span><span class="sxs-lookup"><span data-stu-id="e17d1-106">[in] The number of `ICorDebugThread` instances to be retrieved.</span></span>  
  
 `threads`  
 <span data-ttu-id="e17d1-107">заполняет Массив указателей, каждый из которых указывает на объект `ICorDebugThread`, представляющий поток.</span><span class="sxs-lookup"><span data-stu-id="e17d1-107">[out] An array of pointers, each of which points to an `ICorDebugThread` object that represents a thread.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="e17d1-108">заполняет Указатель на число фактически возвращаемых экземпляров `ICorDebugThread`.</span><span class="sxs-lookup"><span data-stu-id="e17d1-108">[out] Pointer to the number of `ICorDebugThread` instances actually returned.</span></span> <span data-ttu-id="e17d1-109">Это значение может быть равно null, если `celt` является одним.</span><span class="sxs-lookup"><span data-stu-id="e17d1-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e17d1-110">Требования</span><span class="sxs-lookup"><span data-stu-id="e17d1-110">Requirements</span></span>  
 <span data-ttu-id="e17d1-111">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e17d1-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e17d1-112">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e17d1-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e17d1-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e17d1-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e17d1-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e17d1-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

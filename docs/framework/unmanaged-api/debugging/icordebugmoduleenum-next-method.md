---
title: Метод ICorDebugModuleEnum::Next
ms.date: 03/30/2017
api_name:
- ICorDebugModuleEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModuleEnum::Next
helpviewer_keywords:
- ICorDebugModuleEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugModuleEnum interface [.NET Framework debugging]
ms.assetid: 9ff3fcd6-38fe-41f8-bfd3-f0ab6c7d77ca
topic_type:
- apiref
ms.openlocfilehash: 6c4262c18e4efcbbca1b3e2a327fec7d4b609a31
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73096927"
---
# <a name="icordebugmoduleenumnext-method"></a><span data-ttu-id="9d909-102">Метод ICorDebugModuleEnum::Next</span><span class="sxs-lookup"><span data-stu-id="9d909-102">ICorDebugModuleEnum::Next Method</span></span>
<span data-ttu-id="9d909-103">Возвращает количество экземпляров "ICorDebugModule", заданных `celt` из перечисления, начиная с текущей позиции.</span><span class="sxs-lookup"><span data-stu-id="9d909-103">Gets the number of "ICorDebugModule" instances specified by `celt` from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9d909-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9d909-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in]  ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugModule *modules[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9d909-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="9d909-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="9d909-106">окне Число извлекаемых экземпляров `ICorDebugModule`.</span><span class="sxs-lookup"><span data-stu-id="9d909-106">[in] The number of `ICorDebugModule` instances to be retrieved.</span></span>  
  
 `modules`  
 <span data-ttu-id="9d909-107">заполняет Массив указателей, каждый из которых указывает на объект `ICorDebugModule`.</span><span class="sxs-lookup"><span data-stu-id="9d909-107">[out] An array of pointers, each of which points to an `ICorDebugModule` object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="9d909-108">заполняет Указатель на число фактически возвращаемых экземпляров `ICorDebugModule`.</span><span class="sxs-lookup"><span data-stu-id="9d909-108">[out] Pointer to the number of `ICorDebugModule` instances actually returned.</span></span> <span data-ttu-id="9d909-109">Это значение может быть равно null, если `celt` является одним.</span><span class="sxs-lookup"><span data-stu-id="9d909-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9d909-110">Требования</span><span class="sxs-lookup"><span data-stu-id="9d909-110">Requirements</span></span>  
 <span data-ttu-id="9d909-111">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9d909-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9d909-112">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9d909-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9d909-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9d909-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9d909-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9d909-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d909-115">См. также</span><span class="sxs-lookup"><span data-stu-id="9d909-115">See also</span></span>

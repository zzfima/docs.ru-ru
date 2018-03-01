---
title: "Метод ICorDebugValueEnum::Next"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorDebugValueEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValueEnum::Next
helpviewer_keywords:
- ICorDebugValueEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugValueEnum interface [.NET Framework debugging]
ms.assetid: f5ef94dd-dfee-49d3-a398-b110f8906dd8
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 4a497488c06dd387f65182318c22f3189dfd7725
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugvalueenumnext-method"></a><span data-ttu-id="391ba-102">Метод ICorDebugValueEnum::Next</span><span class="sxs-lookup"><span data-stu-id="391ba-102">ICorDebugValueEnum::Next Method</span></span>
<span data-ttu-id="391ba-103">Получает заданное число экземпляров «ICorDebugValue» из перечисления, начиная с текущей позиции.</span><span class="sxs-lookup"><span data-stu-id="391ba-103">Gets the specified number of "ICorDebugValue" instances from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="391ba-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="391ba-104">Syntax</span></span>  
  
```  
HRESULT Next (  
    [in]  ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugValue *values[],  
    [out] ULONG *pceltFetched  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="391ba-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="391ba-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="391ba-106">[in] Количество `ICorDebugValue` извлекаемых экземпляров.</span><span class="sxs-lookup"><span data-stu-id="391ba-106">[in] The number of `ICorDebugValue` instances to be retrieved.</span></span>  
  
 `values`  
 <span data-ttu-id="391ba-107">[out] Массив указателей, каждый из которых указывает на `ICorDebugValue` объекта.</span><span class="sxs-lookup"><span data-stu-id="391ba-107">[out] An array of pointers, each of which points to an `ICorDebugValue` object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="391ba-108">[out] Указатель на число `ICorDebugValue` фактически возвращаемых экземпляров.</span><span class="sxs-lookup"><span data-stu-id="391ba-108">[out] Pointer to the number of `ICorDebugValue` instances actually returned.</span></span> <span data-ttu-id="391ba-109">Это значение может быть значение null, если `celt` — один.</span><span class="sxs-lookup"><span data-stu-id="391ba-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="391ba-110">Требования</span><span class="sxs-lookup"><span data-stu-id="391ba-110">Requirements</span></span>  
 <span data-ttu-id="391ba-111">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="391ba-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="391ba-112">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="391ba-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="391ba-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="391ba-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="391ba-114">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="391ba-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="391ba-115">См. также</span><span class="sxs-lookup"><span data-stu-id="391ba-115">See Also</span></span>  
    
 

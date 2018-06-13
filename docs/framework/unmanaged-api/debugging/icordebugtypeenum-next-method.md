---
title: Метод ICorDebugTypeEnum::Next
ms.date: 03/30/2017
api_name:
- ICorDebugTypeEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugTypeEnum::Next
helpviewer_keywords:
- ICorDebugTypeEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugTypeEnum interface [.NET Framework debugging]
ms.assetid: d0fdeba3-c195-4ece-8caf-79b1f40025d2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9812fa4248533ccb898c98082e42e288c091f776
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33420590"
---
# <a name="icordebugtypeenumnext-method"></a><span data-ttu-id="3d15b-102">Метод ICorDebugTypeEnum::Next</span><span class="sxs-lookup"><span data-stu-id="3d15b-102">ICorDebugTypeEnum::Next Method</span></span>
<span data-ttu-id="3d15b-103">Возвращает число экземпляров «ICorDebugType», заданных параметром `celt` из перечисления, начиная с текущей позиции.</span><span class="sxs-lookup"><span data-stu-id="3d15b-103">Gets the number of "ICorDebugType" instances specified by `celt` from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3d15b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3d15b-104">Syntax</span></span>  
  
```  
HRESULT Next (  
    [in]  ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugType *values[],  
    [out] ULONG *pceltFetched  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3d15b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="3d15b-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="3d15b-106">[in] Количество `ICorDebugType` извлекаемых экземпляров.</span><span class="sxs-lookup"><span data-stu-id="3d15b-106">[in] The number of `ICorDebugType` instances to be retrieved.</span></span>  
  
 `values`  
 <span data-ttu-id="3d15b-107">[out] Массив указателей, каждый из которых указывает на `ICorDebugType` объекта.</span><span class="sxs-lookup"><span data-stu-id="3d15b-107">[out] An array of pointers, each of which points to an `ICorDebugType` object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="3d15b-108">[out] Указатель на число `ICorDebugType` фактически возвращаемых экземпляров.</span><span class="sxs-lookup"><span data-stu-id="3d15b-108">[out] Pointer to the number of `ICorDebugType` instances actually returned.</span></span> <span data-ttu-id="3d15b-109">Это значение может быть значение null, если `celt` — один.</span><span class="sxs-lookup"><span data-stu-id="3d15b-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3d15b-110">Требования</span><span class="sxs-lookup"><span data-stu-id="3d15b-110">Requirements</span></span>  
 <span data-ttu-id="3d15b-111">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3d15b-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3d15b-112">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3d15b-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3d15b-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3d15b-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3d15b-114">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3d15b-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d15b-115">См. также</span><span class="sxs-lookup"><span data-stu-id="3d15b-115">See Also</span></span>  
 

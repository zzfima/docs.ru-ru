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
ms.openlocfilehash: d47f14ff2adb37fca16cf6774a2b80cb2e074b17
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59157317"
---
# <a name="icordebugtypeenumnext-method"></a><span data-ttu-id="2028d-102">Метод ICorDebugTypeEnum::Next</span><span class="sxs-lookup"><span data-stu-id="2028d-102">ICorDebugTypeEnum::Next Method</span></span>
<span data-ttu-id="2028d-103">Возвращает число экземпляров «ICorDebugType», определяемое `celt` из перечисления, начиная с текущей позиции.</span><span class="sxs-lookup"><span data-stu-id="2028d-103">Gets the number of "ICorDebugType" instances specified by `celt` from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2028d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2028d-104">Syntax</span></span>  
  
```  
HRESULT Next (  
    [in]  ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugType *values[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2028d-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="2028d-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="2028d-106">[in] Количество `ICorDebugType` извлекаемых экземпляров.</span><span class="sxs-lookup"><span data-stu-id="2028d-106">[in] The number of `ICorDebugType` instances to be retrieved.</span></span>  
  
 `values`  
 <span data-ttu-id="2028d-107">[out] Массив указателей, каждый из которых указывает `ICorDebugType` объекта.</span><span class="sxs-lookup"><span data-stu-id="2028d-107">[out] An array of pointers, each of which points to an `ICorDebugType` object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="2028d-108">[out] Указатель на число `ICorDebugType` фактически возвращенных экземпляров.</span><span class="sxs-lookup"><span data-stu-id="2028d-108">[out] Pointer to the number of `ICorDebugType` instances actually returned.</span></span> <span data-ttu-id="2028d-109">Это значение может иметь значение null Если `celt` — один.</span><span class="sxs-lookup"><span data-stu-id="2028d-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2028d-110">Требования</span><span class="sxs-lookup"><span data-stu-id="2028d-110">Requirements</span></span>  
 <span data-ttu-id="2028d-111">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2028d-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2028d-112">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2028d-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2028d-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2028d-113">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="2028d-114">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="2028d-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="2028d-115">См. также</span><span class="sxs-lookup"><span data-stu-id="2028d-115">See also</span></span>

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
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59157317"
---
# <a name="icordebugtypeenumnext-method"></a><span data-ttu-id="96c20-102">Метод ICorDebugTypeEnum::Next</span><span class="sxs-lookup"><span data-stu-id="96c20-102">ICorDebugTypeEnum::Next Method</span></span>
<span data-ttu-id="96c20-103">Возвращает число экземпляров «ICorDebugType», определяемое `celt` из перечисления, начиная с текущей позиции.</span><span class="sxs-lookup"><span data-stu-id="96c20-103">Gets the number of "ICorDebugType" instances specified by `celt` from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="96c20-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="96c20-104">Syntax</span></span>  
  
```  
HRESULT Next (  
    [in]  ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugType *values[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="96c20-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="96c20-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="96c20-106">[in] Количество `ICorDebugType` извлекаемых экземпляров.</span><span class="sxs-lookup"><span data-stu-id="96c20-106">[in] The number of `ICorDebugType` instances to be retrieved.</span></span>  
  
 `values`  
 <span data-ttu-id="96c20-107">[out] Массив указателей, каждый из которых указывает `ICorDebugType` объекта.</span><span class="sxs-lookup"><span data-stu-id="96c20-107">[out] An array of pointers, each of which points to an `ICorDebugType` object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="96c20-108">[out] Указатель на число `ICorDebugType` фактически возвращенных экземпляров.</span><span class="sxs-lookup"><span data-stu-id="96c20-108">[out] Pointer to the number of `ICorDebugType` instances actually returned.</span></span> <span data-ttu-id="96c20-109">Это значение может иметь значение null Если `celt` — один.</span><span class="sxs-lookup"><span data-stu-id="96c20-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="96c20-110">Требования</span><span class="sxs-lookup"><span data-stu-id="96c20-110">Requirements</span></span>  
 <span data-ttu-id="96c20-111">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="96c20-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="96c20-112">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="96c20-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="96c20-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="96c20-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="96c20-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="96c20-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96c20-115">См. также</span><span class="sxs-lookup"><span data-stu-id="96c20-115">See also</span></span>

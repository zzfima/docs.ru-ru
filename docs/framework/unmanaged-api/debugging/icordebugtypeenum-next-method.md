---
title: "Метод ICorDebugTypeEnum::Next"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugTypeEnum.Next
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugTypeEnum::Next
helpviewer_keywords:
- ICorDebugTypeEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugTypeEnum interface [.NET Framework debugging]
ms.assetid: d0fdeba3-c195-4ece-8caf-79b1f40025d2
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 38f48c379ad4d84c2b16c208b33b71ac75caa52f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugtypeenumnext-method"></a><span data-ttu-id="18db6-102">Метод ICorDebugTypeEnum::Next</span><span class="sxs-lookup"><span data-stu-id="18db6-102">ICorDebugTypeEnum::Next Method</span></span>
<span data-ttu-id="18db6-103">Возвращает число экземпляров «ICorDebugType», заданных параметром `celt` из перечисления, начиная с текущей позиции.</span><span class="sxs-lookup"><span data-stu-id="18db6-103">Gets the number of "ICorDebugType" instances specified by `celt` from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="18db6-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="18db6-104">Syntax</span></span>  
  
```  
HRESULT Next (  
    [in]  ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugType *values[],  
    [out] ULONG *pceltFetched  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="18db6-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="18db6-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="18db6-106">[in] Количество `ICorDebugType` извлекаемых экземпляров.</span><span class="sxs-lookup"><span data-stu-id="18db6-106">[in] The number of `ICorDebugType` instances to be retrieved.</span></span>  
  
 `values`  
 <span data-ttu-id="18db6-107">[out] Массив указателей, каждый из которых указывает на `ICorDebugType` объекта.</span><span class="sxs-lookup"><span data-stu-id="18db6-107">[out] An array of pointers, each of which points to an `ICorDebugType` object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="18db6-108">[out] Указатель на число `ICorDebugType` фактически возвращаемых экземпляров.</span><span class="sxs-lookup"><span data-stu-id="18db6-108">[out] Pointer to the number of `ICorDebugType` instances actually returned.</span></span> <span data-ttu-id="18db6-109">Это значение может быть значение null, если `celt` — один.</span><span class="sxs-lookup"><span data-stu-id="18db6-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="18db6-110">Требования</span><span class="sxs-lookup"><span data-stu-id="18db6-110">Requirements</span></span>  
 <span data-ttu-id="18db6-111">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="18db6-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="18db6-112">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="18db6-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="18db6-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="18db6-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="18db6-114">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="18db6-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18db6-115">См. также</span><span class="sxs-lookup"><span data-stu-id="18db6-115">See Also</span></span>  
 

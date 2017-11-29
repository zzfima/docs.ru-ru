---
title: "Метод ICorDebugThreadEnum::Next"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugThreadEnum.Next
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugThreadEnum::Next
helpviewer_keywords:
- ICorDebugThreadEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugThreadEnum interface [.NET Framework debugging]
ms.assetid: f967c93d-9a7f-4aaf-99a1-a1317899ff3f
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: cb26dd4cd625c025685113611a189b51a4d56a99
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugthreadenumnext-method"></a><span data-ttu-id="49fe7-102">Метод ICorDebugThreadEnum::Next</span><span class="sxs-lookup"><span data-stu-id="49fe7-102">ICorDebugThreadEnum::Next Method</span></span>
<span data-ttu-id="49fe7-103">Возвращает количество экземпляров указанного ICorDebugThread из перечисления, начиная с текущей позиции.</span><span class="sxs-lookup"><span data-stu-id="49fe7-103">Gets the number of specified ICorDebugThread instances from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="49fe7-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="49fe7-104">Syntax</span></span>  
  
```  
HRESULT Next (  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugThread *threads[],  
    [out] ULONG *pceltFetched  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="49fe7-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="49fe7-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="49fe7-106">[in] Количество `ICorDebugThread` извлекаемых экземпляров.</span><span class="sxs-lookup"><span data-stu-id="49fe7-106">[in] The number of `ICorDebugThread` instances to be retrieved.</span></span>  
  
 `threads`  
 <span data-ttu-id="49fe7-107">[out] Массив указателей, каждый из которых указывает на `ICorDebugThread` , представляющий поток.</span><span class="sxs-lookup"><span data-stu-id="49fe7-107">[out] An array of pointers, each of which points to an `ICorDebugThread` object that represents a thread.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="49fe7-108">[out] Указатель на число `ICorDebugThread` фактически возвращаемых экземпляров.</span><span class="sxs-lookup"><span data-stu-id="49fe7-108">[out] Pointer to the number of `ICorDebugThread` instances actually returned.</span></span> <span data-ttu-id="49fe7-109">Это значение может быть значение null, если `celt` — один.</span><span class="sxs-lookup"><span data-stu-id="49fe7-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="49fe7-110">Требования</span><span class="sxs-lookup"><span data-stu-id="49fe7-110">Requirements</span></span>  
 <span data-ttu-id="49fe7-111">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="49fe7-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="49fe7-112">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="49fe7-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="49fe7-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="49fe7-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="49fe7-114">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="49fe7-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

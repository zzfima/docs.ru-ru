---
title: "Метод ICorDebugAssemblyEnum::Next"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugAssemblyEnum.Next
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugAssemblyEnum::Next method
helpviewer_keywords:
- ICorDebugAssemblyEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugAssemblyEnum interface [.NET Framework debugging]
ms.assetid: b3e7d0c2-3baa-4ef8-8e3f-b865cf252940
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 69f43a24caff7e67f307bbf4521094e8ebfd98cf
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugassemblyenumnext-method"></a><span data-ttu-id="923df-102">Метод ICorDebugAssemblyEnum::Next</span><span class="sxs-lookup"><span data-stu-id="923df-102">ICorDebugAssemblyEnum::Next Method</span></span>
<span data-ttu-id="923df-103">Возвращает заданное число сборок из коллекции, начиная с текущей позиции курсора.</span><span class="sxs-lookup"><span data-stu-id="923df-103">Gets the specified number of assemblies from the collection, starting at the current cursor position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="923df-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="923df-104">Syntax</span></span>  
  
```  
HRESULT Next (  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugAssembly *values[],  
    [out] ULONG *pceltFetched  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="923df-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="923df-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="923df-106">[in] Число сборок, которые требуется получить.</span><span class="sxs-lookup"><span data-stu-id="923df-106">[in] The number of assemblies to be retrieved.</span></span>  
  
 `values`  
 <span data-ttu-id="923df-107">[out] Массив указателей, каждый из которых указывает на объект ICorDebugAssembly, представляет сборку.</span><span class="sxs-lookup"><span data-stu-id="923df-107">[out] An array of pointers, each of which points to an ICorDebugAssembly object that represents an assembly.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="923df-108">[out] Указатель на число сборок, фактически извлеченных.</span><span class="sxs-lookup"><span data-stu-id="923df-108">[out] A pointer to the number of assemblies actually returned.</span></span> <span data-ttu-id="923df-109">Это значение может быть значение null, если `celt` — один.</span><span class="sxs-lookup"><span data-stu-id="923df-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="923df-110">Требования</span><span class="sxs-lookup"><span data-stu-id="923df-110">Requirements</span></span>  
 <span data-ttu-id="923df-111">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="923df-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="923df-112">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="923df-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="923df-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="923df-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="923df-114">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="923df-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

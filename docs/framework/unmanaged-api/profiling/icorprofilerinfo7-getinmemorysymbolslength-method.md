---
title: "Метод ICorProfilerInfo7::GetInMemorySymbolsLength"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
api_name: ICorProfilerInfo7.GetInMemorySymbolsLength
api_location:
- mscorwks.dll
- icorprof.idl
api_type: COM
ms.assetid: d62c4a4c-8a62-45aa-8f01-a8387cf36159
caps.latest.revision: "3"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 34da00bdc33a836e5f459e6e4314f252e1e39e9b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilerinfo7getinmemorysymbolslength-method"></a><span data-ttu-id="ba6e4-102">Метод ICorProfilerInfo7::GetInMemorySymbolsLength</span><span class="sxs-lookup"><span data-stu-id="ba6e4-102">ICorProfilerInfo7::GetInMemorySymbolsLength Method</span></span>
<span data-ttu-id="ba6e4-103">[Поддерживается в .NET Framework 4.6.1 и более поздних версиях.]</span><span class="sxs-lookup"><span data-stu-id="ba6e4-103">[Supported in the .NET Framework 4.6.1 and later versions]</span></span>  
  
 <span data-ttu-id="ba6e4-104">Возвращает длину потока в памяти символа.</span><span class="sxs-lookup"><span data-stu-id="ba6e4-104">Returns the length of an in-memory symbol stream.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ba6e4-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ba6e4-105">Syntax</span></span>  
  
```  
HRESULT GetInMemorySymbolsLength(  
        [in] ModuleID moduleId,  
        [out] DWORD* pCountSymbolBytes  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ba6e4-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="ba6e4-106">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="ba6e4-107">[in] Идентификатор модуля, содержащего потока в памяти.</span><span class="sxs-lookup"><span data-stu-id="ba6e4-107">[in] The identifier of the module containing the in-memory stream.</span></span>  
  
 <span data-ttu-id="ba6e4-108">pCountSymbolBytes</span><span class="sxs-lookup"><span data-stu-id="ba6e4-108">pCountSymbolBytes</span></span>  
 <span data-ttu-id="ba6e4-109">[out] Указатель на `DWORD` значение, которое при возврате из метода содержит длину потока в байтах.</span><span class="sxs-lookup"><span data-stu-id="ba6e4-109">[out] A pointer to a `DWORD` value that, when the method returns, contains the length of the stream in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ba6e4-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="ba6e4-110">Return Value</span></span>  
 <span data-ttu-id="ba6e4-111">Метод возвращает `S_OK` Если длина потока памяти может определяться, даже если оно равно нулю (0).</span><span class="sxs-lookup"><span data-stu-id="ba6e4-111">The method returns `S_OK` if the length of the memory stream can be determined, even if it is zero (0).</span></span>  
  
 <span data-ttu-id="ba6e4-112">Метод возвращает `CORPROF_E_MODULE_IS_DYNAMIC` метод создан с помощью <xref:System.Reflection.Emit?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="ba6e4-112">The method returns `CORPROF_E_MODULE_IS_DYNAMIC` if the method was created using <xref:System.Reflection.Emit?displayProperty=nameWithType>.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ba6e4-113">Примечания</span><span class="sxs-lookup"><span data-stu-id="ba6e4-113">Remarks</span></span>  
 <span data-ttu-id="ba6e4-114">Если модуль содержит символы в памяти, длина потока помещается в `pCountSymbolBytes`.</span><span class="sxs-lookup"><span data-stu-id="ba6e4-114">If the module has in-memory symbols, the length of the stream is placed in `pCountSymbolBytes`.</span></span> <span data-ttu-id="ba6e4-115">Если модуль не содержит символов в памяти `*pCountSymbolBytes = 0`.</span><span class="sxs-lookup"><span data-stu-id="ba6e4-115">If the module doesn't have in-memory     symbols, `*pCountSymbolBytes = 0`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ba6e4-116">Текущая реализация не поддерживает Reflection.Emit.</span><span class="sxs-lookup"><span data-stu-id="ba6e4-116">The current implementation does not support Reflection.Emit.</span></span> <span data-ttu-id="ba6e4-117">Если модуль был создан с помощью Reflection.Emit, метод возвращает `CORPROF_E_MODULE_IS_DYNAMIC`.</span><span class="sxs-lookup"><span data-stu-id="ba6e4-117">If the module was created by using Reflection.Emit, the method returns `CORPROF_E_MODULE_IS_DYNAMIC`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ba6e4-118">Требования</span><span class="sxs-lookup"><span data-stu-id="ba6e4-118">Requirements</span></span>  
 <span data-ttu-id="ba6e4-119">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ba6e4-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ba6e4-120">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ba6e4-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ba6e4-121">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ba6e4-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ba6e4-122">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ba6e4-122">**.NET Framework Versions:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba6e4-123">См. также</span><span class="sxs-lookup"><span data-stu-id="ba6e4-123">See Also</span></span>  
 [<span data-ttu-id="ba6e4-124">Интерфейс ICorProfilerInfo7</span><span class="sxs-lookup"><span data-stu-id="ba6e4-124">ICorProfilerInfo7 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-interface.md)

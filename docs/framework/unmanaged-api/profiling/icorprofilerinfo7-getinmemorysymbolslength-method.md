---
title: 'Метод ICorProfilerInfo7:: GetInMemorySymbolsLength'
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo7.GetInMemorySymbolsLength
api_location:
- mscorwks.dll
- icorprof.idl
api_type:
- COM
ms.assetid: d62c4a4c-8a62-45aa-8f01-a8387cf36159
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 157b0e215f8afa58cccb3d54a65baa9c307ba966
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69955423"
---
# <a name="icorprofilerinfo7getinmemorysymbolslength-method"></a><span data-ttu-id="3ba66-102">Метод ICorProfilerInfo7:: GetInMemorySymbolsLength</span><span class="sxs-lookup"><span data-stu-id="3ba66-102">ICorProfilerInfo7::GetInMemorySymbolsLength Method</span></span>
<span data-ttu-id="3ba66-103">[Поддерживается в .NET Framework 4.6.1 и более поздних версиях.]</span><span class="sxs-lookup"><span data-stu-id="3ba66-103">[Supported in the .NET Framework 4.6.1 and later versions]</span></span>  
  
 <span data-ttu-id="3ba66-104">Возвращает длину потока символов в памяти.</span><span class="sxs-lookup"><span data-stu-id="3ba66-104">Returns the length of an in-memory symbol stream.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3ba66-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3ba66-105">Syntax</span></span>  
  
```cpp  
HRESULT GetInMemorySymbolsLength(  
        [in] ModuleID moduleId,  
        [out] DWORD* pCountSymbolBytes  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3ba66-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="3ba66-106">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="3ba66-107">окне Идентификатор модуля, содержащего поток в памяти.</span><span class="sxs-lookup"><span data-stu-id="3ba66-107">[in] The identifier of the module containing the in-memory stream.</span></span>  
  
 <span data-ttu-id="3ba66-108">пкаунтсимболбитес</span><span class="sxs-lookup"><span data-stu-id="3ba66-108">pCountSymbolBytes</span></span>  
 <span data-ttu-id="3ba66-109">заполняет Указатель на `DWORD` значение, которое при возврате метода содержит длину потока в байтах.</span><span class="sxs-lookup"><span data-stu-id="3ba66-109">[out] A pointer to a `DWORD` value that, when the method returns, contains the length of the stream in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3ba66-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="3ba66-110">Return Value</span></span>  
 <span data-ttu-id="3ba66-111">Метод возвращает `S_OK` значение, если длина потока памяти может быть определена, даже если она равна нулю (0).</span><span class="sxs-lookup"><span data-stu-id="3ba66-111">The method returns `S_OK` if the length of the memory stream can be determined, even if it is zero (0).</span></span>  
  
 <span data-ttu-id="3ba66-112">Метод возвращает `CORPROF_E_MODULE_IS_DYNAMIC` значение, если метод был создан с <xref:System.Reflection.Emit?displayProperty=nameWithType>помощью.</span><span class="sxs-lookup"><span data-stu-id="3ba66-112">The method returns `CORPROF_E_MODULE_IS_DYNAMIC` if the method was created using <xref:System.Reflection.Emit?displayProperty=nameWithType>.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3ba66-113">Примечания</span><span class="sxs-lookup"><span data-stu-id="3ba66-113">Remarks</span></span>  
 <span data-ttu-id="3ba66-114">Если модуль содержит символы в памяти, длина потока помещается в `pCountSymbolBytes`.</span><span class="sxs-lookup"><span data-stu-id="3ba66-114">If the module has in-memory symbols, the length of the stream is placed in `pCountSymbolBytes`.</span></span> <span data-ttu-id="3ba66-115">Если у модуля нет символов в памяти, `*pCountSymbolBytes = 0`то.</span><span class="sxs-lookup"><span data-stu-id="3ba66-115">If the module doesn't have in-memory     symbols, `*pCountSymbolBytes = 0`.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3ba66-116">Текущая реализация не поддерживает отражение. Emit.</span><span class="sxs-lookup"><span data-stu-id="3ba66-116">The current implementation does not support Reflection.Emit.</span></span> <span data-ttu-id="3ba66-117">Если модуль был создан с помощью отражения. Emit, метод возвращает `CORPROF_E_MODULE_IS_DYNAMIC`значение.</span><span class="sxs-lookup"><span data-stu-id="3ba66-117">If the module was created by using Reflection.Emit, the method returns `CORPROF_E_MODULE_IS_DYNAMIC`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3ba66-118">Требования</span><span class="sxs-lookup"><span data-stu-id="3ba66-118">Requirements</span></span>  
 <span data-ttu-id="3ba66-119">**Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3ba66-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3ba66-120">**Заголовок.** CorProf. idl, CorProf. h</span><span class="sxs-lookup"><span data-stu-id="3ba66-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="3ba66-121">**Библиотечная** Коргуидс. lib</span><span class="sxs-lookup"><span data-stu-id="3ba66-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3ba66-122">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3ba66-122">**.NET Framework Versions:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ba66-123">См. также</span><span class="sxs-lookup"><span data-stu-id="3ba66-123">See also</span></span>

- [<span data-ttu-id="3ba66-124">Интерфейс ICorProfilerInfo7</span><span class="sxs-lookup"><span data-stu-id="3ba66-124">ICorProfilerInfo7 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-interface.md)

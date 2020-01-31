---
title: Метод ICorProfilerAssemblyReferenceProvider::AddAssemblyReference
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorProfilerAssemblyReferenceProvider.AddAssemblyReference
api_location:
- mscorwks.dll
api_type:
- COM
ms.assetid: 3d5af8e7-c337-48f4-9fa6-97c83878b9b1
topic_type:
- apiref
ms.openlocfilehash: 2357e5348192db5d41adfe1176300359440aeee3
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866732"
---
# <a name="icorprofilerassemblyreferenceprovideraddassemblyreference-method"></a><span data-ttu-id="d5a22-102">Метод ICorProfilerAssemblyReferenceProvider::AddAssemblyReference</span><span class="sxs-lookup"><span data-stu-id="d5a22-102">ICorProfilerAssemblyReferenceProvider::AddAssemblyReference Method</span></span>
<span data-ttu-id="d5a22-103">[Поддерживается в .NET Framework 4.5.2 и более поздних версиях.]</span><span class="sxs-lookup"><span data-stu-id="d5a22-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="d5a22-104">Информирует среду CLR о ссылке сборки, которую профилировщик планирует добавить в обратный вызов [ICorProfilerCallback:: ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) .</span><span class="sxs-lookup"><span data-stu-id="d5a22-104">Informs the common language runtime (CLR) of an assembly reference that the profiler plans to add in the [ICorProfilerCallback::ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) callback.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d5a22-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d5a22-105">Syntax</span></span>  
  
```cpp
HRESULT AddAssemblyReference(  
        const COR_PRF_ASSEMBLY_REFERENCE_INFO* pAssemblyRefInfo  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d5a22-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="d5a22-106">Parameters</span></span>

- `pAssemblyRefInfo`

  <span data-ttu-id="d5a22-107">Указатель на структуру [COR_PRF_ASSEMBLY_REFERENCE_INFO](cor-prf-assembly-reference-info-structure.md) , которая предоставляет среде CLR сведения о ссылке на сборку, которую следует учитывать при выполнении анализа закрытия ссылок на сборки.</span><span class="sxs-lookup"><span data-stu-id="d5a22-107">A pointer to a [COR_PRF_ASSEMBLY_REFERENCE_INFO](cor-prf-assembly-reference-info-structure.md) structure that provides the CLR with information about an assembly reference that it should consider when performing an assembly reference closure walk.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="d5a22-108">Заметки</span><span class="sxs-lookup"><span data-stu-id="d5a22-108">Remarks</span></span>  
 <span data-ttu-id="d5a22-109">Профилировщик вызывает этот метод для каждой целевой сборки, на которую планируется ссылаться из сборки, указанной в аргументе `wszAssemblyPath` обратного вызова [ICorProfilerCallback6:: GetAssemblyReferences](icorprofilercallback6-getassemblyreferences-method.md) .</span><span class="sxs-lookup"><span data-stu-id="d5a22-109">The profiler calls this method for each target assembly it plans to reference from the assembly specified in the `wszAssemblyPath` argument of the [ICorProfilerCallback6::GetAssemblyReferences](icorprofilercallback6-getassemblyreferences-method.md) callback.</span></span> <span data-ttu-id="d5a22-110">Объект интерфейса [ICorProfilerAssemblyReferenceProvider](icorprofilerassemblyreferenceprovider-interface.md) передается обратному вызову [ICorProfilerCallback6:: GetAssemblyReferences](icorprofilercallback6-getassemblyreferences-method.md) профилировщика вместе с путем к сборке и именем в аргументе `wszAssemblyPath`.</span><span class="sxs-lookup"><span data-stu-id="d5a22-110">The [ICorProfilerAssemblyReferenceProvider](icorprofilerassemblyreferenceprovider-interface.md) interface object is passed to the profiler's [ICorProfilerCallback6::GetAssemblyReferences](icorprofilercallback6-getassemblyreferences-method.md) callback, along with the assembly path and name in the `wszAssemblyPath` argument.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d5a22-111">Требования</span><span class="sxs-lookup"><span data-stu-id="d5a22-111">Requirements</span></span>  
 <span data-ttu-id="d5a22-112">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d5a22-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d5a22-113">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d5a22-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d5a22-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d5a22-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d5a22-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d5a22-115">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5a22-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="d5a22-116">See also</span></span>

- [<span data-ttu-id="d5a22-117">Интерфейс ICorProfilerAssemblyReferenceProvider</span><span class="sxs-lookup"><span data-stu-id="d5a22-117">ICorProfilerAssemblyReferenceProvider Interface</span></span>](icorprofilerassemblyreferenceprovider-interface.md)
- [<span data-ttu-id="d5a22-118">Метод GetAssemblyReferences</span><span class="sxs-lookup"><span data-stu-id="d5a22-118">GetAssemblyReferences Method</span></span>](icorprofilercallback6-getassemblyreferences-method.md)
- [<span data-ttu-id="d5a22-119">Метод ModuleLoadFinished</span><span class="sxs-lookup"><span data-stu-id="d5a22-119">ModuleLoadFinished Method</span></span>](icorprofilercallback-moduleloadfinished-method.md)

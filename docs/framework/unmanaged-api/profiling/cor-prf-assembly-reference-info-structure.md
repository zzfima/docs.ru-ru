---
title: Структура COR_PRF_ASSEMBLY_REFERENCE_INFO
ms.date: 03/30/2017
dev_langs:
- cpp
ms.assetid: c8c1d916-8d1a-4f82-8128-9fd3732383fc
ms.openlocfilehash: ac7ddeed5694ad0ae6ef3d4a11fcb1fb23755b8e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73123227"
---
# <a name="cor_prf_assembly_reference_info-structure"></a><span data-ttu-id="7ab6d-102">Структура COR_PRF_ASSEMBLY_REFERENCE_INFO</span><span class="sxs-lookup"><span data-stu-id="7ab6d-102">COR_PRF_ASSEMBLY_REFERENCE_INFO Structure</span></span>
<span data-ttu-id="7ab6d-103">[Поддерживается в .NET Framework 4.5.2 и более поздних версиях.]</span><span class="sxs-lookup"><span data-stu-id="7ab6d-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="7ab6d-104">Обеспечивает среду CLR информацией о ссылке на сборку, которую ей следует учитывать при выполнении обхода замыкания.</span><span class="sxs-lookup"><span data-stu-id="7ab6d-104">Provides the common language runtime with information about an assembly reference that it should consider when performing an assembly reference closure walk.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7ab6d-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7ab6d-105">Syntax</span></span>  
  
```cpp  
typedef struct _COR_PRF_ASSEMBLY_REFERENCE_INFO {  
    void* pbPublicKeyOrToken;  
    ULONG cbPublicKeyOrToken;  
    LPCWSTR szName;  
    ASSEMBLYMETADATA* pMetaData;  
    void* pbHashValue;  
    ULONG cbHashValue;  
    DWORD dwAssemblyRefFlags;  
} COR_PRF_EX_CLAUSE_INFO;  
```  
  
## <a name="members"></a><span data-ttu-id="7ab6d-106">Члены</span><span class="sxs-lookup"><span data-stu-id="7ab6d-106">Members</span></span>  
  
|<span data-ttu-id="7ab6d-107">Член</span><span class="sxs-lookup"><span data-stu-id="7ab6d-107">Member</span></span>|<span data-ttu-id="7ab6d-108">Описание</span><span class="sxs-lookup"><span data-stu-id="7ab6d-108">Description</span></span>|  
|------------|-----------------|  
|`pbPublicKeyOrToken`|<span data-ttu-id="7ab6d-109">Указатель на открытый ключ или маркер сборки.</span><span class="sxs-lookup"><span data-stu-id="7ab6d-109">A pointer to the public key or token of the assembly.</span></span>|  
|`cbPublicKeyOrToken`|<span data-ttu-id="7ab6d-110">Количество байтов в открытом ключе или маркере.</span><span class="sxs-lookup"><span data-stu-id="7ab6d-110">The number of bytes in the public key or token.</span></span>|  
|`szName`|<span data-ttu-id="7ab6d-111">Имя сборки, на которую дается ссылка.</span><span class="sxs-lookup"><span data-stu-id="7ab6d-111">The name of the assembly that is referenced.</span></span>|  
|`pMetaData`|<span data-ttu-id="7ab6d-112">Указатель на метаданные сборки.</span><span class="sxs-lookup"><span data-stu-id="7ab6d-112">A pointer to the assembly's metadata.</span></span>|  
|`pbHashValue`|<span data-ttu-id="7ab6d-113">Указатель на хэшированный большой двоичный объект (BLOB).</span><span class="sxs-lookup"><span data-stu-id="7ab6d-113">A pointer to a hash binary large object (BLOB).</span></span>|  
|`cbHashValue`|<span data-ttu-id="7ab6d-114">Количество байтов в хэшированном BLOB.</span><span class="sxs-lookup"><span data-stu-id="7ab6d-114">The number of bytes in the hash BLOB.</span></span>|  
|`dwAssemblyRefFlags`|<span data-ttu-id="7ab6d-115">Флаги сборки.</span><span class="sxs-lookup"><span data-stu-id="7ab6d-115">The assembly's flags.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7ab6d-116">Заметки</span><span class="sxs-lookup"><span data-stu-id="7ab6d-116">Remarks</span></span>  
 <span data-ttu-id="7ab6d-117">Структура `COR_PRF_EX_CLAUSE_INFO` заполняется профилировщиком при его объявлении дополнительных ссылок на сборку, которые среда CLR должна учитывать при выполнении обхода замыкания.</span><span class="sxs-lookup"><span data-stu-id="7ab6d-117">The `COR_PRF_EX_CLAUSE_INFO` structure is populated by the profiler when it declares additional assembly references that the common language runtime should consider when performing an assembly reference closure walk.</span></span>  
  
 <span data-ttu-id="7ab6d-118">Если профилировщик регистрируется для метода обратного вызова [ICorProfilerCallback6:: GetAssemblyReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) , среда выполнения передает путь и имя загружаемой сборки вместе с указателем на [ICorProfilerAssemblyReferenceProvider](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-interface.md) объект интерфейса для этого метода.</span><span class="sxs-lookup"><span data-stu-id="7ab6d-118">If the profiler registers for the [ICorProfilerCallback6::GetAssemblyReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) callback method, the runtime passes the path and name of the assembly to be loaded, along with a pointer to an [ICorProfilerAssemblyReferenceProvider](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-interface.md) interface object to that method.</span></span> <span data-ttu-id="7ab6d-119">Затем профилировщик может вызвать метод [ICorProfilerAssemblyReferenceProvider:: AddAssemblyReference](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-addassemblyreference-method.md) с объектом `COR_PRF_ASSEMBLY_REFERENCE_INFO` для каждой целевой сборки, на которую планируется ссылаться из сборки, указанной в [ICorProfilerCallback6:: ](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md)Обратный вызов GetAssemblyReferences.</span><span class="sxs-lookup"><span data-stu-id="7ab6d-119">The profiler can then call the [ICorProfilerAssemblyReferenceProvider::AddAssemblyReference](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-addassemblyreference-method.md) method with a `COR_PRF_ASSEMBLY_REFERENCE_INFO` object for each target assembly it plans to reference from the assembly specified in the [ICorProfilerCallback6::GetAssemblyReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7ab6d-120">Требования</span><span class="sxs-lookup"><span data-stu-id="7ab6d-120">Requirements</span></span>  
 <span data-ttu-id="7ab6d-121">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7ab6d-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7ab6d-122">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="7ab6d-122">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="7ab6d-123">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7ab6d-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7ab6d-124">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7ab6d-124">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ab6d-125">См. также</span><span class="sxs-lookup"><span data-stu-id="7ab6d-125">See also</span></span>

- [<span data-ttu-id="7ab6d-126">Структуры профилирования</span><span class="sxs-lookup"><span data-stu-id="7ab6d-126">Profiling Structures</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)
- [<span data-ttu-id="7ab6d-127">Метод GetAssemblyReferences</span><span class="sxs-lookup"><span data-stu-id="7ab6d-127">GetAssemblyReferences Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md)
- [<span data-ttu-id="7ab6d-128">Метод AddAssemblyReference</span><span class="sxs-lookup"><span data-stu-id="7ab6d-128">AddAssemblyReference Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-addassemblyreference-method.md)

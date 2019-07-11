---
title: Метод ICorProfilerInfo2::GetStaticFieldInfo
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetStaticFieldInfo
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetStaticFieldInfo
helpviewer_keywords:
- ICorProfilerInfo2::GetStaticFieldInfo method [.NET Framework profiling]
- GetStaticFieldInfo method [.NET Framework profiling]
ms.assetid: fc663e76-e23f-49a8-bdd5-52cdf1a3b2b3
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 36cb8d5865cdc4c1c8e34671010ede25d531bacf
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67782255"
---
# <a name="icorprofilerinfo2getstaticfieldinfo-method"></a><span data-ttu-id="7c33d-102">Метод ICorProfilerInfo2::GetStaticFieldInfo</span><span class="sxs-lookup"><span data-stu-id="7c33d-102">ICorProfilerInfo2::GetStaticFieldInfo Method</span></span>
<span data-ttu-id="7c33d-103">Получает значение, указывающее тип статического объекта, применяемого к указанному полю.</span><span class="sxs-lookup"><span data-stu-id="7c33d-103">Gets a value that indicates the kind of static that applies to the specified field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7c33d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7c33d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStaticFieldInfo (  
    [in] ClassID               classId,  
    [in] mdFieldDef            fieldToken,  
    [out] COR_PRF_STATIC_TYPE  *pFieldInfo);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7c33d-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="7c33d-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="7c33d-106">[in] Идентификатор класса, в котором определен статического поля.</span><span class="sxs-lookup"><span data-stu-id="7c33d-106">[in] The ID of the class in which the static field is defined.</span></span>  
  
 `fieldToken`  
 <span data-ttu-id="7c33d-107">[in] Токен метаданных для статического поля.</span><span class="sxs-lookup"><span data-stu-id="7c33d-107">[in] The metadata token for the static field.</span></span>  
  
 `pFieldInfo`  
 <span data-ttu-id="7c33d-108">[out] Указатель на значение [COR_PRF_STATIC_TYPE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-static-type-enumeration.md) перечисления, указывающее является ли указанное поле является статическим, и если таким образом, тип статического объекта, применяет к полю.</span><span class="sxs-lookup"><span data-stu-id="7c33d-108">[out] A pointer to a value of the [COR_PRF_STATIC_TYPE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-static-type-enumeration.md) enumeration that indicates whether the specified field is static, and if so, the kind of static that applies to the field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7c33d-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="7c33d-109">Remarks</span></span>  
 <span data-ttu-id="7c33d-110">Эти сведения можно использовать, чтобы определить, какую функцию вызвать, чтобы получить адрес статического поля.</span><span class="sxs-lookup"><span data-stu-id="7c33d-110">This information can be used to determine which function to call to get the address of the static field.</span></span>  
  
 <span data-ttu-id="7c33d-111">Профилировщик кода по-прежнему следует проверить метаданные для статического поля, чтобы убедиться, что он действительно имеет адрес.</span><span class="sxs-lookup"><span data-stu-id="7c33d-111">The profiler code should still check the metadata for a static field to ensure that it actually has an address.</span></span> <span data-ttu-id="7c33d-112">Статические литералы (то есть константы) существуют только в метаданных и не имеют адреса.</span><span class="sxs-lookup"><span data-stu-id="7c33d-112">Static literals (that is, constants) exist only in the metadata and do not have an address.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7c33d-113">Требования</span><span class="sxs-lookup"><span data-stu-id="7c33d-113">Requirements</span></span>  
 <span data-ttu-id="7c33d-114">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7c33d-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7c33d-115">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="7c33d-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="7c33d-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7c33d-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7c33d-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7c33d-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c33d-118">См. также</span><span class="sxs-lookup"><span data-stu-id="7c33d-118">See also</span></span>

- [<span data-ttu-id="7c33d-119">Интерфейс ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="7c33d-119">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [<span data-ttu-id="7c33d-120">Интерфейс ICorProfilerInfo2</span><span class="sxs-lookup"><span data-stu-id="7c33d-120">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)

---
title: Метод ICorProfilerInfo::GetClassIDInfo
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetClassIDInfo
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetClassIDInfo
helpviewer_keywords:
- GetClassIDInfo method [.NET Framework profiling]
- ICorProfilerInfo::GetClassIDInfo method [.NET Framework profiling]
ms.assetid: 9e93b99e-5aca-415c-8e37-7f33753b612d
topic_type:
- apiref
ms.openlocfilehash: 4b9c577fab91e9527a1edc6c93e0618c8fe4e662
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76864078"
---
# <a name="icorprofilerinfogetclassidinfo-method"></a><span data-ttu-id="cf506-102">Метод ICorProfilerInfo::GetClassIDInfo</span><span class="sxs-lookup"><span data-stu-id="cf506-102">ICorProfilerInfo::GetClassIDInfo Method</span></span>
<span data-ttu-id="cf506-103">Возвращает родительский модуль и маркер метаданных для указанного класса.</span><span class="sxs-lookup"><span data-stu-id="cf506-103">Gets the parent module and the metadata token for the specified class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cf506-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cf506-104">Syntax</span></span>  
  
```cpp  
HRESULT GetClassIDInfo(  
    [in]  ClassID   classId,  
    [out] ModuleID  *pModuleId,  
    [out] mdTypeDef *pTypeDefToken);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cf506-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="cf506-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="cf506-106">окне Идентификатор класса, для которого необходимо получить сведения.</span><span class="sxs-lookup"><span data-stu-id="cf506-106">[in] The ID of the class for which to get the information.</span></span>  
  
 `pModuleId`  
 <span data-ttu-id="cf506-107">заполняет Указатель на идентификатор родительского модуля класса.</span><span class="sxs-lookup"><span data-stu-id="cf506-107">[out] A pointer to the ID of the parent module of the class.</span></span>  
  
 `pTypeDefToken`  
 <span data-ttu-id="cf506-108">заполняет Указатель на маркер метаданных для класса.</span><span class="sxs-lookup"><span data-stu-id="cf506-108">[out] A pointer to the metadata token for the class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cf506-109">Заметки</span><span class="sxs-lookup"><span data-stu-id="cf506-109">Remarks</span></span>  
 <span data-ttu-id="cf506-110">Чтобы получить интерфейс метаданных для заданного модуля, код профилировщика может вызвать метод [ICorProfilerInfo:: жетмодулеметадата](icorprofilerinfo-getmodulemetadata-method.md) .</span><span class="sxs-lookup"><span data-stu-id="cf506-110">The profiler code can call [ICorProfilerInfo::GetModuleMetaData](icorprofilerinfo-getmodulemetadata-method.md) to obtain a metadata interface for a given module.</span></span> <span data-ttu-id="cf506-111">Токен метаданных, возвращенный в расположение, на которое ссылается `pTypeDefToken`, можно впоследствии использовать для доступа к метаданным класса.</span><span class="sxs-lookup"><span data-stu-id="cf506-111">The metadata token that is returned to the location referenced by `pTypeDefToken` can then be used to access the metadata for the class.</span></span>  
  
 <span data-ttu-id="cf506-112">Чтобы получить дополнительные сведения для универсальных типов, используйте [ICorProfilerInfo2:: GetClassIDInfo2](icorprofilerinfo2-getclassidinfo2-method.md).</span><span class="sxs-lookup"><span data-stu-id="cf506-112">To get more information for generic types, use [ICorProfilerInfo2::GetClassIDInfo2](icorprofilerinfo2-getclassidinfo2-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cf506-113">Требования</span><span class="sxs-lookup"><span data-stu-id="cf506-113">Requirements</span></span>  
 <span data-ttu-id="cf506-114">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cf506-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cf506-115">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="cf506-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="cf506-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cf506-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cf506-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cf506-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf506-118">См. также:</span><span class="sxs-lookup"><span data-stu-id="cf506-118">See also</span></span>

- [<span data-ttu-id="cf506-119">Интерфейс ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="cf506-119">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)

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
ms.openlocfilehash: d30d0bc262d76cf8980f90d8384173d89baf92d5
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76862690"
---
# <a name="icorprofilerinfo2getstaticfieldinfo-method"></a><span data-ttu-id="e9b26-102">Метод ICorProfilerInfo2::GetStaticFieldInfo</span><span class="sxs-lookup"><span data-stu-id="e9b26-102">ICorProfilerInfo2::GetStaticFieldInfo Method</span></span>
<span data-ttu-id="e9b26-103">Возвращает значение, указывающее тип статического объекта, который применяется к указанному полю.</span><span class="sxs-lookup"><span data-stu-id="e9b26-103">Gets a value that indicates the kind of static that applies to the specified field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e9b26-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e9b26-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStaticFieldInfo (  
    [in] ClassID               classId,  
    [in] mdFieldDef            fieldToken,  
    [out] COR_PRF_STATIC_TYPE  *pFieldInfo);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e9b26-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="e9b26-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="e9b26-106">окне Идентификатор класса, в котором определено статическое поле.</span><span class="sxs-lookup"><span data-stu-id="e9b26-106">[in] The ID of the class in which the static field is defined.</span></span>  
  
 `fieldToken`  
 <span data-ttu-id="e9b26-107">окне Маркер метаданных для статического поля.</span><span class="sxs-lookup"><span data-stu-id="e9b26-107">[in] The metadata token for the static field.</span></span>  
  
 `pFieldInfo`  
 <span data-ttu-id="e9b26-108">заполняет Указатель на значение перечисления [COR_PRF_STATIC_TYPE](cor-prf-static-type-enumeration.md) , указывающее, является ли указанное поле статическим, и, если это так, тип статического, применяемого к полю.</span><span class="sxs-lookup"><span data-stu-id="e9b26-108">[out] A pointer to a value of the [COR_PRF_STATIC_TYPE](cor-prf-static-type-enumeration.md) enumeration that indicates whether the specified field is static, and if so, the kind of static that applies to the field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e9b26-109">Заметки</span><span class="sxs-lookup"><span data-stu-id="e9b26-109">Remarks</span></span>  
 <span data-ttu-id="e9b26-110">Эти сведения можно использовать для определения функции, вызываемой для получения адреса статического поля.</span><span class="sxs-lookup"><span data-stu-id="e9b26-110">This information can be used to determine which function to call to get the address of the static field.</span></span>  
  
 <span data-ttu-id="e9b26-111">Код профилировщика должен по-прежнему проверять метаданные для статического поля, чтобы убедиться, что он действительно имеет адрес.</span><span class="sxs-lookup"><span data-stu-id="e9b26-111">The profiler code should still check the metadata for a static field to ensure that it actually has an address.</span></span> <span data-ttu-id="e9b26-112">Статические литералы (константы) существуют только в метаданных и не имеют адреса.</span><span class="sxs-lookup"><span data-stu-id="e9b26-112">Static literals (that is, constants) exist only in the metadata and do not have an address.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e9b26-113">Требования</span><span class="sxs-lookup"><span data-stu-id="e9b26-113">Requirements</span></span>  
 <span data-ttu-id="e9b26-114">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e9b26-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e9b26-115">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e9b26-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e9b26-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e9b26-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e9b26-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e9b26-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9b26-118">См. также:</span><span class="sxs-lookup"><span data-stu-id="e9b26-118">See also</span></span>

- [<span data-ttu-id="e9b26-119">Интерфейс ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="e9b26-119">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="e9b26-120">Интерфейс ICorProfilerInfo2</span><span class="sxs-lookup"><span data-stu-id="e9b26-120">ICorProfilerInfo2 Interface</span></span>](icorprofilerinfo2-interface.md)

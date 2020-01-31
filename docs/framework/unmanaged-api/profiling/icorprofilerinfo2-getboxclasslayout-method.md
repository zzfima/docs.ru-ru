---
title: Метод ICorProfilerInfo2::GetBoxClassLayout
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetBoxClassLayout
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetBoxClassLayout
helpviewer_keywords:
- GetBoxClassLayout method [.NET Framework profiling]
- ICorProfilerInfo2::GetBoxClassLayout method [.NET Framework profiling]
ms.assetid: 624672b5-1189-488a-85d2-3e12b49617c1
topic_type:
- apiref
ms.openlocfilehash: 500cf74c320438fc1b78f0aac737b418716e1a11
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76862832"
---
# <a name="icorprofilerinfo2getboxclasslayout-method"></a><span data-ttu-id="62657-102">Метод ICorProfilerInfo2::GetBoxClassLayout</span><span class="sxs-lookup"><span data-stu-id="62657-102">ICorProfilerInfo2::GetBoxClassLayout Method</span></span>
<span data-ttu-id="62657-103">Возвращает сведения о расположении указанного типа значения при его упаковке.</span><span class="sxs-lookup"><span data-stu-id="62657-103">Gets information about where the specified value type is located when it is boxed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="62657-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="62657-104">Syntax</span></span>  
  
```cpp  
HRESULT GetBoxClassLayout(  
    [in] ClassID classId,  
    [out] ULONG32 *pBufferOffset);  
```  
  
## <a name="parameters"></a><span data-ttu-id="62657-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="62657-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="62657-106">окне Идентификатор класса, который описывает упакованный тип значения.</span><span class="sxs-lookup"><span data-stu-id="62657-106">[in] The ID of the class that describes the value type that is boxed.</span></span>  
  
 `pBufferOffset`  
 <span data-ttu-id="62657-107">заполняет Целое число, которое является смещением относительно указателя на идентификатор упакованного объекта для типа значения.</span><span class="sxs-lookup"><span data-stu-id="62657-107">[out] An integer that is the offset, relative to the boxed object ID pointer, of the value type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="62657-108">Заметки</span><span class="sxs-lookup"><span data-stu-id="62657-108">Remarks</span></span>  
 <span data-ttu-id="62657-109">`pBufferOffset` значение — это расположение типа значения в поле.</span><span class="sxs-lookup"><span data-stu-id="62657-109">The `pBufferOffset` value is the location of the value type within a box.</span></span> <span data-ttu-id="62657-110">После применения `pBufferOffset` к упакованному объекту можно использовать макет класса типа значения для интерпретации значения объекта.</span><span class="sxs-lookup"><span data-stu-id="62657-110">After `pBufferOffset` is applied to a boxed object, the value type's class layout can be used to interpret the object's value.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="62657-111">Требования</span><span class="sxs-lookup"><span data-stu-id="62657-111">Requirements</span></span>  
 <span data-ttu-id="62657-112">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="62657-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="62657-113">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="62657-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="62657-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="62657-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="62657-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="62657-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62657-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="62657-116">See also</span></span>

- [<span data-ttu-id="62657-117">Интерфейс ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="62657-117">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="62657-118">Интерфейс ICorProfilerInfo2</span><span class="sxs-lookup"><span data-stu-id="62657-118">ICorProfilerInfo2 Interface</span></span>](icorprofilerinfo2-interface.md)

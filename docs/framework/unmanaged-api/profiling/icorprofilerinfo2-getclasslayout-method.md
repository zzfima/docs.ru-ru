---
title: Метод ICorProfilerInfo2::GetClassLayout
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetClassLayout
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetClassLayout
helpviewer_keywords:
- ICorProfilerInfo2::GetClassLayout method [.NET Framework profiling]
- GetClassLayout method, ICorProfilerInfo2 interface [.NET Framework profiling]
ms.assetid: a3a36987-5666-4e2f-95b5-d0cb246502ec
topic_type:
- apiref
ms.openlocfilehash: 37400e3b69b3884e31479fd7cdfccb473408bfbf
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74433390"
---
# <a name="icorprofilerinfo2getclasslayout-method"></a><span data-ttu-id="ae06a-102">Метод ICorProfilerInfo2::GetClassLayout</span><span class="sxs-lookup"><span data-stu-id="ae06a-102">ICorProfilerInfo2::GetClassLayout Method</span></span>
<span data-ttu-id="ae06a-103">Получает сведения о макете в памяти полей, определенных с помощью указанного класса.</span><span class="sxs-lookup"><span data-stu-id="ae06a-103">Gets information about the layout, in memory, of the fields defined by the specified class.</span></span> <span data-ttu-id="ae06a-104">То есть этот метод получает смещения полей класса.</span><span class="sxs-lookup"><span data-stu-id="ae06a-104">That is, this method gets the offsets of the class's fields.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ae06a-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ae06a-105">Syntax</span></span>  
  
```cpp  
HRESULT GetClassLayout(  
    [in]  ClassID classID,  
    [in, out] COR_FIELD_OFFSET rFieldOffset[],  
    [in]  ULONG cFieldOffset,  
    [out] ULONG *pcFieldOffset,  
    [out] ULONG *pulClassSize);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ae06a-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="ae06a-106">Parameters</span></span>  
 `classID`  
 <span data-ttu-id="ae06a-107">[in] Идентификатор класса, для которого будет извлекаться макет.</span><span class="sxs-lookup"><span data-stu-id="ae06a-107">[in] The ID of the class for which the layout will be retrieved.</span></span>  
  
 `rFieldOffset`  
 <span data-ttu-id="ae06a-108">[вход, выход] Массив структур [COR_FIELD_OFFSET](../../../../docs/framework/unmanaged-api/metadata/cor-field-offset-structure.md) , каждый из которых содержит токены и смещения полей класса.</span><span class="sxs-lookup"><span data-stu-id="ae06a-108">[in, out] An array of [COR_FIELD_OFFSET](../../../../docs/framework/unmanaged-api/metadata/cor-field-offset-structure.md) structures, each of which contains the tokens and offsets of the class's fields.</span></span>  
  
 `cFieldOffset`  
 <span data-ttu-id="ae06a-109">[in] Размер массива `rFieldOffset`.</span><span class="sxs-lookup"><span data-stu-id="ae06a-109">[in] The size of the `rFieldOffset` array.</span></span>  
  
 `pcFieldOffset`  
 <span data-ttu-id="ae06a-110">[out] Указатель на общее число доступных элементов.</span><span class="sxs-lookup"><span data-stu-id="ae06a-110">[out] A pointer to the total number of available elements.</span></span> <span data-ttu-id="ae06a-111">Если параметр `cFieldOffset` имеет значение 0, это значение указывает число необходимых элементов.</span><span class="sxs-lookup"><span data-stu-id="ae06a-111">If `cFieldOffset` is 0, this value indicates the number of elements needed.</span></span>  
  
 `pulClassSize`  
 <span data-ttu-id="ae06a-112">[out] Указатель на расположение, которое содержит размер класса в байтах.</span><span class="sxs-lookup"><span data-stu-id="ae06a-112">[out] A pointer to a location that contains the size, in bytes, of the class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ae06a-113">Заметки</span><span class="sxs-lookup"><span data-stu-id="ae06a-113">Remarks</span></span>  
 <span data-ttu-id="ae06a-114">Метод `GetClassLayout` возвращает только поля, определенные самим классом.</span><span class="sxs-lookup"><span data-stu-id="ae06a-114">The `GetClassLayout` method returns only the fields defined by the class itself.</span></span> <span data-ttu-id="ae06a-115">Если в родительском классе этого класса также определены поля, профилировщик должен вызвать `GetClassLayout` в родительском классе, чтобы получить эти поля.</span><span class="sxs-lookup"><span data-stu-id="ae06a-115">If the class's parent class has defined fields as well, the profiler must call `GetClassLayout` on the parent class to obtain those fields.</span></span>  
  
 <span data-ttu-id="ae06a-116">Если вы используете метод `GetClassLayout` со строковыми классами, метод завершится с ошибкой с кодом ошибки E_INVALIDARG.</span><span class="sxs-lookup"><span data-stu-id="ae06a-116">If you use `GetClassLayout` with string classes, the method will fail with error code E_INVALIDARG.</span></span> <span data-ttu-id="ae06a-117">Чтобы получить сведения о макете строки, используйте [ICorProfilerInfo2:: GetStringLayout](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getstringlayout-method.md) .</span><span class="sxs-lookup"><span data-stu-id="ae06a-117">Use [ICorProfilerInfo2::GetStringLayout](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getstringlayout-method.md) to get information about the layout of a string.</span></span> <span data-ttu-id="ae06a-118">`GetClassLayout` также завершится ошибкой при вызове с классом массива.</span><span class="sxs-lookup"><span data-stu-id="ae06a-118">`GetClassLayout` will also fail when called with an array class.</span></span>  
  
 <span data-ttu-id="ae06a-119">После возврата метода `GetClassLayout` необходимо убедиться, что буфер `rFieldOffset` был достаточно велик, чтобы вместить в себя все доступные структуры `COR_FIELD_OFFSET`.</span><span class="sxs-lookup"><span data-stu-id="ae06a-119">After `GetClassLayout` returns, you must verify that the `rFieldOffset` buffer was large enough to contain all the available `COR_FIELD_OFFSET` structures.</span></span> <span data-ttu-id="ae06a-120">Для этого нужно сравнить значение, указанное параметром `pcFieldOffset`, с размером `rFieldOffset`, деленным на размер структуры `COR_FIELD_OFFSET`.</span><span class="sxs-lookup"><span data-stu-id="ae06a-120">To do this, compare the value that `pcFieldOffset` points to with the size of `rFieldOffset` divided by the size of a `COR_FIELD_OFFSET` structure.</span></span> <span data-ttu-id="ae06a-121">Если параметр `rFieldOffset` имеет недостаточно большое значение, выделите буфер `rFieldOffset` большего размера, обновите параметр `cFieldOffset`, задав новый, больший размер, и вызовите метод `GetClassLayout` снова.</span><span class="sxs-lookup"><span data-stu-id="ae06a-121">If `rFieldOffset` is not large enough, allocate a larger `rFieldOffset` buffer, update `cFieldOffset` with the new, larger size, and call `GetClassLayout` again.</span></span>  
  
 <span data-ttu-id="ae06a-122">Кроме того, сначала можно вызвать метод `GetClassLayout` с буфером `rFieldOffset` нулевой длины для получения правильного размера буфера.</span><span class="sxs-lookup"><span data-stu-id="ae06a-122">Alternatively, you can first call `GetClassLayout` with a zero-length `rFieldOffset` buffer to obtain the correct buffer size.</span></span> <span data-ttu-id="ae06a-123">Затем можно задать размер буфера равным значению, возвращенному в параметре `pcFieldOffset`, и вызвать метод `GetClassLayout` снова.</span><span class="sxs-lookup"><span data-stu-id="ae06a-123">You can then set the buffer size to the value returned in `pcFieldOffset` and call `GetClassLayout` again.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ae06a-124">Требования</span><span class="sxs-lookup"><span data-stu-id="ae06a-124">Requirements</span></span>  
 <span data-ttu-id="ae06a-125">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ae06a-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ae06a-126">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ae06a-126">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ae06a-127">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ae06a-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ae06a-128">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ae06a-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae06a-129">См. также</span><span class="sxs-lookup"><span data-stu-id="ae06a-129">See also</span></span>

- [<span data-ttu-id="ae06a-130">Интерфейс ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="ae06a-130">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [<span data-ttu-id="ae06a-131">Интерфейс ICorProfilerInfo2</span><span class="sxs-lookup"><span data-stu-id="ae06a-131">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
- [<span data-ttu-id="ae06a-132">Интерфейсы профилирования</span><span class="sxs-lookup"><span data-stu-id="ae06a-132">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="ae06a-133">Профилирование</span><span class="sxs-lookup"><span data-stu-id="ae06a-133">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)

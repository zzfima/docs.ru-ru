---
title: "Метод ICorDebugClass2::GetParameterizedType"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorDebugClass2.GetParameterizedType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugClass2::GetParameterizedType
helpviewer_keywords:
- GetParameterizedType method [.NET Framework debugging]
- ICorDebugClass2::GetParameterizedType method [.NET Framework debugging]
ms.assetid: 94b591c4-9302-4af2-a510-089496afb036
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: a9cbb755bd8f52482f7eece6e9d236f29cadc419
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugclass2getparameterizedtype-method"></a><span data-ttu-id="98435-102">Метод ICorDebugClass2::GetParameterizedType</span><span class="sxs-lookup"><span data-stu-id="98435-102">ICorDebugClass2::GetParameterizedType Method</span></span>
<span data-ttu-id="98435-103">Возвращает объявление типа для этого класса.</span><span class="sxs-lookup"><span data-stu-id="98435-103">Gets the type declaration for this class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="98435-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="98435-104">Syntax</span></span>  
  
```  
HRESULT GetParameterizedType (  
    [in] CorElementType                      elementType,  
    [in] ULONG32                             nTypeArgs,  
    [in, size_is(nTypeArgs)] ICorDebugType  *ppTypeArgs[],  
    [out] ICorDebugType                    **ppType  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="98435-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="98435-105">Parameters</span></span>  
 `elementType`  
 <span data-ttu-id="98435-106">[in] Значение CorElementType перечисление, которое указывает тип элемента для данного класса: это значение равно ELEMENT_TYPE_VALUETYPE при этом ICorDebugClass2 представляет тип значения.</span><span class="sxs-lookup"><span data-stu-id="98435-106">[in] A value of the CorElementType enumeration that specifies the element type for this class: Set this value to ELEMENT_TYPE_VALUETYPE if this ICorDebugClass2 represents a value type.</span></span> <span data-ttu-id="98435-107">Это значение равно ELEMENT_TYPE_CLASS при этом `ICorDebugClass2` представляет сложный тип.</span><span class="sxs-lookup"><span data-stu-id="98435-107">Set this value to ELEMENT_TYPE_CLASS if this `ICorDebugClass2` represents a complex type.</span></span>  
  
 `nTypeArgs`  
 <span data-ttu-id="98435-108">[in] Число параметров типа, если тип является универсальным.</span><span class="sxs-lookup"><span data-stu-id="98435-108">[in] The number of type parameters, if the type is generic.</span></span> <span data-ttu-id="98435-109">Число параметров типа (если имеется) должно соответствовать числу, требуемым для класса.</span><span class="sxs-lookup"><span data-stu-id="98435-109">The number of type parameters (if any) must match the number required by the class.</span></span>  
  
 `ppTypeArgs`  
 <span data-ttu-id="98435-110">[in] Массив указателей, каждый из которых указывает на объект ICorDebugType, который представляет параметр типа.</span><span class="sxs-lookup"><span data-stu-id="98435-110">[in] An array of pointers, each of which points to an ICorDebugType object that represents a type parameter.</span></span> <span data-ttu-id="98435-111">Если класс является неуниверсальным, это значение равно null.</span><span class="sxs-lookup"><span data-stu-id="98435-111">If the class is non-generic, this value is null.</span></span>  
  
 `ppType`  
 <span data-ttu-id="98435-112">[out] Указатель на адрес `ICorDebugType` , представляющий объявление типа.</span><span class="sxs-lookup"><span data-stu-id="98435-112">[out] A pointer to the address of an `ICorDebugType` object that represents the type declaration.</span></span> <span data-ttu-id="98435-113">Этот объект эквивалентен <xref:System.Type> объекта в управляемом коде.</span><span class="sxs-lookup"><span data-stu-id="98435-113">This object is equivalent to a <xref:System.Type> object in managed code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="98435-114">Примечания</span><span class="sxs-lookup"><span data-stu-id="98435-114">Remarks</span></span>  
 <span data-ttu-id="98435-115">Если класс является неуниверсальных, то есть, если он не имеет параметров типа, `GetParameterizedType` просто возвращает объект типа среды выполнения, соответствующий данному классу.</span><span class="sxs-lookup"><span data-stu-id="98435-115">If the class is non-generic, that is, if it has no type parameters, `GetParameterizedType` simply gets the runtime type object corresponding to the class.</span></span> <span data-ttu-id="98435-116">`elementType` Параметра должно быть присвоено типом правильный элемент для данного класса: ELEMENT_TYPE_VALUETYPE, если класс является типом значения; в противном случае ELEMENT_TYPE_CLASS.</span><span class="sxs-lookup"><span data-stu-id="98435-116">The `elementType` parameter should be set to the correct element type for the class: ELEMENT_TYPE_VALUETYPE if the class is a value type; otherwise, ELEMENT_TYPE_CLASS.</span></span>  
  
 <span data-ttu-id="98435-117">Если класс принимает параметры типа (например, `ArrayList<T>`), можно использовать `GetParameterizedType` , чтобы создать объект типа экземпляры типа, такие как `ArrayList<int>`.</span><span class="sxs-lookup"><span data-stu-id="98435-117">If the class accepts type parameters (for example, `ArrayList<T>`), you can use `GetParameterizedType` to construct a type object for an instantiated type such as `ArrayList<int>`.</span></span>  
  
## <a name="background-information"></a><span data-ttu-id="98435-118">Основные сведения</span><span class="sxs-lookup"><span data-stu-id="98435-118">Background Information</span></span>  
 <span data-ttu-id="98435-119">В .NET Framework версий 1.0 и 1.1 каждый тип в метаданных может быть напрямую сопоставлен с типом выполняющегося процесса.</span><span class="sxs-lookup"><span data-stu-id="98435-119">In the .NET Framework versions 1.0 and 1.1, every type in the metadata could be directly mapped to a type in the running process.</span></span> <span data-ttu-id="98435-120">Таким образом тип метаданных и тип среды выполнения было единое представление выполняющегося процесса.</span><span class="sxs-lookup"><span data-stu-id="98435-120">Thus, a metadata type and a runtime type had a single representation in the running process.</span></span> <span data-ttu-id="98435-121">Однако одного универсального типа в метаданных можно сопоставить нескольким различным экземплярам типа в выполняемом процессе.</span><span class="sxs-lookup"><span data-stu-id="98435-121">However, one generic type in metadata can be mapped to many different instantiations of the type in the running process.</span></span> <span data-ttu-id="98435-122">Например, тип метаданных `SortedList<K,V>` можно сопоставить с `SortedList<String, EmployeeRecord>`, `SortedList<Int32, String>`, `SortedList<String,Array<Int32>>`, и т. д.</span><span class="sxs-lookup"><span data-stu-id="98435-122">For example, the metadata type `SortedList<K,V>` can map to `SortedList<String, EmployeeRecord>`, `SortedList<Int32, String>`, `SortedList<String,Array<Int32>>`, and so on.</span></span> <span data-ttu-id="98435-123">Таким образом вам необходим способ для обработки экземпляра типа.</span><span class="sxs-lookup"><span data-stu-id="98435-123">Thus, you need a way to handle type instantiation.</span></span>  
  
 <span data-ttu-id="98435-124">.NET Framework версии 2.0 появился `ICorDebugType` интерфейса.</span><span class="sxs-lookup"><span data-stu-id="98435-124">The .NET Framework version 2.0 introduces the `ICorDebugType` interface.</span></span> <span data-ttu-id="98435-125">Для универсального типа `ICorDebugClass` или `ICorDebugClass2` представляет объект типа без экземпляров (`SortedList<K,V>`) и `ICorDebugType` объект представляет экземпляр различных типов.</span><span class="sxs-lookup"><span data-stu-id="98435-125">For a generic type, an `ICorDebugClass` or `ICorDebugClass2` object represents the uninstantiated type (`SortedList<K,V>`), and an `ICorDebugType` object represents the various instantiated types.</span></span> <span data-ttu-id="98435-126">Получает `ICorDebugClass` или `ICorDebugClass2` объекта, можно создать `ICorDebugType` объекта для любого экземпляра путем вызова `ICorDebugClass2::GetParameterizedType` метод.</span><span class="sxs-lookup"><span data-stu-id="98435-126">Given an `ICorDebugClass` or `ICorDebugClass2` object, you can create an `ICorDebugType` object for any instantiation by calling the `ICorDebugClass2::GetParameterizedType` method.</span></span> <span data-ttu-id="98435-127">Можно также создать `ICorDebugType` объекта для простого типа, например, Int32, или для неуниверсального типа.</span><span class="sxs-lookup"><span data-stu-id="98435-127">You can also create an `ICorDebugType` object for a simple type, such as Int32, or for a non-generic type.</span></span>  
  
 <span data-ttu-id="98435-128">Введение `ICorDebugType` объект для представления времени выполнения понятие типа имеет оказывает влияние на протяжении API.</span><span class="sxs-lookup"><span data-stu-id="98435-128">The introduction of the `ICorDebugType` object to represent the run-time notion of a type has a ripple effect throughout the API.</span></span> <span data-ttu-id="98435-129">Функции, которые ранее были `ICorDebugClass` или `ICorDebugClass2` объекта или даже `CorElementType` значение обобщены, чтобы воспользоваться `ICorDebugType` объекта.</span><span class="sxs-lookup"><span data-stu-id="98435-129">Functions that previously took an `ICorDebugClass` or `ICorDebugClass2` object or even a `CorElementType` value are generalized to take an `ICorDebugType` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="98435-130">Требования</span><span class="sxs-lookup"><span data-stu-id="98435-130">Requirements</span></span>  
 <span data-ttu-id="98435-131">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="98435-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="98435-132">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="98435-132">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="98435-133">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="98435-133">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="98435-134">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="98435-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>

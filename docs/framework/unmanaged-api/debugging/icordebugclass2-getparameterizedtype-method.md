---
title: Метод ICorDebugClass2::GetParameterizedType
ms.date: 03/30/2017
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
ms.openlocfilehash: 64537ab97c1256cc6f963999b027bafc25cbbccb
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125729"
---
# <a name="icordebugclass2getparameterizedtype-method"></a><span data-ttu-id="29416-102">Метод ICorDebugClass2::GetParameterizedType</span><span class="sxs-lookup"><span data-stu-id="29416-102">ICorDebugClass2::GetParameterizedType Method</span></span>
<span data-ttu-id="29416-103">Возвращает объявление типа для этого класса.</span><span class="sxs-lookup"><span data-stu-id="29416-103">Gets the type declaration for this class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="29416-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="29416-104">Syntax</span></span>  
  
```cpp  
HRESULT GetParameterizedType (  
    [in] CorElementType                      elementType,  
    [in] ULONG32                             nTypeArgs,  
    [in, size_is(nTypeArgs)] ICorDebugType  *ppTypeArgs[],  
    [out] ICorDebugType                    **ppType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="29416-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="29416-105">Parameters</span></span>  
 `elementType`  
 <span data-ttu-id="29416-106">окне Значение перечисления Корелементтипе, указывающее тип элемента для этого класса: Установите это значение в ELEMENT_TYPE_VALUETYPE, если это ICorDebugClass2 представляет тип значения.</span><span class="sxs-lookup"><span data-stu-id="29416-106">[in] A value of the CorElementType enumeration that specifies the element type for this class: Set this value to ELEMENT_TYPE_VALUETYPE if this ICorDebugClass2 represents a value type.</span></span> <span data-ttu-id="29416-107">Присвойте этому параметру значение ELEMENT_TYPE_CLASS, если это `ICorDebugClass2` представляет сложный тип.</span><span class="sxs-lookup"><span data-stu-id="29416-107">Set this value to ELEMENT_TYPE_CLASS if this `ICorDebugClass2` represents a complex type.</span></span>  
  
 `nTypeArgs`  
 <span data-ttu-id="29416-108">окне Число параметров типа, если тип является универсальным.</span><span class="sxs-lookup"><span data-stu-id="29416-108">[in] The number of type parameters, if the type is generic.</span></span> <span data-ttu-id="29416-109">Количество параметров типа (если таковое имеется) должно совпадать с числом, необходимым для класса.</span><span class="sxs-lookup"><span data-stu-id="29416-109">The number of type parameters (if any) must match the number required by the class.</span></span>  
  
 `ppTypeArgs`  
 <span data-ttu-id="29416-110">окне Массив указателей, каждый из которых указывает на объект ICorDebugType, представляющий параметр типа.</span><span class="sxs-lookup"><span data-stu-id="29416-110">[in] An array of pointers, each of which points to an ICorDebugType object that represents a type parameter.</span></span> <span data-ttu-id="29416-111">Если класс не является универсальным, это значение равно null.</span><span class="sxs-lookup"><span data-stu-id="29416-111">If the class is non-generic, this value is null.</span></span>  
  
 `ppType`  
 <span data-ttu-id="29416-112">заполняет Указатель на адрес объекта `ICorDebugType`, который представляет объявление типа.</span><span class="sxs-lookup"><span data-stu-id="29416-112">[out] A pointer to the address of an `ICorDebugType` object that represents the type declaration.</span></span> <span data-ttu-id="29416-113">Этот объект эквивалентен объекту <xref:System.Type> в управляемом коде.</span><span class="sxs-lookup"><span data-stu-id="29416-113">This object is equivalent to a <xref:System.Type> object in managed code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="29416-114">Заметки</span><span class="sxs-lookup"><span data-stu-id="29416-114">Remarks</span></span>  
 <span data-ttu-id="29416-115">Если класс не является универсальным, то есть если он не имеет параметров типа, `GetParameterizedType` просто получает объект типа среды выполнения, соответствующий классу.</span><span class="sxs-lookup"><span data-stu-id="29416-115">If the class is non-generic, that is, if it has no type parameters, `GetParameterizedType` simply gets the runtime type object corresponding to the class.</span></span> <span data-ttu-id="29416-116">Для параметра `elementType` должен быть задан правильный тип элемента для класса: ELEMENT_TYPE_VALUETYPE, если класс является типом значения; в противном случае — ELEMENT_TYPE_CLASS.</span><span class="sxs-lookup"><span data-stu-id="29416-116">The `elementType` parameter should be set to the correct element type for the class: ELEMENT_TYPE_VALUETYPE if the class is a value type; otherwise, ELEMENT_TYPE_CLASS.</span></span>  
  
 <span data-ttu-id="29416-117">Если класс принимает параметры типа (например, `ArrayList<T>`), можно использовать `GetParameterizedType` для создания объекта типа для экземпляра типа, такого как `ArrayList<int>`.</span><span class="sxs-lookup"><span data-stu-id="29416-117">If the class accepts type parameters (for example, `ArrayList<T>`), you can use `GetParameterizedType` to construct a type object for an instantiated type such as `ArrayList<int>`.</span></span>  
  
## <a name="background-information"></a><span data-ttu-id="29416-118">Основные сведения</span><span class="sxs-lookup"><span data-stu-id="29416-118">Background Information</span></span>  
 <span data-ttu-id="29416-119">В .NET Framework версиях 1,0 и 1,1 каждый тип в метаданных можно напрямую сопоставить с типом в выполняемом процессе.</span><span class="sxs-lookup"><span data-stu-id="29416-119">In the .NET Framework versions 1.0 and 1.1, every type in the metadata could be directly mapped to a type in the running process.</span></span> <span data-ttu-id="29416-120">Таким словами, тип метаданных и тип среды выполнения имеют одно представление в выполняющемся процессе.</span><span class="sxs-lookup"><span data-stu-id="29416-120">Thus, a metadata type and a runtime type had a single representation in the running process.</span></span> <span data-ttu-id="29416-121">Однако один универсальный тип в метаданных может быть сопоставлен с множеством различных экземпляров типа в выполняющемся процессе.</span><span class="sxs-lookup"><span data-stu-id="29416-121">However, one generic type in metadata can be mapped to many different instantiations of the type in the running process.</span></span> <span data-ttu-id="29416-122">Например, тип метаданных `SortedList<K,V>` может сопоставляться с `SortedList<String, EmployeeRecord>`, `SortedList<Int32, String>`, `SortedList<String,Array<Int32>>`и т. д.</span><span class="sxs-lookup"><span data-stu-id="29416-122">For example, the metadata type `SortedList<K,V>` can map to `SortedList<String, EmployeeRecord>`, `SortedList<Int32, String>`, `SortedList<String,Array<Int32>>`, and so on.</span></span> <span data-ttu-id="29416-123">Таким образом, необходим способ для управления созданием экземпляров типа.</span><span class="sxs-lookup"><span data-stu-id="29416-123">Thus, you need a way to handle type instantiation.</span></span>  
  
 <span data-ttu-id="29416-124">В .NET Framework версии 2,0 появился интерфейс `ICorDebugType`.</span><span class="sxs-lookup"><span data-stu-id="29416-124">The .NET Framework version 2.0 introduces the `ICorDebugType` interface.</span></span> <span data-ttu-id="29416-125">Для универсального типа объект `ICorDebugClass` или `ICorDebugClass2` представляет тип, не являющийся экземпляром (`SortedList<K,V>`), а объект `ICorDebugType` представляет различные экземпляры типов.</span><span class="sxs-lookup"><span data-stu-id="29416-125">For a generic type, an `ICorDebugClass` or `ICorDebugClass2` object represents the uninstantiated type (`SortedList<K,V>`), and an `ICorDebugType` object represents the various instantiated types.</span></span> <span data-ttu-id="29416-126">При наличии объекта `ICorDebugClass` или `ICorDebugClass2` можно создать объект `ICorDebugType` для любого экземпляра, вызвав метод `ICorDebugClass2::GetParameterizedType`.</span><span class="sxs-lookup"><span data-stu-id="29416-126">Given an `ICorDebugClass` or `ICorDebugClass2` object, you can create an `ICorDebugType` object for any instantiation by calling the `ICorDebugClass2::GetParameterizedType` method.</span></span> <span data-ttu-id="29416-127">Можно также создать объект `ICorDebugType` для простого типа, например Int32, или для типа, не являющегося универсальным.</span><span class="sxs-lookup"><span data-stu-id="29416-127">You can also create an `ICorDebugType` object for a simple type, such as Int32, or for a non-generic type.</span></span>  
  
 <span data-ttu-id="29416-128">Введение объекта `ICorDebugType`, представляющего представление типа во время выполнения, оказывает воздействие на весь интерфейс API.</span><span class="sxs-lookup"><span data-stu-id="29416-128">The introduction of the `ICorDebugType` object to represent the run-time notion of a type has a ripple effect throughout the API.</span></span> <span data-ttu-id="29416-129">Функции, которые ранее предпринимали `ICorDebugClass` или `ICorDebugClass2` объект или даже `CorElementType`, обобщены для получения объекта `ICorDebugType`.</span><span class="sxs-lookup"><span data-stu-id="29416-129">Functions that previously took an `ICorDebugClass` or `ICorDebugClass2` object or even a `CorElementType` value are generalized to take an `ICorDebugType` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="29416-130">Требования</span><span class="sxs-lookup"><span data-stu-id="29416-130">Requirements</span></span>  
 <span data-ttu-id="29416-131">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="29416-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="29416-132">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="29416-132">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="29416-133">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="29416-133">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="29416-134">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="29416-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>

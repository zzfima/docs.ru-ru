---
title: Интерфейс ICorDebugEval2
ms.date: 03/30/2017
api_name:
- ICorDebugEval2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval2
helpviewer_keywords:
- ICorDebugEval2 interface [.NET Framework debugging]
ms.assetid: fce34531-2687-406d-9131-d6ad94f2ce0e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3767368c9da8c97cd081787c0945a15552a1da46
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59092673"
---
# <a name="icordebugeval2-interface"></a><span data-ttu-id="50ac3-102">Интерфейс ICorDebugEval2</span><span class="sxs-lookup"><span data-stu-id="50ac3-102">ICorDebugEval2 Interface</span></span>

<span data-ttu-id="50ac3-103">Расширяет «ICorDebugEval» для предоставления поддержки универсальных типов.</span><span class="sxs-lookup"><span data-stu-id="50ac3-103">Extends "ICorDebugEval" to provide support for generic types.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="50ac3-104">Методы</span><span class="sxs-lookup"><span data-stu-id="50ac3-104">Methods</span></span>  
  
|<span data-ttu-id="50ac3-105">Метод</span><span class="sxs-lookup"><span data-stu-id="50ac3-105">Method</span></span>|<span data-ttu-id="50ac3-106">Описание</span><span class="sxs-lookup"><span data-stu-id="50ac3-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="50ac3-107">Метод CallParameterizedFunction</span><span class="sxs-lookup"><span data-stu-id="50ac3-107">CallParameterizedFunction Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-callparameterizedfunction-method.md)|<span data-ttu-id="50ac3-108">Задает вызов указанного «ICorDebugFunction», который может быть вложен в тип, конструктор которого принимает параметр типа, или можно использовать параметры типа.</span><span class="sxs-lookup"><span data-stu-id="50ac3-108">Sets up a call to the specified "ICorDebugFunction", which can be nested inside a type whose constructor takes type parameters, or can itself take type parameters.</span></span>|  
|[<span data-ttu-id="50ac3-109">Метод CreateValueForType</span><span class="sxs-lookup"><span data-stu-id="50ac3-109">CreateValueForType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-createvaluefortype-method.md)|<span data-ttu-id="50ac3-110">Возвращает указатель на новый «ICorDebugValue» указанного типа, с начальным значением null или нуль.</span><span class="sxs-lookup"><span data-stu-id="50ac3-110">Gets a pointer to a new "ICorDebugValue" of the specified type, with an initial value of null or zero.</span></span>|  
|[<span data-ttu-id="50ac3-111">Метод NewParameterizedArray</span><span class="sxs-lookup"><span data-stu-id="50ac3-111">NewParameterizedArray Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedarray-method.md)|<span data-ttu-id="50ac3-112">Выделяет новый массив элементов указанного типа и измерений.</span><span class="sxs-lookup"><span data-stu-id="50ac3-112">Allocates a new array of the specified element type and dimensions.</span></span>|  
|[<span data-ttu-id="50ac3-113">Метод NewParameterizedObject</span><span class="sxs-lookup"><span data-stu-id="50ac3-113">NewParameterizedObject Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobject-method.md)|<span data-ttu-id="50ac3-114">Создает новый объект параметризованного типа и вызывает метод-конструктор объекта.</span><span class="sxs-lookup"><span data-stu-id="50ac3-114">Instantiates a new parameterized type object and calls the object's constructor method.</span></span>|  
|[<span data-ttu-id="50ac3-115">Метод NewParameterizedObjectNoConstructor</span><span class="sxs-lookup"><span data-stu-id="50ac3-115">NewParameterizedObjectNoConstructor Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobjectnoconstructor-method.md)|<span data-ttu-id="50ac3-116">Создает новый объект параметризованного типа указанного класса не пытается вызвать метод-конструктор</span><span class="sxs-lookup"><span data-stu-id="50ac3-116">Instantiates a new parameterized type object of the specified class without attempting to call a constructor method</span></span>|  
|[<span data-ttu-id="50ac3-117">Метод NewStringWithLength</span><span class="sxs-lookup"><span data-stu-id="50ac3-117">NewStringWithLength Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newstringwithlength-method.md)|<span data-ttu-id="50ac3-118">Создает новую строку указанной длины с указанным содержимым.</span><span class="sxs-lookup"><span data-stu-id="50ac3-118">Creates a new string of the specified length with the specified contents.</span></span>|  
|[<span data-ttu-id="50ac3-119">Метод RudeAbort</span><span class="sxs-lookup"><span data-stu-id="50ac3-119">RudeAbort Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-rudeabort-method.md)|<span data-ttu-id="50ac3-120">Прерывает вычисление, `ICorDebugEval2` выполняет.</span><span class="sxs-lookup"><span data-stu-id="50ac3-120">Aborts the computation that this `ICorDebugEval2` is currently performing.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="50ac3-121">Примечания</span><span class="sxs-lookup"><span data-stu-id="50ac3-121">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="50ac3-122">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="50ac3-122">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="50ac3-123">Требования</span><span class="sxs-lookup"><span data-stu-id="50ac3-123">Requirements</span></span>  
 <span data-ttu-id="50ac3-124">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="50ac3-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="50ac3-125">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="50ac3-125">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="50ac3-126">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="50ac3-126">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="50ac3-127">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="50ac3-127">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="50ac3-128">См. также</span><span class="sxs-lookup"><span data-stu-id="50ac3-128">See also</span></span>

- [<span data-ttu-id="50ac3-129">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="50ac3-129">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

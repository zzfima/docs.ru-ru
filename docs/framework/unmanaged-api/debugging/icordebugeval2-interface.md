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
ms.openlocfilehash: d4315c9f5296e8c3ffc9d8241b929c71c2448db6
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2019
ms.locfileid: "56965869"
---
# <a name="icordebugeval2-interface"></a><span data-ttu-id="c9263-102">Интерфейс ICorDebugEval2</span><span class="sxs-lookup"><span data-stu-id="c9263-102">ICorDebugEval2 Interface</span></span>

<span data-ttu-id="c9263-103">Расширяет «ICorDebugEval» для предоставления поддержки универсальных типов.</span><span class="sxs-lookup"><span data-stu-id="c9263-103">Extends "ICorDebugEval" to provide support for generic types.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c9263-104">Методы</span><span class="sxs-lookup"><span data-stu-id="c9263-104">Methods</span></span>  
  
|<span data-ttu-id="c9263-105">Метод</span><span class="sxs-lookup"><span data-stu-id="c9263-105">Method</span></span>|<span data-ttu-id="c9263-106">Описание</span><span class="sxs-lookup"><span data-stu-id="c9263-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c9263-107">Метод CallParameterizedFunction</span><span class="sxs-lookup"><span data-stu-id="c9263-107">CallParameterizedFunction Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-callparameterizedfunction-method.md)|<span data-ttu-id="c9263-108">Задает вызов указанного «ICorDebugFunction», который может быть вложен в тип, конструктор которого принимает параметр типа, или можно использовать параметры типа.</span><span class="sxs-lookup"><span data-stu-id="c9263-108">Sets up a call to the specified "ICorDebugFunction", which can be nested inside a type whose constructor takes type parameters, or can itself take type parameters.</span></span>|  
|[<span data-ttu-id="c9263-109">Метод CreateValueForType</span><span class="sxs-lookup"><span data-stu-id="c9263-109">CreateValueForType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-createvaluefortype-method.md)|<span data-ttu-id="c9263-110">Возвращает указатель на новый «ICorDebugValue» указанного типа, с начальным значением null или нуль.</span><span class="sxs-lookup"><span data-stu-id="c9263-110">Gets a pointer to a new "ICorDebugValue" of the specified type, with an initial value of null or zero.</span></span>|  
|[<span data-ttu-id="c9263-111">Метод NewParameterizedArray</span><span class="sxs-lookup"><span data-stu-id="c9263-111">NewParameterizedArray Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedarray-method.md)|<span data-ttu-id="c9263-112">Выделяет новый массив элементов указанного типа и измерений.</span><span class="sxs-lookup"><span data-stu-id="c9263-112">Allocates a new array of the specified element type and dimensions.</span></span>|  
|[<span data-ttu-id="c9263-113">Метод NewParameterizedObject</span><span class="sxs-lookup"><span data-stu-id="c9263-113">NewParameterizedObject Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobject-method.md)|<span data-ttu-id="c9263-114">Создает новый объект параметризованного типа и вызывает метод-конструктор объекта.</span><span class="sxs-lookup"><span data-stu-id="c9263-114">Instantiates a new parameterized type object and calls the object's constructor method.</span></span>|  
|[<span data-ttu-id="c9263-115">Метод NewParameterizedObjectNoConstructor</span><span class="sxs-lookup"><span data-stu-id="c9263-115">NewParameterizedObjectNoConstructor Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobjectnoconstructor-method.md)|<span data-ttu-id="c9263-116">Создает новый объект параметризованного типа указанного класса не пытается вызвать метод-конструктор</span><span class="sxs-lookup"><span data-stu-id="c9263-116">Instantiates a new parameterized type object of the specified class without attempting to call a constructor method</span></span>|  
|[<span data-ttu-id="c9263-117">Метод NewStringWithLength</span><span class="sxs-lookup"><span data-stu-id="c9263-117">NewStringWithLength Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newstringwithlength-method.md)|<span data-ttu-id="c9263-118">Создает новую строку указанной длины с указанным содержимым.</span><span class="sxs-lookup"><span data-stu-id="c9263-118">Creates a new string of the specified length with the specified contents.</span></span>|  
|[<span data-ttu-id="c9263-119">Метод RudeAbort</span><span class="sxs-lookup"><span data-stu-id="c9263-119">RudeAbort Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-rudeabort-method.md)|<span data-ttu-id="c9263-120">Прерывает вычисление, `ICorDebugEval2` выполняет.</span><span class="sxs-lookup"><span data-stu-id="c9263-120">Aborts the computation that this `ICorDebugEval2` is currently performing.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c9263-121">Примечания</span><span class="sxs-lookup"><span data-stu-id="c9263-121">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c9263-122">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="c9263-122">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c9263-123">Требования</span><span class="sxs-lookup"><span data-stu-id="c9263-123">Requirements</span></span>  
 <span data-ttu-id="c9263-124">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c9263-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c9263-125">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c9263-125">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c9263-126">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c9263-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c9263-127">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c9263-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9263-128">См. также</span><span class="sxs-lookup"><span data-stu-id="c9263-128">See also</span></span>
- [<span data-ttu-id="c9263-129">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="c9263-129">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

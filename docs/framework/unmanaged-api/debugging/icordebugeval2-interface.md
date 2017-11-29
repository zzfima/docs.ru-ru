---
title: "ICorDebugEval2 интерфейс1"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugEval2
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugEval2
helpviewer_keywords: ICorDebugEval2 interface [.NET Framework debugging]
ms.assetid: fce34531-2687-406d-9131-d6ad94f2ce0e
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: fbcf36ff7aca84299c55083b4ae135ce0a9ec4f3
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugeval2-interface1"></a><span data-ttu-id="cc36d-102">ICorDebugEval2 интерфейс1</span><span class="sxs-lookup"><span data-stu-id="cc36d-102">ICorDebugEval2 Interface1</span></span>
<span data-ttu-id="cc36d-103">Расширяет «ICorDebugEval» для предоставления поддержки универсальных типов.</span><span class="sxs-lookup"><span data-stu-id="cc36d-103">Extends "ICorDebugEval" to provide support for generic types.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="cc36d-104">Методы</span><span class="sxs-lookup"><span data-stu-id="cc36d-104">Methods</span></span>  
  
|<span data-ttu-id="cc36d-105">Метод</span><span class="sxs-lookup"><span data-stu-id="cc36d-105">Method</span></span>|<span data-ttu-id="cc36d-106">Описание</span><span class="sxs-lookup"><span data-stu-id="cc36d-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="cc36d-107">Метод CallParameterizedFunction</span><span class="sxs-lookup"><span data-stu-id="cc36d-107">CallParameterizedFunction Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-callparameterizedfunction-method.md)|<span data-ttu-id="cc36d-108">Устанавливает вызов указанного «ICorDebugFunction», который может быть вложен в тип, конструктор которого принимает параметр типа, или можно принимать параметров типов.</span><span class="sxs-lookup"><span data-stu-id="cc36d-108">Sets up a call to the specified "ICorDebugFunction", which can be nested inside a type whose constructor takes type parameters, or can itself take type parameters.</span></span>|  
|[<span data-ttu-id="cc36d-109">Метод CreateValueForType</span><span class="sxs-lookup"><span data-stu-id="cc36d-109">CreateValueForType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-createvaluefortype-method.md)|<span data-ttu-id="cc36d-110">Возвращает указатель на нового «ICorDebugValue» указанного типа с начальным значением null или же равно нулю.</span><span class="sxs-lookup"><span data-stu-id="cc36d-110">Gets a pointer to a new "ICorDebugValue" of the specified type, with an initial value of null or zero.</span></span>|  
|[<span data-ttu-id="cc36d-111">Метод NewParameterizedArray</span><span class="sxs-lookup"><span data-stu-id="cc36d-111">NewParameterizedArray Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedarray-method.md)|<span data-ttu-id="cc36d-112">Выделяет новый массив с заданным типом элементов и измерений.</span><span class="sxs-lookup"><span data-stu-id="cc36d-112">Allocates a new array of the specified element type and dimensions.</span></span>|  
|[<span data-ttu-id="cc36d-113">Метод NewParameterizedObject</span><span class="sxs-lookup"><span data-stu-id="cc36d-113">NewParameterizedObject Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobject-method.md)|<span data-ttu-id="cc36d-114">Создает новый объект параметризованного типа и вызывает метод конструктора объекта.</span><span class="sxs-lookup"><span data-stu-id="cc36d-114">Instantiates a new parameterized type object and calls the object's constructor method.</span></span>|  
|[<span data-ttu-id="cc36d-115">Метод NewParameterizedObjectNoConstructor</span><span class="sxs-lookup"><span data-stu-id="cc36d-115">NewParameterizedObjectNoConstructor Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobjectnoconstructor-method.md)|<span data-ttu-id="cc36d-116">Создает новый объект параметризованного типа указанного класса без попытки вызова метода конструктора</span><span class="sxs-lookup"><span data-stu-id="cc36d-116">Instantiates a new parameterized type object of the specified class without attempting to call a constructor method</span></span>|  
|[<span data-ttu-id="cc36d-117">Метод NewStringWithLength</span><span class="sxs-lookup"><span data-stu-id="cc36d-117">NewStringWithLength Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newstringwithlength-method.md)|<span data-ttu-id="cc36d-118">Создает новую строку указанной длины с указанным содержимым.</span><span class="sxs-lookup"><span data-stu-id="cc36d-118">Creates a new string of the specified length with the specified contents.</span></span>|  
|[<span data-ttu-id="cc36d-119">Метод RudeAbort</span><span class="sxs-lookup"><span data-stu-id="cc36d-119">RudeAbort Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-rudeabort-method.md)|<span data-ttu-id="cc36d-120">Прерывает вычисление этим `ICorDebugEval2` в настоящее время выполнения.</span><span class="sxs-lookup"><span data-stu-id="cc36d-120">Aborts the computation that this `ICorDebugEval2` is currently performing.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cc36d-121">Примечания</span><span class="sxs-lookup"><span data-stu-id="cc36d-121">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cc36d-122">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="cc36d-122">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cc36d-123">Требования</span><span class="sxs-lookup"><span data-stu-id="cc36d-123">Requirements</span></span>  
 <span data-ttu-id="cc36d-124">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cc36d-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cc36d-125">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cc36d-125">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cc36d-126">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cc36d-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cc36d-127">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cc36d-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc36d-128">См. также</span><span class="sxs-lookup"><span data-stu-id="cc36d-128">See Also</span></span>  
 [<span data-ttu-id="cc36d-129">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="cc36d-129">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

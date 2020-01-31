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
ms.openlocfilehash: e69b32430651edd0222db874e2659bd959f89549
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788708"
---
# <a name="icordebugeval2-interface"></a><span data-ttu-id="5d9e3-102">Интерфейс ICorDebugEval2</span><span class="sxs-lookup"><span data-stu-id="5d9e3-102">ICorDebugEval2 Interface</span></span>

<span data-ttu-id="5d9e3-103">Расширяет "ICorDebugEval" для обеспечения поддержки универсальных типов.</span><span class="sxs-lookup"><span data-stu-id="5d9e3-103">Extends "ICorDebugEval" to provide support for generic types.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5d9e3-104">Методы</span><span class="sxs-lookup"><span data-stu-id="5d9e3-104">Methods</span></span>  
  
|<span data-ttu-id="5d9e3-105">Метод</span><span class="sxs-lookup"><span data-stu-id="5d9e3-105">Method</span></span>|<span data-ttu-id="5d9e3-106">Описание</span><span class="sxs-lookup"><span data-stu-id="5d9e3-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5d9e3-107">Метод CallParameterizedFunction</span><span class="sxs-lookup"><span data-stu-id="5d9e3-107">CallParameterizedFunction Method</span></span>](icordebugeval2-callparameterizedfunction-method.md)|<span data-ttu-id="5d9e3-108">Настраивает вызов указанного "ICorDebugFunction", который может быть вложен в тип, конструктор которого принимает параметры типа или сам может принимать параметры типа.</span><span class="sxs-lookup"><span data-stu-id="5d9e3-108">Sets up a call to the specified "ICorDebugFunction", which can be nested inside a type whose constructor takes type parameters, or can itself take type parameters.</span></span>|  
|[<span data-ttu-id="5d9e3-109">Метод CreateValueForType</span><span class="sxs-lookup"><span data-stu-id="5d9e3-109">CreateValueForType Method</span></span>](icordebugeval2-createvaluefortype-method.md)|<span data-ttu-id="5d9e3-110">Возвращает указатель на новый "ICorDebugValue" указанного типа с начальным значением NULL или нулем.</span><span class="sxs-lookup"><span data-stu-id="5d9e3-110">Gets a pointer to a new "ICorDebugValue" of the specified type, with an initial value of null or zero.</span></span>|  
|[<span data-ttu-id="5d9e3-111">Метод NewParameterizedArray</span><span class="sxs-lookup"><span data-stu-id="5d9e3-111">NewParameterizedArray Method</span></span>](icordebugeval2-newparameterizedarray-method.md)|<span data-ttu-id="5d9e3-112">Выделяет новый массив указанного типа элемента и измерений.</span><span class="sxs-lookup"><span data-stu-id="5d9e3-112">Allocates a new array of the specified element type and dimensions.</span></span>|  
|[<span data-ttu-id="5d9e3-113">Метод NewParameterizedObject</span><span class="sxs-lookup"><span data-stu-id="5d9e3-113">NewParameterizedObject Method</span></span>](icordebugeval2-newparameterizedobject-method.md)|<span data-ttu-id="5d9e3-114">Создает новый объект параметризованного типа и вызывает метод конструктора объекта.</span><span class="sxs-lookup"><span data-stu-id="5d9e3-114">Instantiates a new parameterized type object and calls the object's constructor method.</span></span>|  
|[<span data-ttu-id="5d9e3-115">Метод NewParameterizedObjectNoConstructor</span><span class="sxs-lookup"><span data-stu-id="5d9e3-115">NewParameterizedObjectNoConstructor Method</span></span>](icordebugeval2-newparameterizedobjectnoconstructor-method.md)|<span data-ttu-id="5d9e3-116">Создает новый объект параметризованного типа указанного класса без попытки вызова метода конструктора</span><span class="sxs-lookup"><span data-stu-id="5d9e3-116">Instantiates a new parameterized type object of the specified class without attempting to call a constructor method</span></span>|  
|[<span data-ttu-id="5d9e3-117">Метод NewStringWithLength</span><span class="sxs-lookup"><span data-stu-id="5d9e3-117">NewStringWithLength Method</span></span>](icordebugeval2-newstringwithlength-method.md)|<span data-ttu-id="5d9e3-118">Создает новую строку указанной длины с указанным содержимым.</span><span class="sxs-lookup"><span data-stu-id="5d9e3-118">Creates a new string of the specified length with the specified contents.</span></span>|  
|[<span data-ttu-id="5d9e3-119">Метод RudeAbort</span><span class="sxs-lookup"><span data-stu-id="5d9e3-119">RudeAbort Method</span></span>](icordebugeval2-rudeabort-method.md)|<span data-ttu-id="5d9e3-120">Прерывает вычисление, выполняемое в данный момент `ICorDebugEval2`.</span><span class="sxs-lookup"><span data-stu-id="5d9e3-120">Aborts the computation that this `ICorDebugEval2` is currently performing.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5d9e3-121">Заметки</span><span class="sxs-lookup"><span data-stu-id="5d9e3-121">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5d9e3-122">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="5d9e3-122">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5d9e3-123">Требования</span><span class="sxs-lookup"><span data-stu-id="5d9e3-123">Requirements</span></span>  
 <span data-ttu-id="5d9e3-124">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5d9e3-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5d9e3-125">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5d9e3-125">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5d9e3-126">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5d9e3-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5d9e3-127">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5d9e3-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d9e3-128">См. также:</span><span class="sxs-lookup"><span data-stu-id="5d9e3-128">See also</span></span>

- [<span data-ttu-id="5d9e3-129">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="5d9e3-129">Debugging Interfaces</span></span>](debugging-interfaces.md)

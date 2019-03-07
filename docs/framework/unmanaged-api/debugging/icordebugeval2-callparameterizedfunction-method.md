---
title: Метод ICorDebugEval2::CallParameterizedFunction
ms.date: 03/30/2017
api_name:
- ICorDebugEval2.CallParameterizedFunction
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval2::CallParameterizedFunction
helpviewer_keywords:
- ICorDebugEval2::CallParameterizedFunction method [.NET Framework debugging]
- CallParameterizedFunction method [.NET Framework debugging]
ms.assetid: 72f54a45-dbe6-4bb4-8c99-e879a27368e5
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cba4eb2b76d7057a5ed66a35342a79615cb8539f
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57487733"
---
# <a name="icordebugeval2callparameterizedfunction-method"></a><span data-ttu-id="8d8a7-102">Метод ICorDebugEval2::CallParameterizedFunction</span><span class="sxs-lookup"><span data-stu-id="8d8a7-102">ICorDebugEval2::CallParameterizedFunction Method</span></span>
<span data-ttu-id="8d8a7-103">Устанавливает для указанного ICorDebugFunction, который может быть вложен в класс, конструктор которого принимает вызов <xref:System.Type> параметры или сам может занять <xref:System.Type> параметров.</span><span class="sxs-lookup"><span data-stu-id="8d8a7-103">Sets up a call to the specified ICorDebugFunction, which can be nested inside a class whose constructor takes <xref:System.Type> parameters, or can itself take <xref:System.Type> parameters.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8d8a7-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8d8a7-104">Syntax</span></span>  
  
```  
HRESULT CallParameterizedFunction (  
    [in] ICorDebugFunction     *pFunction,  
    [in] ULONG32               nTypeArgs,  
    [in, size_is(nTypeArgs)] ICorDebugType *ppTypeArgs[],  
    [in] ULONG32               nArgs,  
    [in, size_is(nArgs)] ICorDebugValue *ppArgs[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8d8a7-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="8d8a7-105">Parameters</span></span>  
 `pFunction`  
 <span data-ttu-id="8d8a7-106">[in] Указатель на `ICorDebugFunction` объект, который представляет функцию для вызова.</span><span class="sxs-lookup"><span data-stu-id="8d8a7-106">[in] A pointer to an `ICorDebugFunction` object that represents the function to be called.</span></span>  
  
 `nTypeArgs`  
 <span data-ttu-id="8d8a7-107">[in] Число аргументов, функция принимает.</span><span class="sxs-lookup"><span data-stu-id="8d8a7-107">[in] The number of arguments that the function takes.</span></span>  
  
 `ppTypeArgs`  
 <span data-ttu-id="8d8a7-108">[in] Массив указателей, каждый из которых указывает ICorDebugType объект, представляющий аргумент функции.</span><span class="sxs-lookup"><span data-stu-id="8d8a7-108">[in] An array of pointers, each of which points to an ICorDebugType object that represents a function argument.</span></span>  
  
 `nArgs`  
 <span data-ttu-id="8d8a7-109">[in] Число значений, переданных в функцию.</span><span class="sxs-lookup"><span data-stu-id="8d8a7-109">[in] The number of values passed in the function.</span></span>  
  
 `ppArgs`  
 <span data-ttu-id="8d8a7-110">[in] Массив указателей, каждый из которых указывает ICorDebugValue объект, представляющий значение передается в качестве аргумента функции.</span><span class="sxs-lookup"><span data-stu-id="8d8a7-110">[in] An array of pointers, each of which points to an ICorDebugValue object that represents a value passed in a function argument.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8d8a7-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="8d8a7-111">Remarks</span></span>  
 <span data-ttu-id="8d8a7-112">`CallParameterizedFunction` Подобно [ICorDebugEval::CallFunction](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-callfunction-method.md) за исключением того, что функция может быть внутри класса с параметрами типа, может сам принимают параметры типа или оба.</span><span class="sxs-lookup"><span data-stu-id="8d8a7-112">`CallParameterizedFunction` is like [ICorDebugEval::CallFunction](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-callfunction-method.md) except that the function may be inside a class with type parameters, may itself take type parameters, or both.</span></span> <span data-ttu-id="8d8a7-113">Аргументы типа должны быть заданы сначала для класса, а затем для функции.</span><span class="sxs-lookup"><span data-stu-id="8d8a7-113">The type arguments should be given first for the class, and then for the function.</span></span>  
  
 <span data-ttu-id="8d8a7-114">Если функция находится в другом домене приложения, будет выполнен переход.</span><span class="sxs-lookup"><span data-stu-id="8d8a7-114">If the function is in a different application domain, a transition will occur.</span></span> <span data-ttu-id="8d8a7-115">Тем не менее все аргументы типа и значения должны быть в целевом домене приложения.</span><span class="sxs-lookup"><span data-stu-id="8d8a7-115">However, all type and value arguments must be in the target application domain.</span></span>  
  
 <span data-ttu-id="8d8a7-116">Вычисление функции могут выполняться только в ограниченном числе сценариев.</span><span class="sxs-lookup"><span data-stu-id="8d8a7-116">Function evaluation can be performed only in limited scenarios.</span></span> <span data-ttu-id="8d8a7-117">Если `CallParameterizedFunction` или `ICorDebugEval::CallFunction` завершается сбоем, возвращенное значение HRESULT указывает наиболее общие возможные причины сбоя.</span><span class="sxs-lookup"><span data-stu-id="8d8a7-117">If `CallParameterizedFunction` or `ICorDebugEval::CallFunction` fails, the returned HRESULT will indicate the most general possible reason for failure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8d8a7-118">Требования</span><span class="sxs-lookup"><span data-stu-id="8d8a7-118">Requirements</span></span>  
 <span data-ttu-id="8d8a7-119">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8d8a7-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8d8a7-120">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8d8a7-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8d8a7-121">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8d8a7-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8d8a7-122">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8d8a7-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>

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
ms.openlocfilehash: 77d9ec0cf1cbca63382e7f29de85c2f9566dc2bb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33416170"
---
# <a name="icordebugeval2callparameterizedfunction-method"></a><span data-ttu-id="9bd1a-102">Метод ICorDebugEval2::CallParameterizedFunction</span><span class="sxs-lookup"><span data-stu-id="9bd1a-102">ICorDebugEval2::CallParameterizedFunction Method</span></span>
<span data-ttu-id="9bd1a-103">Устанавливает для указанного ICorDebugFunction, который может быть вложен в класс, конструктор которого принимает вызов <xref:System.Type> параметры или сам может занять <xref:System.Type> параметров.</span><span class="sxs-lookup"><span data-stu-id="9bd1a-103">Sets up a call to the specified ICorDebugFunction, which can be nested inside a class whose constructor takes <xref:System.Type> parameters, or can itself take <xref:System.Type> parameters.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9bd1a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9bd1a-104">Syntax</span></span>  
  
```  
HRESULT CallParameterizedFunction (  
    [in] ICorDebugFunction     *pFunction,  
    [in] ULONG32               nTypeArgs,  
    [in, size_is(nTypeArgs)] ICorDebugType *ppTypeArgs[],  
    [in] ULONG32               nArgs,  
    [in, size_is(nArgs)] ICorDebugValue *ppArgs[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9bd1a-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="9bd1a-105">Parameters</span></span>  
 `pFunction`  
 <span data-ttu-id="9bd1a-106">[in] Указатель на `ICorDebugFunction` объект, который представляет вызываемую функцию.</span><span class="sxs-lookup"><span data-stu-id="9bd1a-106">[in] A pointer to an `ICorDebugFunction` object that represents the function to be called.</span></span>  
  
 `nTypeArgs`  
 <span data-ttu-id="9bd1a-107">[in] Количество аргументов, которые принимает функция.</span><span class="sxs-lookup"><span data-stu-id="9bd1a-107">[in] The number of arguments that the function takes.</span></span>  
  
 `ppTypeArgs`  
 <span data-ttu-id="9bd1a-108">[in] Массив указателей, каждый из которых указывает на объект ICorDebugType, представляющий аргумент функции.</span><span class="sxs-lookup"><span data-stu-id="9bd1a-108">[in] An array of pointers, each of which points to an ICorDebugType object that represents a function argument.</span></span>  
  
 `nArgs`  
 <span data-ttu-id="9bd1a-109">[in] Количество значений, переданных в функцию.</span><span class="sxs-lookup"><span data-stu-id="9bd1a-109">[in] The number of values passed in the function.</span></span>  
  
 `ppArgs`  
 <span data-ttu-id="9bd1a-110">[in] Массив указателей, каждый из которых указывает на объект ICorDebugValue, представляющий значение, переданное аргументу функции.</span><span class="sxs-lookup"><span data-stu-id="9bd1a-110">[in] An array of pointers, each of which points to an ICorDebugValue object that represents a value passed in a function argument.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9bd1a-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="9bd1a-111">Remarks</span></span>  
 <span data-ttu-id="9bd1a-112">`CallParameterizedFunction` Подобно [ICorDebugEval::CallFunction](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-callfunction-method.md) за исключением того, что функция может быть внутри класса с параметрами типов, может сам принимают параметры типа или оба.</span><span class="sxs-lookup"><span data-stu-id="9bd1a-112">`CallParameterizedFunction` is like [ICorDebugEval::CallFunction](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-callfunction-method.md) except that the function may be inside a class with type parameters, may itself take type parameters, or both.</span></span> <span data-ttu-id="9bd1a-113">Аргументы типа должны быть заданы сначала для класса, а затем для функции.</span><span class="sxs-lookup"><span data-stu-id="9bd1a-113">The type arguments should be given first for the class, and then for the function.</span></span>  
  
 <span data-ttu-id="9bd1a-114">Если функция находится в другом домене приложения, будет выполнен переход.</span><span class="sxs-lookup"><span data-stu-id="9bd1a-114">If the function is in a different application domain, a transition will occur.</span></span> <span data-ttu-id="9bd1a-115">Однако все аргументы типа и значения должны быть в целевом домене приложения.</span><span class="sxs-lookup"><span data-stu-id="9bd1a-115">However, all type and value arguments must be in the target application domain.</span></span>  
  
 <span data-ttu-id="9bd1a-116">Вычисление функции могут выполняться только в ограниченных сценариях.</span><span class="sxs-lookup"><span data-stu-id="9bd1a-116">Function evaluation can be performed only in limited scenarios.</span></span> <span data-ttu-id="9bd1a-117">Если `CallParameterizedFunction` или `ICorDebugEval::CallFunction` завершается ошибкой, возвращенное значение HRESULT указывает наиболее общие возможную причину сбоя.</span><span class="sxs-lookup"><span data-stu-id="9bd1a-117">If `CallParameterizedFunction` or `ICorDebugEval::CallFunction` fails, the returned HRESULT will indicate the most general possible reason for failure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9bd1a-118">Требования</span><span class="sxs-lookup"><span data-stu-id="9bd1a-118">Requirements</span></span>  
 <span data-ttu-id="9bd1a-119">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9bd1a-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9bd1a-120">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9bd1a-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9bd1a-121">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9bd1a-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9bd1a-122">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9bd1a-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>

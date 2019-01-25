---
title: Метод ICorDebugEval::CallFunction
ms.date: 03/30/2017
api_name:
- ICorDebugEval.CallFunction
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval::CallFunction
helpviewer_keywords:
- ICorDebugEval::CallFunction method [.NET Framework debugging]
- CallFunction method [.NET Framework debugging]
ms.assetid: 7f470c5c-e1c0-4d8d-aad8-830f113ae751
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 493b4850436b3724287210878992d1d8ce8fe168
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54589403"
---
# <a name="icordebugevalcallfunction-method"></a><span data-ttu-id="9d7d6-102">Метод ICorDebugEval::CallFunction</span><span class="sxs-lookup"><span data-stu-id="9d7d6-102">ICorDebugEval::CallFunction Method</span></span>
<span data-ttu-id="9d7d6-103">Настраивает вызов указанной функции.</span><span class="sxs-lookup"><span data-stu-id="9d7d6-103">Sets up a call to the specified function.</span></span>  
  
 <span data-ttu-id="9d7d6-104">Этот метод является устаревшим в .NET Framework версии 2.0.</span><span class="sxs-lookup"><span data-stu-id="9d7d6-104">This method is obsolete in the .NET Framework version 2.0.</span></span> <span data-ttu-id="9d7d6-105">Используйте [ICorDebugEval2::CallParameterizedFunction](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-callparameterizedfunction-method.md) вместо этого.</span><span class="sxs-lookup"><span data-stu-id="9d7d6-105">Use [ICorDebugEval2::CallParameterizedFunction](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-callparameterizedfunction-method.md) instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9d7d6-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9d7d6-106">Syntax</span></span>  
  
```  
HRESULT CallFunction (  
    [in] ICorDebugFunction  *pFunction,  
    [in] ULONG32            nArgs,  
    [in, size_is(nArgs)] ICorDebugValue *ppArgs[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9d7d6-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="9d7d6-107">Parameters</span></span>  
 `pFunction`  
 <span data-ttu-id="9d7d6-108">[in] Указатель на объект ICorDebugFunction, который указывает функция, которая вызывается.</span><span class="sxs-lookup"><span data-stu-id="9d7d6-108">[in] Pointer to an ICorDebugFunction object that specifies the function to be called.</span></span>  
  
 `nArgs`  
 <span data-ttu-id="9d7d6-109">[in] Число аргументов для функции.</span><span class="sxs-lookup"><span data-stu-id="9d7d6-109">[in] The number of arguments for the function.</span></span>  
  
 `ppArgs`  
 <span data-ttu-id="9d7d6-110">[in] Массив указателей, каждый из которых указывает на объект ICorDebugValue, который указывает аргумент, передаваемый в функцию.</span><span class="sxs-lookup"><span data-stu-id="9d7d6-110">[in] An array of pointers, each of which points to an ICorDebugValue object that specifies an argument to be passed to the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9d7d6-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="9d7d6-111">Remarks</span></span>  
 <span data-ttu-id="9d7d6-112">Если функция является виртуальной, `CallFunction` выполнит виртуальной диспетчеризации.</span><span class="sxs-lookup"><span data-stu-id="9d7d6-112">If the function is virtual, `CallFunction` will perform virtual dispatch.</span></span> <span data-ttu-id="9d7d6-113">Если функция находится в другом домене приложения, будет выполнен переход, до тех пор, пока все аргументы имеют также в этом домене приложения.</span><span class="sxs-lookup"><span data-stu-id="9d7d6-113">If the function is in a different application domain, a transition will occur as long as all arguments are also in that application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9d7d6-114">Требования</span><span class="sxs-lookup"><span data-stu-id="9d7d6-114">Requirements</span></span>  
 <span data-ttu-id="9d7d6-115">**Платформы:** WindowSee [требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9d7d6-115">**Platforms:** WindowSee [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9d7d6-116">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9d7d6-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9d7d6-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9d7d6-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9d7d6-118">**Версии платформы .NET framework:** 1.1, 1.0</span><span class="sxs-lookup"><span data-stu-id="9d7d6-118">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d7d6-119">См. также</span><span class="sxs-lookup"><span data-stu-id="9d7d6-119">See also</span></span>
- [<span data-ttu-id="9d7d6-120">Метод CallParameterizedFunction</span><span class="sxs-lookup"><span data-stu-id="9d7d6-120">CallParameterizedFunction Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-callparameterizedfunction-method.md)

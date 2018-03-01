---
title: "Метод ICorDebugEval::CallFunction"
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 3c2d5582c9ac69692546e9a2310c4d0c9cdde83e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugevalcallfunction-method"></a><span data-ttu-id="7b48c-102">Метод ICorDebugEval::CallFunction</span><span class="sxs-lookup"><span data-stu-id="7b48c-102">ICorDebugEval::CallFunction Method</span></span>
<span data-ttu-id="7b48c-103">Настраивает вызов указанной функции.</span><span class="sxs-lookup"><span data-stu-id="7b48c-103">Sets up a call to the specified function.</span></span>  
  
 <span data-ttu-id="7b48c-104">Этот метод является устаревшим в .NET Framework версии 2.0.</span><span class="sxs-lookup"><span data-stu-id="7b48c-104">This method is obsolete in the .NET Framework version 2.0.</span></span> <span data-ttu-id="7b48c-105">Используйте [ICorDebugEval2::CallParameterizedFunction](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-callparameterizedfunction-method.md) вместо него.</span><span class="sxs-lookup"><span data-stu-id="7b48c-105">Use [ICorDebugEval2::CallParameterizedFunction](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-callparameterizedfunction-method.md) instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7b48c-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7b48c-106">Syntax</span></span>  
  
```  
HRESULT CallFunction (  
    [in] ICorDebugFunction  *pFunction,  
    [in] ULONG32            nArgs,  
    [in, size_is(nArgs)] ICorDebugValue *ppArgs[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7b48c-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="7b48c-107">Parameters</span></span>  
 `pFunction`  
 <span data-ttu-id="7b48c-108">[in] Указатель на объект ICorDebugFunction, который задает вызываемую функцию.</span><span class="sxs-lookup"><span data-stu-id="7b48c-108">[in] Pointer to an ICorDebugFunction object that specifies the function to be called.</span></span>  
  
 `nArgs`  
 <span data-ttu-id="7b48c-109">[in] Число аргументов для функции.</span><span class="sxs-lookup"><span data-stu-id="7b48c-109">[in] The number of arguments for the function.</span></span>  
  
 `ppArgs`  
 <span data-ttu-id="7b48c-110">[in] Массив указателей, каждый из которых указывает на объект ICorDebugValue, который указывает аргумент, передаваемый в функцию.</span><span class="sxs-lookup"><span data-stu-id="7b48c-110">[in] An array of pointers, each of which points to an ICorDebugValue object that specifies an argument to be passed to the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7b48c-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="7b48c-111">Remarks</span></span>  
 <span data-ttu-id="7b48c-112">Если функция является виртуальной, `CallFunction` выполнит виртуальной отправки.</span><span class="sxs-lookup"><span data-stu-id="7b48c-112">If the function is virtual, `CallFunction` will perform virtual dispatch.</span></span> <span data-ttu-id="7b48c-113">Если функция находится в другом домене приложения, будет выполнен переход при условии, что все аргументы также имеются в этом домене приложения.</span><span class="sxs-lookup"><span data-stu-id="7b48c-113">If the function is in a different application domain, a transition will occur as long as all arguments are also in that application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7b48c-114">Требования</span><span class="sxs-lookup"><span data-stu-id="7b48c-114">Requirements</span></span>  
 <span data-ttu-id="7b48c-115">**Платформы:** WindowSee [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7b48c-115">**Platforms:** WindowSee [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7b48c-116">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7b48c-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7b48c-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7b48c-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7b48c-118">**Версии платформы .NET framework:** 1.1, 1.0</span><span class="sxs-lookup"><span data-stu-id="7b48c-118">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b48c-119">См. также</span><span class="sxs-lookup"><span data-stu-id="7b48c-119">See Also</span></span>  
 [<span data-ttu-id="7b48c-120">Метод CallParameterizedFunction</span><span class="sxs-lookup"><span data-stu-id="7b48c-120">CallParameterizedFunction Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-callparameterizedfunction-method.md)

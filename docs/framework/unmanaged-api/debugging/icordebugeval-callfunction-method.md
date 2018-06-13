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
ms.openlocfilehash: 86d48461c601b53d4461331a11a0e0ac7ddc6e7c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33412556"
---
# <a name="icordebugevalcallfunction-method"></a><span data-ttu-id="4688b-102">Метод ICorDebugEval::CallFunction</span><span class="sxs-lookup"><span data-stu-id="4688b-102">ICorDebugEval::CallFunction Method</span></span>
<span data-ttu-id="4688b-103">Настраивает вызов указанной функции.</span><span class="sxs-lookup"><span data-stu-id="4688b-103">Sets up a call to the specified function.</span></span>  
  
 <span data-ttu-id="4688b-104">Этот метод является устаревшим в .NET Framework версии 2.0.</span><span class="sxs-lookup"><span data-stu-id="4688b-104">This method is obsolete in the .NET Framework version 2.0.</span></span> <span data-ttu-id="4688b-105">Используйте [ICorDebugEval2::CallParameterizedFunction](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-callparameterizedfunction-method.md) вместо него.</span><span class="sxs-lookup"><span data-stu-id="4688b-105">Use [ICorDebugEval2::CallParameterizedFunction](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-callparameterizedfunction-method.md) instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4688b-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4688b-106">Syntax</span></span>  
  
```  
HRESULT CallFunction (  
    [in] ICorDebugFunction  *pFunction,  
    [in] ULONG32            nArgs,  
    [in, size_is(nArgs)] ICorDebugValue *ppArgs[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4688b-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="4688b-107">Parameters</span></span>  
 `pFunction`  
 <span data-ttu-id="4688b-108">[in] Указатель на объект ICorDebugFunction, который задает вызываемую функцию.</span><span class="sxs-lookup"><span data-stu-id="4688b-108">[in] Pointer to an ICorDebugFunction object that specifies the function to be called.</span></span>  
  
 `nArgs`  
 <span data-ttu-id="4688b-109">[in] Число аргументов для функции.</span><span class="sxs-lookup"><span data-stu-id="4688b-109">[in] The number of arguments for the function.</span></span>  
  
 `ppArgs`  
 <span data-ttu-id="4688b-110">[in] Массив указателей, каждый из которых указывает на объект ICorDebugValue, который указывает аргумент, передаваемый в функцию.</span><span class="sxs-lookup"><span data-stu-id="4688b-110">[in] An array of pointers, each of which points to an ICorDebugValue object that specifies an argument to be passed to the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4688b-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="4688b-111">Remarks</span></span>  
 <span data-ttu-id="4688b-112">Если функция является виртуальной, `CallFunction` выполнит виртуальной отправки.</span><span class="sxs-lookup"><span data-stu-id="4688b-112">If the function is virtual, `CallFunction` will perform virtual dispatch.</span></span> <span data-ttu-id="4688b-113">Если функция находится в другом домене приложения, будет выполнен переход при условии, что все аргументы также имеются в этом домене приложения.</span><span class="sxs-lookup"><span data-stu-id="4688b-113">If the function is in a different application domain, a transition will occur as long as all arguments are also in that application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4688b-114">Требования</span><span class="sxs-lookup"><span data-stu-id="4688b-114">Requirements</span></span>  
 <span data-ttu-id="4688b-115">**Платформы:** WindowSee [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4688b-115">**Platforms:** WindowSee [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4688b-116">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4688b-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4688b-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4688b-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4688b-118">**Версии платформы .NET framework:** 1.1, 1.0</span><span class="sxs-lookup"><span data-stu-id="4688b-118">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4688b-119">См. также</span><span class="sxs-lookup"><span data-stu-id="4688b-119">See Also</span></span>  
 [<span data-ttu-id="4688b-120">Метод CallParameterizedFunction</span><span class="sxs-lookup"><span data-stu-id="4688b-120">CallParameterizedFunction Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-callparameterizedfunction-method.md)

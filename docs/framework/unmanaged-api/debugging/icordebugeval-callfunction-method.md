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
ms.openlocfilehash: 66e51dc15f7d44ede26634571fa04c58e9735694
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57364155"
---
# <a name="icordebugevalcallfunction-method"></a><span data-ttu-id="c57bc-102">Метод ICorDebugEval::CallFunction</span><span class="sxs-lookup"><span data-stu-id="c57bc-102">ICorDebugEval::CallFunction Method</span></span>

<span data-ttu-id="c57bc-103">Настраивает вызов указанной функции.</span><span class="sxs-lookup"><span data-stu-id="c57bc-103">Sets up a call to the specified function.</span></span>

<span data-ttu-id="c57bc-104">Этот метод является устаревшим в .NET Framework версии 2.0.</span><span class="sxs-lookup"><span data-stu-id="c57bc-104">This method is obsolete in the .NET Framework version 2.0.</span></span> <span data-ttu-id="c57bc-105">Используйте [ICorDebugEval2::CallParameterizedFunction](icordebugeval2-callparameterizedfunction-method.md) вместо этого.</span><span class="sxs-lookup"><span data-stu-id="c57bc-105">Use [ICorDebugEval2::CallParameterizedFunction](icordebugeval2-callparameterizedfunction-method.md) instead.</span></span>

## <a name="syntax"></a><span data-ttu-id="c57bc-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c57bc-106">Syntax</span></span>

```cpp
HRESULT CallFunction (
    [in] ICorDebugFunction  *pFunction,
    [in] ULONG32            nArgs,
    [in, size_is(nArgs)] ICorDebugValue *ppArgs[]
);
```

## <a name="parameters"></a><span data-ttu-id="c57bc-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="c57bc-107">Parameters</span></span>

`pFunction`\
<span data-ttu-id="c57bc-108">[in] Указатель на объект ICorDebugFunction, который указывает функция, которая вызывается.</span><span class="sxs-lookup"><span data-stu-id="c57bc-108">[in] Pointer to an ICorDebugFunction object that specifies the function to be called.</span></span>

`nArgs`\
<span data-ttu-id="c57bc-109">[in] Число аргументов для функции.</span><span class="sxs-lookup"><span data-stu-id="c57bc-109">[in] The number of arguments for the function.</span></span>

`ppArgs`\
<span data-ttu-id="c57bc-110">[in] Массив указателей, каждый из которых указывает на объект ICorDebugValue, который указывает аргумент, передаваемый в функцию.</span><span class="sxs-lookup"><span data-stu-id="c57bc-110">[in] An array of pointers, each of which points to an ICorDebugValue object that specifies an argument to be passed to the function.</span></span>

## <a name="remarks"></a><span data-ttu-id="c57bc-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="c57bc-111">Remarks</span></span>

<span data-ttu-id="c57bc-112">Если функция является виртуальной, `CallFunction` выполнит виртуальной диспетчеризации.</span><span class="sxs-lookup"><span data-stu-id="c57bc-112">If the function is virtual, `CallFunction` will perform virtual dispatch.</span></span> <span data-ttu-id="c57bc-113">Если функция находится в другом домене приложения, будет выполнен переход, до тех пор, пока все аргументы имеют также в этом домене приложения.</span><span class="sxs-lookup"><span data-stu-id="c57bc-113">If the function is in a different application domain, a transition will occur as long as all arguments are also in that application domain.</span></span>

## <a name="requirements"></a><span data-ttu-id="c57bc-114">Требования</span><span class="sxs-lookup"><span data-stu-id="c57bc-114">Requirements</span></span>

<span data-ttu-id="c57bc-115">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c57bc-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="c57bc-116">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c57bc-116">**Header:** CorDebug.idl, CorDebug.h</span></span>

<span data-ttu-id="c57bc-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c57bc-117">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="c57bc-118">**Версии платформы .NET framework:** 1.1, 1.0</span><span class="sxs-lookup"><span data-stu-id="c57bc-118">**.NET Framework Versions:** 1.1, 1.0</span></span>

## <a name="see-also"></a><span data-ttu-id="c57bc-119">См. также</span><span class="sxs-lookup"><span data-stu-id="c57bc-119">See also</span></span>

- [<span data-ttu-id="c57bc-120">Метод CallParameterizedFunction</span><span class="sxs-lookup"><span data-stu-id="c57bc-120">CallParameterizedFunction Method</span></span>](icordebugeval2-callparameterizedfunction-method.md)
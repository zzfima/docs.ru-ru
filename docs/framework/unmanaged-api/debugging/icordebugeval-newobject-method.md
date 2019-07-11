---
title: Метод ICorDebugEval::NewObject
ms.date: 03/30/2017
api_name:
- ICorDebugEval.NewObject
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval::NewObject
helpviewer_keywords:
- NewObject method [.NET Framework debugging]
- ICorDebugEval::NewObject method [.NET Framework debugging]
ms.assetid: ce3025e8-defa-4c5e-8298-f49d71fa5736
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 362c01e0b08145919793cec011a856f0090e5c47
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67752990"
---
# <a name="icordebugevalnewobject-method"></a><span data-ttu-id="bf5b7-102">Метод ICorDebugEval::NewObject</span><span class="sxs-lookup"><span data-stu-id="bf5b7-102">ICorDebugEval::NewObject Method</span></span>
<span data-ttu-id="bf5b7-103">Выделяет новый экземпляр объекта и вызывает заданный метод конструктора.</span><span class="sxs-lookup"><span data-stu-id="bf5b7-103">Allocates a new object instance and calls the specified constructor method.</span></span>  
  
 <span data-ttu-id="bf5b7-104">Этот метод является устаревшим в .NET Framework версии 2.0.</span><span class="sxs-lookup"><span data-stu-id="bf5b7-104">This method is obsolete in the .NET Framework version 2.0.</span></span> <span data-ttu-id="bf5b7-105">Используйте [ICorDebugEval2::NewParameterizedObject](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobject-method.md) вместо этого.</span><span class="sxs-lookup"><span data-stu-id="bf5b7-105">Use [ICorDebugEval2::NewParameterizedObject](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobject-method.md) instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bf5b7-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bf5b7-106">Syntax</span></span>  
  
```cpp  
HRESULT NewObject (  
    [in] ICorDebugFunction  *pConstructor,  
    [in] ULONG32            nArgs,  
    [in, size_is(nArgs)] ICorDebugValue *ppArgs[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bf5b7-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="bf5b7-107">Parameters</span></span>  
 `pConstructor`  
 <span data-ttu-id="bf5b7-108">[in] К вызову конструктора.</span><span class="sxs-lookup"><span data-stu-id="bf5b7-108">[in] The constructor to be called.</span></span>  
  
 `nArgs`  
 <span data-ttu-id="bf5b7-109">[in] Размер массива `ppArgs`.</span><span class="sxs-lookup"><span data-stu-id="bf5b7-109">[in] The size of the `ppArgs` array.</span></span>  
  
 `ppArgs`  
 <span data-ttu-id="bf5b7-110">[in] Массив объектов ICorDebugValue, каждый из которых представляет аргумент, передаваемый в конструктор.</span><span class="sxs-lookup"><span data-stu-id="bf5b7-110">[in] An array of ICorDebugValue objects, each of which represents an argument to be passed to the constructor.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bf5b7-111">Требования</span><span class="sxs-lookup"><span data-stu-id="bf5b7-111">Requirements</span></span>  
 <span data-ttu-id="bf5b7-112">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bf5b7-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bf5b7-113">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bf5b7-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bf5b7-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bf5b7-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bf5b7-115">**Версии платформы .NET framework:** 1.1, 1.0</span><span class="sxs-lookup"><span data-stu-id="bf5b7-115">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf5b7-116">См. также</span><span class="sxs-lookup"><span data-stu-id="bf5b7-116">See also</span></span>

- [<span data-ttu-id="bf5b7-117">Метод NewParameterizedObject</span><span class="sxs-lookup"><span data-stu-id="bf5b7-117">NewParameterizedObject Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobject-method.md)

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
ms.openlocfilehash: 9c2d6a66eca080b480b508afea36c33b3e0aeec0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61989044"
---
# <a name="icordebugevalnewobject-method"></a><span data-ttu-id="445ea-102">Метод ICorDebugEval::NewObject</span><span class="sxs-lookup"><span data-stu-id="445ea-102">ICorDebugEval::NewObject Method</span></span>
<span data-ttu-id="445ea-103">Выделяет новый экземпляр объекта и вызывает заданный метод конструктора.</span><span class="sxs-lookup"><span data-stu-id="445ea-103">Allocates a new object instance and calls the specified constructor method.</span></span>  
  
 <span data-ttu-id="445ea-104">Этот метод является устаревшим в .NET Framework версии 2.0.</span><span class="sxs-lookup"><span data-stu-id="445ea-104">This method is obsolete in the .NET Framework version 2.0.</span></span> <span data-ttu-id="445ea-105">Используйте [ICorDebugEval2::NewParameterizedObject](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobject-method.md) вместо этого.</span><span class="sxs-lookup"><span data-stu-id="445ea-105">Use [ICorDebugEval2::NewParameterizedObject](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobject-method.md) instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="445ea-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="445ea-106">Syntax</span></span>  
  
```  
HRESULT NewObject (  
    [in] ICorDebugFunction  *pConstructor,  
    [in] ULONG32            nArgs,  
    [in, size_is(nArgs)] ICorDebugValue *ppArgs[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="445ea-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="445ea-107">Parameters</span></span>  
 `pConstructor`  
 <span data-ttu-id="445ea-108">[in] К вызову конструктора.</span><span class="sxs-lookup"><span data-stu-id="445ea-108">[in] The constructor to be called.</span></span>  
  
 `nArgs`  
 <span data-ttu-id="445ea-109">[in] Размер массива `ppArgs`.</span><span class="sxs-lookup"><span data-stu-id="445ea-109">[in] The size of the `ppArgs` array.</span></span>  
  
 `ppArgs`  
 <span data-ttu-id="445ea-110">[in] Массив объектов ICorDebugValue, каждый из которых представляет аргумент, передаваемый в конструктор.</span><span class="sxs-lookup"><span data-stu-id="445ea-110">[in] An array of ICorDebugValue objects, each of which represents an argument to be passed to the constructor.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="445ea-111">Требования</span><span class="sxs-lookup"><span data-stu-id="445ea-111">Requirements</span></span>  
 <span data-ttu-id="445ea-112">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="445ea-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="445ea-113">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="445ea-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="445ea-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="445ea-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="445ea-115">**Версии платформы .NET framework:** 1.1, 1.0</span><span class="sxs-lookup"><span data-stu-id="445ea-115">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="445ea-116">См. также</span><span class="sxs-lookup"><span data-stu-id="445ea-116">See also</span></span>

- [<span data-ttu-id="445ea-117">Метод NewParameterizedObject</span><span class="sxs-lookup"><span data-stu-id="445ea-117">NewParameterizedObject Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobject-method.md)

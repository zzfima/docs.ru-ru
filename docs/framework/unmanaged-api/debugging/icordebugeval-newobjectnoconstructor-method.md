---
title: Метод ICorDebugEval::NewObjectNoConstructor
ms.date: 03/30/2017
api_name:
- ICorDebugEval.NewObjectNoConstructor
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval::NewObjectNoConstructor
helpviewer_keywords:
- NewObjectNoConstructor method [.NET Framework debugging]
- ICorDebugEval::NewObjectNoConstructor method [.NET Framework debugging]
ms.assetid: 80d509ca-b5e3-4c46-9c14-800db73d9bf7
topic_type:
- apiref
ms.openlocfilehash: 255d88dcdd880c73a7535cddcad410dcfdcf1d70
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132651"
---
# <a name="icordebugevalnewobjectnoconstructor-method"></a><span data-ttu-id="c672e-102">Метод ICorDebugEval::NewObjectNoConstructor</span><span class="sxs-lookup"><span data-stu-id="c672e-102">ICorDebugEval::NewObjectNoConstructor Method</span></span>
<span data-ttu-id="c672e-103">Выделяет новый экземпляр объекта указанного типа без попытки вызова метода конструктора.</span><span class="sxs-lookup"><span data-stu-id="c672e-103">Allocates a new object instance of the specified type, without attempting to call a constructor method.</span></span>  
  
 <span data-ttu-id="c672e-104">Этот метод является устаревшим в .NET Framework версии 2,0.</span><span class="sxs-lookup"><span data-stu-id="c672e-104">This method is obsolete in the .NET Framework version 2.0.</span></span> <span data-ttu-id="c672e-105">Вместо этого используйте [ICorDebugEval2:: невпараметеризедобжектноконструктор](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobjectnoconstructor-method.md) .</span><span class="sxs-lookup"><span data-stu-id="c672e-105">Use [ICorDebugEval2::NewParameterizedObjectNoConstructor](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobjectnoconstructor-method.md) instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c672e-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c672e-106">Syntax</span></span>  
  
```cpp  
HRESULT NewObjectNoConstructor (  
    [in] ICorDebugClass     *pClass  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c672e-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="c672e-107">Parameters</span></span>  
 `pClass`  
 <span data-ttu-id="c672e-108">окне Указатель на объект ICorDebugClass, представляющий тип объекта, для которого создается экземпляр.</span><span class="sxs-lookup"><span data-stu-id="c672e-108">[in] Pointer to an ICorDebugClass object that represents the type of object to be instantiated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c672e-109">Требования</span><span class="sxs-lookup"><span data-stu-id="c672e-109">Requirements</span></span>  
 <span data-ttu-id="c672e-110">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c672e-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c672e-111">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c672e-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c672e-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c672e-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c672e-113">**.NET Framework версии:** 1,1, 1,0</span><span class="sxs-lookup"><span data-stu-id="c672e-113">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c672e-114">См. также</span><span class="sxs-lookup"><span data-stu-id="c672e-114">See also</span></span>

- [<span data-ttu-id="c672e-115">Метод NewParameterizedObjectNoConstructor</span><span class="sxs-lookup"><span data-stu-id="c672e-115">NewParameterizedObjectNoConstructor Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobjectnoconstructor-method.md)

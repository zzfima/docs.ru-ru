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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6846b866fd47674ca6b5fd187b580fd28e080fd0
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59162310"
---
# <a name="icordebugevalnewobjectnoconstructor-method"></a><span data-ttu-id="f6ca4-102">Метод ICorDebugEval::NewObjectNoConstructor</span><span class="sxs-lookup"><span data-stu-id="f6ca4-102">ICorDebugEval::NewObjectNoConstructor Method</span></span>
<span data-ttu-id="f6ca4-103">Выделяет новый экземпляр объекта указанного типа, не пытается вызвать метод-конструктор.</span><span class="sxs-lookup"><span data-stu-id="f6ca4-103">Allocates a new object instance of the specified type, without attempting to call a constructor method.</span></span>  
  
 <span data-ttu-id="f6ca4-104">Этот метод является устаревшим в .NET Framework версии 2.0.</span><span class="sxs-lookup"><span data-stu-id="f6ca4-104">This method is obsolete in the .NET Framework version 2.0.</span></span> <span data-ttu-id="f6ca4-105">Используйте [ICorDebugEval2::NewParameterizedObjectNoConstructor](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobjectnoconstructor-method.md) вместо этого.</span><span class="sxs-lookup"><span data-stu-id="f6ca4-105">Use [ICorDebugEval2::NewParameterizedObjectNoConstructor](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobjectnoconstructor-method.md) instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f6ca4-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f6ca4-106">Syntax</span></span>  
  
```  
HRESULT NewObjectNoConstructor (  
    [in] ICorDebugClass     *pClass  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f6ca4-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="f6ca4-107">Parameters</span></span>  
 `pClass`  
 <span data-ttu-id="f6ca4-108">[in] Указатель на объект ICorDebugClass, представляющий тип объекта для создания экземпляра.</span><span class="sxs-lookup"><span data-stu-id="f6ca4-108">[in] Pointer to an ICorDebugClass object that represents the type of object to be instantiated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f6ca4-109">Требования</span><span class="sxs-lookup"><span data-stu-id="f6ca4-109">Requirements</span></span>  
 <span data-ttu-id="f6ca4-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f6ca4-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f6ca4-111">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f6ca4-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f6ca4-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f6ca4-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f6ca4-113">**Версии платформы .NET framework:** 1.1, 1.0</span><span class="sxs-lookup"><span data-stu-id="f6ca4-113">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6ca4-114">См. также</span><span class="sxs-lookup"><span data-stu-id="f6ca4-114">See also</span></span>

- [<span data-ttu-id="f6ca4-115">Метод NewParameterizedObjectNoConstructor</span><span class="sxs-lookup"><span data-stu-id="f6ca4-115">NewParameterizedObjectNoConstructor Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobjectnoconstructor-method.md)

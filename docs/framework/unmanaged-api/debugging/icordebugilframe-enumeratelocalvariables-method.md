---
title: Метод ICorDebugILFrame::EnumerateLocalVariables
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame.EnumerateLocalVariables
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame::EnumerateLocalVariables
helpviewer_keywords:
- EnumerateLocalVariables method [.NET Framework debugging]
- ICorDebugILFrame::EnumerateLocalVariables method [.NET Framework debugging]
ms.assetid: 1a67fa1b-2419-4cd0-aad4-6f46a0719b4b
topic_type:
- apiref
ms.openlocfilehash: c071a7ddb7d8d3f0e6487ab85284c45f9a7f0372
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178842"
---
# <a name="icordebugilframeenumeratelocalvariables-method"></a><span data-ttu-id="14950-102">Метод ICorDebugILFrame::EnumerateLocalVariables</span><span class="sxs-lookup"><span data-stu-id="14950-102">ICorDebugILFrame::EnumerateLocalVariables Method</span></span>
<span data-ttu-id="14950-103">Получает регистратор для локальных переменных в этом кадре.</span><span class="sxs-lookup"><span data-stu-id="14950-103">Gets an enumerator for the local variables in this frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="14950-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="14950-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateLocalVariables(
    [out] ICorDebugValueEnum    **ppValueEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="14950-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="14950-105">Parameters</span></span>  
 `ppValueEnum`  
 <span data-ttu-id="14950-106">[из] Указатель на адрес объекта ICorDebugValueEnum, который является перечислителем для локальных переменных в этом кадре.</span><span class="sxs-lookup"><span data-stu-id="14950-106">[out] A pointer to the address of an ICorDebugValueEnum object that is the enumerator for the local variables in this frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="14950-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="14950-107">Remarks</span></span>  
 <span data-ttu-id="14950-108">`EnumerateLocalVariables`получает список, который может перечислить локальные переменные, доступные в кадре вызова, который представлен этим объектом ICorDebugILFrame.</span><span class="sxs-lookup"><span data-stu-id="14950-108">`EnumerateLocalVariables` gets an enumerator that can list the local variables available in the call frame that is represented by this ICorDebugILFrame object.</span></span> <span data-ttu-id="14950-109">Список не может включать все локальные переменные в функции выполнения, поскольку некоторые из них могут быть неактивными.</span><span class="sxs-lookup"><span data-stu-id="14950-109">The list may not include all of the local variables in the running function, because some of them may not be active.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="14950-110">Требования</span><span class="sxs-lookup"><span data-stu-id="14950-110">Requirements</span></span>  
 <span data-ttu-id="14950-111">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="14950-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="14950-112">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="14950-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="14950-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="14950-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="14950-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="14950-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

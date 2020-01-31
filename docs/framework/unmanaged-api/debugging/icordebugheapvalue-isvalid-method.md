---
title: Метод ICorDebugHeapValue::IsValid
ms.date: 03/30/2017
api_name:
- ICorDebugHeapValue.IsValid
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHeapValue::IsValid
helpviewer_keywords:
- IsValid method [.NET Framework debugging]
- ICorDebugHeapValue::IsValid method [.NET Framework debugging]
ms.assetid: 68e20e62-203d-46d8-bb91-8d3c61cfacc3
topic_type:
- apiref
ms.openlocfilehash: 7685d1b6d5458a4405fc5a4abdb2f3134618f01c
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76794405"
---
# <a name="icordebugheapvalueisvalid-method"></a><span data-ttu-id="efb2b-102">Метод ICorDebugHeapValue::IsValid</span><span class="sxs-lookup"><span data-stu-id="efb2b-102">ICorDebugHeapValue::IsValid Method</span></span>
<span data-ttu-id="efb2b-103">Возвращает значение, указывающее, является ли допустимым объект, представленный этим ICorDebugHeapValue.</span><span class="sxs-lookup"><span data-stu-id="efb2b-103">Gets a value that indicates whether the object represented by this ICorDebugHeapValue is valid.</span></span>  
  
 <span data-ttu-id="efb2b-104">Этот метод не рекомендуется к использованию в .NET Framework версии 2,0.</span><span class="sxs-lookup"><span data-stu-id="efb2b-104">This method has been deprecated in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="efb2b-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="efb2b-105">Syntax</span></span>  
  
```cpp  
HRESULT IsValid (  
    [out] BOOL    *pbValid  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="efb2b-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="efb2b-106">Parameters</span></span>  
 `pbValid`  
 <span data-ttu-id="efb2b-107">заполняет Указатель на логическое значение, указывающее, является ли значение в куче допустимым.</span><span class="sxs-lookup"><span data-stu-id="efb2b-107">[out] A pointer to a Boolean value that indicates whether this value on the heap is valid.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="efb2b-108">Заметки</span><span class="sxs-lookup"><span data-stu-id="efb2b-108">Remarks</span></span>  
 <span data-ttu-id="efb2b-109">Значение недопустимо, если оно было освобождено сборщиком мусора.</span><span class="sxs-lookup"><span data-stu-id="efb2b-109">The value is invalid if it has been reclaimed by the garbage collector.</span></span>  
  
 <span data-ttu-id="efb2b-110">Этот метод использовать не рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="efb2b-110">This method has been deprecated.</span></span> <span data-ttu-id="efb2b-111">В .NET Framework 2,0 все значения являются допустимыми до тех пор, пока не будет вызван метод [ICorDebugController:: Continue](icordebugcontroller-continue-method.md) , после чего значения становятся недействительными.</span><span class="sxs-lookup"><span data-stu-id="efb2b-111">In the .NET Framework 2.0, all values are valid until [ICorDebugController::Continue](icordebugcontroller-continue-method.md) is called, at which time the values are invalidated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="efb2b-112">Требования</span><span class="sxs-lookup"><span data-stu-id="efb2b-112">Requirements</span></span>  
 <span data-ttu-id="efb2b-113">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="efb2b-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="efb2b-114">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="efb2b-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="efb2b-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="efb2b-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="efb2b-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="efb2b-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

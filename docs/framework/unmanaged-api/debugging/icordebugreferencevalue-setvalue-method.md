---
title: Метод ICorDebugReferenceValue::SetValue
ms.date: 03/30/2017
api_name:
- ICorDebugReferenceValue.SetValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugReferenceValue::SetValue
helpviewer_keywords:
- SetValue method, ICorDebugReferenceValue interface [.NET Framework debugging]
- ICorDebugReferenceValue::SetValue method [.NET Framework debugging]
ms.assetid: 3d3f6eec-d772-401f-a028-1a2ecdc31e95
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2f0c06f9b04c5f15171464b93dc93765625d6f19
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33418146"
---
# <a name="icordebugreferencevaluesetvalue-method"></a><span data-ttu-id="b7581-102">Метод ICorDebugReferenceValue::SetValue</span><span class="sxs-lookup"><span data-stu-id="b7581-102">ICorDebugReferenceValue::SetValue Method</span></span>
<span data-ttu-id="b7581-103">Задает указанному адресу памяти.</span><span class="sxs-lookup"><span data-stu-id="b7581-103">Sets the specified memory address.</span></span> <span data-ttu-id="b7581-104">То есть этот метод задает этот ICorDebugReferenceValue, чтобы он указывал на объект.</span><span class="sxs-lookup"><span data-stu-id="b7581-104">That is, this method sets this ICorDebugReferenceValue to point to an object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b7581-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b7581-105">Syntax</span></span>  
  
```  
HRESULT SetValue (  
    [in] CORDB_ADDRESS    value  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b7581-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="b7581-106">Parameters</span></span>  
 `value`  
 <span data-ttu-id="b7581-107">[in] Объект `CORDB_ADDRESS` значение, указывающее адрес объекта, к которому `ICorDebugReferenceValue` точек.</span><span class="sxs-lookup"><span data-stu-id="b7581-107">[in] A `CORDB_ADDRESS` value that specifies the address of the object to which this `ICorDebugReferenceValue` points.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b7581-108">Требования</span><span class="sxs-lookup"><span data-stu-id="b7581-108">Requirements</span></span>  
 <span data-ttu-id="b7581-109">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b7581-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b7581-110">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b7581-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b7581-111">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b7581-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b7581-112">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b7581-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

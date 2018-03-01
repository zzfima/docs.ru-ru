---
title: "Метод ICorDebugReferenceValue::Dereference"
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
- ICorDebugReferenceValue.Dereference
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugReferenceValue::Dereference
helpviewer_keywords:
- ICorDebugReferenceValue::Dereference method [.NET Framework debugging]
- Dereference method [.NET Framework debugging]
ms.assetid: 5ec8cf76-3deb-4ce6-9a49-77a4c35d80b9
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 0dbf2775217a78c1cbb9a96093354f0fc0b278bb
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugreferencevaluedereference-method"></a><span data-ttu-id="69352-102">Метод ICorDebugReferenceValue::Dereference</span><span class="sxs-lookup"><span data-stu-id="69352-102">ICorDebugReferenceValue::Dereference Method</span></span>
<span data-ttu-id="69352-103">Возвращает объект, на который имеется ссылка.</span><span class="sxs-lookup"><span data-stu-id="69352-103">Gets the object that is referenced.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="69352-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="69352-104">Syntax</span></span>  
  
```  
HRESULT Dereference (  
    [out] ICorDebugValue  **ppValue  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="69352-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="69352-105">Parameters</span></span>  
 `ppValue`  
 <span data-ttu-id="69352-106">[out] Указатель на адрес ICorDebugValue, который представляет объект, на который указывает этот объект ICorDebugReferenceValue.</span><span class="sxs-lookup"><span data-stu-id="69352-106">[out] A pointer to the address of an ICorDebugValue that represents the object to which this ICorDebugReferenceValue object points.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="69352-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="69352-107">Remarks</span></span>  
 <span data-ttu-id="69352-108">`ICorDebugValue` Объект является допустимым только во время его ссылок не были отключены.</span><span class="sxs-lookup"><span data-stu-id="69352-108">The `ICorDebugValue` object is valid only while its reference has not yet been disabled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="69352-109">Требования</span><span class="sxs-lookup"><span data-stu-id="69352-109">Requirements</span></span>  
 <span data-ttu-id="69352-110">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="69352-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="69352-111">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="69352-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="69352-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="69352-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="69352-113">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="69352-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

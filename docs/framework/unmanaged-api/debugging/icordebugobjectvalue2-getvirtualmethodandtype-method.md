---
title: Метод ICorDebugObjectValue2::GetVirtualMethodAndType
ms.date: 03/30/2017
api_name:
- ICorDebugObjectValue2.GetVirtualMethodAndType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugObjectValue2::GetVirtualMethodAndType
helpviewer_keywords:
- GetVirtualMethodAndType method [.NET Framework debugging]
- ICorDebugObjectValue2::GetVirtualMethodAndType method
ms.assetid: 621b4543-a8f7-4117-98e4-930992cd688a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 252a65c66764d60f5e307ba1eaad4ded34d9744d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59162154"
---
# <a name="icordebugobjectvalue2getvirtualmethodandtype-method"></a><span data-ttu-id="480e0-102">Метод ICorDebugObjectValue2::GetVirtualMethodAndType</span><span class="sxs-lookup"><span data-stu-id="480e0-102">ICorDebugObjectValue2::GetVirtualMethodAndType Method</span></span>
<span data-ttu-id="480e0-103">Этот метод еще не реализован.</span><span class="sxs-lookup"><span data-stu-id="480e0-103">This method is not yet implemented.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="480e0-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="480e0-104">Syntax</span></span>  
  
```  
HRESULT GetVirtualMethodAndType (  
    [in] mdMemberRef          memberRef,  
    [out] ICorDebugFunction   **ppFunction,  
    [out] ICorDebugType       **ppType  
);  
```  
  
## <a name="remarks"></a><span data-ttu-id="480e0-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="480e0-105">Remarks</span></span>  
 <span data-ttu-id="480e0-106">Получает указатели интерфейса на экземпляры «ICorDebugFunction» и «ICorDebugType», представляющие наиболее производный метод и тип для заданной ссылки на член.</span><span class="sxs-lookup"><span data-stu-id="480e0-106">Gets interface pointers to the "ICorDebugFunction" and "ICorDebugType" instances that represent the most derived method and type for the specified member reference.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="480e0-107">См. также</span><span class="sxs-lookup"><span data-stu-id="480e0-107">See also</span></span>

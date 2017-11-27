---
title: "Метод ICorDebugObjectValue2::GetVirtualMethodAndType"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugObjectValue2.GetVirtualMethodAndType
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugObjectValue2::GetVirtualMethodAndType
helpviewer_keywords:
- GetVirtualMethodAndType method [.NET Framework debugging]
- ICorDebugObjectValue2::GetVirtualMethodAndType method
ms.assetid: 621b4543-a8f7-4117-98e4-930992cd688a
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: aa4b2e35ded77c92ecc66eaeb4167a12db20c532
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugobjectvalue2getvirtualmethodandtype-method"></a><span data-ttu-id="c4b95-102">Метод ICorDebugObjectValue2::GetVirtualMethodAndType</span><span class="sxs-lookup"><span data-stu-id="c4b95-102">ICorDebugObjectValue2::GetVirtualMethodAndType Method</span></span>
<span data-ttu-id="c4b95-103">Этот метод еще не реализован.</span><span class="sxs-lookup"><span data-stu-id="c4b95-103">This method is not yet implemented.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c4b95-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c4b95-104">Syntax</span></span>  
  
```  
HRESULT GetVirtualMethodAndType (  
    [in] mdMemberRef          memberRef,  
    [out] ICorDebugFunction   **ppFunction,  
    [out] ICorDebugType       **ppType  
);  
```  
  
## <a name="remarks"></a><span data-ttu-id="c4b95-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="c4b95-105">Remarks</span></span>  
 <span data-ttu-id="c4b95-106">Получает указатели интерфейса на «ICorDebugFunction» и «ICorDebugType» экземпляры, которые представляют наиболее производного метода и тип для ссылки на указанный элемент.</span><span class="sxs-lookup"><span data-stu-id="c4b95-106">Gets interface pointers to the "ICorDebugFunction" and "ICorDebugType" instances that represent the most derived method and type for the specified member reference.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4b95-107">См. также</span><span class="sxs-lookup"><span data-stu-id="c4b95-107">See Also</span></span>  
    
 

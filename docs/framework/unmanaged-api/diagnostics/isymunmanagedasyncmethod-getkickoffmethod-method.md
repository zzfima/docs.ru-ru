---
title: "Метод ISymUnmanagedAsyncMethod::GetKickoffMethod"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: ba084444-9e68-4cde-9388-54b950670987
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 866632b3916cd2e35e7832c4d58b5988fa350c52
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedasyncmethodgetkickoffmethod-method"></a><span data-ttu-id="fed03-102">Метод ISymUnmanagedAsyncMethod::GetKickoffMethod</span><span class="sxs-lookup"><span data-stu-id="fed03-102">ISymUnmanagedAsyncMethod::GetKickoffMethod Method</span></span>
<span data-ttu-id="fed03-103">В разделе [метод DefineKickoffMethod](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definekickoffmethod-method.md).</span><span class="sxs-lookup"><span data-stu-id="fed03-103">See [DefineKickoffMethod Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definekickoffmethod-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fed03-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fed03-104">Syntax</span></span>  
  
```idl  
HRESULT GetKickoffMethod(    [out, retval] mdToken* kickoffMethod);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="fed03-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="fed03-105">Parameters</span></span>  
  
|<span data-ttu-id="fed03-106">Параметр</span><span class="sxs-lookup"><span data-stu-id="fed03-106">Parameter</span></span>|<span data-ttu-id="fed03-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="fed03-107">Description</span></span>|  
|---------------|-----------------|  
|`kickoffMethod`||  
  
## <a name="return-value"></a><span data-ttu-id="fed03-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="fed03-108">Return Value</span></span>  
 <span data-ttu-id="fed03-109">Возвращает `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="fed03-109">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fed03-110">Требования</span><span class="sxs-lookup"><span data-stu-id="fed03-110">Requirements</span></span>  
 <span data-ttu-id="fed03-111">**Заголовок:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="fed03-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fed03-112">См. также</span><span class="sxs-lookup"><span data-stu-id="fed03-112">See Also</span></span>  
 [<span data-ttu-id="fed03-113">Интерфейс ISymUnmanagedAsyncMethod</span><span class="sxs-lookup"><span data-stu-id="fed03-113">ISymUnmanagedAsyncMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-interface.md)

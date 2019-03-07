---
title: Метод ISymUnmanagedAsyncMethod::GetKickoffMethod
ms.date: 03/30/2017
ms.assetid: ba084444-9e68-4cde-9388-54b950670987
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 84aef2b26e008d1a3c6d95d7ec1e130ab0594a11
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57484554"
---
# <a name="isymunmanagedasyncmethodgetkickoffmethod-method"></a><span data-ttu-id="0e242-102">Метод ISymUnmanagedAsyncMethod::GetKickoffMethod</span><span class="sxs-lookup"><span data-stu-id="0e242-102">ISymUnmanagedAsyncMethod::GetKickoffMethod Method</span></span>
<span data-ttu-id="0e242-103">См. в разделе [метод DefineKickoffMethod](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definekickoffmethod-method.md).</span><span class="sxs-lookup"><span data-stu-id="0e242-103">See [DefineKickoffMethod Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definekickoffmethod-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0e242-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0e242-104">Syntax</span></span>  
  
```idl  
HRESULT GetKickoffMethod(    [out, retval] mdToken* kickoffMethod);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0e242-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="0e242-105">Parameters</span></span>  
  
|<span data-ttu-id="0e242-106">Параметр</span><span class="sxs-lookup"><span data-stu-id="0e242-106">Parameter</span></span>|<span data-ttu-id="0e242-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="0e242-107">Description</span></span>|  
|---------------|-----------------|  
|`kickoffMethod`||  
  
## <a name="return-value"></a><span data-ttu-id="0e242-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="0e242-108">Return Value</span></span>  
 <span data-ttu-id="0e242-109">Возвращает `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="0e242-109">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0e242-110">Требования</span><span class="sxs-lookup"><span data-stu-id="0e242-110">Requirements</span></span>  
 <span data-ttu-id="0e242-111">**Заголовок.** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="0e242-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e242-112">См. также</span><span class="sxs-lookup"><span data-stu-id="0e242-112">See also</span></span>
- [<span data-ttu-id="0e242-113">Интерфейс ISymUnmanagedAsyncMethod</span><span class="sxs-lookup"><span data-stu-id="0e242-113">ISymUnmanagedAsyncMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-interface.md)

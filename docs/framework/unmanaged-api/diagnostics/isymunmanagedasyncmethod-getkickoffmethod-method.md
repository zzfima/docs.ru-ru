---
title: Метод ISymUnmanagedAsyncMethod::GetKickoffMethod
ms.date: 03/30/2017
ms.assetid: ba084444-9e68-4cde-9388-54b950670987
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4599d41336778db8ce8dcf3ac567e4e2cc8833e6
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59174945"
---
# <a name="isymunmanagedasyncmethodgetkickoffmethod-method"></a><span data-ttu-id="749b2-102">Метод ISymUnmanagedAsyncMethod::GetKickoffMethod</span><span class="sxs-lookup"><span data-stu-id="749b2-102">ISymUnmanagedAsyncMethod::GetKickoffMethod Method</span></span>
<span data-ttu-id="749b2-103">См. в разделе [метод DefineKickoffMethod](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definekickoffmethod-method.md).</span><span class="sxs-lookup"><span data-stu-id="749b2-103">See [DefineKickoffMethod Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definekickoffmethod-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="749b2-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="749b2-104">Syntax</span></span>  
  
```idl  
HRESULT GetKickoffMethod(    [out, retval] mdToken* kickoffMethod);  
```  
  
## <a name="parameters"></a><span data-ttu-id="749b2-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="749b2-105">Parameters</span></span>  
  
|<span data-ttu-id="749b2-106">Параметр</span><span class="sxs-lookup"><span data-stu-id="749b2-106">Parameter</span></span>|<span data-ttu-id="749b2-107">Описание</span><span class="sxs-lookup"><span data-stu-id="749b2-107">Description</span></span>|  
|---------------|-----------------|  
|`kickoffMethod`||  
  
## <a name="return-value"></a><span data-ttu-id="749b2-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="749b2-108">Return Value</span></span>  
 <span data-ttu-id="749b2-109">Возвращает `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="749b2-109">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="749b2-110">Требования</span><span class="sxs-lookup"><span data-stu-id="749b2-110">Requirements</span></span>  
 <span data-ttu-id="749b2-111">**Заголовок.** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="749b2-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="749b2-112">См. также</span><span class="sxs-lookup"><span data-stu-id="749b2-112">See also</span></span>

- [<span data-ttu-id="749b2-113">Интерфейс ISymUnmanagedAsyncMethod</span><span class="sxs-lookup"><span data-stu-id="749b2-113">ISymUnmanagedAsyncMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-interface.md)

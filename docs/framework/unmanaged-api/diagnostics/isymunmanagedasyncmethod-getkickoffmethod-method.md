---
title: Метод ISymUnmanagedAsyncMethod::GetKickoffMethod
ms.date: 03/30/2017
ms.assetid: ba084444-9e68-4cde-9388-54b950670987
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e2f055dc19bf7f40036283102d8cc4549555b992
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33424772"
---
# <a name="isymunmanagedasyncmethodgetkickoffmethod-method"></a><span data-ttu-id="3b58b-102">Метод ISymUnmanagedAsyncMethod::GetKickoffMethod</span><span class="sxs-lookup"><span data-stu-id="3b58b-102">ISymUnmanagedAsyncMethod::GetKickoffMethod Method</span></span>
<span data-ttu-id="3b58b-103">В разделе [метод DefineKickoffMethod](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definekickoffmethod-method.md).</span><span class="sxs-lookup"><span data-stu-id="3b58b-103">See [DefineKickoffMethod Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definekickoffmethod-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3b58b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3b58b-104">Syntax</span></span>  
  
```idl  
HRESULT GetKickoffMethod(    [out, retval] mdToken* kickoffMethod);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3b58b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="3b58b-105">Parameters</span></span>  
  
|<span data-ttu-id="3b58b-106">Параметр</span><span class="sxs-lookup"><span data-stu-id="3b58b-106">Parameter</span></span>|<span data-ttu-id="3b58b-107">Описание</span><span class="sxs-lookup"><span data-stu-id="3b58b-107">Description</span></span>|  
|---------------|-----------------|  
|`kickoffMethod`||  
  
## <a name="return-value"></a><span data-ttu-id="3b58b-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="3b58b-108">Return Value</span></span>  
 <span data-ttu-id="3b58b-109">Возвращает `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="3b58b-109">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3b58b-110">Требования</span><span class="sxs-lookup"><span data-stu-id="3b58b-110">Requirements</span></span>  
 <span data-ttu-id="3b58b-111">**Заголовок:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="3b58b-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b58b-112">См. также</span><span class="sxs-lookup"><span data-stu-id="3b58b-112">See Also</span></span>  
 [<span data-ttu-id="3b58b-113">Интерфейс ISymUnmanagedAsyncMethod</span><span class="sxs-lookup"><span data-stu-id="3b58b-113">ISymUnmanagedAsyncMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-interface.md)

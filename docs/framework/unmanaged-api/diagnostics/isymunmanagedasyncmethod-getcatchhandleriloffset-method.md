---
title: Метод ISymUnmanagedAsyncMethod::GetCatchHandlerILOffset
ms.date: 03/30/2017
ms.assetid: d5f88656-433d-447c-b21c-2a12bed2e72a
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 82101da6c4e47f0e981bb358b79ae2c6670af2c5
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57471307"
---
# <a name="isymunmanagedasyncmethodgetcatchhandleriloffset-method"></a><span data-ttu-id="6d550-102">Метод ISymUnmanagedAsyncMethod::GetCatchHandlerILOffset</span><span class="sxs-lookup"><span data-stu-id="6d550-102">ISymUnmanagedAsyncMethod::GetCatchHandlerILOffset Method</span></span>
<span data-ttu-id="6d550-103">См. в разделе [метод DefineCatchHandlerILOffset](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definecatchhandleriloffset-method.md).</span><span class="sxs-lookup"><span data-stu-id="6d550-103">See [DefineCatchHandlerILOffset Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definecatchhandleriloffset-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6d550-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6d550-104">Syntax</span></span>  
  
```idl  
HRESULT GetCatchHandlerILOffset(    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6d550-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="6d550-105">Parameters</span></span>  
  
|<span data-ttu-id="6d550-106">Параметр</span><span class="sxs-lookup"><span data-stu-id="6d550-106">Parameter</span></span>|<span data-ttu-id="6d550-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="6d550-107">Description</span></span>|  
|---------------|-----------------|  
|`pRetVal`||  
  
## <a name="return-value"></a><span data-ttu-id="6d550-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="6d550-108">Return Value</span></span>  
 <span data-ttu-id="6d550-109">Возвращает `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="6d550-109">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6d550-110">Требования</span><span class="sxs-lookup"><span data-stu-id="6d550-110">Requirements</span></span>  
 <span data-ttu-id="6d550-111">**Заголовок.** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="6d550-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d550-112">См. также</span><span class="sxs-lookup"><span data-stu-id="6d550-112">See also</span></span>
- [<span data-ttu-id="6d550-113">Интерфейс ISymUnmanagedAsyncMethod</span><span class="sxs-lookup"><span data-stu-id="6d550-113">ISymUnmanagedAsyncMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-interface.md)

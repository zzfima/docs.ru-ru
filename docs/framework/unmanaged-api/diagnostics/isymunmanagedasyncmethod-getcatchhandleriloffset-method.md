---
title: Метод ISymUnmanagedAsyncMethod::GetCatchHandlerILOffset
ms.date: 03/30/2017
ms.assetid: d5f88656-433d-447c-b21c-2a12bed2e72a
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 527e686eb0c354c3a1ebba36772e30211e995ab2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33425357"
---
# <a name="isymunmanagedasyncmethodgetcatchhandleriloffset-method"></a><span data-ttu-id="9cb5d-102">Метод ISymUnmanagedAsyncMethod::GetCatchHandlerILOffset</span><span class="sxs-lookup"><span data-stu-id="9cb5d-102">ISymUnmanagedAsyncMethod::GetCatchHandlerILOffset Method</span></span>
<span data-ttu-id="9cb5d-103">В разделе [метод DefineCatchHandlerILOffset](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definecatchhandleriloffset-method.md).</span><span class="sxs-lookup"><span data-stu-id="9cb5d-103">See [DefineCatchHandlerILOffset Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definecatchhandleriloffset-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9cb5d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9cb5d-104">Syntax</span></span>  
  
```idl  
HRESULT GetCatchHandlerILOffset(    [out, retval] ULONG32* pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9cb5d-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="9cb5d-105">Parameters</span></span>  
  
|<span data-ttu-id="9cb5d-106">Параметр</span><span class="sxs-lookup"><span data-stu-id="9cb5d-106">Parameter</span></span>|<span data-ttu-id="9cb5d-107">Описание</span><span class="sxs-lookup"><span data-stu-id="9cb5d-107">Description</span></span>|  
|---------------|-----------------|  
|`pRetVal`||  
  
## <a name="return-value"></a><span data-ttu-id="9cb5d-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="9cb5d-108">Return Value</span></span>  
 <span data-ttu-id="9cb5d-109">Возвращает `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="9cb5d-109">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9cb5d-110">Требования</span><span class="sxs-lookup"><span data-stu-id="9cb5d-110">Requirements</span></span>  
 <span data-ttu-id="9cb5d-111">**Заголовок:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="9cb5d-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9cb5d-112">См. также</span><span class="sxs-lookup"><span data-stu-id="9cb5d-112">See Also</span></span>  
 [<span data-ttu-id="9cb5d-113">Интерфейс ISymUnmanagedAsyncMethod</span><span class="sxs-lookup"><span data-stu-id="9cb5d-113">ISymUnmanagedAsyncMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-interface.md)

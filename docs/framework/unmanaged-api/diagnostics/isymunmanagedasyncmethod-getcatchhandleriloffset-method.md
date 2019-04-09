---
title: Метод ISymUnmanagedAsyncMethod::GetCatchHandlerILOffset
ms.date: 03/30/2017
ms.assetid: d5f88656-433d-447c-b21c-2a12bed2e72a
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8c9fbada0317738c80f21e0c86199c1df43d1be6
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59128496"
---
# <a name="isymunmanagedasyncmethodgetcatchhandleriloffset-method"></a><span data-ttu-id="611f0-102">Метод ISymUnmanagedAsyncMethod::GetCatchHandlerILOffset</span><span class="sxs-lookup"><span data-stu-id="611f0-102">ISymUnmanagedAsyncMethod::GetCatchHandlerILOffset Method</span></span>
<span data-ttu-id="611f0-103">См. в разделе [метод DefineCatchHandlerILOffset](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definecatchhandleriloffset-method.md).</span><span class="sxs-lookup"><span data-stu-id="611f0-103">See [DefineCatchHandlerILOffset Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definecatchhandleriloffset-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="611f0-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="611f0-104">Syntax</span></span>  
  
```idl  
HRESULT GetCatchHandlerILOffset(    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="611f0-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="611f0-105">Parameters</span></span>  
  
|<span data-ttu-id="611f0-106">Параметр</span><span class="sxs-lookup"><span data-stu-id="611f0-106">Parameter</span></span>|<span data-ttu-id="611f0-107">Описание</span><span class="sxs-lookup"><span data-stu-id="611f0-107">Description</span></span>|  
|---------------|-----------------|  
|`pRetVal`||  
  
## <a name="return-value"></a><span data-ttu-id="611f0-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="611f0-108">Return Value</span></span>  
 <span data-ttu-id="611f0-109">Возвращает `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="611f0-109">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="611f0-110">Требования</span><span class="sxs-lookup"><span data-stu-id="611f0-110">Requirements</span></span>  
 <span data-ttu-id="611f0-111">**Заголовок.** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="611f0-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="611f0-112">См. также</span><span class="sxs-lookup"><span data-stu-id="611f0-112">See also</span></span>

- [<span data-ttu-id="611f0-113">Интерфейс ISymUnmanagedAsyncMethod</span><span class="sxs-lookup"><span data-stu-id="611f0-113">ISymUnmanagedAsyncMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-interface.md)

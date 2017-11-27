---
title: "Метод ISymUnmanagedAsyncMethod::GetAsyncStepInfoCount"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 32a4e084-09b2-4946-a4a7-19a1fed9f7cc
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 6b2431662caa41c67746da7e21591c743896c161
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedasyncmethodgetasyncstepinfocount-method"></a><span data-ttu-id="3d30a-102">Метод ISymUnmanagedAsyncMethod::GetAsyncStepInfoCount</span><span class="sxs-lookup"><span data-stu-id="3d30a-102">ISymUnmanagedAsyncMethod::GetAsyncStepInfoCount Method</span></span>
<span data-ttu-id="3d30a-103">В разделе [метод DefineAsyncStepInfo](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md).</span><span class="sxs-lookup"><span data-stu-id="3d30a-103">See [DefineAsyncStepInfo Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3d30a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3d30a-104">Syntax</span></span>  
  
```idl  
HRESULT GetAsyncStepInfoCount(    [out, retval] ULONG32* pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3d30a-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="3d30a-105">Parameters</span></span>  
  
|<span data-ttu-id="3d30a-106">Параметр</span><span class="sxs-lookup"><span data-stu-id="3d30a-106">Parameter</span></span>|<span data-ttu-id="3d30a-107">Описание</span><span class="sxs-lookup"><span data-stu-id="3d30a-107">Description</span></span>|  
|---------------|-----------------|  
|`pRetVal`||  
  
## <a name="return-value"></a><span data-ttu-id="3d30a-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="3d30a-108">Return Value</span></span>  
 <span data-ttu-id="3d30a-109">Возвращает `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="3d30a-109">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3d30a-110">Требования</span><span class="sxs-lookup"><span data-stu-id="3d30a-110">Requirements</span></span>  
 <span data-ttu-id="3d30a-111">**Заголовок:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="3d30a-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d30a-112">См. также</span><span class="sxs-lookup"><span data-stu-id="3d30a-112">See Also</span></span>  
 [<span data-ttu-id="3d30a-113">Интерфейс ISymUnmanagedAsyncMethod</span><span class="sxs-lookup"><span data-stu-id="3d30a-113">ISymUnmanagedAsyncMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-interface.md)

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
ms.openlocfilehash: 3e017097183243c84a2ce40cc473067e05c80c3c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedasyncmethodgetkickoffmethod-method"></a><span data-ttu-id="88441-102">Метод ISymUnmanagedAsyncMethod::GetKickoffMethod</span><span class="sxs-lookup"><span data-stu-id="88441-102">ISymUnmanagedAsyncMethod::GetKickoffMethod Method</span></span>
<span data-ttu-id="88441-103">В разделе [метод DefineKickoffMethod](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definekickoffmethod-method.md).</span><span class="sxs-lookup"><span data-stu-id="88441-103">See [DefineKickoffMethod Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definekickoffmethod-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="88441-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="88441-104">Syntax</span></span>  
  
```idl  
HRESULT GetKickoffMethod(    [out, retval] mdToken* kickoffMethod);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="88441-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="88441-105">Parameters</span></span>  
  
|<span data-ttu-id="88441-106">Параметр</span><span class="sxs-lookup"><span data-stu-id="88441-106">Parameter</span></span>|<span data-ttu-id="88441-107">Описание</span><span class="sxs-lookup"><span data-stu-id="88441-107">Description</span></span>|  
|---------------|-----------------|  
|`kickoffMethod`||  
  
## <a name="return-value"></a><span data-ttu-id="88441-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="88441-108">Return Value</span></span>  
 <span data-ttu-id="88441-109">Возвращает `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="88441-109">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="88441-110">Требования</span><span class="sxs-lookup"><span data-stu-id="88441-110">Requirements</span></span>  
 <span data-ttu-id="88441-111">**Заголовок:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="88441-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88441-112">См. также</span><span class="sxs-lookup"><span data-stu-id="88441-112">See Also</span></span>  
 [<span data-ttu-id="88441-113">Интерфейс ISymUnmanagedAsyncMethod</span><span class="sxs-lookup"><span data-stu-id="88441-113">ISymUnmanagedAsyncMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-interface.md)

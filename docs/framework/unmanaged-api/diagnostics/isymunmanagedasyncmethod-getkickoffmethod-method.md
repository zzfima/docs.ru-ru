---
title: Метод ISymUnmanagedAsyncMethod::GetKickoffMethod
ms.date: 03/30/2017
ms.assetid: ba084444-9e68-4cde-9388-54b950670987
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4599d41336778db8ce8dcf3ac567e4e2cc8833e6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61940209"
---
# <a name="isymunmanagedasyncmethodgetkickoffmethod-method"></a><span data-ttu-id="05d81-102">Метод ISymUnmanagedAsyncMethod::GetKickoffMethod</span><span class="sxs-lookup"><span data-stu-id="05d81-102">ISymUnmanagedAsyncMethod::GetKickoffMethod Method</span></span>
<span data-ttu-id="05d81-103">См. в разделе [метод DefineKickoffMethod](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definekickoffmethod-method.md).</span><span class="sxs-lookup"><span data-stu-id="05d81-103">See [DefineKickoffMethod Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definekickoffmethod-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="05d81-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="05d81-104">Syntax</span></span>  
  
```idl  
HRESULT GetKickoffMethod(    [out, retval] mdToken* kickoffMethod);  
```  
  
## <a name="parameters"></a><span data-ttu-id="05d81-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="05d81-105">Parameters</span></span>  
  
|<span data-ttu-id="05d81-106">Параметр</span><span class="sxs-lookup"><span data-stu-id="05d81-106">Parameter</span></span>|<span data-ttu-id="05d81-107">Описание</span><span class="sxs-lookup"><span data-stu-id="05d81-107">Description</span></span>|  
|---------------|-----------------|  
|`kickoffMethod`||  
  
## <a name="return-value"></a><span data-ttu-id="05d81-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="05d81-108">Return Value</span></span>  
 <span data-ttu-id="05d81-109">Возвращает `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="05d81-109">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="05d81-110">Требования</span><span class="sxs-lookup"><span data-stu-id="05d81-110">Requirements</span></span>  
 <span data-ttu-id="05d81-111">**Заголовок.** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="05d81-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05d81-112">См. также</span><span class="sxs-lookup"><span data-stu-id="05d81-112">See also</span></span>

- [<span data-ttu-id="05d81-113">Интерфейс ISymUnmanagedAsyncMethod</span><span class="sxs-lookup"><span data-stu-id="05d81-113">ISymUnmanagedAsyncMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-interface.md)

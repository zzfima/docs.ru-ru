---
title: Интерфейс ISymUnmanagedAsyncMethod
ms.date: 03/30/2017
ms.assetid: f2de5224-fd91-45de-9e58-bc600c6d22f1
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3dd7b351de8e82f9fdbe623505f86b54f6eba68d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54694871"
---
# <a name="isymunmanagedasyncmethod-interface"></a><span data-ttu-id="6d39d-102">Интерфейс ISymUnmanagedAsyncMethod</span><span class="sxs-lookup"><span data-stu-id="6d39d-102">ISymUnmanagedAsyncMethod Interface</span></span>
<span data-ttu-id="6d39d-103">Этот интерфейс является дополнением к чтения [интерфейс ISymUnmanagedAsyncMethodPropertiesWriter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md).</span><span class="sxs-lookup"><span data-stu-id="6d39d-103">This interface is the reading complement to [ISymUnmanagedAsyncMethodPropertiesWriter Interface](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6d39d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6d39d-104">Syntax</span></span>  
  
```idl  
[object,uuid(B20D55B3-532E-4906-87E7-25BD5734ABD2),pointer_default(unique)]interface ISymUnmanagedAsyncMethod : IUnknown  
```  
  
## <a name="methods"></a><span data-ttu-id="6d39d-105">Методы</span><span class="sxs-lookup"><span data-stu-id="6d39d-105">Methods</span></span>  
 <span data-ttu-id="6d39d-106">Этот интерфейс содержит следующие методы:</span><span class="sxs-lookup"><span data-stu-id="6d39d-106">This interface contains the following methods:</span></span>  
  
|<span data-ttu-id="6d39d-107">Метод</span><span class="sxs-lookup"><span data-stu-id="6d39d-107">Method</span></span>|<span data-ttu-id="6d39d-108">Описание:</span><span class="sxs-lookup"><span data-stu-id="6d39d-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="6d39d-109">Метод GetAsyncStepInfo</span><span class="sxs-lookup"><span data-stu-id="6d39d-109">GetAsyncStepInfo Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-getasyncstepinfo-method.md)|<span data-ttu-id="6d39d-110">См. в разделе [метод DefineAsyncStepInfo](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md).</span><span class="sxs-lookup"><span data-stu-id="6d39d-110">See [DefineAsyncStepInfo Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md).</span></span>|  
|[<span data-ttu-id="6d39d-111">Метод GetAsyncStepInfoCount</span><span class="sxs-lookup"><span data-stu-id="6d39d-111">GetAsyncStepInfoCount Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-getasyncstepinfocount-method.md)|<span data-ttu-id="6d39d-112">См. в разделе [метод DefineAsyncStepInfo](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md).</span><span class="sxs-lookup"><span data-stu-id="6d39d-112">See [DefineAsyncStepInfo Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md).</span></span>|  
|[<span data-ttu-id="6d39d-113">Метод GetCatchHandlerILOffset</span><span class="sxs-lookup"><span data-stu-id="6d39d-113">GetCatchHandlerILOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-getcatchhandleriloffset-method.md)|<span data-ttu-id="6d39d-114">См. в разделе [метод DefineCatchHandlerILOffset](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definecatchhandleriloffset-method.md).</span><span class="sxs-lookup"><span data-stu-id="6d39d-114">See [DefineCatchHandlerILOffset Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definecatchhandleriloffset-method.md).</span></span>|  
|[<span data-ttu-id="6d39d-115">Метод GetKickoffMethod</span><span class="sxs-lookup"><span data-stu-id="6d39d-115">GetKickoffMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-getkickoffmethod-method.md)|<span data-ttu-id="6d39d-116">См. в разделе [метод DefineKickoffMethod](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definekickoffmethod-method.md).</span><span class="sxs-lookup"><span data-stu-id="6d39d-116">See [DefineKickoffMethod Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definekickoffmethod-method.md).</span></span>|  
|[<span data-ttu-id="6d39d-117">Метод HasCatchHandlerILOffset</span><span class="sxs-lookup"><span data-stu-id="6d39d-117">HasCatchHandlerILOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-hascatchhandleriloffset-method.md)|<span data-ttu-id="6d39d-118">См. в разделе [метод DefineCatchHandlerILOffset](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definecatchhandleriloffset-method.md).</span><span class="sxs-lookup"><span data-stu-id="6d39d-118">See [DefineCatchHandlerILOffset Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definecatchhandleriloffset-method.md).</span></span>|  
|[<span data-ttu-id="6d39d-119">Метод IsAsyncMethod</span><span class="sxs-lookup"><span data-stu-id="6d39d-119">IsAsyncMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-isasyncmethod-method.md)|<span data-ttu-id="6d39d-120">Проверяет, если метод имеет async сведения или нет.</span><span class="sxs-lookup"><span data-stu-id="6d39d-120">Checks if the method has async information or not.</span></span><br /><br /> <span data-ttu-id="6d39d-121">Если этот метод возвращает `FALSE` затем не допускается вызывать остальные методы в этом интерфейсе.</span><span class="sxs-lookup"><span data-stu-id="6d39d-121">If this method returns `FALSE` then it is invalid to call any other methods in this interface.</span></span> <span data-ttu-id="6d39d-122">Они будут все возврата `E_UNEXPECTED` в данном случае.</span><span class="sxs-lookup"><span data-stu-id="6d39d-122">They will all return `E_UNEXPECTED` in this case.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6d39d-123">Требования</span><span class="sxs-lookup"><span data-stu-id="6d39d-123">Requirements</span></span>  
 <span data-ttu-id="6d39d-124">**Заголовок.** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="6d39d-124">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d39d-125">См. также</span><span class="sxs-lookup"><span data-stu-id="6d39d-125">See also</span></span>
- [<span data-ttu-id="6d39d-126">Интерфейсы хранилища символов диагностики</span><span class="sxs-lookup"><span data-stu-id="6d39d-126">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)

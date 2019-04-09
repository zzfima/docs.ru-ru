---
title: Интерфейс ISymUnmanagedAsyncMethod
ms.date: 03/30/2017
ms.assetid: f2de5224-fd91-45de-9e58-bc600c6d22f1
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cd524446cd9fd5cf9c067ab5778a654ed000ffb3
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59179807"
---
# <a name="isymunmanagedasyncmethod-interface"></a><span data-ttu-id="f5ed9-102">Интерфейс ISymUnmanagedAsyncMethod</span><span class="sxs-lookup"><span data-stu-id="f5ed9-102">ISymUnmanagedAsyncMethod Interface</span></span>
<span data-ttu-id="f5ed9-103">Этот интерфейс является дополнением к чтения [интерфейс ISymUnmanagedAsyncMethodPropertiesWriter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md).</span><span class="sxs-lookup"><span data-stu-id="f5ed9-103">This interface is the reading complement to [ISymUnmanagedAsyncMethodPropertiesWriter Interface](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f5ed9-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f5ed9-104">Syntax</span></span>  
  
```idl  
[object,uuid(B20D55B3-532E-4906-87E7-25BD5734ABD2),pointer_default(unique)]interface ISymUnmanagedAsyncMethod : IUnknown  
```  
  
## <a name="methods"></a><span data-ttu-id="f5ed9-105">Методы</span><span class="sxs-lookup"><span data-stu-id="f5ed9-105">Methods</span></span>  
 <span data-ttu-id="f5ed9-106">Этот интерфейс содержит следующие методы:</span><span class="sxs-lookup"><span data-stu-id="f5ed9-106">This interface contains the following methods:</span></span>  
  
|<span data-ttu-id="f5ed9-107">Метод</span><span class="sxs-lookup"><span data-stu-id="f5ed9-107">Method</span></span>|<span data-ttu-id="f5ed9-108">Описание</span><span class="sxs-lookup"><span data-stu-id="f5ed9-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f5ed9-109">Метод GetAsyncStepInfo</span><span class="sxs-lookup"><span data-stu-id="f5ed9-109">GetAsyncStepInfo Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-getasyncstepinfo-method.md)|<span data-ttu-id="f5ed9-110">См. в разделе [метод DefineAsyncStepInfo](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md).</span><span class="sxs-lookup"><span data-stu-id="f5ed9-110">See [DefineAsyncStepInfo Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md).</span></span>|  
|[<span data-ttu-id="f5ed9-111">Метод GetAsyncStepInfoCount</span><span class="sxs-lookup"><span data-stu-id="f5ed9-111">GetAsyncStepInfoCount Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-getasyncstepinfocount-method.md)|<span data-ttu-id="f5ed9-112">См. в разделе [метод DefineAsyncStepInfo](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md).</span><span class="sxs-lookup"><span data-stu-id="f5ed9-112">See [DefineAsyncStepInfo Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md).</span></span>|  
|[<span data-ttu-id="f5ed9-113">Метод GetCatchHandlerILOffset</span><span class="sxs-lookup"><span data-stu-id="f5ed9-113">GetCatchHandlerILOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-getcatchhandleriloffset-method.md)|<span data-ttu-id="f5ed9-114">См. в разделе [метод DefineCatchHandlerILOffset](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definecatchhandleriloffset-method.md).</span><span class="sxs-lookup"><span data-stu-id="f5ed9-114">See [DefineCatchHandlerILOffset Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definecatchhandleriloffset-method.md).</span></span>|  
|[<span data-ttu-id="f5ed9-115">Метод GetKickoffMethod</span><span class="sxs-lookup"><span data-stu-id="f5ed9-115">GetKickoffMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-getkickoffmethod-method.md)|<span data-ttu-id="f5ed9-116">См. в разделе [метод DefineKickoffMethod](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definekickoffmethod-method.md).</span><span class="sxs-lookup"><span data-stu-id="f5ed9-116">See [DefineKickoffMethod Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definekickoffmethod-method.md).</span></span>|  
|[<span data-ttu-id="f5ed9-117">Метод HasCatchHandlerILOffset</span><span class="sxs-lookup"><span data-stu-id="f5ed9-117">HasCatchHandlerILOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-hascatchhandleriloffset-method.md)|<span data-ttu-id="f5ed9-118">См. в разделе [метод DefineCatchHandlerILOffset](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definecatchhandleriloffset-method.md).</span><span class="sxs-lookup"><span data-stu-id="f5ed9-118">See [DefineCatchHandlerILOffset Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definecatchhandleriloffset-method.md).</span></span>|  
|[<span data-ttu-id="f5ed9-119">Метод IsAsyncMethod</span><span class="sxs-lookup"><span data-stu-id="f5ed9-119">IsAsyncMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-isasyncmethod-method.md)|<span data-ttu-id="f5ed9-120">Проверяет, если метод имеет async сведения или нет.</span><span class="sxs-lookup"><span data-stu-id="f5ed9-120">Checks if the method has async information or not.</span></span><br /><br /> <span data-ttu-id="f5ed9-121">Если этот метод возвращает `FALSE` затем не допускается вызывать остальные методы в этом интерфейсе.</span><span class="sxs-lookup"><span data-stu-id="f5ed9-121">If this method returns `FALSE` then it is invalid to call any other methods in this interface.</span></span> <span data-ttu-id="f5ed9-122">Они будут все возврата `E_UNEXPECTED` в данном случае.</span><span class="sxs-lookup"><span data-stu-id="f5ed9-122">They will all return `E_UNEXPECTED` in this case.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f5ed9-123">Требования</span><span class="sxs-lookup"><span data-stu-id="f5ed9-123">Requirements</span></span>  
 <span data-ttu-id="f5ed9-124">**Заголовок.** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="f5ed9-124">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5ed9-125">См. также</span><span class="sxs-lookup"><span data-stu-id="f5ed9-125">See also</span></span>

- [<span data-ttu-id="f5ed9-126">Интерфейсы хранилища символов диагностики</span><span class="sxs-lookup"><span data-stu-id="f5ed9-126">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)

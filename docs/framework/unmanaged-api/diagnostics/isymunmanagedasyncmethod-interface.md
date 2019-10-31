---
title: Интерфейс ISymUnmanagedAsyncMethod
ms.date: 03/30/2017
ms.assetid: f2de5224-fd91-45de-9e58-bc600c6d22f1
ms.openlocfilehash: 0b8adba9dbffbdc47bb526cef9aad3ffa4b48065
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129226"
---
# <a name="isymunmanagedasyncmethod-interface"></a><span data-ttu-id="2cec0-102">Интерфейс ISymUnmanagedAsyncMethod</span><span class="sxs-lookup"><span data-stu-id="2cec0-102">ISymUnmanagedAsyncMethod Interface</span></span>
<span data-ttu-id="2cec0-103">Этот интерфейс является дополнением к [интерфейсу метод isymunmanagedasyncmethodpropertieswriter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md)для чтения.</span><span class="sxs-lookup"><span data-stu-id="2cec0-103">This interface is the reading complement to [ISymUnmanagedAsyncMethodPropertiesWriter Interface](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2cec0-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2cec0-104">Syntax</span></span>  
  
```idl  
[object,uuid(B20D55B3-532E-4906-87E7-25BD5734ABD2),pointer_default(unique)]interface ISymUnmanagedAsyncMethod : IUnknown  
```  
  
## <a name="methods"></a><span data-ttu-id="2cec0-105">Методы</span><span class="sxs-lookup"><span data-stu-id="2cec0-105">Methods</span></span>  
 <span data-ttu-id="2cec0-106">Этот интерфейс содержит следующие методы:</span><span class="sxs-lookup"><span data-stu-id="2cec0-106">This interface contains the following methods:</span></span>  
  
|<span data-ttu-id="2cec0-107">Метод</span><span class="sxs-lookup"><span data-stu-id="2cec0-107">Method</span></span>|<span data-ttu-id="2cec0-108">Описание</span><span class="sxs-lookup"><span data-stu-id="2cec0-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="2cec0-109">Метод GetAsyncStepInfo</span><span class="sxs-lookup"><span data-stu-id="2cec0-109">GetAsyncStepInfo Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-getasyncstepinfo-method.md)|<span data-ttu-id="2cec0-110">См. раздел [метод дефинеасинкстепинфо](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md).</span><span class="sxs-lookup"><span data-stu-id="2cec0-110">See [DefineAsyncStepInfo Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md).</span></span>|  
|[<span data-ttu-id="2cec0-111">Метод GetAsyncStepInfoCount</span><span class="sxs-lookup"><span data-stu-id="2cec0-111">GetAsyncStepInfoCount Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-getasyncstepinfocount-method.md)|<span data-ttu-id="2cec0-112">См. раздел [метод дефинеасинкстепинфо](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md).</span><span class="sxs-lookup"><span data-stu-id="2cec0-112">See [DefineAsyncStepInfo Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md).</span></span>|  
|[<span data-ttu-id="2cec0-113">Метод GetCatchHandlerILOffset</span><span class="sxs-lookup"><span data-stu-id="2cec0-113">GetCatchHandlerILOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-getcatchhandleriloffset-method.md)|<span data-ttu-id="2cec0-114">См. раздел [метод DefineCatchHandlerILOffset](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definecatchhandleriloffset-method.md).</span><span class="sxs-lookup"><span data-stu-id="2cec0-114">See [DefineCatchHandlerILOffset Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definecatchhandleriloffset-method.md).</span></span>|  
|[<span data-ttu-id="2cec0-115">Метод GetKickoffMethod</span><span class="sxs-lookup"><span data-stu-id="2cec0-115">GetKickoffMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-getkickoffmethod-method.md)|<span data-ttu-id="2cec0-116">См. раздел [метод DefineKickoffMethod](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definekickoffmethod-method.md).</span><span class="sxs-lookup"><span data-stu-id="2cec0-116">See [DefineKickoffMethod Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definekickoffmethod-method.md).</span></span>|  
|[<span data-ttu-id="2cec0-117">Метод HasCatchHandlerILOffset</span><span class="sxs-lookup"><span data-stu-id="2cec0-117">HasCatchHandlerILOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-hascatchhandleriloffset-method.md)|<span data-ttu-id="2cec0-118">См. раздел [метод DefineCatchHandlerILOffset](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definecatchhandleriloffset-method.md).</span><span class="sxs-lookup"><span data-stu-id="2cec0-118">See [DefineCatchHandlerILOffset Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definecatchhandleriloffset-method.md).</span></span>|  
|[<span data-ttu-id="2cec0-119">Метод IsAsyncMethod</span><span class="sxs-lookup"><span data-stu-id="2cec0-119">IsAsyncMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-isasyncmethod-method.md)|<span data-ttu-id="2cec0-120">Проверяет, имеет ли метод асинхронную информацию.</span><span class="sxs-lookup"><span data-stu-id="2cec0-120">Checks if the method has async information or not.</span></span><br /><br /> <span data-ttu-id="2cec0-121">Если этот метод возвращает `FALSE`, то он недопустим для вызова любых других методов в этом интерфейсе.</span><span class="sxs-lookup"><span data-stu-id="2cec0-121">If this method returns `FALSE` then it is invalid to call any other methods in this interface.</span></span> <span data-ttu-id="2cec0-122">В этом случае все они будут возвращать `E_UNEXPECTED`.</span><span class="sxs-lookup"><span data-stu-id="2cec0-122">They will all return `E_UNEXPECTED` in this case.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="2cec0-123">Требования</span><span class="sxs-lookup"><span data-stu-id="2cec0-123">Requirements</span></span>  
 <span data-ttu-id="2cec0-124">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="2cec0-124">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2cec0-125">См. также</span><span class="sxs-lookup"><span data-stu-id="2cec0-125">See also</span></span>

- [<span data-ttu-id="2cec0-126">Интерфейсы хранилища символов диагностики</span><span class="sxs-lookup"><span data-stu-id="2cec0-126">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)

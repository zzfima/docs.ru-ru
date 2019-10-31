---
title: Метод ISymUnmanagedAsyncMethod::GetKickoffMethod
ms.date: 03/30/2017
ms.assetid: ba084444-9e68-4cde-9388-54b950670987
ms.openlocfilehash: 58daec30b4cbae9cfaab27d4ce76521ba839cf83
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139846"
---
# <a name="isymunmanagedasyncmethodgetkickoffmethod-method"></a><span data-ttu-id="98f2f-102">Метод ISymUnmanagedAsyncMethod::GetKickoffMethod</span><span class="sxs-lookup"><span data-stu-id="98f2f-102">ISymUnmanagedAsyncMethod::GetKickoffMethod Method</span></span>
<span data-ttu-id="98f2f-103">См. раздел [метод DefineKickoffMethod](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definekickoffmethod-method.md).</span><span class="sxs-lookup"><span data-stu-id="98f2f-103">See [DefineKickoffMethod Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definekickoffmethod-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="98f2f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="98f2f-104">Syntax</span></span>  
  
```idl  
HRESULT GetKickoffMethod(    [out, retval] mdToken* kickoffMethod);  
```  
  
## <a name="parameters"></a><span data-ttu-id="98f2f-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="98f2f-105">Parameters</span></span>  
  
|<span data-ttu-id="98f2f-106">Параметр</span><span class="sxs-lookup"><span data-stu-id="98f2f-106">Parameter</span></span>|<span data-ttu-id="98f2f-107">Описание</span><span class="sxs-lookup"><span data-stu-id="98f2f-107">Description</span></span>|  
|---------------|-----------------|  
|`kickoffMethod`||  
  
## <a name="return-value"></a><span data-ttu-id="98f2f-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="98f2f-108">Return Value</span></span>  
 <span data-ttu-id="98f2f-109">Возвращает `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="98f2f-109">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="98f2f-110">Требования</span><span class="sxs-lookup"><span data-stu-id="98f2f-110">Requirements</span></span>  
 <span data-ttu-id="98f2f-111">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="98f2f-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98f2f-112">См. также</span><span class="sxs-lookup"><span data-stu-id="98f2f-112">See also</span></span>

- [<span data-ttu-id="98f2f-113">Интерфейс ISymUnmanagedAsyncMethod</span><span class="sxs-lookup"><span data-stu-id="98f2f-113">ISymUnmanagedAsyncMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-interface.md)

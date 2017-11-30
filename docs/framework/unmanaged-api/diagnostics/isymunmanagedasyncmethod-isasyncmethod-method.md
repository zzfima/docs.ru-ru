---
title: "Метод ISymUnmanagedAsyncMethod::IsAsyncMethod"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 670a7653-dac6-4171-98ee-d669e3adf4b2
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ce91552d7468579d9941c1da75c4d281999d66fd
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedasyncmethodisasyncmethod-method"></a><span data-ttu-id="9033c-102">Метод ISymUnmanagedAsyncMethod::IsAsyncMethod</span><span class="sxs-lookup"><span data-stu-id="9033c-102">ISymUnmanagedAsyncMethod::IsAsyncMethod Method</span></span>
<span data-ttu-id="9033c-103">Проверяет, метод async сведения или нет.</span><span class="sxs-lookup"><span data-stu-id="9033c-103">Checks if the method has async information or not.</span></span>  
  
 <span data-ttu-id="9033c-104">Если этот метод возвращает `FALSE` затем не допускается вызывать остальные методы в этом интерфейсе.</span><span class="sxs-lookup"><span data-stu-id="9033c-104">If this method returns `FALSE` then it is invalid to call any other methods in this interface.</span></span> <span data-ttu-id="9033c-105">Они будут все возврата `E_UNEXPECTED` в этом случае.</span><span class="sxs-lookup"><span data-stu-id="9033c-105">They will all return `E_UNEXPECTED` in this case.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9033c-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9033c-106">Syntax</span></span>  
  
```idl  
HRESULT IsAsyncMethod(    [out, retval] BOOL* pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9033c-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="9033c-107">Parameters</span></span>  
  
|<span data-ttu-id="9033c-108">Параметр</span><span class="sxs-lookup"><span data-stu-id="9033c-108">Parameter</span></span>|<span data-ttu-id="9033c-109">Описание</span><span class="sxs-lookup"><span data-stu-id="9033c-109">Description</span></span>|  
|---------------|-----------------|  
|`pRetVal`||  
  
## <a name="return-value"></a><span data-ttu-id="9033c-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="9033c-110">Return Value</span></span>  
 <span data-ttu-id="9033c-111">Возвращает `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="9033c-111">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9033c-112">Требования</span><span class="sxs-lookup"><span data-stu-id="9033c-112">Requirements</span></span>  
 <span data-ttu-id="9033c-113">**Заголовок:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="9033c-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9033c-114">См. также</span><span class="sxs-lookup"><span data-stu-id="9033c-114">See Also</span></span>  
 [<span data-ttu-id="9033c-115">Интерфейс ISymUnmanagedAsyncMethod</span><span class="sxs-lookup"><span data-stu-id="9033c-115">ISymUnmanagedAsyncMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-interface.md)

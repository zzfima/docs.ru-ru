---
title: Метод ISymUnmanagedAsyncMethod::IsAsyncMethod
ms.date: 03/30/2017
ms.assetid: 670a7653-dac6-4171-98ee-d669e3adf4b2
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 049f8e4d04498b70533134c01765af2d996d86dc
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54499110"
---
# <a name="isymunmanagedasyncmethodisasyncmethod-method"></a><span data-ttu-id="fb0c0-102">Метод ISymUnmanagedAsyncMethod::IsAsyncMethod</span><span class="sxs-lookup"><span data-stu-id="fb0c0-102">ISymUnmanagedAsyncMethod::IsAsyncMethod Method</span></span>
<span data-ttu-id="fb0c0-103">Проверяет, если метод имеет async сведения или нет.</span><span class="sxs-lookup"><span data-stu-id="fb0c0-103">Checks if the method has async information or not.</span></span>  
  
 <span data-ttu-id="fb0c0-104">Если этот метод возвращает `FALSE` затем не допускается вызывать остальные методы в этом интерфейсе.</span><span class="sxs-lookup"><span data-stu-id="fb0c0-104">If this method returns `FALSE` then it is invalid to call any other methods in this interface.</span></span> <span data-ttu-id="fb0c0-105">Они будут все возврата `E_UNEXPECTED` в данном случае.</span><span class="sxs-lookup"><span data-stu-id="fb0c0-105">They will all return `E_UNEXPECTED` in this case.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fb0c0-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fb0c0-106">Syntax</span></span>  
  
```idl  
HRESULT IsAsyncMethod(    [out, retval] BOOL* pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="fb0c0-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="fb0c0-107">Parameters</span></span>  
  
|<span data-ttu-id="fb0c0-108">Параметр</span><span class="sxs-lookup"><span data-stu-id="fb0c0-108">Parameter</span></span>|<span data-ttu-id="fb0c0-109">Описание</span><span class="sxs-lookup"><span data-stu-id="fb0c0-109">Description</span></span>|  
|---------------|-----------------|  
|`pRetVal`||  
  
## <a name="return-value"></a><span data-ttu-id="fb0c0-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="fb0c0-110">Return Value</span></span>  
 <span data-ttu-id="fb0c0-111">Возвращает `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="fb0c0-111">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fb0c0-112">Требования</span><span class="sxs-lookup"><span data-stu-id="fb0c0-112">Requirements</span></span>  
 <span data-ttu-id="fb0c0-113">**Заголовок.** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="fb0c0-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb0c0-114">См. также</span><span class="sxs-lookup"><span data-stu-id="fb0c0-114">See also</span></span>
- [<span data-ttu-id="fb0c0-115">Интерфейс ISymUnmanagedAsyncMethod</span><span class="sxs-lookup"><span data-stu-id="fb0c0-115">ISymUnmanagedAsyncMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-interface.md)

---
title: Метод ISymUnmanagedAsyncMethod::IsAsyncMethod
ms.date: 03/30/2017
ms.assetid: 670a7653-dac6-4171-98ee-d669e3adf4b2
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 460d6781405b6042262d50e1aa79ee8c77f781a7
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57489730"
---
# <a name="isymunmanagedasyncmethodisasyncmethod-method"></a><span data-ttu-id="f1cbd-102">Метод ISymUnmanagedAsyncMethod::IsAsyncMethod</span><span class="sxs-lookup"><span data-stu-id="f1cbd-102">ISymUnmanagedAsyncMethod::IsAsyncMethod Method</span></span>
<span data-ttu-id="f1cbd-103">Проверяет, если метод имеет async сведения или нет.</span><span class="sxs-lookup"><span data-stu-id="f1cbd-103">Checks if the method has async information or not.</span></span>  
  
 <span data-ttu-id="f1cbd-104">Если этот метод возвращает `FALSE` затем не допускается вызывать остальные методы в этом интерфейсе.</span><span class="sxs-lookup"><span data-stu-id="f1cbd-104">If this method returns `FALSE` then it is invalid to call any other methods in this interface.</span></span> <span data-ttu-id="f1cbd-105">Они будут все возврата `E_UNEXPECTED` в данном случае.</span><span class="sxs-lookup"><span data-stu-id="f1cbd-105">They will all return `E_UNEXPECTED` in this case.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f1cbd-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f1cbd-106">Syntax</span></span>  
  
```idl  
HRESULT IsAsyncMethod(    [out, retval] BOOL* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f1cbd-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="f1cbd-107">Parameters</span></span>  
  
|<span data-ttu-id="f1cbd-108">Параметр</span><span class="sxs-lookup"><span data-stu-id="f1cbd-108">Parameter</span></span>|<span data-ttu-id="f1cbd-109">Описание:</span><span class="sxs-lookup"><span data-stu-id="f1cbd-109">Description</span></span>|  
|---------------|-----------------|  
|`pRetVal`||  
  
## <a name="return-value"></a><span data-ttu-id="f1cbd-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="f1cbd-110">Return Value</span></span>  
 <span data-ttu-id="f1cbd-111">Возвращает `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="f1cbd-111">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f1cbd-112">Требования</span><span class="sxs-lookup"><span data-stu-id="f1cbd-112">Requirements</span></span>  
 <span data-ttu-id="f1cbd-113">**Заголовок.** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="f1cbd-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1cbd-114">См. также</span><span class="sxs-lookup"><span data-stu-id="f1cbd-114">See also</span></span>
- [<span data-ttu-id="f1cbd-115">Интерфейс ISymUnmanagedAsyncMethod</span><span class="sxs-lookup"><span data-stu-id="f1cbd-115">ISymUnmanagedAsyncMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-interface.md)

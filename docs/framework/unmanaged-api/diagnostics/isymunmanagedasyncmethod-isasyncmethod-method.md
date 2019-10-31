---
title: Метод ISymUnmanagedAsyncMethod::IsAsyncMethod
ms.date: 03/30/2017
ms.assetid: 670a7653-dac6-4171-98ee-d669e3adf4b2
ms.openlocfilehash: 0ea4c21e9e6a49d7bbbad5e1853598c440cd6410
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129215"
---
# <a name="isymunmanagedasyncmethodisasyncmethod-method"></a><span data-ttu-id="9a10d-102">Метод ISymUnmanagedAsyncMethod::IsAsyncMethod</span><span class="sxs-lookup"><span data-stu-id="9a10d-102">ISymUnmanagedAsyncMethod::IsAsyncMethod Method</span></span>
<span data-ttu-id="9a10d-103">Проверяет, имеет ли метод асинхронную информацию.</span><span class="sxs-lookup"><span data-stu-id="9a10d-103">Checks if the method has async information or not.</span></span>  
  
 <span data-ttu-id="9a10d-104">Если этот метод возвращает `FALSE`, то он недопустим для вызова любых других методов в этом интерфейсе.</span><span class="sxs-lookup"><span data-stu-id="9a10d-104">If this method returns `FALSE` then it is invalid to call any other methods in this interface.</span></span> <span data-ttu-id="9a10d-105">В этом случае все они будут возвращать `E_UNEXPECTED`.</span><span class="sxs-lookup"><span data-stu-id="9a10d-105">They will all return `E_UNEXPECTED` in this case.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9a10d-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9a10d-106">Syntax</span></span>  
  
```idl  
HRESULT IsAsyncMethod(    [out, retval] BOOL* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9a10d-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="9a10d-107">Parameters</span></span>  
  
|<span data-ttu-id="9a10d-108">Параметр</span><span class="sxs-lookup"><span data-stu-id="9a10d-108">Parameter</span></span>|<span data-ttu-id="9a10d-109">Описание</span><span class="sxs-lookup"><span data-stu-id="9a10d-109">Description</span></span>|  
|---------------|-----------------|  
|`pRetVal`||  
  
## <a name="return-value"></a><span data-ttu-id="9a10d-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="9a10d-110">Return Value</span></span>  
 <span data-ttu-id="9a10d-111">Возвращает `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="9a10d-111">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9a10d-112">Требования</span><span class="sxs-lookup"><span data-stu-id="9a10d-112">Requirements</span></span>  
 <span data-ttu-id="9a10d-113">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="9a10d-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a10d-114">См. также</span><span class="sxs-lookup"><span data-stu-id="9a10d-114">See also</span></span>

- [<span data-ttu-id="9a10d-115">Интерфейс ISymUnmanagedAsyncMethod</span><span class="sxs-lookup"><span data-stu-id="9a10d-115">ISymUnmanagedAsyncMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-interface.md)

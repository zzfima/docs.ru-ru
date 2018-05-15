---
title: Метод ISymUnmanagedAsyncMethod::IsAsyncMethod
ms.date: 03/30/2017
ms.assetid: 670a7653-dac6-4171-98ee-d669e3adf4b2
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3f5bf8252986ffa90ea5380d5342595cb91e5419
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="isymunmanagedasyncmethodisasyncmethod-method"></a><span data-ttu-id="71653-102">Метод ISymUnmanagedAsyncMethod::IsAsyncMethod</span><span class="sxs-lookup"><span data-stu-id="71653-102">ISymUnmanagedAsyncMethod::IsAsyncMethod Method</span></span>
<span data-ttu-id="71653-103">Проверяет, метод async сведения или нет.</span><span class="sxs-lookup"><span data-stu-id="71653-103">Checks if the method has async information or not.</span></span>  
  
 <span data-ttu-id="71653-104">Если этот метод возвращает `FALSE` затем не допускается вызывать остальные методы в этом интерфейсе.</span><span class="sxs-lookup"><span data-stu-id="71653-104">If this method returns `FALSE` then it is invalid to call any other methods in this interface.</span></span> <span data-ttu-id="71653-105">Они будут все возврата `E_UNEXPECTED` в этом случае.</span><span class="sxs-lookup"><span data-stu-id="71653-105">They will all return `E_UNEXPECTED` in this case.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="71653-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="71653-106">Syntax</span></span>  
  
```idl  
HRESULT IsAsyncMethod(    [out, retval] BOOL* pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="71653-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="71653-107">Parameters</span></span>  
  
|<span data-ttu-id="71653-108">Параметр</span><span class="sxs-lookup"><span data-stu-id="71653-108">Parameter</span></span>|<span data-ttu-id="71653-109">Описание</span><span class="sxs-lookup"><span data-stu-id="71653-109">Description</span></span>|  
|---------------|-----------------|  
|`pRetVal`||  
  
## <a name="return-value"></a><span data-ttu-id="71653-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="71653-110">Return Value</span></span>  
 <span data-ttu-id="71653-111">Возвращает `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="71653-111">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="71653-112">Требования</span><span class="sxs-lookup"><span data-stu-id="71653-112">Requirements</span></span>  
 <span data-ttu-id="71653-113">**Заголовок:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="71653-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71653-114">См. также</span><span class="sxs-lookup"><span data-stu-id="71653-114">See Also</span></span>  
 [<span data-ttu-id="71653-115">Интерфейс ISymUnmanagedAsyncMethod</span><span class="sxs-lookup"><span data-stu-id="71653-115">ISymUnmanagedAsyncMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-interface.md)

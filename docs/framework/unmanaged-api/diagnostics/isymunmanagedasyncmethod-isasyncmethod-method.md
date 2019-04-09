---
title: Метод ISymUnmanagedAsyncMethod::IsAsyncMethod
ms.date: 03/30/2017
ms.assetid: 670a7653-dac6-4171-98ee-d669e3adf4b2
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e5cddf34f1a6277e966901c9692bff63e26a3b8e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59136738"
---
# <a name="isymunmanagedasyncmethodisasyncmethod-method"></a><span data-ttu-id="d8228-102">Метод ISymUnmanagedAsyncMethod::IsAsyncMethod</span><span class="sxs-lookup"><span data-stu-id="d8228-102">ISymUnmanagedAsyncMethod::IsAsyncMethod Method</span></span>
<span data-ttu-id="d8228-103">Проверяет, если метод имеет async сведения или нет.</span><span class="sxs-lookup"><span data-stu-id="d8228-103">Checks if the method has async information or not.</span></span>  
  
 <span data-ttu-id="d8228-104">Если этот метод возвращает `FALSE` затем не допускается вызывать остальные методы в этом интерфейсе.</span><span class="sxs-lookup"><span data-stu-id="d8228-104">If this method returns `FALSE` then it is invalid to call any other methods in this interface.</span></span> <span data-ttu-id="d8228-105">Они будут все возврата `E_UNEXPECTED` в данном случае.</span><span class="sxs-lookup"><span data-stu-id="d8228-105">They will all return `E_UNEXPECTED` in this case.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d8228-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d8228-106">Syntax</span></span>  
  
```idl  
HRESULT IsAsyncMethod(    [out, retval] BOOL* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d8228-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="d8228-107">Parameters</span></span>  
  
|<span data-ttu-id="d8228-108">Параметр</span><span class="sxs-lookup"><span data-stu-id="d8228-108">Parameter</span></span>|<span data-ttu-id="d8228-109">Описание</span><span class="sxs-lookup"><span data-stu-id="d8228-109">Description</span></span>|  
|---------------|-----------------|  
|`pRetVal`||  
  
## <a name="return-value"></a><span data-ttu-id="d8228-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="d8228-110">Return Value</span></span>  
 <span data-ttu-id="d8228-111">Возвращает `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="d8228-111">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d8228-112">Требования</span><span class="sxs-lookup"><span data-stu-id="d8228-112">Requirements</span></span>  
 <span data-ttu-id="d8228-113">**Заголовок.** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="d8228-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8228-114">См. также</span><span class="sxs-lookup"><span data-stu-id="d8228-114">See also</span></span>

- [<span data-ttu-id="d8228-115">Интерфейс ISymUnmanagedAsyncMethod</span><span class="sxs-lookup"><span data-stu-id="d8228-115">ISymUnmanagedAsyncMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-interface.md)

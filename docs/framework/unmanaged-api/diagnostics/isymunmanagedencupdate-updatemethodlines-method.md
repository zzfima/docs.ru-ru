---
title: Метод ISymUnmanagedENCUpdate::UpdateMethodLines
ms.date: 03/30/2017
api_name:
- ISymUnmanagedENCUpdate.UpdateMethodLines
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedENCUpdate::UpdateMethodLines
helpviewer_keywords:
- UpdateMethodLines method [.NET Framework debugging]
- ISymUnmanagedENCUpdate::UpdateMethodLines method [.NET Framework debugging]
ms.assetid: 275ef87b-0b53-49f9-af6b-58506335dc06
topic_type:
- apiref
ms.openlocfilehash: 9aace77c4b3549c033433d4c305b07daa1f7a8c1
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448993"
---
# <a name="isymunmanagedencupdateupdatemethodlines-method"></a><span data-ttu-id="f9557-102">Метод ISymUnmanagedENCUpdate::UpdateMethodLines</span><span class="sxs-lookup"><span data-stu-id="f9557-102">ISymUnmanagedENCUpdate::UpdateMethodLines Method</span></span>
<span data-ttu-id="f9557-103">Позволяет обновлять сведения о строке для метода, который не был перекомпилирован, но строки были перемещены независимо друг от друга.</span><span class="sxs-lookup"><span data-stu-id="f9557-103">Allows updating the line information for a method that has not been recompiled, but whose lines have moved independently.</span></span> <span data-ttu-id="f9557-104">Допускается использование разности для каждой инструкции.</span><span class="sxs-lookup"><span data-stu-id="f9557-104">A delta for each statement is allowed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f9557-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f9557-105">Syntax</span></span>  
  
```cpp  
HRESULT UpdateMethodLines(  
    [in]  mdMethodDef  mdMethodToken,  
    [in, size_is(cDeltas)] INT32*  pDeltas,  
    [in]  ULONG        cDeltas);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f9557-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="f9557-106">Parameters</span></span>  
 `mdMethodToken`  
 <span data-ttu-id="f9557-107">окне Метаданные токена метода.</span><span class="sxs-lookup"><span data-stu-id="f9557-107">[in] The metadata of the method token.</span></span>  
  
 `pDeltas`  
 <span data-ttu-id="f9557-108">окне Массив значений `INT32`, указывающий разность для каждой точки следования в методе.</span><span class="sxs-lookup"><span data-stu-id="f9557-108">[in] An array of `INT32` values that indicates deltas for each sequence point in the method.</span></span>  
  
 `cDeltas`  
 <span data-ttu-id="f9557-109">окне `ULONG`, содержащий размер параметра `pDeltas`.</span><span class="sxs-lookup"><span data-stu-id="f9557-109">[in] A `ULONG` containing the size of the `pDeltas` parameter.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f9557-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="f9557-110">Return Value</span></span>  
 <span data-ttu-id="f9557-111">S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.</span><span class="sxs-lookup"><span data-stu-id="f9557-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f9557-112">Требования</span><span class="sxs-lookup"><span data-stu-id="f9557-112">Requirements</span></span>  
 <span data-ttu-id="f9557-113">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="f9557-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9557-114">См. также</span><span class="sxs-lookup"><span data-stu-id="f9557-114">See also</span></span>

- [<span data-ttu-id="f9557-115">Интерфейс ISymUnmanagedENCUpdate</span><span class="sxs-lookup"><span data-stu-id="f9557-115">ISymUnmanagedENCUpdate Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-interface.md)

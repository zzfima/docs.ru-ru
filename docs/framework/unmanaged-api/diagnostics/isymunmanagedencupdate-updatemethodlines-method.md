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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: bd1f101e2e9cf9baeb28290c7607ccab3d8d7440
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59178923"
---
# <a name="isymunmanagedencupdateupdatemethodlines-method"></a><span data-ttu-id="9b68e-102">Метод ISymUnmanagedENCUpdate::UpdateMethodLines</span><span class="sxs-lookup"><span data-stu-id="9b68e-102">ISymUnmanagedENCUpdate::UpdateMethodLines Method</span></span>
<span data-ttu-id="9b68e-103">Позволяет обновлять данные строки для метода, который не был повторно скомпилирован, но его строки были перемещены независимо друг от друга.</span><span class="sxs-lookup"><span data-stu-id="9b68e-103">Allows updating the line information for a method that has not been recompiled, but whose lines have moved independently.</span></span> <span data-ttu-id="9b68e-104">Допускается разницы для каждой инструкции.</span><span class="sxs-lookup"><span data-stu-id="9b68e-104">A delta for each statement is allowed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9b68e-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9b68e-105">Syntax</span></span>  
  
```  
HRESULT UpdateMethodLines(  
    [in]  mdMethodDef  mdMethodToken,  
    [in, size_is(cDeltas)] INT32*  pDeltas,  
    [in]  ULONG        cDeltas);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9b68e-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="9b68e-106">Parameters</span></span>  
 `mdMethodToken`  
 <span data-ttu-id="9b68e-107">[in] Метаданные маркер метода.</span><span class="sxs-lookup"><span data-stu-id="9b68e-107">[in] The metadata of the method token.</span></span>  
  
 `pDeltas`  
 <span data-ttu-id="9b68e-108">[in] Массив `INT32` значений, указывающее «дельты» для каждой точки последовательности в методе.</span><span class="sxs-lookup"><span data-stu-id="9b68e-108">[in] An array of `INT32` values that indicates deltas for each sequence point in the method.</span></span>  
  
 `cDeltas`  
 <span data-ttu-id="9b68e-109">[in] Объект `ULONG` содержащий размер `pDeltas` параметра.</span><span class="sxs-lookup"><span data-stu-id="9b68e-109">[in] A `ULONG` containing the size of the `pDeltas` parameter.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9b68e-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="9b68e-110">Return Value</span></span>  
 <span data-ttu-id="9b68e-111">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="9b68e-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9b68e-112">Требования</span><span class="sxs-lookup"><span data-stu-id="9b68e-112">Requirements</span></span>  
 <span data-ttu-id="9b68e-113">**Заголовок.** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="9b68e-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b68e-114">См. также</span><span class="sxs-lookup"><span data-stu-id="9b68e-114">See also</span></span>

- [<span data-ttu-id="9b68e-115">Интерфейс ISymUnmanagedENCUpdate</span><span class="sxs-lookup"><span data-stu-id="9b68e-115">ISymUnmanagedENCUpdate Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-interface.md)

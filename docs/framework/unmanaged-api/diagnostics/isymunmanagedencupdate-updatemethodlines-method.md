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
ms.openlocfilehash: 50d9ac08b01a67df68ff077721ff5421fbc27707
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33424278"
---
# <a name="isymunmanagedencupdateupdatemethodlines-method"></a><span data-ttu-id="0a265-102">Метод ISymUnmanagedENCUpdate::UpdateMethodLines</span><span class="sxs-lookup"><span data-stu-id="0a265-102">ISymUnmanagedENCUpdate::UpdateMethodLines Method</span></span>
<span data-ttu-id="0a265-103">Позволяет обновить строки для метода, который не был повторно скомпилирован, но его строки были перемещены независимо друг от друга.</span><span class="sxs-lookup"><span data-stu-id="0a265-103">Allows updating the line information for a method that has not been recompiled, but whose lines have moved independently.</span></span> <span data-ttu-id="0a265-104">Допускается разницы для каждой инструкции.</span><span class="sxs-lookup"><span data-stu-id="0a265-104">A delta for each statement is allowed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0a265-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0a265-105">Syntax</span></span>  
  
```  
HRESULT UpdateMethodLines(  
    [in]  mdMethodDef  mdMethodToken,  
    [in, size_is(cDeltas)] INT32*  pDeltas,  
    [in]  ULONG        cDeltas);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0a265-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="0a265-106">Parameters</span></span>  
 `mdMethodToken`  
 <span data-ttu-id="0a265-107">[in] Метаданные маркер метода.</span><span class="sxs-lookup"><span data-stu-id="0a265-107">[in] The metadata of the method token.</span></span>  
  
 `pDeltas`  
 <span data-ttu-id="0a265-108">[in] Массив `INT32` значений, указывающее дельты для каждой точки последовательности в методе.</span><span class="sxs-lookup"><span data-stu-id="0a265-108">[in] An array of `INT32` values that indicates deltas for each sequence point in the method.</span></span>  
  
 `cDeltas`  
 <span data-ttu-id="0a265-109">[in] Объект `ULONG` содержащий размер `pDeltas` параметра.</span><span class="sxs-lookup"><span data-stu-id="0a265-109">[in] A `ULONG` containing the size of the `pDeltas` parameter.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0a265-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="0a265-110">Return Value</span></span>  
 <span data-ttu-id="0a265-111">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="0a265-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0a265-112">Требования</span><span class="sxs-lookup"><span data-stu-id="0a265-112">Requirements</span></span>  
 <span data-ttu-id="0a265-113">**Заголовок:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="0a265-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a265-114">См. также</span><span class="sxs-lookup"><span data-stu-id="0a265-114">See Also</span></span>  
 [<span data-ttu-id="0a265-115">Интерфейс ISymUnmanagedENCUpdate</span><span class="sxs-lookup"><span data-stu-id="0a265-115">ISymUnmanagedENCUpdate Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-interface.md)

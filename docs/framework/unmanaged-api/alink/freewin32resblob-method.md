---
title: Метод FreeWin32ResBlob
ms.date: 03/30/2017
api_name:
- IALink.FreeWin32ResBlob
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- FreeWin32ResBlob
helpviewer_keywords:
- FreeWin32ResBlob method
ms.assetid: d941102b-2679-4c49-b15e-c0fc9c53e11f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6f7ffef0af68bee3e7184fe8bde9264f570230be
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54573642"
---
# <a name="freewin32resblob-method"></a><span data-ttu-id="f126f-102">Метод FreeWin32ResBlob</span><span class="sxs-lookup"><span data-stu-id="f126f-102">FreeWin32ResBlob Method</span></span>
<span data-ttu-id="f126f-103">Освобождает большой двоичный объект ресурса Win32 и связанные с ней ресурсы.</span><span class="sxs-lookup"><span data-stu-id="f126f-103">Releases the Win32 resource blob and associated resources.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f126f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f126f-104">Syntax</span></span>  
  
```  
HRESULT FreeWin32ResBlob(  
    const void** ppResBlob  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f126f-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="f126f-105">Parameters</span></span>  
 `ppResBlob`  
 <span data-ttu-id="f126f-106">Большой двоичный объект ресурса к освобождению.</span><span class="sxs-lookup"><span data-stu-id="f126f-106">The resource blob to be released.</span></span> <span data-ttu-id="f126f-107">Этот метод назначает BLOB-объектов указатель NULL.</span><span class="sxs-lookup"><span data-stu-id="f126f-107">This method assigns the blob pointer to NULL.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f126f-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="f126f-108">Return Value</span></span>  
 <span data-ttu-id="f126f-109">Возвращает S_OK, если метод выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="f126f-109">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f126f-110">Требования</span><span class="sxs-lookup"><span data-stu-id="f126f-110">Requirements</span></span>  
 <span data-ttu-id="f126f-111">Требуется alink.h</span><span class="sxs-lookup"><span data-stu-id="f126f-111">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f126f-112">См. также</span><span class="sxs-lookup"><span data-stu-id="f126f-112">See also</span></span>
- [<span data-ttu-id="f126f-113">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="f126f-113">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="f126f-114">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="f126f-114">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="f126f-115">API ALink</span><span class="sxs-lookup"><span data-stu-id="f126f-115">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)

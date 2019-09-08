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
ms.openlocfilehash: ea0fbceb1e778a2f26e0625a337b803f417b59eb
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70777245"
---
# <a name="freewin32resblob-method"></a><span data-ttu-id="b6331-102">Метод FreeWin32ResBlob</span><span class="sxs-lookup"><span data-stu-id="b6331-102">FreeWin32ResBlob Method</span></span>
<span data-ttu-id="b6331-103">Освобождает большой двоичный объект ресурсов Win32 и связанные ресурсы.</span><span class="sxs-lookup"><span data-stu-id="b6331-103">Releases the Win32 resource blob and associated resources.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b6331-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b6331-104">Syntax</span></span>  
  
```cpp  
HRESULT FreeWin32ResBlob(  
    const void** ppResBlob  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="b6331-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="b6331-105">Parameters</span></span>  
 `ppResBlob`  
 <span data-ttu-id="b6331-106">Большой двоичный объект ресурса, который необходимо освободить.</span><span class="sxs-lookup"><span data-stu-id="b6331-106">The resource blob to be released.</span></span> <span data-ttu-id="b6331-107">Этот метод присваивает указатель большого двоичного объекта значению NULL.</span><span class="sxs-lookup"><span data-stu-id="b6331-107">This method assigns the blob pointer to NULL.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b6331-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="b6331-108">Return Value</span></span>  
 <span data-ttu-id="b6331-109">Если метод завершается с ошибкой, возвращает значение S_OK.</span><span class="sxs-lookup"><span data-stu-id="b6331-109">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b6331-110">Требования</span><span class="sxs-lookup"><span data-stu-id="b6331-110">Requirements</span></span>  
 <span data-ttu-id="b6331-111">Требуется ALink. h</span><span class="sxs-lookup"><span data-stu-id="b6331-111">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6331-112">См. также</span><span class="sxs-lookup"><span data-stu-id="b6331-112">See also</span></span>

- [<span data-ttu-id="b6331-113">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="b6331-113">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="b6331-114">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="b6331-114">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="b6331-115">API ALink</span><span class="sxs-lookup"><span data-stu-id="b6331-115">ALink API</span></span>](index.md)

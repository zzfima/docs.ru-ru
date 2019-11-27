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
ms.openlocfilehash: 2b1addc752c7238116e072c6e957d2b277ceb1e3
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449400"
---
# <a name="freewin32resblob-method"></a><span data-ttu-id="c7d5a-102">Метод FreeWin32ResBlob</span><span class="sxs-lookup"><span data-stu-id="c7d5a-102">FreeWin32ResBlob Method</span></span>
<span data-ttu-id="c7d5a-103">Освобождает большой двоичный объект ресурсов Win32 и связанные ресурсы.</span><span class="sxs-lookup"><span data-stu-id="c7d5a-103">Releases the Win32 resource blob and associated resources.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c7d5a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c7d5a-104">Syntax</span></span>  
  
```cpp  
HRESULT FreeWin32ResBlob(  
    const void** ppResBlob  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="c7d5a-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c7d5a-105">Parameters</span></span>  
 `ppResBlob`  
 <span data-ttu-id="c7d5a-106">Большой двоичный объект ресурса, который необходимо освободить.</span><span class="sxs-lookup"><span data-stu-id="c7d5a-106">The resource blob to be released.</span></span> <span data-ttu-id="c7d5a-107">Этот метод присваивает указатель большого двоичного объекта значению NULL.</span><span class="sxs-lookup"><span data-stu-id="c7d5a-107">This method assigns the blob pointer to NULL.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c7d5a-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="c7d5a-108">Return Value</span></span>  
 <span data-ttu-id="c7d5a-109">Возвращает S_OK, если метод завершается с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="c7d5a-109">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c7d5a-110">Требования</span><span class="sxs-lookup"><span data-stu-id="c7d5a-110">Requirements</span></span>  
 <span data-ttu-id="c7d5a-111">Требуется ALink. h</span><span class="sxs-lookup"><span data-stu-id="c7d5a-111">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7d5a-112">См. также</span><span class="sxs-lookup"><span data-stu-id="c7d5a-112">See also</span></span>

- [<span data-ttu-id="c7d5a-113">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="c7d5a-113">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="c7d5a-114">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="c7d5a-114">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="c7d5a-115">API ALink</span><span class="sxs-lookup"><span data-stu-id="c7d5a-115">ALink API</span></span>](index.md)

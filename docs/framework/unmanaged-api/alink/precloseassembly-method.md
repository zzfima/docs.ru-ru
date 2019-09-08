---
title: Метод PreCloseAssembly
ms.date: 03/30/2017
api_name:
- IALink.PreCloseAssembly
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- PreCloseAssembly
helpviewer_keywords:
- PreCloseAssembly method
ms.assetid: 6d23ac54-15ea-4027-a172-9ebef43e8f56
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d4cf862ae3676b85a7fc3f09a4f5794e01284737
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70787232"
---
# <a name="precloseassembly-method"></a><span data-ttu-id="26efa-102">Метод PreCloseAssembly</span><span class="sxs-lookup"><span data-stu-id="26efa-102">PreCloseAssembly Method</span></span>
<span data-ttu-id="26efa-103">Закрывает файл сборки.</span><span class="sxs-lookup"><span data-stu-id="26efa-103">Closes the assembly file.</span></span> <span data-ttu-id="26efa-104">Вызовите этот метод после закрытия всех остальных файлов, но перед закрытием файла сборки.</span><span class="sxs-lookup"><span data-stu-id="26efa-104">Call this method after closing all other files, but before closing the assembly file.</span></span> <span data-ttu-id="26efa-105">Не вызывайте этот метод для непривязанных модулей.</span><span class="sxs-lookup"><span data-stu-id="26efa-105">Do not call this method for unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="26efa-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="26efa-106">Syntax</span></span>  
  
```cpp  
HRESULT PreCloseAssembly(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="26efa-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="26efa-107">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="26efa-108">Идентификатор сборки.</span><span class="sxs-lookup"><span data-stu-id="26efa-108">ID of the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="26efa-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="26efa-109">Return Value</span></span>  
 <span data-ttu-id="26efa-110">Если метод завершается с ошибкой, возвращает значение S_OK.</span><span class="sxs-lookup"><span data-stu-id="26efa-110">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="26efa-111">Требования</span><span class="sxs-lookup"><span data-stu-id="26efa-111">Requirements</span></span>  
 <span data-ttu-id="26efa-112">Требуется ALink. h.</span><span class="sxs-lookup"><span data-stu-id="26efa-112">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26efa-113">См. также</span><span class="sxs-lookup"><span data-stu-id="26efa-113">See also</span></span>

- [<span data-ttu-id="26efa-114">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="26efa-114">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="26efa-115">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="26efa-115">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="26efa-116">API ALink</span><span class="sxs-lookup"><span data-stu-id="26efa-116">ALink API</span></span>](index.md)

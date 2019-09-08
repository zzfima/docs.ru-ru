---
title: Метод SetNonAssemblyFlags
ms.date: 03/30/2017
api_name:
- IALink.SetNonAssemblyFlags
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- SetNonAssemblyFlags
helpviewer_keywords:
- SetNonAssemblyFlags method
ms.assetid: f8ba6fc8-f5aa-4066-ac96-56332758f5ec
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e8a22e958740b69ba0e09bf062bf4d86075c3ff1
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70777012"
---
# <a name="setnonassemblyflags-method"></a><span data-ttu-id="33c9b-102">Метод SetNonAssemblyFlags</span><span class="sxs-lookup"><span data-stu-id="33c9b-102">SetNonAssemblyFlags Method</span></span>
<span data-ttu-id="33c9b-103">Устанавливает флаги, не зависящие от сборки.</span><span class="sxs-lookup"><span data-stu-id="33c9b-103">Sets flags that are not assembly-specific.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="33c9b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="33c9b-104">Syntax</span></span>  
  
```cpp  
HRESULT SetNonAssemblyFlags(  
    AssemblyFlags afFlags  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="33c9b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="33c9b-105">Parameters</span></span>  
 `afFlags`  
 <span data-ttu-id="33c9b-106">Флаги ALink.</span><span class="sxs-lookup"><span data-stu-id="33c9b-106">ALink flags.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="33c9b-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="33c9b-107">Return Value</span></span>  
 <span data-ttu-id="33c9b-108">Если метод завершается с ошибкой, возвращает значение S_OK.</span><span class="sxs-lookup"><span data-stu-id="33c9b-108">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="33c9b-109">Требования</span><span class="sxs-lookup"><span data-stu-id="33c9b-109">Requirements</span></span>  
 <span data-ttu-id="33c9b-110">Требуется ALink. h</span><span class="sxs-lookup"><span data-stu-id="33c9b-110">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33c9b-111">См. также</span><span class="sxs-lookup"><span data-stu-id="33c9b-111">See also</span></span>

- [<span data-ttu-id="33c9b-112">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="33c9b-112">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="33c9b-113">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="33c9b-113">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="33c9b-114">API ALink</span><span class="sxs-lookup"><span data-stu-id="33c9b-114">ALink API</span></span>](index.md)

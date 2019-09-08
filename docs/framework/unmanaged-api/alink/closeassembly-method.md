---
title: Метод CloseAssembly
ms.date: 03/30/2017
api_name:
- IALink.CloseAssembly
- CloseAssembly
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- CloseAssembly
helpviewer_keywords:
- CloseAssembly method
ms.assetid: f66a43bc-a5c5-4190-acbe-63fd27640634
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b7828c86018724bb934de99cab4617f9885fdca6
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70787609"
---
# <a name="closeassembly-method"></a><span data-ttu-id="3b9b4-102">Метод CloseAssembly</span><span class="sxs-lookup"><span data-stu-id="3b9b4-102">CloseAssembly Method</span></span>
<span data-ttu-id="3b9b4-103">Завершает операции сборки.</span><span class="sxs-lookup"><span data-stu-id="3b9b4-103">Finalizes assembly operations.</span></span> <span data-ttu-id="3b9b4-104">Вызовите этот метод перед началом новой сборки или несвязанного модуля.</span><span class="sxs-lookup"><span data-stu-id="3b9b4-104">Call this method before beginning a new assembly or unbound module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3b9b4-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3b9b4-105">Syntax</span></span>  
  
```cpp  
HRESULT CloseAssembly(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="3b9b4-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="3b9b4-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="3b9b4-107">Идентификатор сборки.</span><span class="sxs-lookup"><span data-stu-id="3b9b4-107">ID of the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3b9b4-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="3b9b4-108">Return Value</span></span>  
 <span data-ttu-id="3b9b4-109">Если метод завершается с ошибкой, возвращает значение S_OK.</span><span class="sxs-lookup"><span data-stu-id="3b9b4-109">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3b9b4-110">Требования</span><span class="sxs-lookup"><span data-stu-id="3b9b4-110">Requirements</span></span>  
 <span data-ttu-id="3b9b4-111">Требуется ALink. h.</span><span class="sxs-lookup"><span data-stu-id="3b9b4-111">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b9b4-112">См. также</span><span class="sxs-lookup"><span data-stu-id="3b9b4-112">See also</span></span>

- [<span data-ttu-id="3b9b4-113">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="3b9b4-113">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="3b9b4-114">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="3b9b4-114">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="3b9b4-115">API ALink</span><span class="sxs-lookup"><span data-stu-id="3b9b4-115">ALink API</span></span>](index.md)

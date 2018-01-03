---
title: "Метод PreCloseAssembly"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IALink.PreCloseAssembly
api_location: alink.dll
api_type: COM
f1_keywords: PreCloseAssembly
helpviewer_keywords: PreCloseAssembly method
ms.assetid: 6d23ac54-15ea-4027-a172-9ebef43e8f56
topic_type: apiref
caps.latest.revision: "6"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5a4d1f2eed036552ab17b6768b7b2d84f4a52c9c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="precloseassembly-method"></a><span data-ttu-id="13b88-102">Метод PreCloseAssembly</span><span class="sxs-lookup"><span data-stu-id="13b88-102">PreCloseAssembly Method</span></span>
<span data-ttu-id="13b88-103">Закрывает файл сборки.</span><span class="sxs-lookup"><span data-stu-id="13b88-103">Closes the assembly file.</span></span> <span data-ttu-id="13b88-104">Этот метод следует вызывайте после закрытия всех файлов, но до закрытия файла сборки.</span><span class="sxs-lookup"><span data-stu-id="13b88-104">Call this method after closing all other files, but before closing the assembly file.</span></span> <span data-ttu-id="13b88-105">Не вызывайте этот метод для несвязанных модулей.</span><span class="sxs-lookup"><span data-stu-id="13b88-105">Do not call this method for unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="13b88-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="13b88-106">Syntax</span></span>  
  
```  
HRESULT PreCloseAssembly(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="13b88-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="13b88-107">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="13b88-108">Идентификатор сборки.</span><span class="sxs-lookup"><span data-stu-id="13b88-108">ID of the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="13b88-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="13b88-109">Return Value</span></span>  
 <span data-ttu-id="13b88-110">Возвращает значение S_OK, если метод выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="13b88-110">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="13b88-111">Требования</span><span class="sxs-lookup"><span data-stu-id="13b88-111">Requirements</span></span>  
 <span data-ttu-id="13b88-112">Требуется alink.h.</span><span class="sxs-lookup"><span data-stu-id="13b88-112">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13b88-113">См. также</span><span class="sxs-lookup"><span data-stu-id="13b88-113">See Also</span></span>  
 [<span data-ttu-id="13b88-114">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="13b88-114">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="13b88-115">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="13b88-115">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="13b88-116">API ALink</span><span class="sxs-lookup"><span data-stu-id="13b88-116">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)

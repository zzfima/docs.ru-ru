---
title: "Метод SetNonAssemblyFlags"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IALink.SetNonAssemblyFlags
api_location: alink.dll
api_type: COM
f1_keywords: SetNonAssemblyFlags
helpviewer_keywords: SetNonAssemblyFlags method
ms.assetid: f8ba6fc8-f5aa-4066-ac96-56332758f5ec
topic_type: apiref
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: c5f8761259e89b4befd0eeaf893ffbe5d4142350
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="setnonassemblyflags-method"></a><span data-ttu-id="c65b9-102">Метод SetNonAssemblyFlags</span><span class="sxs-lookup"><span data-stu-id="c65b9-102">SetNonAssemblyFlags Method</span></span>
<span data-ttu-id="c65b9-103">Задает флаги, не зависящие от сборки.</span><span class="sxs-lookup"><span data-stu-id="c65b9-103">Sets flags that are not assembly-specific.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c65b9-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c65b9-104">Syntax</span></span>  
  
```  
HRESULT SetNonAssemblyFlags(  
    AssemblyFlags afFlags  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c65b9-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c65b9-105">Parameters</span></span>  
 `afFlags`  
 <span data-ttu-id="c65b9-106">Флаги ALink.</span><span class="sxs-lookup"><span data-stu-id="c65b9-106">ALink flags.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c65b9-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="c65b9-107">Return Value</span></span>  
 <span data-ttu-id="c65b9-108">Возвращает значение S_OK, если метод выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="c65b9-108">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c65b9-109">Требования</span><span class="sxs-lookup"><span data-stu-id="c65b9-109">Requirements</span></span>  
 <span data-ttu-id="c65b9-110">Требуется alink.h</span><span class="sxs-lookup"><span data-stu-id="c65b9-110">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c65b9-111">См. также</span><span class="sxs-lookup"><span data-stu-id="c65b9-111">See Also</span></span>  
 [<span data-ttu-id="c65b9-112">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="c65b9-112">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="c65b9-113">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="c65b9-113">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="c65b9-114">ALink-интерфейс API</span><span class="sxs-lookup"><span data-stu-id="c65b9-114">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)

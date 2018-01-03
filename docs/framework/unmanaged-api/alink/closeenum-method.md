---
title: "Метод CloseEnum"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- CloseEnum
- IALink.CloseEnum
api_location: alink.dll
api_type: COM
f1_keywords: CloseEnum
helpviewer_keywords: CloseEnum method
ms.assetid: aa4a091e-13fe-4264-91de-e12f1c767c87
topic_type: apiref
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 89f5b7069af0bfdfd732ed1ab4935771a565a20f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="closeenum-method"></a><span data-ttu-id="cc048-102">Метод CloseEnum</span><span class="sxs-lookup"><span data-stu-id="cc048-102">CloseEnum Method</span></span>
<span data-ttu-id="cc048-103">Закрывает указанное перечисление и освобождает связанные ресурсы.</span><span class="sxs-lookup"><span data-stu-id="cc048-103">Closes the indicated enumeration and frees associated resources.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cc048-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cc048-104">Syntax</span></span>  
  
```  
HRESULT CloseEnum(  
    HALINKENUM hEnum  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="cc048-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="cc048-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="cc048-106">Дескриптор перечисления должен быть закрыт.</span><span class="sxs-lookup"><span data-stu-id="cc048-106">Handle of enumeration to be closed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cc048-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="cc048-107">Return Value</span></span>  
 <span data-ttu-id="cc048-108">Возвращает значение S_OK, если метод выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="cc048-108">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cc048-109">Требования</span><span class="sxs-lookup"><span data-stu-id="cc048-109">Requirements</span></span>  
 <span data-ttu-id="cc048-110">Требуется alink.h</span><span class="sxs-lookup"><span data-stu-id="cc048-110">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc048-111">См. также</span><span class="sxs-lookup"><span data-stu-id="cc048-111">See Also</span></span>  
 [<span data-ttu-id="cc048-112">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="cc048-112">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="cc048-113">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="cc048-113">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="cc048-114">API ALink</span><span class="sxs-lookup"><span data-stu-id="cc048-114">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)

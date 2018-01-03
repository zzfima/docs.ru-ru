---
title: "Метод EndMerge"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IALink.EndMerge
- EndMerge
api_location: alink.dll
api_type: COM
f1_keywords: EndMerge
helpviewer_keywords: EndMerge method
ms.assetid: 1d03bb15-a2c8-4a04-8fc6-b126c89c3778
topic_type: apiref
caps.latest.revision: "5"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 58e9cecae43fb69f1ce2e90eb9d6551d287ca7b3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="endmerge-method"></a><span data-ttu-id="5d16a-102">Метод EndMerge</span><span class="sxs-lookup"><span data-stu-id="5d16a-102">EndMerge Method</span></span>
<span data-ttu-id="5d16a-103">Указывает, что все настраиваемые атрибуты были объединены в область выдачи.</span><span class="sxs-lookup"><span data-stu-id="5d16a-103">Indicates that all custom attributes have been merged into the emit scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5d16a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5d16a-104">Syntax</span></span>  
  
```  
HRESULT EndMerge(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5d16a-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="5d16a-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="5d16a-106">Идентификатор сборки.</span><span class="sxs-lookup"><span data-stu-id="5d16a-106">ID of the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5d16a-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="5d16a-107">Return Value</span></span>  
 <span data-ttu-id="5d16a-108">Возвращает значение S_OK, если метод выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="5d16a-108">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5d16a-109">Требования</span><span class="sxs-lookup"><span data-stu-id="5d16a-109">Requirements</span></span>  
 <span data-ttu-id="5d16a-110">Требуется alink.h</span><span class="sxs-lookup"><span data-stu-id="5d16a-110">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d16a-111">См. также</span><span class="sxs-lookup"><span data-stu-id="5d16a-111">See Also</span></span>  
 [<span data-ttu-id="5d16a-112">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="5d16a-112">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="5d16a-113">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="5d16a-113">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="5d16a-114">API ALink</span><span class="sxs-lookup"><span data-stu-id="5d16a-114">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)

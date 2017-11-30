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
ms.openlocfilehash: 7f29abf03c636fc552fe550534ca1b1395b43aae
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="endmerge-method"></a><span data-ttu-id="d7a9b-102">Метод EndMerge</span><span class="sxs-lookup"><span data-stu-id="d7a9b-102">EndMerge Method</span></span>
<span data-ttu-id="d7a9b-103">Указывает, что все настраиваемые атрибуты были объединены в область выдачи.</span><span class="sxs-lookup"><span data-stu-id="d7a9b-103">Indicates that all custom attributes have been merged into the emit scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d7a9b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d7a9b-104">Syntax</span></span>  
  
```  
HRESULT EndMerge(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d7a9b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="d7a9b-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="d7a9b-106">Идентификатор сборки.</span><span class="sxs-lookup"><span data-stu-id="d7a9b-106">ID of the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d7a9b-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="d7a9b-107">Return Value</span></span>  
 <span data-ttu-id="d7a9b-108">Возвращает значение S_OK, если метод выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="d7a9b-108">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d7a9b-109">Требования</span><span class="sxs-lookup"><span data-stu-id="d7a9b-109">Requirements</span></span>  
 <span data-ttu-id="d7a9b-110">Требуется alink.h</span><span class="sxs-lookup"><span data-stu-id="d7a9b-110">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7a9b-111">См. также</span><span class="sxs-lookup"><span data-stu-id="d7a9b-111">See Also</span></span>  
 [<span data-ttu-id="d7a9b-112">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="d7a9b-112">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="d7a9b-113">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="d7a9b-113">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="d7a9b-114">ALink-интерфейс API</span><span class="sxs-lookup"><span data-stu-id="d7a9b-114">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)

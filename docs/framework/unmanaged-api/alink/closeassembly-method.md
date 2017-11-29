---
title: "Метод CloseAssembly"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IALink.CloseAssembly
- CloseAssembly
api_location: alink.dll
api_type: COM
f1_keywords: CloseAssembly
helpviewer_keywords: CloseAssembly method
ms.assetid: f66a43bc-a5c5-4190-acbe-63fd27640634
topic_type: apiref
caps.latest.revision: "6"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: be68348b619f342eca4841a6052088bf7152f453
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="closeassembly-method"></a><span data-ttu-id="3a165-102">Метод CloseAssembly</span><span class="sxs-lookup"><span data-stu-id="3a165-102">CloseAssembly Method</span></span>
<span data-ttu-id="3a165-103">Завершает операции сборки.</span><span class="sxs-lookup"><span data-stu-id="3a165-103">Finalizes assembly operations.</span></span> <span data-ttu-id="3a165-104">Этот метод следует вызывайте до начала новой сборки или непривязанного модуля.</span><span class="sxs-lookup"><span data-stu-id="3a165-104">Call this method before beginning a new assembly or unbound module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3a165-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3a165-105">Syntax</span></span>  
  
```  
HRESULT CloseAssembly(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3a165-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="3a165-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="3a165-107">Идентификатор сборки.</span><span class="sxs-lookup"><span data-stu-id="3a165-107">ID of the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3a165-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="3a165-108">Return Value</span></span>  
 <span data-ttu-id="3a165-109">Возвращает значение S_OK, если метод выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="3a165-109">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3a165-110">Требования</span><span class="sxs-lookup"><span data-stu-id="3a165-110">Requirements</span></span>  
 <span data-ttu-id="3a165-111">Требуется alink.h.</span><span class="sxs-lookup"><span data-stu-id="3a165-111">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a165-112">См. также</span><span class="sxs-lookup"><span data-stu-id="3a165-112">See Also</span></span>  
 [<span data-ttu-id="3a165-113">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="3a165-113">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="3a165-114">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="3a165-114">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="3a165-115">ALink-интерфейс API</span><span class="sxs-lookup"><span data-stu-id="3a165-115">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)

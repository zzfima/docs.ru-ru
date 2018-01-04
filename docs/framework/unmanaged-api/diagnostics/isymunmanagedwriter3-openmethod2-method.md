---
title: "Метод ISymUnmanagedWriter3::OpenMethod2"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedWriter3.OpenMethod2
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedWriter3::OpenMethod2
helpviewer_keywords:
- ISymUnmanagedWriter3::OpenMethod2 method [.NET Framework debugging]
- OpenMethod2 method [.NET Framework debugging]
ms.assetid: 025e358c-448f-4423-a2f2-57acf437c8a5
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8da6de0271ddce5b956e667420a206c09cc291d8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedwriter3openmethod2-method"></a><span data-ttu-id="b9096-102">Метод ISymUnmanagedWriter3::OpenMethod2</span><span class="sxs-lookup"><span data-stu-id="b9096-102">ISymUnmanagedWriter3::OpenMethod2 Method</span></span>
<span data-ttu-id="b9096-103">Открывает метод и предоставляет его фактическое смещение раздела в образе.</span><span class="sxs-lookup"><span data-stu-id="b9096-103">Opens a method and provides its real section offset in the image.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b9096-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b9096-104">Syntax</span></span>  
  
```  
HRESULT OpenMethod2(   
    [in] mdMethodDef method,  
    [in] ULONG32 isect,  
    [in] ULONG32 offset);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b9096-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="b9096-105">Parameters</span></span>  
 `method`  
 <span data-ttu-id="b9096-106">[in] Токен метаданных для открываемого метода.</span><span class="sxs-lookup"><span data-stu-id="b9096-106">[in] The metadata token for the method to be opened.</span></span>  
  
 `isect`  
 <span data-ttu-id="b9096-107">[in] Смещение раздела в образе.</span><span class="sxs-lookup"><span data-stu-id="b9096-107">[in] The section offset in the image.</span></span>  
  
 `offset`  
 <span data-ttu-id="b9096-108">[in] Смещение в образе.</span><span class="sxs-lookup"><span data-stu-id="b9096-108">[in] The offset in the image.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b9096-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="b9096-109">Return Value</span></span>  
 <span data-ttu-id="b9096-110">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="b9096-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b9096-111">Требования</span><span class="sxs-lookup"><span data-stu-id="b9096-111">Requirements</span></span>  
 <span data-ttu-id="b9096-112">**Заголовок:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="b9096-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9096-113">См. также</span><span class="sxs-lookup"><span data-stu-id="b9096-113">See Also</span></span>  
 [<span data-ttu-id="b9096-114">Интерфейс ISymUnmanagedWriter3</span><span class="sxs-lookup"><span data-stu-id="b9096-114">ISymUnmanagedWriter3 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-interface.md)  
 [<span data-ttu-id="b9096-115">Метод OpenMethod</span><span class="sxs-lookup"><span data-stu-id="b9096-115">OpenMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openmethod-method.md)

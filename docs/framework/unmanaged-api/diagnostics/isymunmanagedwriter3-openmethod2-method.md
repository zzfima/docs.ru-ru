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
ms.openlocfilehash: 1124eac951e32dbf1cedb7926f582ec6abb99007
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="isymunmanagedwriter3openmethod2-method"></a><span data-ttu-id="42fcb-102">Метод ISymUnmanagedWriter3::OpenMethod2</span><span class="sxs-lookup"><span data-stu-id="42fcb-102">ISymUnmanagedWriter3::OpenMethod2 Method</span></span>
<span data-ttu-id="42fcb-103">Открывает метод и предоставляет его фактическое смещение раздела в образе.</span><span class="sxs-lookup"><span data-stu-id="42fcb-103">Opens a method and provides its real section offset in the image.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="42fcb-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="42fcb-104">Syntax</span></span>  
  
```  
HRESULT OpenMethod2(   
    [in] mdMethodDef method,  
    [in] ULONG32 isect,  
    [in] ULONG32 offset);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="42fcb-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="42fcb-105">Parameters</span></span>  
 `method`  
 <span data-ttu-id="42fcb-106">[in] Токен метаданных для открываемого метода.</span><span class="sxs-lookup"><span data-stu-id="42fcb-106">[in] The metadata token for the method to be opened.</span></span>  
  
 `isect`  
 <span data-ttu-id="42fcb-107">[in] Смещение раздела в образе.</span><span class="sxs-lookup"><span data-stu-id="42fcb-107">[in] The section offset in the image.</span></span>  
  
 `offset`  
 <span data-ttu-id="42fcb-108">[in] Смещение в образе.</span><span class="sxs-lookup"><span data-stu-id="42fcb-108">[in] The offset in the image.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="42fcb-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="42fcb-109">Return Value</span></span>  
 <span data-ttu-id="42fcb-110">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="42fcb-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="42fcb-111">Требования</span><span class="sxs-lookup"><span data-stu-id="42fcb-111">Requirements</span></span>  
 <span data-ttu-id="42fcb-112">**Заголовок:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="42fcb-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42fcb-113">См. также</span><span class="sxs-lookup"><span data-stu-id="42fcb-113">See Also</span></span>  
 [<span data-ttu-id="42fcb-114">Isymunmanagedwriter3-интерфейс</span><span class="sxs-lookup"><span data-stu-id="42fcb-114">ISymUnmanagedWriter3 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-interface.md)  
 [<span data-ttu-id="42fcb-115">Метод OpenMethod</span><span class="sxs-lookup"><span data-stu-id="42fcb-115">OpenMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openmethod-method.md)

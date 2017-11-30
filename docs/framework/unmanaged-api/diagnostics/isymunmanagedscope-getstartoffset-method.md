---
title: "Метод ISymUnmanagedScope::GetStartOffset"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedScope.GetStartOffset
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedScope::GetStartOffset
helpviewer_keywords:
- GetStartOffset method, ISymUnmanagedScope interface [.NET Framework debugging]
- ISymUnmanagedScope::GetStartOffset method [.NET Framework debugging]
ms.assetid: da6bbc75-94d1-4354-9722-0d455b4428fb
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 8e24924607cad1922f2d1b5a816dc635eb6c7820
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="isymunmanagedscopegetstartoffset-method"></a><span data-ttu-id="5ce53-102">Метод ISymUnmanagedScope::GetStartOffset</span><span class="sxs-lookup"><span data-stu-id="5ce53-102">ISymUnmanagedScope::GetStartOffset Method</span></span>
<span data-ttu-id="5ce53-103">Возвращает начальное смещение для этой области.</span><span class="sxs-lookup"><span data-stu-id="5ce53-103">Gets the start offset for this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5ce53-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5ce53-104">Syntax</span></span>  
  
```  
HRESULT GetStartOffset(  
    [out, retval] ULONG32* pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5ce53-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="5ce53-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="5ce53-106">[out] Указатель на `ULONG32` , содержащий начальное смещение.</span><span class="sxs-lookup"><span data-stu-id="5ce53-106">[out] A pointer to a `ULONG32` that contains the starting offset.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5ce53-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="5ce53-107">Return Value</span></span>  
 <span data-ttu-id="5ce53-108">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="5ce53-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5ce53-109">Требования</span><span class="sxs-lookup"><span data-stu-id="5ce53-109">Requirements</span></span>  
 <span data-ttu-id="5ce53-110">**Заголовок:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="5ce53-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ce53-111">См. также</span><span class="sxs-lookup"><span data-stu-id="5ce53-111">See Also</span></span>  
 [<span data-ttu-id="5ce53-112">ISymUnmanagedScope-интерфейс</span><span class="sxs-lookup"><span data-stu-id="5ce53-112">ISymUnmanagedScope Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)  
 [<span data-ttu-id="5ce53-113">Метод GetEndOffset</span><span class="sxs-lookup"><span data-stu-id="5ce53-113">GetEndOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getendoffset-method.md)

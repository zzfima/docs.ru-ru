---
title: Метод ISymUnmanagedScope::GetStartOffset
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope.GetStartOffset
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope::GetStartOffset
helpviewer_keywords:
- GetStartOffset method, ISymUnmanagedScope interface [.NET Framework debugging]
- ISymUnmanagedScope::GetStartOffset method [.NET Framework debugging]
ms.assetid: da6bbc75-94d1-4354-9722-0d455b4428fb
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2b81ac93c67d59c294f22eb825527fa9982d9124
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54721101"
---
# <a name="isymunmanagedscopegetstartoffset-method"></a><span data-ttu-id="fe5e0-102">Метод ISymUnmanagedScope::GetStartOffset</span><span class="sxs-lookup"><span data-stu-id="fe5e0-102">ISymUnmanagedScope::GetStartOffset Method</span></span>
<span data-ttu-id="fe5e0-103">Возвращает начальное смещение для этой области.</span><span class="sxs-lookup"><span data-stu-id="fe5e0-103">Gets the start offset for this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fe5e0-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fe5e0-104">Syntax</span></span>  
  
```  
HRESULT GetStartOffset(  
    [out, retval] ULONG32* pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="fe5e0-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="fe5e0-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="fe5e0-106">[out] Указатель на `ULONG32` , содержащий начальное смещение.</span><span class="sxs-lookup"><span data-stu-id="fe5e0-106">[out] A pointer to a `ULONG32` that contains the starting offset.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fe5e0-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="fe5e0-107">Return Value</span></span>  
 <span data-ttu-id="fe5e0-108">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="fe5e0-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fe5e0-109">Требования</span><span class="sxs-lookup"><span data-stu-id="fe5e0-109">Requirements</span></span>  
 <span data-ttu-id="fe5e0-110">**Заголовок.** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="fe5e0-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe5e0-111">См. также</span><span class="sxs-lookup"><span data-stu-id="fe5e0-111">See also</span></span>
- [<span data-ttu-id="fe5e0-112">Интерфейс ISymUnmanagedScope</span><span class="sxs-lookup"><span data-stu-id="fe5e0-112">ISymUnmanagedScope Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)
- [<span data-ttu-id="fe5e0-113">Метод GetEndOffset</span><span class="sxs-lookup"><span data-stu-id="fe5e0-113">GetEndOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getendoffset-method.md)

---
title: Метод ISymUnmanagedScope2::GetConstantCount
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope2.GetConstantCount
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope2::GetConstantCount
helpviewer_keywords:
- ISymUnmanagedScope2::GetConstantCount method [.NET Framework debugging]
- GetConstantCount method [.NET Framework debugging]
ms.assetid: 1e1f0be6-c4e8-4d6c-98cd-d5fa9f686e87
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d1dfc9ead6256ae700d5e619da4fae5745bdd759
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57485163"
---
# <a name="isymunmanagedscope2getconstantcount-method"></a><span data-ttu-id="b8830-102">Метод ISymUnmanagedScope2::GetConstantCount</span><span class="sxs-lookup"><span data-stu-id="b8830-102">ISymUnmanagedScope2::GetConstantCount Method</span></span>
<span data-ttu-id="b8830-103">Получает число констант, определенных в этой области.</span><span class="sxs-lookup"><span data-stu-id="b8830-103">Gets a count of the constants defined within this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b8830-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b8830-104">Syntax</span></span>  
  
```  
HRESULT GetConstantCount(  
    [out, retval] ULONG32 *pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b8830-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="b8830-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="b8830-106">[out] Указатель на `ULONG32` размер, который получает в символах, буфера, требуемого для хранения констант.</span><span class="sxs-lookup"><span data-stu-id="b8830-106">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the constants.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b8830-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="b8830-107">Return Value</span></span>  
 <span data-ttu-id="b8830-108">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="b8830-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b8830-109">Требования</span><span class="sxs-lookup"><span data-stu-id="b8830-109">Requirements</span></span>  
 <span data-ttu-id="b8830-110">**Заголовок.** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="b8830-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8830-111">См. также</span><span class="sxs-lookup"><span data-stu-id="b8830-111">See also</span></span>
- [<span data-ttu-id="b8830-112">Интерфейс ISymUnmanagedScope2</span><span class="sxs-lookup"><span data-stu-id="b8830-112">ISymUnmanagedScope2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope2-interface.md)

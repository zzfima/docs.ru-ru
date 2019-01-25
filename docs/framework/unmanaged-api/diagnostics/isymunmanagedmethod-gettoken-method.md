---
title: Метод ISymUnmanagedMethod::GetToken
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod.GetToken
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod::GetToken
helpviewer_keywords:
- ISymUnmanagedMethod::GetToken method [.NET Framework debugging]
- GetToken method, ISymUnmanagedMethod interface [.NET Framework debugging]
ms.assetid: 4effbe95-c36e-4a45-8b2a-ee21339415fb
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7e276e93bc1b05dd34e1111cc53c880f8836bf09
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54494890"
---
# <a name="isymunmanagedmethodgettoken-method"></a><span data-ttu-id="8c85a-102">Метод ISymUnmanagedMethod::GetToken</span><span class="sxs-lookup"><span data-stu-id="8c85a-102">ISymUnmanagedMethod::GetToken Method</span></span>
<span data-ttu-id="8c85a-103">Возвращает маркер метаданных для этого метода.</span><span class="sxs-lookup"><span data-stu-id="8c85a-103">Returns the metadata token for this method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8c85a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8c85a-104">Syntax</span></span>  
  
```  
HRESULT GetToken(  
   [out, retval]  mdMethodDef  *pToken);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8c85a-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="8c85a-105">Parameters</span></span>  
 `pToken`  
 <span data-ttu-id="8c85a-106">[out] Указатель на `mdMethodDef` размер, который получает в символах, буфера, требуемого для хранения метаданных.</span><span class="sxs-lookup"><span data-stu-id="8c85a-106">[out] A pointer to a `mdMethodDef` that receives the size, in characters, of the buffer required to contain the metadata.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8c85a-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="8c85a-107">Return Value</span></span>  
 <span data-ttu-id="8c85a-108">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="8c85a-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8c85a-109">Требования</span><span class="sxs-lookup"><span data-stu-id="8c85a-109">Requirements</span></span>  
 <span data-ttu-id="8c85a-110">**Заголовок.** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="8c85a-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c85a-111">См. также</span><span class="sxs-lookup"><span data-stu-id="8c85a-111">See also</span></span>
- [<span data-ttu-id="8c85a-112">Интерфейс ISymUnmanagedMethod</span><span class="sxs-lookup"><span data-stu-id="8c85a-112">ISymUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)

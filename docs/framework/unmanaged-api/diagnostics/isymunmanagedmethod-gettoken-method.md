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
ms.openlocfilehash: 1bb9a444d8e8b674d1f173214d8bac427f24e408
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67759404"
---
# <a name="isymunmanagedmethodgettoken-method"></a><span data-ttu-id="71873-102">Метод ISymUnmanagedMethod::GetToken</span><span class="sxs-lookup"><span data-stu-id="71873-102">ISymUnmanagedMethod::GetToken Method</span></span>
<span data-ttu-id="71873-103">Возвращает маркер метаданных для этого метода.</span><span class="sxs-lookup"><span data-stu-id="71873-103">Returns the metadata token for this method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="71873-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="71873-104">Syntax</span></span>  
  
```cpp  
HRESULT GetToken(  
   [out, retval]  mdMethodDef  *pToken);  
```  
  
## <a name="parameters"></a><span data-ttu-id="71873-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="71873-105">Parameters</span></span>  
 `pToken`  
 <span data-ttu-id="71873-106">[out] Указатель на `mdMethodDef` размер, который получает в символах, буфера, требуемого для хранения метаданных.</span><span class="sxs-lookup"><span data-stu-id="71873-106">[out] A pointer to a `mdMethodDef` that receives the size, in characters, of the buffer required to contain the metadata.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="71873-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="71873-107">Return Value</span></span>  
 <span data-ttu-id="71873-108">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="71873-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="71873-109">Требования</span><span class="sxs-lookup"><span data-stu-id="71873-109">Requirements</span></span>  
 <span data-ttu-id="71873-110">**Заголовок.** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="71873-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71873-111">См. также</span><span class="sxs-lookup"><span data-stu-id="71873-111">See also</span></span>

- [<span data-ttu-id="71873-112">Интерфейс ISymUnmanagedMethod</span><span class="sxs-lookup"><span data-stu-id="71873-112">ISymUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)

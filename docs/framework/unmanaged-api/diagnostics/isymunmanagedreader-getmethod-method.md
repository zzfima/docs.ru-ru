---
title: Метод ISymUnmanagedReader::GetMethod
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetMethod
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetMethod
helpviewer_keywords:
- GetMethod method, ISymUnmanagedReader interface [.NET Framework debugging]
- ISymUnmanagedReader::GetMethod method [.NET Framework debugging]
ms.assetid: ae6cfb29-bc2c-4606-af86-1d32ebd31020
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e9f1056d8d5ec4486e748d3b079507943a8a72ef
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="isymunmanagedreadergetmethod-method"></a><span data-ttu-id="1f8d0-102">Метод ISymUnmanagedReader::GetMethod</span><span class="sxs-lookup"><span data-stu-id="1f8d0-102">ISymUnmanagedReader::GetMethod Method</span></span>
<span data-ttu-id="1f8d0-103">Возвращает метод средства чтения символов, маркер метода.</span><span class="sxs-lookup"><span data-stu-id="1f8d0-103">Gets a symbol reader method, given a method token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1f8d0-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1f8d0-104">Syntax</span></span>  
  
```  
HRESULT GetMethod (  
    [in]  mdMethodDef  token,  
    [out, retval] ISymUnmanagedMethod**  pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1f8d0-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="1f8d0-105">Parameters</span></span>  
 `token`  
 <span data-ttu-id="1f8d0-106">[in] Маркер метода.</span><span class="sxs-lookup"><span data-stu-id="1f8d0-106">[in] The method token.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="1f8d0-107">[out] Указатель на возвращенный интерфейс.</span><span class="sxs-lookup"><span data-stu-id="1f8d0-107">[out] A pointer to the returned interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1f8d0-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="1f8d0-108">Return Value</span></span>  
 <span data-ttu-id="1f8d0-109">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="1f8d0-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1f8d0-110">Требования</span><span class="sxs-lookup"><span data-stu-id="1f8d0-110">Requirements</span></span>  
 <span data-ttu-id="1f8d0-111">**Заголовок:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="1f8d0-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f8d0-112">См. также</span><span class="sxs-lookup"><span data-stu-id="1f8d0-112">See Also</span></span>  
 [<span data-ttu-id="1f8d0-113">Интерфейс ISymUnmanagedReader</span><span class="sxs-lookup"><span data-stu-id="1f8d0-113">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)

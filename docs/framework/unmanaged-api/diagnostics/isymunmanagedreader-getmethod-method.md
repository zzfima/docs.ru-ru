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
ms.openlocfilehash: deb5d7aa24cf750a9584ef2aa32d10816ec12f57
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54614410"
---
# <a name="isymunmanagedreadergetmethod-method"></a><span data-ttu-id="0f71f-102">Метод ISymUnmanagedReader::GetMethod</span><span class="sxs-lookup"><span data-stu-id="0f71f-102">ISymUnmanagedReader::GetMethod Method</span></span>
<span data-ttu-id="0f71f-103">Возвращает метода средства чтения символов, маркер метода.</span><span class="sxs-lookup"><span data-stu-id="0f71f-103">Gets a symbol reader method, given a method token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0f71f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0f71f-104">Syntax</span></span>  
  
```  
HRESULT GetMethod (  
    [in]  mdMethodDef  token,  
    [out, retval] ISymUnmanagedMethod**  pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0f71f-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="0f71f-105">Parameters</span></span>  
 `token`  
 <span data-ttu-id="0f71f-106">[in] Маркер метода.</span><span class="sxs-lookup"><span data-stu-id="0f71f-106">[in] The method token.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="0f71f-107">[out] Указатель на возвращенный интерфейс.</span><span class="sxs-lookup"><span data-stu-id="0f71f-107">[out] A pointer to the returned interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0f71f-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="0f71f-108">Return Value</span></span>  
 <span data-ttu-id="0f71f-109">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="0f71f-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0f71f-110">Требования</span><span class="sxs-lookup"><span data-stu-id="0f71f-110">Requirements</span></span>  
 <span data-ttu-id="0f71f-111">**Заголовок.** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="0f71f-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f71f-112">См. также</span><span class="sxs-lookup"><span data-stu-id="0f71f-112">See also</span></span>
- [<span data-ttu-id="0f71f-113">Интерфейс ISymUnmanagedReader</span><span class="sxs-lookup"><span data-stu-id="0f71f-113">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)

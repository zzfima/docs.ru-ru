---
title: Метод ISymUnmanagedDocument::GetURL
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocument.GetURL
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument::GetURL
helpviewer_keywords:
- GetURL method [.NET Framework debugging]
- ISymUnmanagedDocument::GetURL method [.NET Framework debugging]
ms.assetid: 60600178-c2b5-4cab-b3a5-f0f61acebaf1
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5a447de2bb01e7bbf838ef5443e3ae7951bf8226
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="isymunmanageddocumentgeturl-method"></a><span data-ttu-id="67f44-102">Метод ISymUnmanagedDocument::GetURL</span><span class="sxs-lookup"><span data-stu-id="67f44-102">ISymUnmanagedDocument::GetURL Method</span></span>
<span data-ttu-id="67f44-103">Возвращает универсальный код ресурса URL-адрес для этого документа.</span><span class="sxs-lookup"><span data-stu-id="67f44-103">Returns the uniform resource locator (URL) for this document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="67f44-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="67f44-104">Syntax</span></span>  
  
```  
HRESULT GetURL(  
    [in]  ULONG32  cchUrl,  
    [out] ULONG32  *pcchUrl,  
    [out, size_is(cchUrl), length_is(*pcchUrl)] WCHAR szUrl[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="67f44-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="67f44-105">Parameters</span></span>  
 `cchUrl`  
 <span data-ttu-id="67f44-106">[in] Размер (в символах) для `szURL` буфера.</span><span class="sxs-lookup"><span data-stu-id="67f44-106">[in] The size, in characters, of the `szURL` buffer.</span></span>  
  
 `pcchUrl`  
 <span data-ttu-id="67f44-107">[out] Указатель на переменную, которая получает размер URL-адрес, включая нулем.</span><span class="sxs-lookup"><span data-stu-id="67f44-107">[out] A pointer to a variable that receives the size of the URL, including the null termination.</span></span>  
  
 `szUrl`  
 <span data-ttu-id="67f44-108">[out] Буфер, содержащий URL-адрес.</span><span class="sxs-lookup"><span data-stu-id="67f44-108">[out] The buffer containing the URL.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="67f44-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="67f44-109">Return Value</span></span>  
 <span data-ttu-id="67f44-110">Значение S_OK, если метод выполнен успешно; в противном случае — код ошибки.</span><span class="sxs-lookup"><span data-stu-id="67f44-110">S_OK if the method succeeds; otherwise, an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67f44-111">См. также</span><span class="sxs-lookup"><span data-stu-id="67f44-111">See Also</span></span>  
 [<span data-ttu-id="67f44-112">Интерфейс ISymUnmanagedDocument</span><span class="sxs-lookup"><span data-stu-id="67f44-112">ISymUnmanagedDocument Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)

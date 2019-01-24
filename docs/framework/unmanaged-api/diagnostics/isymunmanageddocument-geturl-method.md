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
ms.openlocfilehash: 9a93ef073d4dd2eaf58c057d4cdf25fa39082e14
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54706330"
---
# <a name="isymunmanageddocumentgeturl-method"></a><span data-ttu-id="af459-102">Метод ISymUnmanagedDocument::GetURL</span><span class="sxs-lookup"><span data-stu-id="af459-102">ISymUnmanagedDocument::GetURL Method</span></span>
<span data-ttu-id="af459-103">Возвращает универсальный код ресурса URL-адрес для этого документа.</span><span class="sxs-lookup"><span data-stu-id="af459-103">Returns the uniform resource locator (URL) for this document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="af459-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="af459-104">Syntax</span></span>  
  
```  
HRESULT GetURL(  
    [in]  ULONG32  cchUrl,  
    [out] ULONG32  *pcchUrl,  
    [out, size_is(cchUrl), length_is(*pcchUrl)] WCHAR szUrl[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="af459-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="af459-105">Parameters</span></span>  
 `cchUrl`  
 <span data-ttu-id="af459-106">[in] Размер в символах, из `szURL` буфера.</span><span class="sxs-lookup"><span data-stu-id="af459-106">[in] The size, in characters, of the `szURL` buffer.</span></span>  
  
 `pcchUrl`  
 <span data-ttu-id="af459-107">[out] Указатель на переменную, которая принимает размер URL-адрес, включая завершающимся нулевым значением.</span><span class="sxs-lookup"><span data-stu-id="af459-107">[out] A pointer to a variable that receives the size of the URL, including the null termination.</span></span>  
  
 `szUrl`  
 <span data-ttu-id="af459-108">[out] Буфер, содержащий URL-адрес.</span><span class="sxs-lookup"><span data-stu-id="af459-108">[out] The buffer containing the URL.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="af459-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="af459-109">Return Value</span></span>  
 <span data-ttu-id="af459-110">Значение S_OK, если метод выполнен успешно; в противном случае — код ошибки.</span><span class="sxs-lookup"><span data-stu-id="af459-110">S_OK if the method succeeds; otherwise, an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af459-111">См. также</span><span class="sxs-lookup"><span data-stu-id="af459-111">See also</span></span>
- [<span data-ttu-id="af459-112">Интерфейс ISymUnmanagedDocument</span><span class="sxs-lookup"><span data-stu-id="af459-112">ISymUnmanagedDocument Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)

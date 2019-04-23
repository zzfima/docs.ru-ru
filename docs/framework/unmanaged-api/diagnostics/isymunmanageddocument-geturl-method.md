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
ms.openlocfilehash: 15b42bb72975fad4c1830a961f83d9e3065d055b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59187464"
---
# <a name="isymunmanageddocumentgeturl-method"></a><span data-ttu-id="627df-102">Метод ISymUnmanagedDocument::GetURL</span><span class="sxs-lookup"><span data-stu-id="627df-102">ISymUnmanagedDocument::GetURL Method</span></span>
<span data-ttu-id="627df-103">Возвращает универсальный код ресурса URL-адрес для этого документа.</span><span class="sxs-lookup"><span data-stu-id="627df-103">Returns the uniform resource locator (URL) for this document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="627df-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="627df-104">Syntax</span></span>  
  
```  
HRESULT GetURL(  
    [in]  ULONG32  cchUrl,  
    [out] ULONG32  *pcchUrl,  
    [out, size_is(cchUrl), length_is(*pcchUrl)] WCHAR szUrl[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="627df-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="627df-105">Parameters</span></span>  
 `cchUrl`  
 <span data-ttu-id="627df-106">[in] Размер в символах, из `szURL` буфера.</span><span class="sxs-lookup"><span data-stu-id="627df-106">[in] The size, in characters, of the `szURL` buffer.</span></span>  
  
 `pcchUrl`  
 <span data-ttu-id="627df-107">[out] Указатель на переменную, которая принимает размер URL-адрес, включая завершающимся нулевым значением.</span><span class="sxs-lookup"><span data-stu-id="627df-107">[out] A pointer to a variable that receives the size of the URL, including the null termination.</span></span>  
  
 `szUrl`  
 <span data-ttu-id="627df-108">[out] Буфер, содержащий URL-адрес.</span><span class="sxs-lookup"><span data-stu-id="627df-108">[out] The buffer containing the URL.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="627df-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="627df-109">Return Value</span></span>  
 <span data-ttu-id="627df-110">Значение S_OK, если метод выполнен успешно; в противном случае — код ошибки.</span><span class="sxs-lookup"><span data-stu-id="627df-110">S_OK if the method succeeds; otherwise, an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="627df-111">См. также</span><span class="sxs-lookup"><span data-stu-id="627df-111">See also</span></span>

- [<span data-ttu-id="627df-112">Интерфейс ISymUnmanagedDocument</span><span class="sxs-lookup"><span data-stu-id="627df-112">ISymUnmanagedDocument Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)

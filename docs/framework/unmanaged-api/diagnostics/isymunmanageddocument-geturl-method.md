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
ms.openlocfilehash: 5d8bc90cc07c2390cc83860b8009a3705f927e80
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67776667"
---
# <a name="isymunmanageddocumentgeturl-method"></a><span data-ttu-id="f89b5-102">Метод ISymUnmanagedDocument::GetURL</span><span class="sxs-lookup"><span data-stu-id="f89b5-102">ISymUnmanagedDocument::GetURL Method</span></span>
<span data-ttu-id="f89b5-103">Возвращает универсальный код ресурса URL-адрес для этого документа.</span><span class="sxs-lookup"><span data-stu-id="f89b5-103">Returns the uniform resource locator (URL) for this document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f89b5-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f89b5-104">Syntax</span></span>  
  
```cpp  
HRESULT GetURL(  
    [in]  ULONG32  cchUrl,  
    [out] ULONG32  *pcchUrl,  
    [out, size_is(cchUrl), length_is(*pcchUrl)] WCHAR szUrl[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f89b5-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="f89b5-105">Parameters</span></span>  
 `cchUrl`  
 <span data-ttu-id="f89b5-106">[in] Размер в символах, из `szURL` буфера.</span><span class="sxs-lookup"><span data-stu-id="f89b5-106">[in] The size, in characters, of the `szURL` buffer.</span></span>  
  
 `pcchUrl`  
 <span data-ttu-id="f89b5-107">[out] Указатель на переменную, которая принимает размер URL-адрес, включая завершающимся нулевым значением.</span><span class="sxs-lookup"><span data-stu-id="f89b5-107">[out] A pointer to a variable that receives the size of the URL, including the null termination.</span></span>  
  
 `szUrl`  
 <span data-ttu-id="f89b5-108">[out] Буфер, содержащий URL-адрес.</span><span class="sxs-lookup"><span data-stu-id="f89b5-108">[out] The buffer containing the URL.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f89b5-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="f89b5-109">Return Value</span></span>  
 <span data-ttu-id="f89b5-110">Значение S_OK, если метод выполнен успешно; в противном случае — код ошибки.</span><span class="sxs-lookup"><span data-stu-id="f89b5-110">S_OK if the method succeeds; otherwise, an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f89b5-111">См. также</span><span class="sxs-lookup"><span data-stu-id="f89b5-111">See also</span></span>

- [<span data-ttu-id="f89b5-112">Интерфейс ISymUnmanagedDocument</span><span class="sxs-lookup"><span data-stu-id="f89b5-112">ISymUnmanagedDocument Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)

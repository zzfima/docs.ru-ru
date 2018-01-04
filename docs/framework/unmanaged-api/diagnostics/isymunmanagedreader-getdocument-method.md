---
title: "Метод ISymUnmanagedReader::GetDocument"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedReader.GetDocument
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedReader::GetDocument
helpviewer_keywords:
- ISymUnmanagedReader::GetDocument method [.NET Framework debugging]
- GetDocument method [.NET Framework debugging]
ms.assetid: bb203853-6a6d-4027-b9e9-603a7f28b9d3
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 00ded0e7e88cacbcedb66e1cef27e4f5eaaf4d29
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedreadergetdocument-method"></a><span data-ttu-id="fd7a0-102">Метод ISymUnmanagedReader::GetDocument</span><span class="sxs-lookup"><span data-stu-id="fd7a0-102">ISymUnmanagedReader::GetDocument Method</span></span>
<span data-ttu-id="fd7a0-103">Обнаружен документ.</span><span class="sxs-lookup"><span data-stu-id="fd7a0-103">Finds a document.</span></span> <span data-ttu-id="fd7a0-104">Язык документа, поставщик и тип являются необязательными.</span><span class="sxs-lookup"><span data-stu-id="fd7a0-104">The document language, vendor, and type are optional.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fd7a0-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fd7a0-105">Syntax</span></span>  
  
```  
HRESULT GetDocument (  
    [in]  WCHAR  *url,  
    [in]  GUID   language,  
    [in]  GUID   languageVendor,  
    [in]  GUID   documentType,  
    [out, retval] ISymUnmanagedDocument** pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="fd7a0-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="fd7a0-106">Parameters</span></span>  
 `url`  
 <span data-ttu-id="fd7a0-107">[in] URL-адрес для идентификации документа.</span><span class="sxs-lookup"><span data-stu-id="fd7a0-107">[in] The URL that identifies the document.</span></span>  
  
 `language`  
 <span data-ttu-id="fd7a0-108">[in] Язык документа.</span><span class="sxs-lookup"><span data-stu-id="fd7a0-108">[in] The document language.</span></span> <span data-ttu-id="fd7a0-109">Этот параметр является необязательным.</span><span class="sxs-lookup"><span data-stu-id="fd7a0-109">This parameter is optional.</span></span>  
  
 `languageVendor`  
 <span data-ttu-id="fd7a0-110">[in] Удостоверение поставщика языка документа.</span><span class="sxs-lookup"><span data-stu-id="fd7a0-110">[in] The identity of the vendor for the document language.</span></span> <span data-ttu-id="fd7a0-111">Этот параметр является необязательным.</span><span class="sxs-lookup"><span data-stu-id="fd7a0-111">This parameter is optional.</span></span>  
  
 `documentType`  
 <span data-ttu-id="fd7a0-112">[in] Тип документа.</span><span class="sxs-lookup"><span data-stu-id="fd7a0-112">[in] The type of the document.</span></span> <span data-ttu-id="fd7a0-113">Этот параметр является необязательным.</span><span class="sxs-lookup"><span data-stu-id="fd7a0-113">This parameter is optional.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="fd7a0-114">[out] Указатель на возвращенный интерфейс.</span><span class="sxs-lookup"><span data-stu-id="fd7a0-114">[out] A pointer to the returned interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fd7a0-115">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="fd7a0-115">Return Value</span></span>  
 <span data-ttu-id="fd7a0-116">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="fd7a0-116">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fd7a0-117">Требования</span><span class="sxs-lookup"><span data-stu-id="fd7a0-117">Requirements</span></span>  
 <span data-ttu-id="fd7a0-118">**Заголовок:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="fd7a0-118">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd7a0-119">См. также</span><span class="sxs-lookup"><span data-stu-id="fd7a0-119">See Also</span></span>  
 [<span data-ttu-id="fd7a0-120">Интерфейс ISymUnmanagedReader</span><span class="sxs-lookup"><span data-stu-id="fd7a0-120">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)

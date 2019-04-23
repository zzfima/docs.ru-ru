---
title: Метод ISymUnmanagedReader::GetDocument
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetDocument
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetDocument
helpviewer_keywords:
- ISymUnmanagedReader::GetDocument method [.NET Framework debugging]
- GetDocument method [.NET Framework debugging]
ms.assetid: bb203853-6a6d-4027-b9e9-603a7f28b9d3
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2a173c23ea33532f05e30d072677715e15d04018
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59093688"
---
# <a name="isymunmanagedreadergetdocument-method"></a><span data-ttu-id="989d0-102">Метод ISymUnmanagedReader::GetDocument</span><span class="sxs-lookup"><span data-stu-id="989d0-102">ISymUnmanagedReader::GetDocument Method</span></span>
<span data-ttu-id="989d0-103">Находит документ.</span><span class="sxs-lookup"><span data-stu-id="989d0-103">Finds a document.</span></span> <span data-ttu-id="989d0-104">Документ языка, поставщика и тип являются необязательными.</span><span class="sxs-lookup"><span data-stu-id="989d0-104">The document language, vendor, and type are optional.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="989d0-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="989d0-105">Syntax</span></span>  
  
```  
HRESULT GetDocument (  
    [in]  WCHAR  *url,  
    [in]  GUID   language,  
    [in]  GUID   languageVendor,  
    [in]  GUID   documentType,  
    [out, retval] ISymUnmanagedDocument** pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="989d0-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="989d0-106">Parameters</span></span>  
 `url`  
 <span data-ttu-id="989d0-107">[in] URL-адрес для идентификации документа.</span><span class="sxs-lookup"><span data-stu-id="989d0-107">[in] The URL that identifies the document.</span></span>  
  
 `language`  
 <span data-ttu-id="989d0-108">[in] Язык документа.</span><span class="sxs-lookup"><span data-stu-id="989d0-108">[in] The document language.</span></span> <span data-ttu-id="989d0-109">Этот параметр является необязательным.</span><span class="sxs-lookup"><span data-stu-id="989d0-109">This parameter is optional.</span></span>  
  
 `languageVendor`  
 <span data-ttu-id="989d0-110">[in] Идентификатор поставщика языка документа.</span><span class="sxs-lookup"><span data-stu-id="989d0-110">[in] The identity of the vendor for the document language.</span></span> <span data-ttu-id="989d0-111">Этот параметр является необязательным.</span><span class="sxs-lookup"><span data-stu-id="989d0-111">This parameter is optional.</span></span>  
  
 `documentType`  
 <span data-ttu-id="989d0-112">[in] Тип документа.</span><span class="sxs-lookup"><span data-stu-id="989d0-112">[in] The type of the document.</span></span> <span data-ttu-id="989d0-113">Этот параметр является необязательным.</span><span class="sxs-lookup"><span data-stu-id="989d0-113">This parameter is optional.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="989d0-114">[out] Указатель на возвращенный интерфейс.</span><span class="sxs-lookup"><span data-stu-id="989d0-114">[out] A pointer to the returned interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="989d0-115">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="989d0-115">Return Value</span></span>  
 <span data-ttu-id="989d0-116">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="989d0-116">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="989d0-117">Требования</span><span class="sxs-lookup"><span data-stu-id="989d0-117">Requirements</span></span>  
 <span data-ttu-id="989d0-118">**Заголовок.** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="989d0-118">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="989d0-119">См. также</span><span class="sxs-lookup"><span data-stu-id="989d0-119">See also</span></span>

- [<span data-ttu-id="989d0-120">Интерфейс ISymUnmanagedReader</span><span class="sxs-lookup"><span data-stu-id="989d0-120">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)

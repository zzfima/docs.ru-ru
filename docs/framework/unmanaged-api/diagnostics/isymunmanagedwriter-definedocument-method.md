---
title: Метод ISymUnmanagedWriter::DefineDocument
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.DefineDocument
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::DefineDocument
helpviewer_keywords:
- ISymUnmanagedWriter::DefineDocument method [.NET Framework debugging]
- DefineDocument method [.NET Framework debugging]
ms.assetid: c3bf15b0-3250-4bbe-b9b5-c5d695289b6f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 532f69afd949971fbb4f56a8fdbcc6eab159446f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="isymunmanagedwriterdefinedocument-method"></a><span data-ttu-id="adb26-102">Метод ISymUnmanagedWriter::DefineDocument</span><span class="sxs-lookup"><span data-stu-id="adb26-102">ISymUnmanagedWriter::DefineDocument Method</span></span>
<span data-ttu-id="adb26-103">Определяет исходный документ.</span><span class="sxs-lookup"><span data-stu-id="adb26-103">Defines a source document.</span></span> <span data-ttu-id="adb26-104">Для известных языков, поставщиков и типов документов предоставляются идентификаторы GUID.</span><span class="sxs-lookup"><span data-stu-id="adb26-104">GUIDs are provided for known languages, vendors, and document types.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="adb26-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="adb26-105">Syntax</span></span>  
  
```  
HRESULT DefineDocument(  
    [in]  const WCHAR  *url,  
    [in]  const GUID   *language,  
    [in]  const GUID   *languageVendor,  
    [in]  const GUID   *documentType,  
    [out, retval] ISymUnmanagedDocumentWriter**  pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="adb26-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="adb26-106">Parameters</span></span>  
 `url`  
 <span data-ttu-id="adb26-107">[in] Указатель на `WCHAR` , определяющий унифицированный указатель ресурса (URL) для идентификации документа.</span><span class="sxs-lookup"><span data-stu-id="adb26-107">[in] A pointer to a `WCHAR` that defines the uniform resource locator (URL) that identifies the document.</span></span>  
  
 `language`  
 <span data-ttu-id="adb26-108">[in] Указатель на идентификатор GUID, который определяет язык документа.</span><span class="sxs-lookup"><span data-stu-id="adb26-108">[in] A pointer to a GUID that defines the document language.</span></span>  
  
 `languageVendor`  
 <span data-ttu-id="adb26-109">[in] Указатель на идентификатор GUID, который определяет удостоверение поставщика языка документа.</span><span class="sxs-lookup"><span data-stu-id="adb26-109">[in] A pointer to a GUID that defines the identity of the vendor for the document language.</span></span>  
  
 `documentType`  
 <span data-ttu-id="adb26-110">[in] Указатель на идентификатор GUID, который определяет тип документа.</span><span class="sxs-lookup"><span data-stu-id="adb26-110">[in] A pointer to a GUID that defines the type of the document.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="adb26-111">[out] Указатель на возвращаемый [ISymUnmanagedWriter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md) интерфейса.</span><span class="sxs-lookup"><span data-stu-id="adb26-111">[out] A pointer to the returned [ISymUnmanagedWriter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="adb26-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="adb26-112">Return Value</span></span>  
 <span data-ttu-id="adb26-113">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="adb26-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="adb26-114">Требования</span><span class="sxs-lookup"><span data-stu-id="adb26-114">Requirements</span></span>  
 <span data-ttu-id="adb26-115">**Заголовок:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="adb26-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="adb26-116">См. также</span><span class="sxs-lookup"><span data-stu-id="adb26-116">See Also</span></span>  
 [<span data-ttu-id="adb26-117">Интерфейс ISymUnmanagedWriter</span><span class="sxs-lookup"><span data-stu-id="adb26-117">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)

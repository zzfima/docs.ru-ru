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
ms.openlocfilehash: 1fcb885b6e19457065c2ca9971f068b42f97147d
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448340"
---
# <a name="isymunmanagedreadergetdocument-method"></a><span data-ttu-id="673ac-102">Метод ISymUnmanagedReader::GetDocument</span><span class="sxs-lookup"><span data-stu-id="673ac-102">ISymUnmanagedReader::GetDocument Method</span></span>
<span data-ttu-id="673ac-103">Находит документ.</span><span class="sxs-lookup"><span data-stu-id="673ac-103">Finds a document.</span></span> <span data-ttu-id="673ac-104">Язык документа, поставщик и тип являются необязательными.</span><span class="sxs-lookup"><span data-stu-id="673ac-104">The document language, vendor, and type are optional.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="673ac-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="673ac-105">Syntax</span></span>  
  
```cpp  
HRESULT GetDocument (  
    [in]  WCHAR  *url,  
    [in]  GUID   language,  
    [in]  GUID   languageVendor,  
    [in]  GUID   documentType,  
    [out, retval] ISymUnmanagedDocument** pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="673ac-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="673ac-106">Parameters</span></span>  
 `url`  
 <span data-ttu-id="673ac-107">окне URL-адрес, определяющий документ.</span><span class="sxs-lookup"><span data-stu-id="673ac-107">[in] The URL that identifies the document.</span></span>  
  
 `language`  
 <span data-ttu-id="673ac-108">окне Язык документа.</span><span class="sxs-lookup"><span data-stu-id="673ac-108">[in] The document language.</span></span> <span data-ttu-id="673ac-109">Этот параметр является необязательным.</span><span class="sxs-lookup"><span data-stu-id="673ac-109">This parameter is optional.</span></span>  
  
 `languageVendor`  
 <span data-ttu-id="673ac-110">окне Удостоверение поставщика для языка документа.</span><span class="sxs-lookup"><span data-stu-id="673ac-110">[in] The identity of the vendor for the document language.</span></span> <span data-ttu-id="673ac-111">Этот параметр является необязательным.</span><span class="sxs-lookup"><span data-stu-id="673ac-111">This parameter is optional.</span></span>  
  
 `documentType`  
 <span data-ttu-id="673ac-112">окне Тип документа.</span><span class="sxs-lookup"><span data-stu-id="673ac-112">[in] The type of the document.</span></span> <span data-ttu-id="673ac-113">Этот параметр является необязательным.</span><span class="sxs-lookup"><span data-stu-id="673ac-113">This parameter is optional.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="673ac-114">заполняет Указатель на возвращаемый интерфейс.</span><span class="sxs-lookup"><span data-stu-id="673ac-114">[out] A pointer to the returned interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="673ac-115">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="673ac-115">Return Value</span></span>  
 <span data-ttu-id="673ac-116">S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.</span><span class="sxs-lookup"><span data-stu-id="673ac-116">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="673ac-117">Требования</span><span class="sxs-lookup"><span data-stu-id="673ac-117">Requirements</span></span>  
 <span data-ttu-id="673ac-118">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="673ac-118">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="673ac-119">См. также:</span><span class="sxs-lookup"><span data-stu-id="673ac-119">See also</span></span>

- [<span data-ttu-id="673ac-120">Интерфейс ISymUnmanagedReader</span><span class="sxs-lookup"><span data-stu-id="673ac-120">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)

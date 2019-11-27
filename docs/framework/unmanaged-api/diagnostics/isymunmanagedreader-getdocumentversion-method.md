---
title: Метод ISymUnmanagedReader::GetDocumentVersion
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetDocumentVersion
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetDocumentVersion
helpviewer_keywords:
- GetDocumentVersion method [.NET Framework debugging]
- ISymUnmanagedReader::GetDocumentVersion method [.NET Framework debugging]
ms.assetid: a51f1f64-e084-44c5-830c-2222da5a6bbf
topic_type:
- apiref
ms.openlocfilehash: 3bc578be680951a1d41c92fb2169c860882b2e31
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448311"
---
# <a name="isymunmanagedreadergetdocumentversion-method"></a><span data-ttu-id="b76f6-102">Метод ISymUnmanagedReader::GetDocumentVersion</span><span class="sxs-lookup"><span data-stu-id="b76f6-102">ISymUnmanagedReader::GetDocumentVersion Method</span></span>
<span data-ttu-id="b76f6-103">Возвращает указанную версию указанного документа.</span><span class="sxs-lookup"><span data-stu-id="b76f6-103">Gets the specified version of the specified document.</span></span> <span data-ttu-id="b76f6-104">Версия документа начинается с 1 и увеличивается каждый раз при обновлении документа с помощью метода [UpdateSymbolStore](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-updatesymbolstore-method.md) .</span><span class="sxs-lookup"><span data-stu-id="b76f6-104">The document version starts at 1 and is incremented each time the document is updated using the [UpdateSymbolStore](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-updatesymbolstore-method.md) method.</span></span> <span data-ttu-id="b76f6-105">Если параметр `pbCurrent` имеет значение `true`, это последняя версия документа.</span><span class="sxs-lookup"><span data-stu-id="b76f6-105">If the `pbCurrent` parameter is `true`, this is the latest version of the document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b76f6-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b76f6-106">Syntax</span></span>  
  
```cpp  
HRESULT GetDocumentVersion (  
    [in]  ISymUnmanagedDocument *pDoc,  
    [out] int* version,  
    [out] BOOL* pbCurrent);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b76f6-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="b76f6-107">Parameters</span></span>  
 `pDoc`  
 <span data-ttu-id="b76f6-108">окне Указанный документ.</span><span class="sxs-lookup"><span data-stu-id="b76f6-108">[in] The specified document.</span></span>  
  
 `version`  
 <span data-ttu-id="b76f6-109">заполняет Указатель на переменную, которая получает версию указанного документа.</span><span class="sxs-lookup"><span data-stu-id="b76f6-109">[out] A pointer to a variable that receives the version of the specified document.</span></span>  
  
 `pbCurrent`  
 <span data-ttu-id="b76f6-110">заполняет Указатель на переменную, которая получает `true`, если это последняя версия документа, или `false`, если это не последняя версия.</span><span class="sxs-lookup"><span data-stu-id="b76f6-110">[out] A pointer to a variable that receives `true` if this is the latest version of the document, or `false` if it isn't the latest version.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b76f6-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="b76f6-111">Return Value</span></span>  
 <span data-ttu-id="b76f6-112">S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.</span><span class="sxs-lookup"><span data-stu-id="b76f6-112">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b76f6-113">Требования</span><span class="sxs-lookup"><span data-stu-id="b76f6-113">Requirements</span></span>  
 <span data-ttu-id="b76f6-114">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="b76f6-114">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b76f6-115">См. также</span><span class="sxs-lookup"><span data-stu-id="b76f6-115">See also</span></span>

- [<span data-ttu-id="b76f6-116">Интерфейс ISymUnmanagedReader</span><span class="sxs-lookup"><span data-stu-id="b76f6-116">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)

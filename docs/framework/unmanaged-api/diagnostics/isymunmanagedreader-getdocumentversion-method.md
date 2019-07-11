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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: efe4d28d207625f00634087b862d76c001518c8d
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67777035"
---
# <a name="isymunmanagedreadergetdocumentversion-method"></a><span data-ttu-id="515e3-102">Метод ISymUnmanagedReader::GetDocumentVersion</span><span class="sxs-lookup"><span data-stu-id="515e3-102">ISymUnmanagedReader::GetDocumentVersion Method</span></span>
<span data-ttu-id="515e3-103">Получает указанную версию указанного документа.</span><span class="sxs-lookup"><span data-stu-id="515e3-103">Gets the specified version of the specified document.</span></span> <span data-ttu-id="515e3-104">Версия документа начинается с 1 и увеличивается каждый раз, необходимо обновить документ с помощью [UpdateSymbolStore](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-updatesymbolstore-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="515e3-104">The document version starts at 1 and is incremented each time the document is updated using the [UpdateSymbolStore](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-updatesymbolstore-method.md) method.</span></span> <span data-ttu-id="515e3-105">Если `pbCurrent` параметр `true`, это последняя версия документа.</span><span class="sxs-lookup"><span data-stu-id="515e3-105">If the `pbCurrent` parameter is `true`, this is the latest version of the document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="515e3-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="515e3-106">Syntax</span></span>  
  
```cpp  
HRESULT GetDocumentVersion (  
    [in]  ISymUnmanagedDocument *pDoc,  
    [out] int* version,  
    [out] BOOL* pbCurrent);  
```  
  
## <a name="parameters"></a><span data-ttu-id="515e3-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="515e3-107">Parameters</span></span>  
 `pDoc`  
 <span data-ttu-id="515e3-108">[in] Указанный документ.</span><span class="sxs-lookup"><span data-stu-id="515e3-108">[in] The specified document.</span></span>  
  
 `version`  
 <span data-ttu-id="515e3-109">[out] Указатель на переменную, которая получает версию указанного документа.</span><span class="sxs-lookup"><span data-stu-id="515e3-109">[out] A pointer to a variable that receives the version of the specified document.</span></span>  
  
 `pbCurrent`  
 <span data-ttu-id="515e3-110">[out] Указатель на переменную, получающую `true` Если это последняя версия документа, или `false` если она не является последней версии.</span><span class="sxs-lookup"><span data-stu-id="515e3-110">[out] A pointer to a variable that receives `true` if this is the latest version of the document, or `false` if it isn't the latest version.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="515e3-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="515e3-111">Return Value</span></span>  
 <span data-ttu-id="515e3-112">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="515e3-112">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="515e3-113">Требования</span><span class="sxs-lookup"><span data-stu-id="515e3-113">Requirements</span></span>  
 <span data-ttu-id="515e3-114">**Заголовок.** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="515e3-114">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="515e3-115">См. также</span><span class="sxs-lookup"><span data-stu-id="515e3-115">See also</span></span>

- [<span data-ttu-id="515e3-116">Интерфейс ISymUnmanagedReader</span><span class="sxs-lookup"><span data-stu-id="515e3-116">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)

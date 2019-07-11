---
title: Метод ISymUnmanagedDocument::GetLanguage
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocument.GetLanguage
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument::GetLanguage
helpviewer_keywords:
- ISymUnmanagedDocument::GetLanguage method [.NET Framework debugging]
- GetLanguage method [.NET Framework debugging]
ms.assetid: c6639418-e9f2-4a99-8ce2-ec9876e0bc79
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 167eb9ae550454afee05cf1e724ba4afa4f95430
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67776733"
---
# <a name="isymunmanageddocumentgetlanguage-method"></a><span data-ttu-id="5014e-102">Метод ISymUnmanagedDocument::GetLanguage</span><span class="sxs-lookup"><span data-stu-id="5014e-102">ISymUnmanagedDocument::GetLanguage Method</span></span>
<span data-ttu-id="5014e-103">Получает идентификатор языка в этом документе</span><span class="sxs-lookup"><span data-stu-id="5014e-103">Gets the language identifier of this document</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5014e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5014e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLanguage(  
    [out, retval]  GUID*  pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5014e-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="5014e-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="5014e-106">[out] Указатель на переменную, которая получает идентификатор языка.</span><span class="sxs-lookup"><span data-stu-id="5014e-106">[out] A pointer to a variable that receives the language identifier.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5014e-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="5014e-107">Return Value</span></span>  
 <span data-ttu-id="5014e-108">Значение S_OK, если метод выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="5014e-108">S_OK if the method succeeds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5014e-109">См. также</span><span class="sxs-lookup"><span data-stu-id="5014e-109">See also</span></span>

- [<span data-ttu-id="5014e-110">Интерфейс ISymUnmanagedDocument</span><span class="sxs-lookup"><span data-stu-id="5014e-110">ISymUnmanagedDocument Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)

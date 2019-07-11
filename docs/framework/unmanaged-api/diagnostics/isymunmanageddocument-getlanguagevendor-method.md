---
title: Метод ISymUnmanagedDocument::GetLanguageVendor
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocument.GetLanguageVendor
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument::GetLanguageVendor
helpviewer_keywords:
- GetLanguageVendor method [.NET Framework debugging]
- ISymUnmanagedDocument::GetLanguageVendor method [.NET Framework debugging]
ms.assetid: 1d4b702e-4922-441d-8b44-03804284f70b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f5140462ae3c869d58187351d2e0ff11f7b6e179
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67776689"
---
# <a name="isymunmanageddocumentgetlanguagevendor-method"></a><span data-ttu-id="b633d-102">Метод ISymUnmanagedDocument::GetLanguageVendor</span><span class="sxs-lookup"><span data-stu-id="b633d-102">ISymUnmanagedDocument::GetLanguageVendor Method</span></span>
<span data-ttu-id="b633d-103">Возвращает поставщика языка документа.</span><span class="sxs-lookup"><span data-stu-id="b633d-103">Gets the language vendor of this document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b633d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b633d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLanguageVendor(  
    [out, retval]  GUID*  pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b633d-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="b633d-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="b633d-106">[out] Указатель на переменную, которая получает поставщика языка.</span><span class="sxs-lookup"><span data-stu-id="b633d-106">[out] A pointer to a variable that receives the language vendor.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b633d-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="b633d-107">Return Value</span></span>  
 <span data-ttu-id="b633d-108">Значение S_OK, если метод выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="b633d-108">S_OK if the method succeeds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b633d-109">См. также</span><span class="sxs-lookup"><span data-stu-id="b633d-109">See also</span></span>

- [<span data-ttu-id="b633d-110">Интерфейс ISymUnmanagedDocument</span><span class="sxs-lookup"><span data-stu-id="b633d-110">ISymUnmanagedDocument Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)

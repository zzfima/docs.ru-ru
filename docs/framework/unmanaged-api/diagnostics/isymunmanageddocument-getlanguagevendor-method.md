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
ms.openlocfilehash: 0a6830f47d5cac2cf9c84144c18486489b0ec581
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33424535"
---
# <a name="isymunmanageddocumentgetlanguagevendor-method"></a><span data-ttu-id="81e31-102">Метод ISymUnmanagedDocument::GetLanguageVendor</span><span class="sxs-lookup"><span data-stu-id="81e31-102">ISymUnmanagedDocument::GetLanguageVendor Method</span></span>
<span data-ttu-id="81e31-103">Возвращает поставщика языка документа.</span><span class="sxs-lookup"><span data-stu-id="81e31-103">Gets the language vendor of this document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="81e31-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="81e31-104">Syntax</span></span>  
  
```  
HRESULT GetLanguageVendor(  
    [out, retval]  GUID*  pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="81e31-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="81e31-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="81e31-106">[out] Указатель на переменную, которая получает поставщика языка.</span><span class="sxs-lookup"><span data-stu-id="81e31-106">[out] A pointer to a variable that receives the language vendor.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="81e31-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="81e31-107">Return Value</span></span>  
 <span data-ttu-id="81e31-108">Значение S_OK, если метод выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="81e31-108">S_OK if the method succeeds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81e31-109">См. также</span><span class="sxs-lookup"><span data-stu-id="81e31-109">See Also</span></span>  
 [<span data-ttu-id="81e31-110">Интерфейс ISymUnmanagedDocument</span><span class="sxs-lookup"><span data-stu-id="81e31-110">ISymUnmanagedDocument Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)

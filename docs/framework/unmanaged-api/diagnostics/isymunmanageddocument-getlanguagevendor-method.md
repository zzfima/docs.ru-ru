---
title: "Метод ISymUnmanagedDocument::GetLanguageVendor"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedDocument.GetLanguageVendor
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedDocument::GetLanguageVendor
helpviewer_keywords:
- GetLanguageVendor method [.NET Framework debugging]
- ISymUnmanagedDocument::GetLanguageVendor method [.NET Framework debugging]
ms.assetid: 1d4b702e-4922-441d-8b44-03804284f70b
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 72fffae9995f44be9a9359c16bb876d79c9a8242
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanageddocumentgetlanguagevendor-method"></a><span data-ttu-id="5eb91-102">Метод ISymUnmanagedDocument::GetLanguageVendor</span><span class="sxs-lookup"><span data-stu-id="5eb91-102">ISymUnmanagedDocument::GetLanguageVendor Method</span></span>
<span data-ttu-id="5eb91-103">Возвращает поставщика языка документа.</span><span class="sxs-lookup"><span data-stu-id="5eb91-103">Gets the language vendor of this document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5eb91-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5eb91-104">Syntax</span></span>  
  
```  
HRESULT GetLanguageVendor(  
    [out, retval]  GUID*  pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5eb91-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="5eb91-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="5eb91-106">[out] Указатель на переменную, которая получает поставщика языка.</span><span class="sxs-lookup"><span data-stu-id="5eb91-106">[out] A pointer to a variable that receives the language vendor.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5eb91-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="5eb91-107">Return Value</span></span>  
 <span data-ttu-id="5eb91-108">Значение S_OK, если метод выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="5eb91-108">S_OK if the method succeeds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5eb91-109">См. также</span><span class="sxs-lookup"><span data-stu-id="5eb91-109">See Also</span></span>  
 [<span data-ttu-id="5eb91-110">Интерфейс ISymUnmanagedDocument</span><span class="sxs-lookup"><span data-stu-id="5eb91-110">ISymUnmanagedDocument Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)

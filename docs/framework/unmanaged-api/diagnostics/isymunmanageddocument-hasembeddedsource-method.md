---
title: Метод ISymUnmanagedDocument::HasEmbeddedSource
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocument.HasEmbeddedSource
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument::HasEmbeddedSource
helpviewer_keywords:
- HasEmbeddedSource method [.NET Framework debugging]
- ISymUnmanagedDocument::HasEmbeddedSource method [.NET Framework debugging]
ms.assetid: 385fc4d3-365c-4645-b7b0-6c4c5344b79f
topic_type:
- apiref
ms.openlocfilehash: 533d8a5481fe9ba7e7e65775229156a9cc3cf4d7
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449108"
---
# <a name="isymunmanageddocumenthasembeddedsource-method"></a><span data-ttu-id="890e9-102">Метод ISymUnmanagedDocument::HasEmbeddedSource</span><span class="sxs-lookup"><span data-stu-id="890e9-102">ISymUnmanagedDocument::HasEmbeddedSource Method</span></span>
<span data-ttu-id="890e9-103">Возвращает `true`, если документ содержит исходный код, внедренный в отладочные символы; в противном случае возвращает `false`.</span><span class="sxs-lookup"><span data-stu-id="890e9-103">Returns `true` if the document has source embedded in the debugging symbols; otherwise, returns `false`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="890e9-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="890e9-104">Syntax</span></span>  
  
```cpp  
HRESULT HasEmbeddedSource(  
   [out, retval]  BOOL  *pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="890e9-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="890e9-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="890e9-106">заполняет Указатель на переменную, которая указывает, имеет ли документ исходный код, внедренный в отладочные символы.</span><span class="sxs-lookup"><span data-stu-id="890e9-106">[out] A pointer to a variable that indicates whether the document has source embedded in the debugging symbols.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="890e9-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="890e9-107">Return Value</span></span>  
 <span data-ttu-id="890e9-108">S_OK, если метод выполнен.</span><span class="sxs-lookup"><span data-stu-id="890e9-108">S_OK if the method succeeds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="890e9-109">См. также:</span><span class="sxs-lookup"><span data-stu-id="890e9-109">See also</span></span>

- [<span data-ttu-id="890e9-110">Интерфейс ISymUnmanagedDocument</span><span class="sxs-lookup"><span data-stu-id="890e9-110">ISymUnmanagedDocument Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)

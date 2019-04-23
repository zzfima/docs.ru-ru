---
title: Метод ISymUnmanagedWriter::CloseNamespace
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.CloseNamespace
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::CloseNamespace
helpviewer_keywords:
- ISymUnmanagedWriter::CloseNamespace method [.NET Framework debugging]
- CloseNamespace method [.NET Framework debugging]
ms.assetid: 7f74d9c5-1377-4958-b842-6306d611cbd5
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 66f8804c911e053758442670afb3c3f27d0f7453
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59130056"
---
# <a name="isymunmanagedwriterclosenamespace-method"></a><span data-ttu-id="a746e-102">Метод ISymUnmanagedWriter::CloseNamespace</span><span class="sxs-lookup"><span data-stu-id="a746e-102">ISymUnmanagedWriter::CloseNamespace Method</span></span>
<span data-ttu-id="a746e-103">Закрывает наиболее недавно открывали пространства имен.</span><span class="sxs-lookup"><span data-stu-id="a746e-103">Closes the most recently opened namespace.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a746e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a746e-104">Syntax</span></span>  
  
```  
HRESULT CloseNamespace();  
```  
  
## <a name="return-value"></a><span data-ttu-id="a746e-105">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="a746e-105">Return Value</span></span>  
 <span data-ttu-id="a746e-106">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="a746e-106">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a746e-107">Требования</span><span class="sxs-lookup"><span data-stu-id="a746e-107">Requirements</span></span>  
 <span data-ttu-id="a746e-108">**Заголовок.** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="a746e-108">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a746e-109">См. также</span><span class="sxs-lookup"><span data-stu-id="a746e-109">See also</span></span>

- [<span data-ttu-id="a746e-110">Интерфейс ISymUnmanagedWriter</span><span class="sxs-lookup"><span data-stu-id="a746e-110">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
- [<span data-ttu-id="a746e-111">Метод OpenNamespace</span><span class="sxs-lookup"><span data-stu-id="a746e-111">OpenNamespace Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-opennamespace-method.md)

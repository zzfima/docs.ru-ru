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
ms.openlocfilehash: 5d7e1e4da51445a55387b813e814183bf7433e45
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33426927"
---
# <a name="isymunmanagedwriterclosenamespace-method"></a><span data-ttu-id="4efa5-102">Метод ISymUnmanagedWriter::CloseNamespace</span><span class="sxs-lookup"><span data-stu-id="4efa5-102">ISymUnmanagedWriter::CloseNamespace Method</span></span>
<span data-ttu-id="4efa5-103">Закрывает последнее открыть пространство имен.</span><span class="sxs-lookup"><span data-stu-id="4efa5-103">Closes the most recently opened namespace.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4efa5-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4efa5-104">Syntax</span></span>  
  
```  
HRESULT CloseNamespace();  
```  
  
## <a name="return-value"></a><span data-ttu-id="4efa5-105">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="4efa5-105">Return Value</span></span>  
 <span data-ttu-id="4efa5-106">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="4efa5-106">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4efa5-107">Требования</span><span class="sxs-lookup"><span data-stu-id="4efa5-107">Requirements</span></span>  
 <span data-ttu-id="4efa5-108">**Заголовок:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="4efa5-108">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4efa5-109">См. также</span><span class="sxs-lookup"><span data-stu-id="4efa5-109">See Also</span></span>  
 [<span data-ttu-id="4efa5-110">Интерфейс ISymUnmanagedWriter</span><span class="sxs-lookup"><span data-stu-id="4efa5-110">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)  
 [<span data-ttu-id="4efa5-111">Метод OpenNamespace</span><span class="sxs-lookup"><span data-stu-id="4efa5-111">OpenNamespace Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-opennamespace-method.md)

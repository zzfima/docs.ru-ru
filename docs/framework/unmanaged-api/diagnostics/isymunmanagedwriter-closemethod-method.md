---
title: "Метод ISymUnmanagedWriter::CloseMethod"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedWriter.CloseMethod
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedWriter::CloseMethod
helpviewer_keywords:
- ISymUnmanagedWriter::CloseMethod method [.NET Framework debugging]
- CloseMethod method [.NET Framework debugging]
ms.assetid: b8025e04-f0e5-40c8-849c-8cd51323420e
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 21c4cdd42613f5e8b60c39426b4f169a034ce7a6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedwriterclosemethod-method"></a><span data-ttu-id="8e1d9-102">Метод ISymUnmanagedWriter::CloseMethod</span><span class="sxs-lookup"><span data-stu-id="8e1d9-102">ISymUnmanagedWriter::CloseMethod Method</span></span>
<span data-ttu-id="8e1d9-103">Закрывает текущий метод.</span><span class="sxs-lookup"><span data-stu-id="8e1d9-103">Closes the current method.</span></span> <span data-ttu-id="8e1d9-104">После закрытия метода отсутствуют дополнительные символы могут определяться внутри него.</span><span class="sxs-lookup"><span data-stu-id="8e1d9-104">Once a method is closed, no more symbols can be defined within it.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8e1d9-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8e1d9-105">Syntax</span></span>  
  
```  
HRESULT CloseMethod();  
```  
  
## <a name="return-value"></a><span data-ttu-id="8e1d9-106">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="8e1d9-106">Return Value</span></span>  
 <span data-ttu-id="8e1d9-107">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="8e1d9-107">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8e1d9-108">Требования</span><span class="sxs-lookup"><span data-stu-id="8e1d9-108">Requirements</span></span>  
 <span data-ttu-id="8e1d9-109">**Заголовок:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="8e1d9-109">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e1d9-110">См. также</span><span class="sxs-lookup"><span data-stu-id="8e1d9-110">See Also</span></span>  
 [<span data-ttu-id="8e1d9-111">Интерфейс ISymUnmanagedWriter</span><span class="sxs-lookup"><span data-stu-id="8e1d9-111">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)  
 [<span data-ttu-id="8e1d9-112">Метод OpenMethod</span><span class="sxs-lookup"><span data-stu-id="8e1d9-112">OpenMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openmethod-method.md)

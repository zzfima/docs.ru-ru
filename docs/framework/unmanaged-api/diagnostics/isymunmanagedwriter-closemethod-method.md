---
title: Метод ISymUnmanagedWriter::CloseMethod
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.CloseMethod
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::CloseMethod
helpviewer_keywords:
- ISymUnmanagedWriter::CloseMethod method [.NET Framework debugging]
- CloseMethod method [.NET Framework debugging]
ms.assetid: b8025e04-f0e5-40c8-849c-8cd51323420e
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 591279a80b7d6a770127fb98eb71c056c48bdffd
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61934151"
---
# <a name="isymunmanagedwriterclosemethod-method"></a><span data-ttu-id="ad0ab-102">Метод ISymUnmanagedWriter::CloseMethod</span><span class="sxs-lookup"><span data-stu-id="ad0ab-102">ISymUnmanagedWriter::CloseMethod Method</span></span>
<span data-ttu-id="ad0ab-103">Закрывает текущий метод.</span><span class="sxs-lookup"><span data-stu-id="ad0ab-103">Closes the current method.</span></span> <span data-ttu-id="ad0ab-104">После закрытия метода, дополнительные символы не могут определяться внутри него.</span><span class="sxs-lookup"><span data-stu-id="ad0ab-104">Once a method is closed, no more symbols can be defined within it.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ad0ab-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ad0ab-105">Syntax</span></span>  
  
```  
HRESULT CloseMethod();  
```  
  
## <a name="return-value"></a><span data-ttu-id="ad0ab-106">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="ad0ab-106">Return Value</span></span>  
 <span data-ttu-id="ad0ab-107">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="ad0ab-107">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ad0ab-108">Требования</span><span class="sxs-lookup"><span data-stu-id="ad0ab-108">Requirements</span></span>  
 <span data-ttu-id="ad0ab-109">**Заголовок.** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="ad0ab-109">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad0ab-110">См. также</span><span class="sxs-lookup"><span data-stu-id="ad0ab-110">See also</span></span>

- [<span data-ttu-id="ad0ab-111">Интерфейс ISymUnmanagedWriter</span><span class="sxs-lookup"><span data-stu-id="ad0ab-111">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
- [<span data-ttu-id="ad0ab-112">Метод OpenMethod</span><span class="sxs-lookup"><span data-stu-id="ad0ab-112">OpenMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openmethod-method.md)

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
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59231218"
---
# <a name="isymunmanagedwriterclosemethod-method"></a><span data-ttu-id="ec7af-102">Метод ISymUnmanagedWriter::CloseMethod</span><span class="sxs-lookup"><span data-stu-id="ec7af-102">ISymUnmanagedWriter::CloseMethod Method</span></span>
<span data-ttu-id="ec7af-103">Закрывает текущий метод.</span><span class="sxs-lookup"><span data-stu-id="ec7af-103">Closes the current method.</span></span> <span data-ttu-id="ec7af-104">После закрытия метода, дополнительные символы не могут определяться внутри него.</span><span class="sxs-lookup"><span data-stu-id="ec7af-104">Once a method is closed, no more symbols can be defined within it.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ec7af-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ec7af-105">Syntax</span></span>  
  
```  
HRESULT CloseMethod();  
```  
  
## <a name="return-value"></a><span data-ttu-id="ec7af-106">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="ec7af-106">Return Value</span></span>  
 <span data-ttu-id="ec7af-107">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="ec7af-107">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ec7af-108">Требования</span><span class="sxs-lookup"><span data-stu-id="ec7af-108">Requirements</span></span>  
 <span data-ttu-id="ec7af-109">**Заголовок.** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="ec7af-109">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec7af-110">См. также</span><span class="sxs-lookup"><span data-stu-id="ec7af-110">See also</span></span>

- [<span data-ttu-id="ec7af-111">Интерфейс ISymUnmanagedWriter</span><span class="sxs-lookup"><span data-stu-id="ec7af-111">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
- [<span data-ttu-id="ec7af-112">Метод OpenMethod</span><span class="sxs-lookup"><span data-stu-id="ec7af-112">OpenMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openmethod-method.md)

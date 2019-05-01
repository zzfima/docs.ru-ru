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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61986093"
---
# <a name="isymunmanagedwriterclosenamespace-method"></a><span data-ttu-id="1e112-102">Метод ISymUnmanagedWriter::CloseNamespace</span><span class="sxs-lookup"><span data-stu-id="1e112-102">ISymUnmanagedWriter::CloseNamespace Method</span></span>
<span data-ttu-id="1e112-103">Закрывает наиболее недавно открывали пространства имен.</span><span class="sxs-lookup"><span data-stu-id="1e112-103">Closes the most recently opened namespace.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1e112-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1e112-104">Syntax</span></span>  
  
```  
HRESULT CloseNamespace();  
```  
  
## <a name="return-value"></a><span data-ttu-id="1e112-105">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="1e112-105">Return Value</span></span>  
 <span data-ttu-id="1e112-106">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="1e112-106">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1e112-107">Требования</span><span class="sxs-lookup"><span data-stu-id="1e112-107">Requirements</span></span>  
 <span data-ttu-id="1e112-108">**Заголовок.** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="1e112-108">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e112-109">См. также</span><span class="sxs-lookup"><span data-stu-id="1e112-109">See also</span></span>

- [<span data-ttu-id="1e112-110">Интерфейс ISymUnmanagedWriter</span><span class="sxs-lookup"><span data-stu-id="1e112-110">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
- [<span data-ttu-id="1e112-111">Метод OpenNamespace</span><span class="sxs-lookup"><span data-stu-id="1e112-111">OpenNamespace Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-opennamespace-method.md)

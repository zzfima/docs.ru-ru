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
ms.openlocfilehash: 3ed618847d398bb4dcccb8ecebabdc947390c874
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67778179"
---
# <a name="isymunmanagedwriterclosenamespace-method"></a><span data-ttu-id="beebe-102">Метод ISymUnmanagedWriter::CloseNamespace</span><span class="sxs-lookup"><span data-stu-id="beebe-102">ISymUnmanagedWriter::CloseNamespace Method</span></span>
<span data-ttu-id="beebe-103">Закрывает наиболее недавно открывали пространства имен.</span><span class="sxs-lookup"><span data-stu-id="beebe-103">Closes the most recently opened namespace.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="beebe-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="beebe-104">Syntax</span></span>  
  
```cpp  
HRESULT CloseNamespace();  
```  
  
## <a name="return-value"></a><span data-ttu-id="beebe-105">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="beebe-105">Return Value</span></span>  
 <span data-ttu-id="beebe-106">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="beebe-106">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="beebe-107">Требования</span><span class="sxs-lookup"><span data-stu-id="beebe-107">Requirements</span></span>  
 <span data-ttu-id="beebe-108">**Заголовок.** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="beebe-108">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="beebe-109">См. также</span><span class="sxs-lookup"><span data-stu-id="beebe-109">See also</span></span>

- [<span data-ttu-id="beebe-110">Интерфейс ISymUnmanagedWriter</span><span class="sxs-lookup"><span data-stu-id="beebe-110">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
- [<span data-ttu-id="beebe-111">Метод OpenNamespace</span><span class="sxs-lookup"><span data-stu-id="beebe-111">OpenNamespace Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-opennamespace-method.md)

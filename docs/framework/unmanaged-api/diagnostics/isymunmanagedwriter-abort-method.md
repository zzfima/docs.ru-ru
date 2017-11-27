---
title: "Метод ISymUnmanagedWriter::Abort"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedWriter.Abort
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedWriter::Abort
helpviewer_keywords:
- ISymUnmanagedWriter::Abort method [.NET Framework debugging]
- Abort method, ISymUnmanagedWriter interface [.NET Framework debugging]
ms.assetid: 416b220f-38d4-48e0-bb49-d2faa7366702
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 29dd11972e8db80f36820bba1eb679070d02146e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedwriterabort-method"></a><span data-ttu-id="6a444-102">Метод ISymUnmanagedWriter::Abort</span><span class="sxs-lookup"><span data-stu-id="6a444-102">ISymUnmanagedWriter::Abort Method</span></span>
<span data-ttu-id="6a444-103">Закрывает средство записи символов без передачи символов в хранилище символов.</span><span class="sxs-lookup"><span data-stu-id="6a444-103">Closes the symbol writer without committing the symbols to the symbol store.</span></span> <span data-ttu-id="6a444-104">После этого вызова модуля записи символов становится недействительным для дальнейших обновлений.</span><span class="sxs-lookup"><span data-stu-id="6a444-104">After this call, the symbol writer becomes invalid for further updates.</span></span> <span data-ttu-id="6a444-105">Чтобы зафиксировать символы и закрыть модуль записи символов, используйте [ISymUnmanagedWriter::Close](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-close-method.md) метод вместо него.</span><span class="sxs-lookup"><span data-stu-id="6a444-105">To commit the symbols and close the symbol writer, use the [ISymUnmanagedWriter::Close](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-close-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6a444-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6a444-106">Syntax</span></span>  
  
```  
HRESULT Abort();  
```  
  
## <a name="return-value"></a><span data-ttu-id="6a444-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="6a444-107">Return Value</span></span>  
 <span data-ttu-id="6a444-108">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="6a444-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6a444-109">Требования</span><span class="sxs-lookup"><span data-stu-id="6a444-109">Requirements</span></span>  
 <span data-ttu-id="6a444-110">**Заголовок:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="6a444-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a444-111">См. также</span><span class="sxs-lookup"><span data-stu-id="6a444-111">See Also</span></span>  
 [<span data-ttu-id="6a444-112">ISymUnmanagedWriter-интерфейс</span><span class="sxs-lookup"><span data-stu-id="6a444-112">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)

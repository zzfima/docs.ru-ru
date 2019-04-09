---
title: Метод ISymUnmanagedWriter::Abort
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.Abort
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::Abort
helpviewer_keywords:
- ISymUnmanagedWriter::Abort method [.NET Framework debugging]
- Abort method, ISymUnmanagedWriter interface [.NET Framework debugging]
ms.assetid: 416b220f-38d4-48e0-bb49-d2faa7366702
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 090183cad17aff6faf5e79639eadff086c1a26ce
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59119539"
---
# <a name="isymunmanagedwriterabort-method"></a><span data-ttu-id="dec90-102">Метод ISymUnmanagedWriter::Abort</span><span class="sxs-lookup"><span data-stu-id="dec90-102">ISymUnmanagedWriter::Abort Method</span></span>
<span data-ttu-id="dec90-103">Закрывает средство записи символов без передачи символов в хранилище символов.</span><span class="sxs-lookup"><span data-stu-id="dec90-103">Closes the symbol writer without committing the symbols to the symbol store.</span></span> <span data-ttu-id="dec90-104">После этого вызова модуля записи символов становится недействительным для дальнейших обновлений.</span><span class="sxs-lookup"><span data-stu-id="dec90-104">After this call, the symbol writer becomes invalid for further updates.</span></span> <span data-ttu-id="dec90-105">Чтобы зафиксировать символы и закрыть модуль записи символов, используйте [ISymUnmanagedWriter::Close](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-close-method.md) метод вместо этого.</span><span class="sxs-lookup"><span data-stu-id="dec90-105">To commit the symbols and close the symbol writer, use the [ISymUnmanagedWriter::Close](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-close-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dec90-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="dec90-106">Syntax</span></span>  
  
```  
HRESULT Abort();  
```  
  
## <a name="return-value"></a><span data-ttu-id="dec90-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="dec90-107">Return Value</span></span>  
 <span data-ttu-id="dec90-108">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="dec90-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dec90-109">Требования</span><span class="sxs-lookup"><span data-stu-id="dec90-109">Requirements</span></span>  
 <span data-ttu-id="dec90-110">**Заголовок.** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="dec90-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dec90-111">См. также</span><span class="sxs-lookup"><span data-stu-id="dec90-111">See also</span></span>

- [<span data-ttu-id="dec90-112">Интерфейс ISymUnmanagedWriter</span><span class="sxs-lookup"><span data-stu-id="dec90-112">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)

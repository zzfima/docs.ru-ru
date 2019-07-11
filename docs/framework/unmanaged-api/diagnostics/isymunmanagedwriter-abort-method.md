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
ms.openlocfilehash: f2debe193b96b065987f6d7ebc6ffc1abac95778
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67778213"
---
# <a name="isymunmanagedwriterabort-method"></a><span data-ttu-id="fcbea-102">Метод ISymUnmanagedWriter::Abort</span><span class="sxs-lookup"><span data-stu-id="fcbea-102">ISymUnmanagedWriter::Abort Method</span></span>
<span data-ttu-id="fcbea-103">Закрывает средство записи символов без передачи символов в хранилище символов.</span><span class="sxs-lookup"><span data-stu-id="fcbea-103">Closes the symbol writer without committing the symbols to the symbol store.</span></span> <span data-ttu-id="fcbea-104">После этого вызова модуля записи символов становится недействительным для дальнейших обновлений.</span><span class="sxs-lookup"><span data-stu-id="fcbea-104">After this call, the symbol writer becomes invalid for further updates.</span></span> <span data-ttu-id="fcbea-105">Чтобы зафиксировать символы и закрыть модуль записи символов, используйте [ISymUnmanagedWriter::Close](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-close-method.md) метод вместо этого.</span><span class="sxs-lookup"><span data-stu-id="fcbea-105">To commit the symbols and close the symbol writer, use the [ISymUnmanagedWriter::Close](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-close-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fcbea-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fcbea-106">Syntax</span></span>  
  
```cpp  
HRESULT Abort();  
```  
  
## <a name="return-value"></a><span data-ttu-id="fcbea-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="fcbea-107">Return Value</span></span>  
 <span data-ttu-id="fcbea-108">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="fcbea-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fcbea-109">Требования</span><span class="sxs-lookup"><span data-stu-id="fcbea-109">Requirements</span></span>  
 <span data-ttu-id="fcbea-110">**Заголовок.** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="fcbea-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fcbea-111">См. также</span><span class="sxs-lookup"><span data-stu-id="fcbea-111">See also</span></span>

- [<span data-ttu-id="fcbea-112">Интерфейс ISymUnmanagedWriter</span><span class="sxs-lookup"><span data-stu-id="fcbea-112">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)

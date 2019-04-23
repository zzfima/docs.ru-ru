---
title: Метод ISymUnmanagedWriter::Close
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.Close
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::Close
helpviewer_keywords:
- Close method, ISymUnmanagedWriter interface [.NET Framework debugging]
- ISymUnmanagedWriter::Close method [.NET Framework debugging]
ms.assetid: 4cce59e1-80b9-4fc4-b3aa-126f1c5876bc
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4d3497d3167715d3e8a04f10a6687260949e4a36
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59104706"
---
# <a name="isymunmanagedwriterclose-method"></a><span data-ttu-id="e332b-102">Метод ISymUnmanagedWriter::Close</span><span class="sxs-lookup"><span data-stu-id="e332b-102">ISymUnmanagedWriter::Close Method</span></span>
<span data-ttu-id="e332b-103">Закрывает средство записи символов после передачи символов в хранилище символов.</span><span class="sxs-lookup"><span data-stu-id="e332b-103">Closes the symbol writer after committing the symbols to the symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e332b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e332b-104">Syntax</span></span>  
  
```  
HRESULT Close();  
```  
  
## <a name="return-value"></a><span data-ttu-id="e332b-105">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="e332b-105">Return Value</span></span>  
 <span data-ttu-id="e332b-106">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="e332b-106">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e332b-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="e332b-107">Remarks</span></span>  
 <span data-ttu-id="e332b-108">После этого вызова модуля записи символов становится недействительным для дальнейших обновлений.</span><span class="sxs-lookup"><span data-stu-id="e332b-108">After this call, the symbol writer becomes invalid for further updates.</span></span> <span data-ttu-id="e332b-109">Чтобы закрыть средство записи символов без передачи символов, используйте [ISymUnmanagedWriter::Abort](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-abort-method.md) метод вместо этого.</span><span class="sxs-lookup"><span data-stu-id="e332b-109">To close the symbol writer without committing the symbols, use the [ISymUnmanagedWriter::Abort](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-abort-method.md) method instead.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e332b-110">Требования</span><span class="sxs-lookup"><span data-stu-id="e332b-110">Requirements</span></span>  
 <span data-ttu-id="e332b-111">**Заголовок.** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="e332b-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e332b-112">См. также</span><span class="sxs-lookup"><span data-stu-id="e332b-112">See also</span></span>

- [<span data-ttu-id="e332b-113">Интерфейс ISymUnmanagedWriter</span><span class="sxs-lookup"><span data-stu-id="e332b-113">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)

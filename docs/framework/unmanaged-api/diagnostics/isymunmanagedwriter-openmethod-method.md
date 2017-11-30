---
title: "Метод ISymUnmanagedWriter::OpenMethod"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedWriter.OpenMethod
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedWriter::OpenMethod
helpviewer_keywords:
- ISymUnmanagedWriter::OpenMethod method [.NET Framework debugging]
- OpenMethod method [.NET Framework debugging]
ms.assetid: fb90cb7f-af88-45e8-a99f-80a0bbddb08b
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 61d63fb96635e34e07c3997c1aad838e67c70742
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="isymunmanagedwriteropenmethod-method"></a><span data-ttu-id="00ae1-102">Метод ISymUnmanagedWriter::OpenMethod</span><span class="sxs-lookup"><span data-stu-id="00ae1-102">ISymUnmanagedWriter::OpenMethod Method</span></span>
<span data-ttu-id="00ae1-103">Открывает метод в символ, который создается информация.</span><span class="sxs-lookup"><span data-stu-id="00ae1-103">Opens a method into which symbol information is emitted.</span></span> <span data-ttu-id="00ae1-104">Данный метод становится текущим методом для вызовов с целью определения точек следования, параметров и лексические области.</span><span class="sxs-lookup"><span data-stu-id="00ae1-104">The given method becomes the current method for calls to define sequence points, parameters, and lexical scopes.</span></span> <span data-ttu-id="00ae1-105">Нет неявную лексическую область вокруг весь метод.</span><span class="sxs-lookup"><span data-stu-id="00ae1-105">There is an implicit lexical scope around the entire method.</span></span> <span data-ttu-id="00ae1-106">Повторное открытие метода, которое было ранее закрыто стирает всех ранее определенных символов для этого метода.</span><span class="sxs-lookup"><span data-stu-id="00ae1-106">Reopening a method that was previously closed erases any previously defined symbols for that method.</span></span> <span data-ttu-id="00ae1-107">Одновременно может существовать только один метод open.</span><span class="sxs-lookup"><span data-stu-id="00ae1-107">There can be only one open method at a time.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="00ae1-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="00ae1-108">Syntax</span></span>  
  
```  
HRESULT OpenMethod(  
    [in] mdMethodDef method);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="00ae1-109">Параметры</span><span class="sxs-lookup"><span data-stu-id="00ae1-109">Parameters</span></span>  
 `method`  
 <span data-ttu-id="00ae1-110">[in] Токен метаданных для открываемого метода.</span><span class="sxs-lookup"><span data-stu-id="00ae1-110">[in] The metadata token for the method to be opened.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="00ae1-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="00ae1-111">Return Value</span></span>  
 <span data-ttu-id="00ae1-112">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="00ae1-112">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="00ae1-113">Требования</span><span class="sxs-lookup"><span data-stu-id="00ae1-113">Requirements</span></span>  
 <span data-ttu-id="00ae1-114">**Заголовок:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="00ae1-114">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00ae1-115">См. также</span><span class="sxs-lookup"><span data-stu-id="00ae1-115">See Also</span></span>  
 [<span data-ttu-id="00ae1-116">ISymUnmanagedWriter-интерфейс</span><span class="sxs-lookup"><span data-stu-id="00ae1-116">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)  
 [<span data-ttu-id="00ae1-117">Метод CloseMethod</span><span class="sxs-lookup"><span data-stu-id="00ae1-117">CloseMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closemethod-method.md)  
 [<span data-ttu-id="00ae1-118">Метод OpenMethod2</span><span class="sxs-lookup"><span data-stu-id="00ae1-118">OpenMethod2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-openmethod2-method.md)

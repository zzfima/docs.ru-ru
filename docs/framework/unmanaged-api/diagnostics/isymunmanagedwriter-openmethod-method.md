---
title: Метод ISymUnmanagedWriter::OpenMethod
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.OpenMethod
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::OpenMethod
helpviewer_keywords:
- ISymUnmanagedWriter::OpenMethod method [.NET Framework debugging]
- OpenMethod method [.NET Framework debugging]
ms.assetid: fb90cb7f-af88-45e8-a99f-80a0bbddb08b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3e6ee68fe3ffed0ae19c2f528a49a863b99fa7f7
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57499554"
---
# <a name="isymunmanagedwriteropenmethod-method"></a><span data-ttu-id="d4238-102">Метод ISymUnmanagedWriter::OpenMethod</span><span class="sxs-lookup"><span data-stu-id="d4238-102">ISymUnmanagedWriter::OpenMethod Method</span></span>
<span data-ttu-id="d4238-103">Открывает метод в символ, который создается сведения.</span><span class="sxs-lookup"><span data-stu-id="d4238-103">Opens a method into which symbol information is emitted.</span></span> <span data-ttu-id="d4238-104">Данный метод становится текущим методом для вызовов с целью определения точек следования, параметров и лексические области.</span><span class="sxs-lookup"><span data-stu-id="d4238-104">The given method becomes the current method for calls to define sequence points, parameters, and lexical scopes.</span></span> <span data-ttu-id="d4238-105">Нет неявную лексическую область вокруг весь метод.</span><span class="sxs-lookup"><span data-stu-id="d4238-105">There is an implicit lexical scope around the entire method.</span></span> <span data-ttu-id="d4238-106">Повторное открытие метода, которое было ранее закрыто приведет к удалению всех ранее определенных символов для этого метода.</span><span class="sxs-lookup"><span data-stu-id="d4238-106">Reopening a method that was previously closed erases any previously defined symbols for that method.</span></span> <span data-ttu-id="d4238-107">Одновременно может существовать только один метод open.</span><span class="sxs-lookup"><span data-stu-id="d4238-107">There can be only one open method at a time.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d4238-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d4238-108">Syntax</span></span>  
  
```  
HRESULT OpenMethod(  
    [in] mdMethodDef method);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d4238-109">Параметры</span><span class="sxs-lookup"><span data-stu-id="d4238-109">Parameters</span></span>  
 `method`  
 <span data-ttu-id="d4238-110">[in] Токен метаданных для открываемого метода.</span><span class="sxs-lookup"><span data-stu-id="d4238-110">[in] The metadata token for the method to be opened.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d4238-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="d4238-111">Return Value</span></span>  
 <span data-ttu-id="d4238-112">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="d4238-112">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d4238-113">Требования</span><span class="sxs-lookup"><span data-stu-id="d4238-113">Requirements</span></span>  
 <span data-ttu-id="d4238-114">**Заголовок.** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="d4238-114">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4238-115">См. также</span><span class="sxs-lookup"><span data-stu-id="d4238-115">See also</span></span>
- [<span data-ttu-id="d4238-116">Интерфейс ISymUnmanagedWriter</span><span class="sxs-lookup"><span data-stu-id="d4238-116">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
- [<span data-ttu-id="d4238-117">Метод CloseMethod</span><span class="sxs-lookup"><span data-stu-id="d4238-117">CloseMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closemethod-method.md)
- [<span data-ttu-id="d4238-118">Метод OpenMethod2</span><span class="sxs-lookup"><span data-stu-id="d4238-118">OpenMethod2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-openmethod2-method.md)

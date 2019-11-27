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
ms.openlocfilehash: 7b13ca9884516e95e0bb922efc5bc1a845344e38
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74427916"
---
# <a name="isymunmanagedwriteropenmethod-method"></a><span data-ttu-id="a264a-102">Метод ISymUnmanagedWriter::OpenMethod</span><span class="sxs-lookup"><span data-stu-id="a264a-102">ISymUnmanagedWriter::OpenMethod Method</span></span>
<span data-ttu-id="a264a-103">Открывает метод, в который порождается символьная информация.</span><span class="sxs-lookup"><span data-stu-id="a264a-103">Opens a method into which symbol information is emitted.</span></span> <span data-ttu-id="a264a-104">Данный метод преобразуется в текущий метод для вызовов для определения точек следования, параметров и лексических областей.</span><span class="sxs-lookup"><span data-stu-id="a264a-104">The given method becomes the current method for calls to define sequence points, parameters, and lexical scopes.</span></span> <span data-ttu-id="a264a-105">Существует неявная лексическая область вокруг всего метода.</span><span class="sxs-lookup"><span data-stu-id="a264a-105">There is an implicit lexical scope around the entire method.</span></span> <span data-ttu-id="a264a-106">Повторное открытие метода, который ранее был закрыт, стирает все ранее определенные символы для этого метода.</span><span class="sxs-lookup"><span data-stu-id="a264a-106">Reopening a method that was previously closed erases any previously defined symbols for that method.</span></span> <span data-ttu-id="a264a-107">Одновременно может быть только один метод открытия.</span><span class="sxs-lookup"><span data-stu-id="a264a-107">There can be only one open method at a time.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a264a-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a264a-108">Syntax</span></span>  
  
```cpp  
HRESULT OpenMethod(  
    [in] mdMethodDef method);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a264a-109">Параметры</span><span class="sxs-lookup"><span data-stu-id="a264a-109">Parameters</span></span>  
 `method`  
 <span data-ttu-id="a264a-110">окне Токен метаданных для открываемого метода.</span><span class="sxs-lookup"><span data-stu-id="a264a-110">[in] The metadata token for the method to be opened.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a264a-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="a264a-111">Return Value</span></span>  
 <span data-ttu-id="a264a-112">S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.</span><span class="sxs-lookup"><span data-stu-id="a264a-112">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a264a-113">Требования</span><span class="sxs-lookup"><span data-stu-id="a264a-113">Requirements</span></span>  
 <span data-ttu-id="a264a-114">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="a264a-114">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a264a-115">См. также</span><span class="sxs-lookup"><span data-stu-id="a264a-115">See also</span></span>

- [<span data-ttu-id="a264a-116">Интерфейс ISymUnmanagedWriter</span><span class="sxs-lookup"><span data-stu-id="a264a-116">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
- [<span data-ttu-id="a264a-117">Метод CloseMethod</span><span class="sxs-lookup"><span data-stu-id="a264a-117">CloseMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closemethod-method.md)
- [<span data-ttu-id="a264a-118">Метод OpenMethod2</span><span class="sxs-lookup"><span data-stu-id="a264a-118">OpenMethod2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-openmethod2-method.md)

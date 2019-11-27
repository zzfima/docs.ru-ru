---
title: Метод ISymUnmanagedWriter::CloseScope
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.CloseScope
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::CloseScope
helpviewer_keywords:
- CloseScope method [.NET Framework debugging]
- ISymUnmanagedWriter::CloseScope method [.NET Framework debugging]
ms.assetid: 6dade525-7770-4cb4-bafd-4bb995ad0d87
topic_type:
- apiref
ms.openlocfilehash: 264b4487483ed5439a9809feefcdc1b20af402dc
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74428079"
---
# <a name="isymunmanagedwriterclosescope-method"></a><span data-ttu-id="3eaa7-102">Метод ISymUnmanagedWriter::CloseScope</span><span class="sxs-lookup"><span data-stu-id="3eaa7-102">ISymUnmanagedWriter::CloseScope Method</span></span>
<span data-ttu-id="3eaa7-103">Закрывает текущую лексическую область видимости.</span><span class="sxs-lookup"><span data-stu-id="3eaa7-103">Closes the current lexical scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3eaa7-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3eaa7-104">Syntax</span></span>  
  
```cpp  
HRESULT CloseScope(  
    [in] ULONG32 endOffset);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3eaa7-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="3eaa7-105">Parameters</span></span>  
 `endOffset`  
 <span data-ttu-id="3eaa7-106">окне Смещение от начала метода точки в конце последней инструкции в лексической области в байтах.</span><span class="sxs-lookup"><span data-stu-id="3eaa7-106">[in] The offset from the beginning of the method of the point at the end of the last instruction in the lexical scope, in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3eaa7-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="3eaa7-107">Return Value</span></span>  
 <span data-ttu-id="3eaa7-108">S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.</span><span class="sxs-lookup"><span data-stu-id="3eaa7-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3eaa7-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="3eaa7-109">Remarks</span></span>  
 <span data-ttu-id="3eaa7-110">После закрытия области в ней больше нельзя определять переменные.</span><span class="sxs-lookup"><span data-stu-id="3eaa7-110">Once a scope is closed, no more variables can be defined within it.</span></span>  
  
 <span data-ttu-id="3eaa7-111">[ISymUnmanagedWriter:: OpenScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openscope-method.md) возвращает непрозрачный идентификатор области, который можно использовать с [ISymUnmanagedWriter:: сетскоперанже](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-setscoperange-method.md) , чтобы определить начальное и конечное смещение области.</span><span class="sxs-lookup"><span data-stu-id="3eaa7-111">[ISymUnmanagedWriter::OpenScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openscope-method.md) returns an opaque scope identifier that can be used with [ISymUnmanagedWriter::SetScopeRange](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-setscoperange-method.md) to later define a scope's starting and ending offset.</span></span> <span data-ttu-id="3eaa7-112">В этом случае смещения, переданные методам `ISymUnmanagedWriter::OpenScope` и `ISymUnmanagedWriter::CloseScope`, пропускаются.</span><span class="sxs-lookup"><span data-stu-id="3eaa7-112">In this case, the offsets passed to `ISymUnmanagedWriter::OpenScope` and `ISymUnmanagedWriter::CloseScope` are ignored.</span></span> <span data-ttu-id="3eaa7-113">Идентификаторы областей допустимы только в текущем методе.</span><span class="sxs-lookup"><span data-stu-id="3eaa7-113">Scope identifiers are valid only in the current method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3eaa7-114">Требования</span><span class="sxs-lookup"><span data-stu-id="3eaa7-114">Requirements</span></span>  
 <span data-ttu-id="3eaa7-115">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="3eaa7-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3eaa7-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="3eaa7-116">See also</span></span>

- [<span data-ttu-id="3eaa7-117">Интерфейс ISymUnmanagedWriter</span><span class="sxs-lookup"><span data-stu-id="3eaa7-117">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)

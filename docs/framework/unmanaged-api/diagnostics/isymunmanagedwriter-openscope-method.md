---
title: Метод ISymUnmanagedWriter::OpenScope
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.OpenScope
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::OpenScope
helpviewer_keywords:
- OpenScope method, ISymUnmanagedWriter interface [.NET Framework debugging]
- ISymUnmanagedWriter::OpenScope method [.NET Framework debugging]
ms.assetid: dbea0644-3873-4329-90b8-624163e87467
topic_type:
- apiref
ms.openlocfilehash: 915b05d0d2ac611678fdcc94dd42bbb1962e6ceb
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74427896"
---
# <a name="isymunmanagedwriteropenscope-method"></a><span data-ttu-id="99c6f-102">Метод ISymUnmanagedWriter::OpenScope</span><span class="sxs-lookup"><span data-stu-id="99c6f-102">ISymUnmanagedWriter::OpenScope Method</span></span>
<span data-ttu-id="99c6f-103">Открывает новую лексическую область видимости в текущем методе.</span><span class="sxs-lookup"><span data-stu-id="99c6f-103">Opens a new lexical scope in the current method.</span></span> <span data-ttu-id="99c6f-104">Область становится новой текущей областью и помещается в стек областей.</span><span class="sxs-lookup"><span data-stu-id="99c6f-104">The scope becomes the new current scope and is pushed onto a stack of scopes.</span></span> <span data-ttu-id="99c6f-105">Области должны образовывать иерархию.</span><span class="sxs-lookup"><span data-stu-id="99c6f-105">Scopes must form a hierarchy.</span></span> <span data-ttu-id="99c6f-106">Не допускается перекрытие одноуровневых элементов.</span><span class="sxs-lookup"><span data-stu-id="99c6f-106">Siblings are not allowed to overlap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99c6f-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="99c6f-107">Syntax</span></span>  
  
```cpp  
HRESULT OpenScope(  
    [in] ULONG32 startOffset,  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="99c6f-108">Параметры</span><span class="sxs-lookup"><span data-stu-id="99c6f-108">Parameters</span></span>  
 `startOffset`  
 <span data-ttu-id="99c6f-109">окне Смещение первой инструкции в лексической области в байтах от начала метода.</span><span class="sxs-lookup"><span data-stu-id="99c6f-109">[in] The offset of the first instruction in the lexical scope, in bytes, from the beginning of the method.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="99c6f-110">заполняет Указатель на `ULONG32`, который получает идентификатор области.</span><span class="sxs-lookup"><span data-stu-id="99c6f-110">[out] A pointer to a `ULONG32` that receives the scope identifier.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="99c6f-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="99c6f-111">Return Value</span></span>  
 <span data-ttu-id="99c6f-112">S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.</span><span class="sxs-lookup"><span data-stu-id="99c6f-112">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="99c6f-113">Примечания</span><span class="sxs-lookup"><span data-stu-id="99c6f-113">Remarks</span></span>  
 <span data-ttu-id="99c6f-114">`ISymUnmanagedWriter::OpenScope` возвращает непрозрачный идентификатор области, который можно использовать с [ISymUnmanagedWriter:: сетскоперанже](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-setscoperange-method.md) для определения начального и конечного смещения области в более позднее время.</span><span class="sxs-lookup"><span data-stu-id="99c6f-114">`ISymUnmanagedWriter::OpenScope` returns an opaque scope identifier that can be used with [ISymUnmanagedWriter::SetScopeRange](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-setscoperange-method.md) to define a scope's starting and ending offset at a later time.</span></span> <span data-ttu-id="99c6f-115">В этом случае смещения, передаваемые в `ISymUnmanagedWriter::OpenScope` и [ISymUnmanagedWriter:: CloseScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closescope-method.md) , игнорируются.</span><span class="sxs-lookup"><span data-stu-id="99c6f-115">In this case, the offsets passed to `ISymUnmanagedWriter::OpenScope` and [ISymUnmanagedWriter::CloseScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closescope-method.md) are ignored.</span></span> <span data-ttu-id="99c6f-116">Идентификаторы областей допустимы только в текущем методе.</span><span class="sxs-lookup"><span data-stu-id="99c6f-116">Scope identifiers are valid only in the current method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="99c6f-117">Требования</span><span class="sxs-lookup"><span data-stu-id="99c6f-117">Requirements</span></span>  
 <span data-ttu-id="99c6f-118">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="99c6f-118">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99c6f-119">См. также:</span><span class="sxs-lookup"><span data-stu-id="99c6f-119">See also</span></span>

- [<span data-ttu-id="99c6f-120">Интерфейс ISymUnmanagedWriter</span><span class="sxs-lookup"><span data-stu-id="99c6f-120">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)

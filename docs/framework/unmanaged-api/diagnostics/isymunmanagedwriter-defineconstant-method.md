---
title: Метод ISymUnmanagedWriter::DefineConstant
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.DefineConstant
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::DefineConstant
helpviewer_keywords:
- DefineConstant method [.NET Framework debugging]
- ISymUnmanagedWriter::DefineConstant method [.NET Framework debugging]
ms.assetid: 9e986986-2223-4d5f-b040-85d716146924
topic_type:
- apiref
ms.openlocfilehash: c8d0145b9dffe1c0ff6ed3281c90f3bcec082ab8
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74428061"
---
# <a name="isymunmanagedwriterdefineconstant-method"></a><span data-ttu-id="c215c-102">Метод ISymUnmanagedWriter::DefineConstant</span><span class="sxs-lookup"><span data-stu-id="c215c-102">ISymUnmanagedWriter::DefineConstant Method</span></span>
<span data-ttu-id="c215c-103">Определяет имя для постоянного значения.</span><span class="sxs-lookup"><span data-stu-id="c215c-103">Defines a name for a constant value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c215c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c215c-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineConstant(  
    [in] const WCHAR *name,  
    [in] VARIANT value,  
    [in] ULONG32 cSig,  
    [in, size_is(cSig)] unsigned char signature[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c215c-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c215c-105">Parameters</span></span>  
 `name`  
 <span data-ttu-id="c215c-106">окне Указатель на `WCHAR`, который определяет имя константы.</span><span class="sxs-lookup"><span data-stu-id="c215c-106">[in] A pointer to a `WCHAR` that defines the constant name.</span></span>  
  
 `value`  
 <span data-ttu-id="c215c-107">окне Значение константы.</span><span class="sxs-lookup"><span data-stu-id="c215c-107">[in] The value of the constant.</span></span>  
  
 `cSig`  
 <span data-ttu-id="c215c-108">[in] Размер массива `signature`.</span><span class="sxs-lookup"><span data-stu-id="c215c-108">[in] The size of the `signature` array.</span></span>  
  
 `signature`  
 <span data-ttu-id="c215c-109">окне Сигнатура типа для константы.</span><span class="sxs-lookup"><span data-stu-id="c215c-109">[in] The type signature for the constant.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c215c-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="c215c-110">Return Value</span></span>  
 <span data-ttu-id="c215c-111">S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.</span><span class="sxs-lookup"><span data-stu-id="c215c-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c215c-112">Требования</span><span class="sxs-lookup"><span data-stu-id="c215c-112">Requirements</span></span>  
 <span data-ttu-id="c215c-113">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="c215c-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c215c-114">См. также</span><span class="sxs-lookup"><span data-stu-id="c215c-114">See also</span></span>

- [<span data-ttu-id="c215c-115">Интерфейс ISymUnmanagedWriter</span><span class="sxs-lookup"><span data-stu-id="c215c-115">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
- [<span data-ttu-id="c215c-116">Метод DefineConstant2</span><span class="sxs-lookup"><span data-stu-id="c215c-116">DefineConstant2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-defineconstant2-method.md)

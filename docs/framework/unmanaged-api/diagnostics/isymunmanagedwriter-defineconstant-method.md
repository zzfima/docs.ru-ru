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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7f470dbe4ef2ef0d5f2204ccbdd5fb64730f9a2c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61930108"
---
# <a name="isymunmanagedwriterdefineconstant-method"></a><span data-ttu-id="d786b-102">Метод ISymUnmanagedWriter::DefineConstant</span><span class="sxs-lookup"><span data-stu-id="d786b-102">ISymUnmanagedWriter::DefineConstant Method</span></span>
<span data-ttu-id="d786b-103">Определяет имя для значения константы.</span><span class="sxs-lookup"><span data-stu-id="d786b-103">Defines a name for a constant value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d786b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d786b-104">Syntax</span></span>  
  
```  
HRESULT DefineConstant(  
    [in] const WCHAR *name,  
    [in] VARIANT value,  
    [in] ULONG32 cSig,  
    [in, size_is(cSig)] unsigned char signature[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d786b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="d786b-105">Parameters</span></span>  
 `name`  
 <span data-ttu-id="d786b-106">[in] Указатель на `WCHAR` , определяющий имя константы.</span><span class="sxs-lookup"><span data-stu-id="d786b-106">[in] A pointer to a `WCHAR` that defines the constant name.</span></span>  
  
 `value`  
 <span data-ttu-id="d786b-107">[in] Значение константы.</span><span class="sxs-lookup"><span data-stu-id="d786b-107">[in] The value of the constant.</span></span>  
  
 `cSig`  
 <span data-ttu-id="d786b-108">[in] Размер массива `signature`.</span><span class="sxs-lookup"><span data-stu-id="d786b-108">[in] The size of the `signature` array.</span></span>  
  
 `signature`  
 <span data-ttu-id="d786b-109">[in] Сигнатура типа для константы.</span><span class="sxs-lookup"><span data-stu-id="d786b-109">[in] The type signature for the constant.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d786b-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="d786b-110">Return Value</span></span>  
 <span data-ttu-id="d786b-111">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="d786b-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d786b-112">Требования</span><span class="sxs-lookup"><span data-stu-id="d786b-112">Requirements</span></span>  
 <span data-ttu-id="d786b-113">**Заголовок.** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="d786b-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d786b-114">См. также</span><span class="sxs-lookup"><span data-stu-id="d786b-114">See also</span></span>

- [<span data-ttu-id="d786b-115">Интерфейс ISymUnmanagedWriter</span><span class="sxs-lookup"><span data-stu-id="d786b-115">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
- [<span data-ttu-id="d786b-116">Метод DefineConstant2</span><span class="sxs-lookup"><span data-stu-id="d786b-116">DefineConstant2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-defineconstant2-method.md)

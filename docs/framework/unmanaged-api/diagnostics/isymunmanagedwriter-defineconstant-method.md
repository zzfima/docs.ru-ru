---
title: "Метод ISymUnmanagedWriter::DefineConstant"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedWriter.DefineConstant
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedWriter::DefineConstant
helpviewer_keywords:
- DefineConstant method [.NET Framework debugging]
- ISymUnmanagedWriter::DefineConstant method [.NET Framework debugging]
ms.assetid: 9e986986-2223-4d5f-b040-85d716146924
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9b22b0d9c9de27ba9950a0501193bc682586bfbc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedwriterdefineconstant-method"></a><span data-ttu-id="b275b-102">Метод ISymUnmanagedWriter::DefineConstant</span><span class="sxs-lookup"><span data-stu-id="b275b-102">ISymUnmanagedWriter::DefineConstant Method</span></span>
<span data-ttu-id="b275b-103">Определяет имя для постоянного значения.</span><span class="sxs-lookup"><span data-stu-id="b275b-103">Defines a name for a constant value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b275b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b275b-104">Syntax</span></span>  
  
```  
HRESULT DefineConstant(  
    [in] const WCHAR *name,  
    [in] VARIANT value,  
    [in] ULONG32 cSig,  
    [in, size_is(cSig)] unsigned char signature[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b275b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="b275b-105">Parameters</span></span>  
 `name`  
 <span data-ttu-id="b275b-106">[in] Указатель на `WCHAR` , определяющий имя константы.</span><span class="sxs-lookup"><span data-stu-id="b275b-106">[in] A pointer to a `WCHAR` that defines the constant name.</span></span>  
  
 `value`  
 <span data-ttu-id="b275b-107">[in] Значение константы.</span><span class="sxs-lookup"><span data-stu-id="b275b-107">[in] The value of the constant.</span></span>  
  
 `cSig`  
 <span data-ttu-id="b275b-108">[in] Размер массива `signature`.</span><span class="sxs-lookup"><span data-stu-id="b275b-108">[in] The size of the `signature` array.</span></span>  
  
 `signature`  
 <span data-ttu-id="b275b-109">[in] Сигнатура типа константы.</span><span class="sxs-lookup"><span data-stu-id="b275b-109">[in] The type signature for the constant.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b275b-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="b275b-110">Return Value</span></span>  
 <span data-ttu-id="b275b-111">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="b275b-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b275b-112">Требования</span><span class="sxs-lookup"><span data-stu-id="b275b-112">Requirements</span></span>  
 <span data-ttu-id="b275b-113">**Заголовок:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="b275b-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b275b-114">См. также</span><span class="sxs-lookup"><span data-stu-id="b275b-114">See Also</span></span>  
 [<span data-ttu-id="b275b-115">Интерфейс ISymUnmanagedWriter</span><span class="sxs-lookup"><span data-stu-id="b275b-115">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)  
 [<span data-ttu-id="b275b-116">Метод DefineConstant2</span><span class="sxs-lookup"><span data-stu-id="b275b-116">DefineConstant2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-defineconstant2-method.md)

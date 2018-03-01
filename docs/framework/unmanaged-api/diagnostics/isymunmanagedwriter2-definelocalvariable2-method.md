---
title: "Метод ISymUnmanagedWriter2::DefineLocalVariable2"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ISymUnmanagedWriter2.DefineLocalVariable2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter2::DefineLocalVariable2
helpviewer_keywords:
- ISymUnmanagedWriter2::DefineLocalVariable2 method [.NET Framework debugging]
- DefineLocalVariable2 method [.NET Framework debugging]
ms.assetid: e774eefe-858c-4362-8d2d-28ebf2ba1a24
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 1124b57bed16e349c753be872c1b709a287e6237
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedwriter2definelocalvariable2-method"></a><span data-ttu-id="bfb79-102">Метод ISymUnmanagedWriter2::DefineLocalVariable2</span><span class="sxs-lookup"><span data-stu-id="bfb79-102">ISymUnmanagedWriter2::DefineLocalVariable2 Method</span></span>
<span data-ttu-id="bfb79-103">Определяет одну переменную в текущей лексической области видимости.</span><span class="sxs-lookup"><span data-stu-id="bfb79-103">Defines a single variable in the current lexical scope.</span></span> <span data-ttu-id="bfb79-104">Этот метод может вызываться несколько раз для переменной с тем же именем, имеющей несколько корневых в пределах области.</span><span class="sxs-lookup"><span data-stu-id="bfb79-104">This method can be called multiple times for a variable of the same name that has multiple homes throughout a scope.</span></span> <span data-ttu-id="bfb79-105">В этом случае, однако значения `startOffset` и `endOffset` параметров не должны перекрываться.</span><span class="sxs-lookup"><span data-stu-id="bfb79-105">In this case, however, the values of the `startOffset` and `endOffset` parameters must not overlap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bfb79-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bfb79-106">Syntax</span></span>  
  
```  
HRESULT DefineLocalVariable2(  
    [in] const WCHAR  *name,  
    [in] ULONG32      attributes,  
    [in] mdSignature  sigToken,  
    [in] ULONG32      addrKind,  
    [in] ULONG32      addr1,  
    [in] ULONG32      addr2,  
    [in] ULONG32      addr3,  
    [in] ULONG32      startOffset,  
    [in] ULONG32      endOffset);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="bfb79-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="bfb79-107">Parameters</span></span>  
 `name`  
 <span data-ttu-id="bfb79-108">[in] Имя локальной переменной.</span><span class="sxs-lookup"><span data-stu-id="bfb79-108">[in] The local variable name.</span></span>  
  
 `attributes`  
 <span data-ttu-id="bfb79-109">[in] Атрибуты локальной переменной.</span><span class="sxs-lookup"><span data-stu-id="bfb79-109">[in] The local variable attributes.</span></span>  
  
 `sigToken`  
 <span data-ttu-id="bfb79-110">[in] Токен метаданных подписи.</span><span class="sxs-lookup"><span data-stu-id="bfb79-110">[in] The metadata token of the signature.</span></span>  
  
 `addrKind`  
 <span data-ttu-id="bfb79-111">[in] Тип адреса.</span><span class="sxs-lookup"><span data-stu-id="bfb79-111">[in] The address type.</span></span>  
  
 `addr1`  
 <span data-ttu-id="bfb79-112">[in] Первый адрес для спецификации параметра.</span><span class="sxs-lookup"><span data-stu-id="bfb79-112">[in] The first address for the parameter specification.</span></span>  
  
 `addr2`  
 <span data-ttu-id="bfb79-113">[in] Второй адрес для спецификации параметра.</span><span class="sxs-lookup"><span data-stu-id="bfb79-113">[in] The second address for the parameter specification.</span></span>  
  
 `addr3`  
 <span data-ttu-id="bfb79-114">[in] Третий адрес для спецификации параметра.</span><span class="sxs-lookup"><span data-stu-id="bfb79-114">[in] The third address for the parameter specification.</span></span>  
  
 `startOffset`  
 <span data-ttu-id="bfb79-115">[in] Начальное смещение для переменной.</span><span class="sxs-lookup"><span data-stu-id="bfb79-115">[in] The start offset for the variable.</span></span> <span data-ttu-id="bfb79-116">Этот параметр является необязательным.</span><span class="sxs-lookup"><span data-stu-id="bfb79-116">This parameter is optional.</span></span> <span data-ttu-id="bfb79-117">Если задано значение 0, этот параметр пропускается и переменная определяется для всей области.</span><span class="sxs-lookup"><span data-stu-id="bfb79-117">If it is 0, this parameter is ignored and the variable is defined throughout the entire scope.</span></span> <span data-ttu-id="bfb79-118">Если ненулевое значение, переменная находится в границах смещений текущей области.</span><span class="sxs-lookup"><span data-stu-id="bfb79-118">If it is a nonzero value, the variable falls within the offsets of the current scope.</span></span>  
  
 `endOffset`  
 <span data-ttu-id="bfb79-119">[in] Конечное смещение для переменной.</span><span class="sxs-lookup"><span data-stu-id="bfb79-119">[in] The end offset for the variable.</span></span> <span data-ttu-id="bfb79-120">Этот параметр является необязательным.</span><span class="sxs-lookup"><span data-stu-id="bfb79-120">This parameter is optional.</span></span> <span data-ttu-id="bfb79-121">Если задано значение 0, этот параметр пропускается и переменная определяется для всей области.</span><span class="sxs-lookup"><span data-stu-id="bfb79-121">If it is 0, this parameter is ignored and the variable is defined throughout the entire scope.</span></span> <span data-ttu-id="bfb79-122">Если ненулевое значение, переменная находится в границах смещений текущей области.</span><span class="sxs-lookup"><span data-stu-id="bfb79-122">If it is a nonzero value, the variable falls within the offsets of the current scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bfb79-123">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="bfb79-123">Return Value</span></span>  
 <span data-ttu-id="bfb79-124">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="bfb79-124">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bfb79-125">Требования</span><span class="sxs-lookup"><span data-stu-id="bfb79-125">Requirements</span></span>  
 <span data-ttu-id="bfb79-126">**Заголовок:** CorSym.idl</span><span class="sxs-lookup"><span data-stu-id="bfb79-126">**Header:** CorSym.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bfb79-127">См. также</span><span class="sxs-lookup"><span data-stu-id="bfb79-127">See Also</span></span>  
 [<span data-ttu-id="bfb79-128">Интерфейс ISymUnmanagedWriter2</span><span class="sxs-lookup"><span data-stu-id="bfb79-128">ISymUnmanagedWriter2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-interface.md)  
 [<span data-ttu-id="bfb79-129">Метод DefineLocalVariable</span><span class="sxs-lookup"><span data-stu-id="bfb79-129">DefineLocalVariable Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-definelocalvariable-method.md)

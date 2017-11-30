---
title: "Метод ISymUnmanagedWriter2::DefineLocalVariable2"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedWriter2.DefineLocalVariable2
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedWriter2::DefineLocalVariable2
helpviewer_keywords:
- ISymUnmanagedWriter2::DefineLocalVariable2 method [.NET Framework debugging]
- DefineLocalVariable2 method [.NET Framework debugging]
ms.assetid: e774eefe-858c-4362-8d2d-28ebf2ba1a24
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 595cc3d8c503a5a6b2cbcb6665f7ff8aff5044d7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="isymunmanagedwriter2definelocalvariable2-method"></a><span data-ttu-id="0c990-102">Метод ISymUnmanagedWriter2::DefineLocalVariable2</span><span class="sxs-lookup"><span data-stu-id="0c990-102">ISymUnmanagedWriter2::DefineLocalVariable2 Method</span></span>
<span data-ttu-id="0c990-103">Определяет одну переменную в текущей лексической области видимости.</span><span class="sxs-lookup"><span data-stu-id="0c990-103">Defines a single variable in the current lexical scope.</span></span> <span data-ttu-id="0c990-104">Этот метод может вызываться несколько раз для переменной с тем же именем, имеющей несколько корневых в пределах области.</span><span class="sxs-lookup"><span data-stu-id="0c990-104">This method can be called multiple times for a variable of the same name that has multiple homes throughout a scope.</span></span> <span data-ttu-id="0c990-105">В этом случае, однако значения `startOffset` и `endOffset` параметров не должны перекрываться.</span><span class="sxs-lookup"><span data-stu-id="0c990-105">In this case, however, the values of the `startOffset` and `endOffset` parameters must not overlap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0c990-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0c990-106">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="0c990-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="0c990-107">Parameters</span></span>  
 `name`  
 <span data-ttu-id="0c990-108">[in] Имя локальной переменной.</span><span class="sxs-lookup"><span data-stu-id="0c990-108">[in] The local variable name.</span></span>  
  
 `attributes`  
 <span data-ttu-id="0c990-109">[in] Атрибуты локальной переменной.</span><span class="sxs-lookup"><span data-stu-id="0c990-109">[in] The local variable attributes.</span></span>  
  
 `sigToken`  
 <span data-ttu-id="0c990-110">[in] Токен метаданных подписи.</span><span class="sxs-lookup"><span data-stu-id="0c990-110">[in] The metadata token of the signature.</span></span>  
  
 `addrKind`  
 <span data-ttu-id="0c990-111">[in] Тип адреса.</span><span class="sxs-lookup"><span data-stu-id="0c990-111">[in] The address type.</span></span>  
  
 `addr1`  
 <span data-ttu-id="0c990-112">[in] Первый адрес для спецификации параметра.</span><span class="sxs-lookup"><span data-stu-id="0c990-112">[in] The first address for the parameter specification.</span></span>  
  
 `addr2`  
 <span data-ttu-id="0c990-113">[in] Второй адрес для спецификации параметра.</span><span class="sxs-lookup"><span data-stu-id="0c990-113">[in] The second address for the parameter specification.</span></span>  
  
 `addr3`  
 <span data-ttu-id="0c990-114">[in] Третий адрес для спецификации параметра.</span><span class="sxs-lookup"><span data-stu-id="0c990-114">[in] The third address for the parameter specification.</span></span>  
  
 `startOffset`  
 <span data-ttu-id="0c990-115">[in] Начальное смещение для переменной.</span><span class="sxs-lookup"><span data-stu-id="0c990-115">[in] The start offset for the variable.</span></span> <span data-ttu-id="0c990-116">Этот параметр является необязательным.</span><span class="sxs-lookup"><span data-stu-id="0c990-116">This parameter is optional.</span></span> <span data-ttu-id="0c990-117">Если задано значение 0, этот параметр пропускается и переменная определяется для всей области.</span><span class="sxs-lookup"><span data-stu-id="0c990-117">If it is 0, this parameter is ignored and the variable is defined throughout the entire scope.</span></span> <span data-ttu-id="0c990-118">Если ненулевое значение, переменная находится в границах смещений текущей области.</span><span class="sxs-lookup"><span data-stu-id="0c990-118">If it is a nonzero value, the variable falls within the offsets of the current scope.</span></span>  
  
 `endOffset`  
 <span data-ttu-id="0c990-119">[in] Конечное смещение для переменной.</span><span class="sxs-lookup"><span data-stu-id="0c990-119">[in] The end offset for the variable.</span></span> <span data-ttu-id="0c990-120">Этот параметр является необязательным.</span><span class="sxs-lookup"><span data-stu-id="0c990-120">This parameter is optional.</span></span> <span data-ttu-id="0c990-121">Если задано значение 0, этот параметр пропускается и переменная определяется для всей области.</span><span class="sxs-lookup"><span data-stu-id="0c990-121">If it is 0, this parameter is ignored and the variable is defined throughout the entire scope.</span></span> <span data-ttu-id="0c990-122">Если ненулевое значение, переменная находится в границах смещений текущей области.</span><span class="sxs-lookup"><span data-stu-id="0c990-122">If it is a nonzero value, the variable falls within the offsets of the current scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0c990-123">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="0c990-123">Return Value</span></span>  
 <span data-ttu-id="0c990-124">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="0c990-124">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0c990-125">Требования</span><span class="sxs-lookup"><span data-stu-id="0c990-125">Requirements</span></span>  
 <span data-ttu-id="0c990-126">**Заголовок:** CorSym.idl</span><span class="sxs-lookup"><span data-stu-id="0c990-126">**Header:** CorSym.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c990-127">См. также</span><span class="sxs-lookup"><span data-stu-id="0c990-127">See Also</span></span>  
 [<span data-ttu-id="0c990-128">Интерфейс ISymUnmanagedWriter2</span><span class="sxs-lookup"><span data-stu-id="0c990-128">ISymUnmanagedWriter2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-interface.md)  
 [<span data-ttu-id="0c990-129">Метод DefineLocalVariable</span><span class="sxs-lookup"><span data-stu-id="0c990-129">DefineLocalVariable Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-definelocalvariable-method.md)

---
title: "Метод ISymUnmanagedWriter::DefineLocalVariable"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedWriter.DefineLocalVariable
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedWriter::DefineLocalVariable
helpviewer_keywords:
- ISymUnmanagedWriter::DefineLocalVariable method [.NET Framework debugging]
- DefineLocalVariable method [.NET Framework debugging]
ms.assetid: 6fab8a58-3883-490f-8b27-64042c90f104
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 89ea3e23166b4745b34b7c2af498d29564cdd68d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedwriterdefinelocalvariable-method"></a><span data-ttu-id="c13ac-102">Метод ISymUnmanagedWriter::DefineLocalVariable</span><span class="sxs-lookup"><span data-stu-id="c13ac-102">ISymUnmanagedWriter::DefineLocalVariable Method</span></span>
<span data-ttu-id="c13ac-103">Определяет одну переменную в текущей лексической области видимости.</span><span class="sxs-lookup"><span data-stu-id="c13ac-103">Defines a single variable in the current lexical scope.</span></span> <span data-ttu-id="c13ac-104">Этот метод может вызываться несколько раз для переменной с тем же именем, имеющей несколько корневых в пределах области.</span><span class="sxs-lookup"><span data-stu-id="c13ac-104">This method can be called multiple times for a variable of the same name that has multiple homes throughout a scope.</span></span> <span data-ttu-id="c13ac-105">В этом случае, однако значения `startOffset` и `endOffset` параметров не должны перекрываться.</span><span class="sxs-lookup"><span data-stu-id="c13ac-105">In this case, however, the values of the `startOffset` and `endOffset` parameters must not overlap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c13ac-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c13ac-106">Syntax</span></span>  
  
```  
HRESULT DefineLocalVariable(  
    [in] const WCHAR  *name,  
    [in] ULONG32      attributes,  
    [in] ULONG32      cSig,  
    [in, size_is(cSig)] unsigned char signature[],  
    [in] ULONG32      addrKind,  
    [in] ULONG32      addr1,  
    [in] ULONG32      addr2,  
    [in] ULONG32      addr3,  
    [in] ULONG32      startOffset,  
    [in] ULONG32      endOffset);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c13ac-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="c13ac-107">Parameters</span></span>  
 `name`  
 <span data-ttu-id="c13ac-108">[in] Указатель на `WCHAR` , определяющий имя локальной переменной.</span><span class="sxs-lookup"><span data-stu-id="c13ac-108">[in] A pointer to a `WCHAR` that defines the local variable name.</span></span>  
  
 `attributes`  
 <span data-ttu-id="c13ac-109">[in] Атрибуты локальной переменной.</span><span class="sxs-lookup"><span data-stu-id="c13ac-109">[in] The local variable attributes.</span></span>  
  
 `cSig`  
 <span data-ttu-id="c13ac-110">[in] Объект `ULONG32` указывает размер в байтах для `signature` буфера.</span><span class="sxs-lookup"><span data-stu-id="c13ac-110">[in] A `ULONG32` that indicates the size, in bytes, of the `signature` buffer.</span></span>  
  
 `signature`  
 <span data-ttu-id="c13ac-111">[in] Подпись локальной переменной.</span><span class="sxs-lookup"><span data-stu-id="c13ac-111">[in] The local variable signature.</span></span>  
  
 `addrKind`  
 <span data-ttu-id="c13ac-112">[in] Тип адреса.</span><span class="sxs-lookup"><span data-stu-id="c13ac-112">[in] The address type.</span></span>  
  
 `addr1`  
 <span data-ttu-id="c13ac-113">[in] Первый адрес для спецификации параметра.</span><span class="sxs-lookup"><span data-stu-id="c13ac-113">[in] The first address for the parameter specification.</span></span>  
  
 `addr2`  
 <span data-ttu-id="c13ac-114">[in] Второй адрес для спецификации параметра.</span><span class="sxs-lookup"><span data-stu-id="c13ac-114">[in] The second address for the parameter specification.</span></span>  
  
 `addr3`  
 <span data-ttu-id="c13ac-115">[in] Третий адрес для спецификации параметра.</span><span class="sxs-lookup"><span data-stu-id="c13ac-115">[in] The third address for the parameter specification.</span></span>  
  
 `startOffset`  
 <span data-ttu-id="c13ac-116">[in] Начальное смещение для переменной.</span><span class="sxs-lookup"><span data-stu-id="c13ac-116">[in] The start offset for the variable.</span></span> <span data-ttu-id="c13ac-117">Этот параметр является необязательным.</span><span class="sxs-lookup"><span data-stu-id="c13ac-117">This parameter is optional.</span></span> <span data-ttu-id="c13ac-118">Если задано значение 0, этот параметр пропускается и переменная определяется для всей области.</span><span class="sxs-lookup"><span data-stu-id="c13ac-118">If it is 0, this parameter is ignored and the variable is defined throughout the entire scope.</span></span> <span data-ttu-id="c13ac-119">Если ненулевое значение, переменная находится в границах смещений текущей области.</span><span class="sxs-lookup"><span data-stu-id="c13ac-119">If it is a nonzero value, the variable falls within the offsets of the current scope.</span></span>  
  
 `endOffset`  
 <span data-ttu-id="c13ac-120">[in] Конечное смещение для переменной.</span><span class="sxs-lookup"><span data-stu-id="c13ac-120">[in] The end offset for the variable.</span></span> <span data-ttu-id="c13ac-121">Этот параметр является необязательным.</span><span class="sxs-lookup"><span data-stu-id="c13ac-121">This parameter is optional.</span></span> <span data-ttu-id="c13ac-122">Если задано значение 0, этот параметр пропускается и переменная определяется для всей области.</span><span class="sxs-lookup"><span data-stu-id="c13ac-122">If it is 0, this parameter is ignored and the variable is defined throughout the entire scope.</span></span> <span data-ttu-id="c13ac-123">Если ненулевое значение, переменная находится в границах смещений текущей области.</span><span class="sxs-lookup"><span data-stu-id="c13ac-123">If it is a nonzero value, the variable falls within the offsets of the current scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c13ac-124">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="c13ac-124">Return Value</span></span>  
 <span data-ttu-id="c13ac-125">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="c13ac-125">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c13ac-126">Требования</span><span class="sxs-lookup"><span data-stu-id="c13ac-126">Requirements</span></span>  
 <span data-ttu-id="c13ac-127">**Заголовок:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="c13ac-127">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c13ac-128">См. также</span><span class="sxs-lookup"><span data-stu-id="c13ac-128">See Also</span></span>  
 [<span data-ttu-id="c13ac-129">Интерфейс ISymUnmanagedWriter</span><span class="sxs-lookup"><span data-stu-id="c13ac-129">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)  
 [<span data-ttu-id="c13ac-130">Метод DefineGlobalVariable</span><span class="sxs-lookup"><span data-stu-id="c13ac-130">DefineGlobalVariable Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-defineglobalvariable-method.md)  
 [<span data-ttu-id="c13ac-131">Метод DefineLocalVariable2</span><span class="sxs-lookup"><span data-stu-id="c13ac-131">DefineLocalVariable2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-definelocalvariable2-method.md)

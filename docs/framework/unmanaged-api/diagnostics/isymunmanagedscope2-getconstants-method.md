---
title: "Метод ISymUnmanagedScope2::GetConstants"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedScope2.GetConstants
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedScope2::GetConstants
helpviewer_keywords:
- ISymUnmanagedScope2::GetConstants method [.NET Framework debugging]
- GetConstants method [.NET Framework debugging]
ms.assetid: f241b620-9ec5-42fd-92ef-3b22329db72a
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: da0d2d39fcc1de8435c7af49a912764c79eb6583
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedscope2getconstants-method"></a><span data-ttu-id="10abd-102">Метод ISymUnmanagedScope2::GetConstants</span><span class="sxs-lookup"><span data-stu-id="10abd-102">ISymUnmanagedScope2::GetConstants Method</span></span>
<span data-ttu-id="10abd-103">Получает локальные константы, определенные в этой области.</span><span class="sxs-lookup"><span data-stu-id="10abd-103">Gets the local constants defined within this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="10abd-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="10abd-104">Syntax</span></span>  
  
```  
HRESULT GetConstants(  
     [in]  ULONG32  cConstants,  
     [out] ULONG32  *pcConstants,  
     [out, size_is(cConstants),  
         length_is(*pcConstants)] ISymUnmanagedConstant*   
             constants[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="10abd-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="10abd-105">Parameters</span></span>  
 `cConstants`  
 <span data-ttu-id="10abd-106">[in] Длина буфера, `pcConstants` указывает параметр.</span><span class="sxs-lookup"><span data-stu-id="10abd-106">[in] The length of the buffer that the `pcConstants` parameter points to.</span></span>  
  
 `pcConstants`  
 <span data-ttu-id="10abd-107">[out] Указатель на `ULONG32` , получающий размер в символах, буфера, необходимый для хранения констант.</span><span class="sxs-lookup"><span data-stu-id="10abd-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the constants.</span></span>  
  
 `constants`  
 <span data-ttu-id="10abd-108">[out] Буфера, хранящего константы.</span><span class="sxs-lookup"><span data-stu-id="10abd-108">[out] The buffer that stores the constants.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="10abd-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="10abd-109">Return Value</span></span>  
 <span data-ttu-id="10abd-110">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="10abd-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="10abd-111">Требования</span><span class="sxs-lookup"><span data-stu-id="10abd-111">Requirements</span></span>  
 <span data-ttu-id="10abd-112">**Заголовок:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="10abd-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10abd-113">См. также</span><span class="sxs-lookup"><span data-stu-id="10abd-113">See Also</span></span>  
 [<span data-ttu-id="10abd-114">Интерфейс ISymUnmanagedScope2</span><span class="sxs-lookup"><span data-stu-id="10abd-114">ISymUnmanagedScope2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope2-interface.md)

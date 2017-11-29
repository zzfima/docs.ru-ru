---
title: "Метод ISymUnmanagedReader::GetMethod"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedReader.GetMethod
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedReader::GetMethod
helpviewer_keywords:
- GetMethod method, ISymUnmanagedReader interface [.NET Framework debugging]
- ISymUnmanagedReader::GetMethod method [.NET Framework debugging]
ms.assetid: ae6cfb29-bc2c-4606-af86-1d32ebd31020
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 94c40555ee62bac99cf7cb34378c5b0fcca5104f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedreadergetmethod-method"></a><span data-ttu-id="54150-102">Метод ISymUnmanagedReader::GetMethod</span><span class="sxs-lookup"><span data-stu-id="54150-102">ISymUnmanagedReader::GetMethod Method</span></span>
<span data-ttu-id="54150-103">Возвращает метод средства чтения символов, маркер метода.</span><span class="sxs-lookup"><span data-stu-id="54150-103">Gets a symbol reader method, given a method token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="54150-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="54150-104">Syntax</span></span>  
  
```  
HRESULT GetMethod (  
    [in]  mdMethodDef  token,  
    [out, retval] ISymUnmanagedMethod**  pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="54150-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="54150-105">Parameters</span></span>  
 `token`  
 <span data-ttu-id="54150-106">[in] Маркер метода.</span><span class="sxs-lookup"><span data-stu-id="54150-106">[in] The method token.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="54150-107">[out] Указатель на возвращенный интерфейс.</span><span class="sxs-lookup"><span data-stu-id="54150-107">[out] A pointer to the returned interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="54150-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="54150-108">Return Value</span></span>  
 <span data-ttu-id="54150-109">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="54150-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="54150-110">Требования</span><span class="sxs-lookup"><span data-stu-id="54150-110">Requirements</span></span>  
 <span data-ttu-id="54150-111">**Заголовок:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="54150-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54150-112">См. также</span><span class="sxs-lookup"><span data-stu-id="54150-112">See Also</span></span>  
 [<span data-ttu-id="54150-113">ISymUnmanagedReader-интерфейс</span><span class="sxs-lookup"><span data-stu-id="54150-113">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)

---
title: "Метод ISymENCUnmanagedMethod::GetDocumentsForMethodCount"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymENCUnmanagedMethod.GetDocumentsForMethodCount
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymENCUnmanagedMethod::GetDocumentsForMethodCount
helpviewer_keywords:
- GetDocumentsForMethodCount method [.NET Framework debugging]
- ISymENCUnmanagedMethod::GetDocumentsForMethodCount method [.NET Framework debugging]
ms.assetid: cc1a823a-3ff3-4a33-b641-96edc93d2b17
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 49b849ced80d526ed529bad1eaa766d5a2a19d51
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="isymencunmanagedmethodgetdocumentsformethodcount-method"></a><span data-ttu-id="d8bb0-102">Метод ISymENCUnmanagedMethod::GetDocumentsForMethodCount</span><span class="sxs-lookup"><span data-stu-id="d8bb0-102">ISymENCUnmanagedMethod::GetDocumentsForMethodCount Method</span></span>
<span data-ttu-id="d8bb0-103">Возвращает количество документов, этот метод имеет строки.</span><span class="sxs-lookup"><span data-stu-id="d8bb0-103">Gets the number of documents that this method has lines in.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d8bb0-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d8bb0-104">Syntax</span></span>  
  
```  
HRESULT GetDocumentsForMethodCount(  
    [out, retval] ULONG32* pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d8bb0-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="d8bb0-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="d8bb0-106">[out] Указатель на `ULONG32` , получающий размер буфера, необходимый для хранения документов.</span><span class="sxs-lookup"><span data-stu-id="d8bb0-106">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the documents.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d8bb0-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="d8bb0-107">Return Value</span></span>  
 <span data-ttu-id="d8bb0-108">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="d8bb0-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d8bb0-109">Требования</span><span class="sxs-lookup"><span data-stu-id="d8bb0-109">Requirements</span></span>  
 <span data-ttu-id="d8bb0-110">**Заголовок:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="d8bb0-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8bb0-111">См. также</span><span class="sxs-lookup"><span data-stu-id="d8bb0-111">See Also</span></span>  
 [<span data-ttu-id="d8bb0-112">Интерфейс ISymENCUnmanagedMethod</span><span class="sxs-lookup"><span data-stu-id="d8bb0-112">ISymENCUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-interface.md)

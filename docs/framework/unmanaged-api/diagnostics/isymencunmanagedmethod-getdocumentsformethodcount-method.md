---
title: Метод ISymENCUnmanagedMethod::GetDocumentsForMethodCount
ms.date: 03/30/2017
api_name:
- ISymENCUnmanagedMethod.GetDocumentsForMethodCount
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymENCUnmanagedMethod::GetDocumentsForMethodCount
helpviewer_keywords:
- GetDocumentsForMethodCount method [.NET Framework debugging]
- ISymENCUnmanagedMethod::GetDocumentsForMethodCount method [.NET Framework debugging]
ms.assetid: cc1a823a-3ff3-4a33-b641-96edc93d2b17
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: bf8cca7751dd9705fd3c4371e36e836ca19be5c9
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67736207"
---
# <a name="isymencunmanagedmethodgetdocumentsformethodcount-method"></a><span data-ttu-id="15203-102">Метод ISymENCUnmanagedMethod::GetDocumentsForMethodCount</span><span class="sxs-lookup"><span data-stu-id="15203-102">ISymENCUnmanagedMethod::GetDocumentsForMethodCount Method</span></span>
<span data-ttu-id="15203-103">Возвращает количество документов, этот метод имеет строки.</span><span class="sxs-lookup"><span data-stu-id="15203-103">Gets the number of documents that this method has lines in.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="15203-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="15203-104">Syntax</span></span>  
  
```cpp  
HRESULT GetDocumentsForMethodCount(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="15203-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="15203-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="15203-106">[out] Указатель на `ULONG32` , принимает размер буфера, требуемого для хранения документов.</span><span class="sxs-lookup"><span data-stu-id="15203-106">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the documents.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="15203-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="15203-107">Return Value</span></span>  
 <span data-ttu-id="15203-108">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="15203-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="15203-109">Требования</span><span class="sxs-lookup"><span data-stu-id="15203-109">Requirements</span></span>  
 <span data-ttu-id="15203-110">**Заголовок.** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="15203-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15203-111">См. также</span><span class="sxs-lookup"><span data-stu-id="15203-111">See also</span></span>

- [<span data-ttu-id="15203-112">Интерфейс ISymENCUnmanagedMethod</span><span class="sxs-lookup"><span data-stu-id="15203-112">ISymENCUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-interface.md)

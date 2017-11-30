---
title: "Метод ISymUnmanagedBinder::GetReaderFromStream"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedBinder.GetReaderFromStream
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedBinder::GetReaderFromStream
helpviewer_keywords:
- ISymUnmanagedBinder::GetReaderFromStream method [.NET Framework debugging]
- GetReaderFromStream method [.NET Framework debugging]
ms.assetid: aa38efd4-de7e-4482-a5d3-adc152093460
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: aa6a2e60e34f6c3a78343318ae102883da84e266
ms.sourcegitcommit: 5177d6ae2e9baf026f07ee0631556700a5a193f7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/28/2017
---
# <a name="isymunmanagedbindergetreaderfromstream-method"></a><span data-ttu-id="ac2ba-102">Метод ISymUnmanagedBinder::GetReaderFromStream</span><span class="sxs-lookup"><span data-stu-id="ac2ba-102">ISymUnmanagedBinder::GetReaderFromStream Method</span></span>
<span data-ttu-id="ac2ba-103">Данный интерфейс метаданных и поток, содержащий хранилище символов, возвращает правильную [ISymUnmanagedReader](isymunmanagedreader-interface.md) структуру, которая будет считывать отладочных символов из данного хранилища символов.</span><span class="sxs-lookup"><span data-stu-id="ac2ba-103">Given a metadata interface and a stream that contains the symbol store, returns the correct [ISymUnmanagedReader](isymunmanagedreader-interface.md) structure that will read the debugging symbols from the given symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ac2ba-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ac2ba-104">Syntax</span></span>  
  
```  
HRESULT GetReaderFromStream(  
    [in]  IUnknown  *importer,  
    [in]  IStream   *pstream,  
    [out,retval] ISymUnmanagedReader **pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ac2ba-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="ac2ba-105">Parameters</span></span>  
 `importer`  
 <span data-ttu-id="ac2ba-106">[in] Указатель на интерфейс импорта метаданных.</span><span class="sxs-lookup"><span data-stu-id="ac2ba-106">[in] A pointer to the metadata import interface.</span></span>  
  
 `pstream`  
 <span data-ttu-id="ac2ba-107">[in] Указатель на поток, содержащий хранилище символов.</span><span class="sxs-lookup"><span data-stu-id="ac2ba-107">[in] A pointer to the stream that contains the symbol store.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="ac2ba-108">[out] Указатель, который задается в возвращаемую [ISymUnmanagedReader](isymunmanagedreader-interface.md) интерфейса.</span><span class="sxs-lookup"><span data-stu-id="ac2ba-108">[out] A pointer that is set to the returned [ISymUnmanagedReader](isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ac2ba-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="ac2ba-109">Return Value</span></span>  
 <span data-ttu-id="ac2ba-110">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="ac2ba-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ac2ba-111">Требования</span><span class="sxs-lookup"><span data-stu-id="ac2ba-111">Requirements</span></span>  
 <span data-ttu-id="ac2ba-112">**Заголовок:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="ac2ba-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac2ba-113">См. также</span><span class="sxs-lookup"><span data-stu-id="ac2ba-113">See Also</span></span>  
 [<span data-ttu-id="ac2ba-114">Интерфейс ISymUnmanagedBinder</span><span class="sxs-lookup"><span data-stu-id="ac2ba-114">ISymUnmanagedBinder Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-interface.md)

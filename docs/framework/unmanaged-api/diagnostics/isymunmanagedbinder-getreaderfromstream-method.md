---
title: Метод ISymUnmanagedBinder::GetReaderFromStream
ms.date: 03/30/2017
api_name:
- ISymUnmanagedBinder.GetReaderFromStream
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedBinder::GetReaderFromStream
helpviewer_keywords:
- ISymUnmanagedBinder::GetReaderFromStream method [.NET Framework debugging]
- GetReaderFromStream method [.NET Framework debugging]
ms.assetid: aa38efd4-de7e-4482-a5d3-adc152093460
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 21e147860c6859ea23409de31fed972c4f2bb432
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59220920"
---
# <a name="isymunmanagedbindergetreaderfromstream-method"></a><span data-ttu-id="9e27d-102">Метод ISymUnmanagedBinder::GetReaderFromStream</span><span class="sxs-lookup"><span data-stu-id="9e27d-102">ISymUnmanagedBinder::GetReaderFromStream Method</span></span>
<span data-ttu-id="9e27d-103">Данный интерфейс метаданных и поток, содержащий хранилище символов, возвращает правильную [ISymUnmanagedReader](isymunmanagedreader-interface.md) структуру, которая будет считывать отладочных символов из данного хранилища символов.</span><span class="sxs-lookup"><span data-stu-id="9e27d-103">Given a metadata interface and a stream that contains the symbol store, returns the correct [ISymUnmanagedReader](isymunmanagedreader-interface.md) structure that will read the debugging symbols from the given symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9e27d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9e27d-104">Syntax</span></span>  
  
```  
HRESULT GetReaderFromStream(  
    [in]  IUnknown  *importer,  
    [in]  IStream   *pstream,  
    [out,retval] ISymUnmanagedReader **pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9e27d-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="9e27d-105">Parameters</span></span>  
 `importer`  
 <span data-ttu-id="9e27d-106">[in] Указатель на интерфейс импорта метаданных.</span><span class="sxs-lookup"><span data-stu-id="9e27d-106">[in] A pointer to the metadata import interface.</span></span>  
  
 `pstream`  
 <span data-ttu-id="9e27d-107">[in] Указатель на поток, содержащий данные в хранилище символов.</span><span class="sxs-lookup"><span data-stu-id="9e27d-107">[in] A pointer to the stream that contains the symbol store.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="9e27d-108">[out] Указатель, который имеет значение равное возвращаемому [ISymUnmanagedReader](isymunmanagedreader-interface.md) интерфейс.</span><span class="sxs-lookup"><span data-stu-id="9e27d-108">[out] A pointer that is set to the returned [ISymUnmanagedReader](isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9e27d-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="9e27d-109">Return Value</span></span>  
 <span data-ttu-id="9e27d-110">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="9e27d-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9e27d-111">Требования</span><span class="sxs-lookup"><span data-stu-id="9e27d-111">Requirements</span></span>  
 <span data-ttu-id="9e27d-112">**Заголовок.** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="9e27d-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e27d-113">См. также</span><span class="sxs-lookup"><span data-stu-id="9e27d-113">See also</span></span>

- [<span data-ttu-id="9e27d-114">Интерфейс ISymUnmanagedBinder</span><span class="sxs-lookup"><span data-stu-id="9e27d-114">ISymUnmanagedBinder Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-interface.md)

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
ms.openlocfilehash: 4c5d3d1b868849d17b2068eecfcfeea0f1e598f8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="isymunmanagedbindergetreaderfromstream-method"></a><span data-ttu-id="186d3-102">Метод ISymUnmanagedBinder::GetReaderFromStream</span><span class="sxs-lookup"><span data-stu-id="186d3-102">ISymUnmanagedBinder::GetReaderFromStream Method</span></span>
<span data-ttu-id="186d3-103">Данный интерфейс метаданных и поток, содержащий хранилище символов, возвращает правильную [ISymUnmanagedReader](isymunmanagedreader-interface.md) структуру, которая будет считывать отладочных символов из данного хранилища символов.</span><span class="sxs-lookup"><span data-stu-id="186d3-103">Given a metadata interface and a stream that contains the symbol store, returns the correct [ISymUnmanagedReader](isymunmanagedreader-interface.md) structure that will read the debugging symbols from the given symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="186d3-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="186d3-104">Syntax</span></span>  
  
```  
HRESULT GetReaderFromStream(  
    [in]  IUnknown  *importer,  
    [in]  IStream   *pstream,  
    [out,retval] ISymUnmanagedReader **pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="186d3-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="186d3-105">Parameters</span></span>  
 `importer`  
 <span data-ttu-id="186d3-106">[in] Указатель на интерфейс импорта метаданных.</span><span class="sxs-lookup"><span data-stu-id="186d3-106">[in] A pointer to the metadata import interface.</span></span>  
  
 `pstream`  
 <span data-ttu-id="186d3-107">[in] Указатель на поток, содержащий хранилище символов.</span><span class="sxs-lookup"><span data-stu-id="186d3-107">[in] A pointer to the stream that contains the symbol store.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="186d3-108">[out] Указатель, который задается в возвращаемую [ISymUnmanagedReader](isymunmanagedreader-interface.md) интерфейса.</span><span class="sxs-lookup"><span data-stu-id="186d3-108">[out] A pointer that is set to the returned [ISymUnmanagedReader](isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="186d3-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="186d3-109">Return Value</span></span>  
 <span data-ttu-id="186d3-110">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="186d3-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="186d3-111">Требования</span><span class="sxs-lookup"><span data-stu-id="186d3-111">Requirements</span></span>  
 <span data-ttu-id="186d3-112">**Заголовок:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="186d3-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="186d3-113">См. также</span><span class="sxs-lookup"><span data-stu-id="186d3-113">See Also</span></span>  
 [<span data-ttu-id="186d3-114">Интерфейс ISymUnmanagedBinder</span><span class="sxs-lookup"><span data-stu-id="186d3-114">ISymUnmanagedBinder Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-interface.md)

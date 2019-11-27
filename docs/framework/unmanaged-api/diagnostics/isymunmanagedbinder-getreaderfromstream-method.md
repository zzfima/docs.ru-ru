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
ms.openlocfilehash: b1cb2bf3aa021ed738f7fad93fc4b86d97baf1e5
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449390"
---
# <a name="isymunmanagedbindergetreaderfromstream-method"></a><span data-ttu-id="6599c-102">Метод ISymUnmanagedBinder::GetReaderFromStream</span><span class="sxs-lookup"><span data-stu-id="6599c-102">ISymUnmanagedBinder::GetReaderFromStream Method</span></span>
<span data-ttu-id="6599c-103">При наличии интерфейса метаданных и потока, содержащего хранилище символов, возвращает правильную структуру [ISymUnmanagedReader](isymunmanagedreader-interface.md) , которая будет считывать отладочные символы из заданного хранилища символов.</span><span class="sxs-lookup"><span data-stu-id="6599c-103">Given a metadata interface and a stream that contains the symbol store, returns the correct [ISymUnmanagedReader](isymunmanagedreader-interface.md) structure that will read the debugging symbols from the given symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6599c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6599c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetReaderFromStream(  
    [in]  IUnknown  *importer,  
    [in]  IStream   *pstream,  
    [out,retval] ISymUnmanagedReader **pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6599c-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="6599c-105">Parameters</span></span>  
 `importer`  
 <span data-ttu-id="6599c-106">окне Указатель на интерфейс импорта метаданных.</span><span class="sxs-lookup"><span data-stu-id="6599c-106">[in] A pointer to the metadata import interface.</span></span>  
  
 `pstream`  
 <span data-ttu-id="6599c-107">окне Указатель на поток, содержащий хранилище символов.</span><span class="sxs-lookup"><span data-stu-id="6599c-107">[in] A pointer to the stream that contains the symbol store.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="6599c-108">заполняет Указатель, которому присваивается возвращаемый интерфейс [ISymUnmanagedReader](isymunmanagedreader-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="6599c-108">[out] A pointer that is set to the returned [ISymUnmanagedReader](isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6599c-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="6599c-109">Return Value</span></span>  
 <span data-ttu-id="6599c-110">S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.</span><span class="sxs-lookup"><span data-stu-id="6599c-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6599c-111">Требования</span><span class="sxs-lookup"><span data-stu-id="6599c-111">Requirements</span></span>  
 <span data-ttu-id="6599c-112">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="6599c-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6599c-113">См. также:</span><span class="sxs-lookup"><span data-stu-id="6599c-113">See also</span></span>

- [<span data-ttu-id="6599c-114">Интерфейс ISymUnmanagedBinder</span><span class="sxs-lookup"><span data-stu-id="6599c-114">ISymUnmanagedBinder Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-interface.md)

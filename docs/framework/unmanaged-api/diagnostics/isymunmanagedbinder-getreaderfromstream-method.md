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
ms.openlocfilehash: 96bd12b69b84537415ddf2e0ae992ec179f32493
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedbindergetreaderfromstream-method"></a><span data-ttu-id="8c562-102">Метод ISymUnmanagedBinder::GetReaderFromStream</span><span class="sxs-lookup"><span data-stu-id="8c562-102">ISymUnmanagedBinder::GetReaderFromStream Method</span></span>
<span data-ttu-id="8c562-103">Данный интерфейс метаданных и поток, содержащий хранилище символов, возвращает правильную <<!--zz xref:ISymUnmanagedReader --> `ISymUnmanagedReader`> структуру, которая будет считывать отладочных символов из данного хранилища символов.</span><span class="sxs-lookup"><span data-stu-id="8c562-103">Given a metadata interface and a stream that contains the symbol store, returns the correct <<!--zz xref:ISymUnmanagedReader --> `ISymUnmanagedReader`> structure that will read the debugging symbols from the given symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8c562-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8c562-104">Syntax</span></span>  
  
```  
HRESULT GetReaderFromStream(  
    [in]  IUnknown  *importer,  
    [in]  IStream   *pstream,  
    [out,retval] ISymUnmanagedReader **pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8c562-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="8c562-105">Parameters</span></span>  
 `importer`  
 <span data-ttu-id="8c562-106">[in] Указатель на интерфейс импорта метаданных.</span><span class="sxs-lookup"><span data-stu-id="8c562-106">[in] A pointer to the metadata import interface.</span></span>  
  
 `pstream`  
 <span data-ttu-id="8c562-107">[in] Указатель на поток, содержащий хранилище символов.</span><span class="sxs-lookup"><span data-stu-id="8c562-107">[in] A pointer to the stream that contains the symbol store.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="8c562-108">[out] Указатель, который задается в возвращаемую <<!--zz xref:ISymUnmanagedReader --> `ISymUnmanagedReader`> интерфейса.</span><span class="sxs-lookup"><span data-stu-id="8c562-108">[out] A pointer that is set to the returned <<!--zz xref:ISymUnmanagedReader --> `ISymUnmanagedReader`> interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8c562-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="8c562-109">Return Value</span></span>  
 <span data-ttu-id="8c562-110">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="8c562-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8c562-111">Требования</span><span class="sxs-lookup"><span data-stu-id="8c562-111">Requirements</span></span>  
 <span data-ttu-id="8c562-112">**Заголовок:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="8c562-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c562-113">См. также</span><span class="sxs-lookup"><span data-stu-id="8c562-113">See Also</span></span>  
 [<span data-ttu-id="8c562-114">Интерфейс ISymUnmanagedBinder</span><span class="sxs-lookup"><span data-stu-id="8c562-114">ISymUnmanagedBinder Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-interface.md)

---
title: "Метод ISymUnmanagedSymbolSearchInfo::GetSearchPathLength"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedSymbolSearchInfo.GetSearchPathLength
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedSymbolSearchInfo::GetSearchPathLength
helpviewer_keywords:
- GetSearchPathLength method [.NET Framework debugging]
- ISymUnmanagedSymbolSearchInfo::GetSearchPathLength method [.NET Framework debugging]
ms.assetid: 274e73cf-8333-47ba-ac12-70214e2b0112
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 58a788d8ef96a52c0b1bc361a97013f27c2809da
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedsymbolsearchinfogetsearchpathlength-method"></a><span data-ttu-id="4a742-102">Метод ISymUnmanagedSymbolSearchInfo::GetSearchPathLength</span><span class="sxs-lookup"><span data-stu-id="4a742-102">ISymUnmanagedSymbolSearchInfo::GetSearchPathLength Method</span></span>
<span data-ttu-id="4a742-103">Получает длину пути поиска.</span><span class="sxs-lookup"><span data-stu-id="4a742-103">Gets the search path length.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4a742-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4a742-104">Syntax</span></span>  
  
```  
HRESULT GetSearchPathLength(  
    [out] ULONG32 *pcchPath);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4a742-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="4a742-105">Parameters</span></span>  
 `pcchPath`  
 <span data-ttu-id="4a742-106">[out] Указатель на `ULONG32` , получающий размер в символах, буфера, необходимый для хранения длину пути поиска.</span><span class="sxs-lookup"><span data-stu-id="4a742-106">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the search path length.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4a742-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="4a742-107">Return Value</span></span>  
 <span data-ttu-id="4a742-108">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="4a742-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4a742-109">Требования</span><span class="sxs-lookup"><span data-stu-id="4a742-109">Requirements</span></span>  
 <span data-ttu-id="4a742-110">**Заголовок:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="4a742-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a742-111">См. также</span><span class="sxs-lookup"><span data-stu-id="4a742-111">See Also</span></span>  
 [<span data-ttu-id="4a742-112">Интерфейс ISymUnmanagedSymbolSearchInfo</span><span class="sxs-lookup"><span data-stu-id="4a742-112">ISymUnmanagedSymbolSearchInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-interface.md)

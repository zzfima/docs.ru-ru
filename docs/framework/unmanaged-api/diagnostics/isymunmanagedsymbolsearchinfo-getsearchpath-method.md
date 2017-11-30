---
title: "Метод ISymUnmanagedSymbolSearchInfo::GetSearchPath"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedSymbolSearchInfo.GetSearchPath
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedSymbolSearchInfo::GetSearchPath
helpviewer_keywords:
- GetSearchPath method [.NET Framework debugging]
- ISymUnmanagedSymbolSearchInfo::GetSearchPath method [.NET Framework debugging]
ms.assetid: b588d470-53c2-4492-be8c-957323eaca0b
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: c896c8bc8aa852fb69f182e484243a0c379e0a1e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedsymbolsearchinfogetsearchpath-method"></a><span data-ttu-id="512fc-102">Метод ISymUnmanagedSymbolSearchInfo::GetSearchPath</span><span class="sxs-lookup"><span data-stu-id="512fc-102">ISymUnmanagedSymbolSearchInfo::GetSearchPath Method</span></span>
<span data-ttu-id="512fc-103">Получает пути поиска.</span><span class="sxs-lookup"><span data-stu-id="512fc-103">Gets the search path.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="512fc-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="512fc-104">Syntax</span></span>  
  
```  
HRESULT GetSearchPathLength(  
    [out] ULONG32 *pcchPath);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="512fc-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="512fc-105">Parameters</span></span>  
 `pcchPath`  
 <span data-ttu-id="512fc-106">[out] Указатель на `ULONG32` , получающий размер в символах, буфера, который требуется включить в путь поиска.</span><span class="sxs-lookup"><span data-stu-id="512fc-106">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the search path.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="512fc-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="512fc-107">Return Value</span></span>  
 <span data-ttu-id="512fc-108">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="512fc-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="512fc-109">Требования</span><span class="sxs-lookup"><span data-stu-id="512fc-109">Requirements</span></span>  
 <span data-ttu-id="512fc-110">**Заголовок:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="512fc-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="512fc-111">См. также</span><span class="sxs-lookup"><span data-stu-id="512fc-111">See Also</span></span>  
 [<span data-ttu-id="512fc-112">Интерфейс ISymUnmanagedSymbolSearchInfo</span><span class="sxs-lookup"><span data-stu-id="512fc-112">ISymUnmanagedSymbolSearchInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-interface.md)

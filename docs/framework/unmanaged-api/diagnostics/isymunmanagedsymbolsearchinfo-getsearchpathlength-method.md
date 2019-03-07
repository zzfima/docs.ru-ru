---
title: Метод ISymUnmanagedSymbolSearchInfo::GetSearchPathLength
ms.date: 03/30/2017
api_name:
- ISymUnmanagedSymbolSearchInfo.GetSearchPathLength
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedSymbolSearchInfo::GetSearchPathLength
helpviewer_keywords:
- GetSearchPathLength method [.NET Framework debugging]
- ISymUnmanagedSymbolSearchInfo::GetSearchPathLength method [.NET Framework debugging]
ms.assetid: 274e73cf-8333-47ba-ac12-70214e2b0112
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 892da7ec41c75e50f7f2cb086b05e466478e1ced
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57484099"
---
# <a name="isymunmanagedsymbolsearchinfogetsearchpathlength-method"></a><span data-ttu-id="49c43-102">Метод ISymUnmanagedSymbolSearchInfo::GetSearchPathLength</span><span class="sxs-lookup"><span data-stu-id="49c43-102">ISymUnmanagedSymbolSearchInfo::GetSearchPathLength Method</span></span>
<span data-ttu-id="49c43-103">Получает длину пути поиска.</span><span class="sxs-lookup"><span data-stu-id="49c43-103">Gets the search path length.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="49c43-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="49c43-104">Syntax</span></span>  
  
```  
HRESULT GetSearchPathLength(  
    [out] ULONG32 *pcchPath);  
```  
  
## <a name="parameters"></a><span data-ttu-id="49c43-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="49c43-105">Parameters</span></span>  
 `pcchPath`  
 <span data-ttu-id="49c43-106">[out] Указатель на `ULONG32` размер, который получает в символах, буфера, требуемого для хранения длину пути поиска.</span><span class="sxs-lookup"><span data-stu-id="49c43-106">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the search path length.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="49c43-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="49c43-107">Return Value</span></span>  
 <span data-ttu-id="49c43-108">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="49c43-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="49c43-109">Требования</span><span class="sxs-lookup"><span data-stu-id="49c43-109">Requirements</span></span>  
 <span data-ttu-id="49c43-110">**Заголовок.** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="49c43-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49c43-111">См. также</span><span class="sxs-lookup"><span data-stu-id="49c43-111">See also</span></span>
- [<span data-ttu-id="49c43-112">Интерфейс ISymUnmanagedSymbolSearchInfo</span><span class="sxs-lookup"><span data-stu-id="49c43-112">ISymUnmanagedSymbolSearchInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-interface.md)

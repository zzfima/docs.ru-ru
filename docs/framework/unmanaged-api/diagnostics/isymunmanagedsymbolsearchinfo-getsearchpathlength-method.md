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
ms.openlocfilehash: 37e9926c8f9677e3b38202c5fb3c43f7b1159edf
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59170616"
---
# <a name="isymunmanagedsymbolsearchinfogetsearchpathlength-method"></a><span data-ttu-id="1782b-102">Метод ISymUnmanagedSymbolSearchInfo::GetSearchPathLength</span><span class="sxs-lookup"><span data-stu-id="1782b-102">ISymUnmanagedSymbolSearchInfo::GetSearchPathLength Method</span></span>
<span data-ttu-id="1782b-103">Получает длину пути поиска.</span><span class="sxs-lookup"><span data-stu-id="1782b-103">Gets the search path length.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1782b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1782b-104">Syntax</span></span>  
  
```  
HRESULT GetSearchPathLength(  
    [out] ULONG32 *pcchPath);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1782b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="1782b-105">Parameters</span></span>  
 `pcchPath`  
 <span data-ttu-id="1782b-106">[out] Указатель на `ULONG32` размер, который получает в символах, буфера, требуемого для хранения длину пути поиска.</span><span class="sxs-lookup"><span data-stu-id="1782b-106">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the search path length.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1782b-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="1782b-107">Return Value</span></span>  
 <span data-ttu-id="1782b-108">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="1782b-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1782b-109">Требования</span><span class="sxs-lookup"><span data-stu-id="1782b-109">Requirements</span></span>  
 <span data-ttu-id="1782b-110">**Заголовок.** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="1782b-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1782b-111">См. также</span><span class="sxs-lookup"><span data-stu-id="1782b-111">See also</span></span>

- [<span data-ttu-id="1782b-112">Интерфейс ISymUnmanagedSymbolSearchInfo</span><span class="sxs-lookup"><span data-stu-id="1782b-112">ISymUnmanagedSymbolSearchInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-interface.md)

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
ms.openlocfilehash: 27de34c1978818c48d5fa38caf9b52ff2a9510f5
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67778084"
---
# <a name="isymunmanagedsymbolsearchinfogetsearchpathlength-method"></a><span data-ttu-id="d44d5-102">Метод ISymUnmanagedSymbolSearchInfo::GetSearchPathLength</span><span class="sxs-lookup"><span data-stu-id="d44d5-102">ISymUnmanagedSymbolSearchInfo::GetSearchPathLength Method</span></span>
<span data-ttu-id="d44d5-103">Получает длину пути поиска.</span><span class="sxs-lookup"><span data-stu-id="d44d5-103">Gets the search path length.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d44d5-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d44d5-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSearchPathLength(  
    [out] ULONG32 *pcchPath);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d44d5-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="d44d5-105">Parameters</span></span>  
 `pcchPath`  
 <span data-ttu-id="d44d5-106">[out] Указатель на `ULONG32` размер, который получает в символах, буфера, требуемого для хранения длину пути поиска.</span><span class="sxs-lookup"><span data-stu-id="d44d5-106">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the search path length.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d44d5-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="d44d5-107">Return Value</span></span>  
 <span data-ttu-id="d44d5-108">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="d44d5-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d44d5-109">Требования</span><span class="sxs-lookup"><span data-stu-id="d44d5-109">Requirements</span></span>  
 <span data-ttu-id="d44d5-110">**Заголовок.** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="d44d5-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d44d5-111">См. также</span><span class="sxs-lookup"><span data-stu-id="d44d5-111">See also</span></span>

- [<span data-ttu-id="d44d5-112">Интерфейс ISymUnmanagedSymbolSearchInfo</span><span class="sxs-lookup"><span data-stu-id="d44d5-112">ISymUnmanagedSymbolSearchInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-interface.md)

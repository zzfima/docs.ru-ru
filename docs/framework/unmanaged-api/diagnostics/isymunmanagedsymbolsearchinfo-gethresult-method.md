---
title: Метод ISymUnmanagedSymbolSearchInfo::GetHRESULT
ms.date: 03/30/2017
api_name:
- ISymUnmanagedSymbolSearchInfo.GetHRESULT
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedSymbolSearchInfo::GetHRESULT
helpviewer_keywords:
- ISymUnmanagedSymbolSearchInfo::GetHRESULT method [.NET Framework debugging]
- GetHRESULT method [.NET Framework debugging]
ms.assetid: 6999dc3d-65d7-4bf6-bb0a-6efc0fc72588
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 775f5a2129a635c79a48d5218d5eb91ee83ee779
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33427887"
---
# <a name="isymunmanagedsymbolsearchinfogethresult-method"></a><span data-ttu-id="6e7a2-102">Метод ISymUnmanagedSymbolSearchInfo::GetHRESULT</span><span class="sxs-lookup"><span data-stu-id="6e7a2-102">ISymUnmanagedSymbolSearchInfo::GetHRESULT Method</span></span>
<span data-ttu-id="6e7a2-103">Возвращает значение HRESULT.</span><span class="sxs-lookup"><span data-stu-id="6e7a2-103">Gets the HRESULT.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6e7a2-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6e7a2-104">Syntax</span></span>  
  
```  
HRESULT GetHRESULT(  
    [out] HRESULT *phr);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6e7a2-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="6e7a2-105">Parameters</span></span>  
 `phr`  
 <span data-ttu-id="6e7a2-106">[out] Указатель на значение HRESULT.</span><span class="sxs-lookup"><span data-stu-id="6e7a2-106">[out] A pointer to the HRESULT.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6e7a2-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="6e7a2-107">Return Value</span></span>  
 <span data-ttu-id="6e7a2-108">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="6e7a2-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6e7a2-109">Требования</span><span class="sxs-lookup"><span data-stu-id="6e7a2-109">Requirements</span></span>  
 <span data-ttu-id="6e7a2-110">**Заголовок:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="6e7a2-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e7a2-111">См. также</span><span class="sxs-lookup"><span data-stu-id="6e7a2-111">See Also</span></span>  
 [<span data-ttu-id="6e7a2-112">Интерфейс ISymUnmanagedSymbolSearchInfo</span><span class="sxs-lookup"><span data-stu-id="6e7a2-112">ISymUnmanagedSymbolSearchInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-interface.md)

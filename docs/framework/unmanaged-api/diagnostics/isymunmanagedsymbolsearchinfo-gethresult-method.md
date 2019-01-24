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
ms.openlocfilehash: 15f85a6f5ab418692d747cc9ad415c637d7b96e2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54614371"
---
# <a name="isymunmanagedsymbolsearchinfogethresult-method"></a><span data-ttu-id="f062f-102">Метод ISymUnmanagedSymbolSearchInfo::GetHRESULT</span><span class="sxs-lookup"><span data-stu-id="f062f-102">ISymUnmanagedSymbolSearchInfo::GetHRESULT Method</span></span>
<span data-ttu-id="f062f-103">Получает значение HRESULT.</span><span class="sxs-lookup"><span data-stu-id="f062f-103">Gets the HRESULT.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f062f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f062f-104">Syntax</span></span>  
  
```  
HRESULT GetHRESULT(  
    [out] HRESULT *phr);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f062f-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="f062f-105">Parameters</span></span>  
 `phr`  
 <span data-ttu-id="f062f-106">[out] Указатель на значение HRESULT.</span><span class="sxs-lookup"><span data-stu-id="f062f-106">[out] A pointer to the HRESULT.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f062f-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="f062f-107">Return Value</span></span>  
 <span data-ttu-id="f062f-108">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="f062f-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f062f-109">Требования</span><span class="sxs-lookup"><span data-stu-id="f062f-109">Requirements</span></span>  
 <span data-ttu-id="f062f-110">**Заголовок.** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="f062f-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f062f-111">См. также</span><span class="sxs-lookup"><span data-stu-id="f062f-111">See also</span></span>
- [<span data-ttu-id="f062f-112">Интерфейс ISymUnmanagedSymbolSearchInfo</span><span class="sxs-lookup"><span data-stu-id="f062f-112">ISymUnmanagedSymbolSearchInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-interface.md)

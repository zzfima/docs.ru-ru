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
ms.openlocfilehash: 1534955c1f7cfd37732a08b0b33cda5bff8a8aab
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59113026"
---
# <a name="isymunmanagedsymbolsearchinfogethresult-method"></a><span data-ttu-id="4bc97-102">Метод ISymUnmanagedSymbolSearchInfo::GetHRESULT</span><span class="sxs-lookup"><span data-stu-id="4bc97-102">ISymUnmanagedSymbolSearchInfo::GetHRESULT Method</span></span>
<span data-ttu-id="4bc97-103">Получает значение HRESULT.</span><span class="sxs-lookup"><span data-stu-id="4bc97-103">Gets the HRESULT.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4bc97-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4bc97-104">Syntax</span></span>  
  
```  
HRESULT GetHRESULT(  
    [out] HRESULT *phr);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4bc97-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="4bc97-105">Parameters</span></span>  
 `phr`  
 <span data-ttu-id="4bc97-106">[out] Указатель на значение HRESULT.</span><span class="sxs-lookup"><span data-stu-id="4bc97-106">[out] A pointer to the HRESULT.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4bc97-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="4bc97-107">Return Value</span></span>  
 <span data-ttu-id="4bc97-108">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="4bc97-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4bc97-109">Требования</span><span class="sxs-lookup"><span data-stu-id="4bc97-109">Requirements</span></span>  
 <span data-ttu-id="4bc97-110">**Заголовок.** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="4bc97-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4bc97-111">См. также</span><span class="sxs-lookup"><span data-stu-id="4bc97-111">See also</span></span>

- [<span data-ttu-id="4bc97-112">Интерфейс ISymUnmanagedSymbolSearchInfo</span><span class="sxs-lookup"><span data-stu-id="4bc97-112">ISymUnmanagedSymbolSearchInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-interface.md)

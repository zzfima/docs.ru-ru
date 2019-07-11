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
ms.openlocfilehash: b32865e0ac9d8a4a049db5d7ed6179879342c10a
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67778108"
---
# <a name="isymunmanagedsymbolsearchinfogethresult-method"></a><span data-ttu-id="153f9-102">Метод ISymUnmanagedSymbolSearchInfo::GetHRESULT</span><span class="sxs-lookup"><span data-stu-id="153f9-102">ISymUnmanagedSymbolSearchInfo::GetHRESULT Method</span></span>
<span data-ttu-id="153f9-103">Получает значение HRESULT.</span><span class="sxs-lookup"><span data-stu-id="153f9-103">Gets the HRESULT.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="153f9-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="153f9-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHRESULT(  
    [out] HRESULT *phr);  
```  
  
## <a name="parameters"></a><span data-ttu-id="153f9-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="153f9-105">Parameters</span></span>  
 `phr`  
 <span data-ttu-id="153f9-106">[out] Указатель на значение HRESULT.</span><span class="sxs-lookup"><span data-stu-id="153f9-106">[out] A pointer to the HRESULT.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="153f9-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="153f9-107">Return Value</span></span>  
 <span data-ttu-id="153f9-108">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="153f9-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="153f9-109">Требования</span><span class="sxs-lookup"><span data-stu-id="153f9-109">Requirements</span></span>  
 <span data-ttu-id="153f9-110">**Заголовок.** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="153f9-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="153f9-111">См. также</span><span class="sxs-lookup"><span data-stu-id="153f9-111">See also</span></span>

- [<span data-ttu-id="153f9-112">Интерфейс ISymUnmanagedSymbolSearchInfo</span><span class="sxs-lookup"><span data-stu-id="153f9-112">ISymUnmanagedSymbolSearchInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-interface.md)

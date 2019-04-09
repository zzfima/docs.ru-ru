---
title: Метод ISymUnmanagedSymbolSearchInfo::GetSearchPath
ms.date: 03/30/2017
api_name:
- ISymUnmanagedSymbolSearchInfo.GetSearchPath
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedSymbolSearchInfo::GetSearchPath
helpviewer_keywords:
- GetSearchPath method [.NET Framework debugging]
- ISymUnmanagedSymbolSearchInfo::GetSearchPath method [.NET Framework debugging]
ms.assetid: b588d470-53c2-4492-be8c-957323eaca0b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 649f44bd7966b9ca89d2d040b7eede662404aa0f
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59093557"
---
# <a name="isymunmanagedsymbolsearchinfogetsearchpath-method"></a><span data-ttu-id="70d89-102">Метод ISymUnmanagedSymbolSearchInfo::GetSearchPath</span><span class="sxs-lookup"><span data-stu-id="70d89-102">ISymUnmanagedSymbolSearchInfo::GetSearchPath Method</span></span>
<span data-ttu-id="70d89-103">Получает пути поиска.</span><span class="sxs-lookup"><span data-stu-id="70d89-103">Gets the search path.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="70d89-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="70d89-104">Syntax</span></span>  
  
```  
HRESULT GetSearchPathLength(  
    [out] ULONG32 *pcchPath);  
```  
  
## <a name="parameters"></a><span data-ttu-id="70d89-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="70d89-105">Parameters</span></span>  
 `pcchPath`  
 <span data-ttu-id="70d89-106">[out] Указатель на `ULONG32` размер, который получает в символах, буфера, требуемого для хранения пути поиска.</span><span class="sxs-lookup"><span data-stu-id="70d89-106">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the search path.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="70d89-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="70d89-107">Return Value</span></span>  
 <span data-ttu-id="70d89-108">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="70d89-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="70d89-109">Требования</span><span class="sxs-lookup"><span data-stu-id="70d89-109">Requirements</span></span>  
 <span data-ttu-id="70d89-110">**Заголовок.** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="70d89-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70d89-111">См. также</span><span class="sxs-lookup"><span data-stu-id="70d89-111">See also</span></span>

- [<span data-ttu-id="70d89-112">Интерфейс ISymUnmanagedSymbolSearchInfo</span><span class="sxs-lookup"><span data-stu-id="70d89-112">ISymUnmanagedSymbolSearchInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-interface.md)

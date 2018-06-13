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
ms.openlocfilehash: 3ad2167ab26eaa8164233ab9566854417f78df29
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33427874"
---
# <a name="isymunmanagedsymbolsearchinfogetsearchpathlength-method"></a><span data-ttu-id="cee54-102">Метод ISymUnmanagedSymbolSearchInfo::GetSearchPathLength</span><span class="sxs-lookup"><span data-stu-id="cee54-102">ISymUnmanagedSymbolSearchInfo::GetSearchPathLength Method</span></span>
<span data-ttu-id="cee54-103">Получает длину пути поиска.</span><span class="sxs-lookup"><span data-stu-id="cee54-103">Gets the search path length.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cee54-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cee54-104">Syntax</span></span>  
  
```  
HRESULT GetSearchPathLength(  
    [out] ULONG32 *pcchPath);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="cee54-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="cee54-105">Parameters</span></span>  
 `pcchPath`  
 <span data-ttu-id="cee54-106">[out] Указатель на `ULONG32` , получающий размер в символах, буфера, необходимый для хранения длину пути поиска.</span><span class="sxs-lookup"><span data-stu-id="cee54-106">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the search path length.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cee54-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="cee54-107">Return Value</span></span>  
 <span data-ttu-id="cee54-108">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="cee54-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cee54-109">Требования</span><span class="sxs-lookup"><span data-stu-id="cee54-109">Requirements</span></span>  
 <span data-ttu-id="cee54-110">**Заголовок:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="cee54-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cee54-111">См. также</span><span class="sxs-lookup"><span data-stu-id="cee54-111">See Also</span></span>  
 [<span data-ttu-id="cee54-112">Интерфейс ISymUnmanagedSymbolSearchInfo</span><span class="sxs-lookup"><span data-stu-id="cee54-112">ISymUnmanagedSymbolSearchInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-interface.md)

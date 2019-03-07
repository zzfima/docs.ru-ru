---
title: Метод ISymUnmanagedReaderSymbolSearchInfo::GetSymbolSearchInfo
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReaderSymbolSearchInfo.GetSymbolSearchInfo
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReaderSymbolSearchInfo::GetSymbolSearchInfo
helpviewer_keywords:
- GetSymbolSearchInfo method [.NET Framework debugging]
- ISymUnmanagedReaderSymbolSearchInfo::GetSymbolSearchInfo method [.NET Framework debugging]
ms.assetid: 40fcdbc5-3bb2-41e9-b995-40984c209a7f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: cbb290314328023c95d0028dd90687b1a6926ff5
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57501075"
---
# <a name="isymunmanagedreadersymbolsearchinfogetsymbolsearchinfo-method"></a><span data-ttu-id="0a9c8-102">Метод ISymUnmanagedReaderSymbolSearchInfo::GetSymbolSearchInfo</span><span class="sxs-lookup"><span data-stu-id="0a9c8-102">ISymUnmanagedReaderSymbolSearchInfo::GetSymbolSearchInfo Method</span></span>
<span data-ttu-id="0a9c8-103">Возвращает сведения о поиске символа.</span><span class="sxs-lookup"><span data-stu-id="0a9c8-103">Gets symbol search information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0a9c8-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0a9c8-104">Syntax</span></span>  
  
```  
HRESULT GetSymbolSearchInfo(  
    [in]  ULONG32  cSearchInfo,  
    [out] ULONG32  *pcSearchInfo,  
    [out, size_is(cSearchInfo), length_is(*pcSearchInfo)]  
        ISymUnmanagedSymbolSearchInfo **rgpSearchInfo);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0a9c8-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="0a9c8-105">Parameters</span></span>  
 `cSearchInfo`  
 <span data-ttu-id="0a9c8-106">[in] Объект `ULONG32` указывает размер `rgpSearchInfo`.</span><span class="sxs-lookup"><span data-stu-id="0a9c8-106">[in] A `ULONG32` that indicates the size of `rgpSearchInfo`.</span></span>  
  
 `pcSearchInfo`  
 <span data-ttu-id="0a9c8-107">[out] Указатель на `ULONG32` , принимает размер буфера, требуемого для хранения сведений для поиска.</span><span class="sxs-lookup"><span data-stu-id="0a9c8-107">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the search information.</span></span>  
  
 `rgpSearchInfo`  
 <span data-ttu-id="0a9c8-108">[out] Указатель, который имеет значение равное возвращаемому [ISymUnmanagedSymbolSearchInfo](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-interface.md) интерфейс.</span><span class="sxs-lookup"><span data-stu-id="0a9c8-108">[out] A pointer that is set to the returned [ISymUnmanagedSymbolSearchInfo](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0a9c8-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="0a9c8-109">Return Value</span></span>  
 <span data-ttu-id="0a9c8-110">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="0a9c8-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0a9c8-111">Требования</span><span class="sxs-lookup"><span data-stu-id="0a9c8-111">Requirements</span></span>  
 <span data-ttu-id="0a9c8-112">**Заголовок.** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="0a9c8-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a9c8-113">См. также</span><span class="sxs-lookup"><span data-stu-id="0a9c8-113">See also</span></span>
- [<span data-ttu-id="0a9c8-114">Интерфейс ISymUnmanagedReaderSymbolSearchInfo</span><span class="sxs-lookup"><span data-stu-id="0a9c8-114">ISymUnmanagedReaderSymbolSearchInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreadersymbolsearchinfo-interface.md)

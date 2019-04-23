---
title: Метод ISymUnmanagedReaderSymbolSearchInfo::GetSymbolSearchInfoCount
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReaderSymbolSearchInfo.GetSymbolSearchInfoCount
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReaderSymbolSearchInfo::GetSymbolSearchInfoCount
helpviewer_keywords:
- GetSymbolSearchInfoCount method [.NET Framework debugging]
- ISymUnmanagedReaderSymbolSearchInfo::GetSymbolSearchInfoCount method [.NET Framework debugging]
ms.assetid: 4068b6ec-525f-4446-8818-0296178cbd19
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0b59d85227f21bb230333456eda9130416563111
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59180535"
---
# <a name="isymunmanagedreadersymbolsearchinfogetsymbolsearchinfocount-method"></a><span data-ttu-id="5e5c8-102">Метод ISymUnmanagedReaderSymbolSearchInfo::GetSymbolSearchInfoCount</span><span class="sxs-lookup"><span data-stu-id="5e5c8-102">ISymUnmanagedReaderSymbolSearchInfo::GetSymbolSearchInfoCount Method</span></span>
<span data-ttu-id="5e5c8-103">Возвращает счетчик для поиска символьной информации.</span><span class="sxs-lookup"><span data-stu-id="5e5c8-103">Gets a count of symbol search information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5e5c8-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5e5c8-104">Syntax</span></span>  
  
```  
HRESULT GetSymbolSearchInfoCount(  
    [out] ULONG32 *pcSearchInfo);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5e5c8-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="5e5c8-105">Parameters</span></span>  
 `pcSearchInfo`  
 <span data-ttu-id="5e5c8-106">[], out] указатель на `ULONG32` , принимает размер буфера, требуемого для хранения сведений для поиска.</span><span class="sxs-lookup"><span data-stu-id="5e5c8-106">]out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the search information.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5e5c8-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="5e5c8-107">Return Value</span></span>  
 <span data-ttu-id="5e5c8-108">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="5e5c8-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5e5c8-109">Требования</span><span class="sxs-lookup"><span data-stu-id="5e5c8-109">Requirements</span></span>  
 <span data-ttu-id="5e5c8-110">**Заголовок.** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="5e5c8-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e5c8-111">См. также</span><span class="sxs-lookup"><span data-stu-id="5e5c8-111">See also</span></span>

- [<span data-ttu-id="5e5c8-112">Интерфейс ISymUnmanagedReaderSymbolSearchInfo</span><span class="sxs-lookup"><span data-stu-id="5e5c8-112">ISymUnmanagedReaderSymbolSearchInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreadersymbolsearchinfo-interface.md)

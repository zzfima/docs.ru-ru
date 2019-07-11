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
ms.openlocfilehash: c1a72f76f1cd6f6571eaebff3a8046de8dcd3d74
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67751456"
---
# <a name="isymunmanagedreadersymbolsearchinfogetsymbolsearchinfocount-method"></a><span data-ttu-id="2e172-102">Метод ISymUnmanagedReaderSymbolSearchInfo::GetSymbolSearchInfoCount</span><span class="sxs-lookup"><span data-stu-id="2e172-102">ISymUnmanagedReaderSymbolSearchInfo::GetSymbolSearchInfoCount Method</span></span>
<span data-ttu-id="2e172-103">Возвращает счетчик для поиска символьной информации.</span><span class="sxs-lookup"><span data-stu-id="2e172-103">Gets a count of symbol search information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2e172-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2e172-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSymbolSearchInfoCount(  
    [out] ULONG32 *pcSearchInfo);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2e172-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="2e172-105">Parameters</span></span>  
 `pcSearchInfo`  
 <span data-ttu-id="2e172-106">[], out] указатель на `ULONG32` , принимает размер буфера, требуемого для хранения сведений для поиска.</span><span class="sxs-lookup"><span data-stu-id="2e172-106">]out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the search information.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2e172-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="2e172-107">Return Value</span></span>  
 <span data-ttu-id="2e172-108">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="2e172-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2e172-109">Требования</span><span class="sxs-lookup"><span data-stu-id="2e172-109">Requirements</span></span>  
 <span data-ttu-id="2e172-110">**Заголовок.** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="2e172-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e172-111">См. также</span><span class="sxs-lookup"><span data-stu-id="2e172-111">See also</span></span>

- [<span data-ttu-id="2e172-112">Интерфейс ISymUnmanagedReaderSymbolSearchInfo</span><span class="sxs-lookup"><span data-stu-id="2e172-112">ISymUnmanagedReaderSymbolSearchInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreadersymbolsearchinfo-interface.md)

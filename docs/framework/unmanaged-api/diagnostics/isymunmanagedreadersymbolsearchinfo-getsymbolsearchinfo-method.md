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
ms.openlocfilehash: 3d910f9e93dbd90f9e23c5f32903a8d819ea01f8
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67751470"
---
# <a name="isymunmanagedreadersymbolsearchinfogetsymbolsearchinfo-method"></a><span data-ttu-id="3b5f1-102">Метод ISymUnmanagedReaderSymbolSearchInfo::GetSymbolSearchInfo</span><span class="sxs-lookup"><span data-stu-id="3b5f1-102">ISymUnmanagedReaderSymbolSearchInfo::GetSymbolSearchInfo Method</span></span>
<span data-ttu-id="3b5f1-103">Возвращает сведения о поиске символа.</span><span class="sxs-lookup"><span data-stu-id="3b5f1-103">Gets symbol search information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3b5f1-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3b5f1-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSymbolSearchInfo(  
    [in]  ULONG32  cSearchInfo,  
    [out] ULONG32  *pcSearchInfo,  
    [out, size_is(cSearchInfo), length_is(*pcSearchInfo)]  
        ISymUnmanagedSymbolSearchInfo **rgpSearchInfo);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3b5f1-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="3b5f1-105">Parameters</span></span>  
 `cSearchInfo`  
 <span data-ttu-id="3b5f1-106">[in] Объект `ULONG32` указывает размер `rgpSearchInfo`.</span><span class="sxs-lookup"><span data-stu-id="3b5f1-106">[in] A `ULONG32` that indicates the size of `rgpSearchInfo`.</span></span>  
  
 `pcSearchInfo`  
 <span data-ttu-id="3b5f1-107">[out] Указатель на `ULONG32` , принимает размер буфера, требуемого для хранения сведений для поиска.</span><span class="sxs-lookup"><span data-stu-id="3b5f1-107">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the search information.</span></span>  
  
 `rgpSearchInfo`  
 <span data-ttu-id="3b5f1-108">[out] Указатель, который имеет значение равное возвращаемому [ISymUnmanagedSymbolSearchInfo](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-interface.md) интерфейс.</span><span class="sxs-lookup"><span data-stu-id="3b5f1-108">[out] A pointer that is set to the returned [ISymUnmanagedSymbolSearchInfo](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3b5f1-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="3b5f1-109">Return Value</span></span>  
 <span data-ttu-id="3b5f1-110">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="3b5f1-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3b5f1-111">Требования</span><span class="sxs-lookup"><span data-stu-id="3b5f1-111">Requirements</span></span>  
 <span data-ttu-id="3b5f1-112">**Заголовок.** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="3b5f1-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b5f1-113">См. также</span><span class="sxs-lookup"><span data-stu-id="3b5f1-113">See also</span></span>

- [<span data-ttu-id="3b5f1-114">Интерфейс ISymUnmanagedReaderSymbolSearchInfo</span><span class="sxs-lookup"><span data-stu-id="3b5f1-114">ISymUnmanagedReaderSymbolSearchInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreadersymbolsearchinfo-interface.md)

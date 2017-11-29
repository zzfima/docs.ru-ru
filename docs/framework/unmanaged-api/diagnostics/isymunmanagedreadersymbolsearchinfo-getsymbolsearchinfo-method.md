---
title: "Метод ISymUnmanagedReaderSymbolSearchInfo::GetSymbolSearchInfo"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedReaderSymbolSearchInfo.GetSymbolSearchInfo
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedReaderSymbolSearchInfo::GetSymbolSearchInfo
helpviewer_keywords:
- GetSymbolSearchInfo method [.NET Framework debugging]
- ISymUnmanagedReaderSymbolSearchInfo::GetSymbolSearchInfo method [.NET Framework debugging]
ms.assetid: 40fcdbc5-3bb2-41e9-b995-40984c209a7f
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 77c573865ad9fba14259e9bb1538a15cb3067925
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedreadersymbolsearchinfogetsymbolsearchinfo-method"></a><span data-ttu-id="b4b50-102">Метод ISymUnmanagedReaderSymbolSearchInfo::GetSymbolSearchInfo</span><span class="sxs-lookup"><span data-stu-id="b4b50-102">ISymUnmanagedReaderSymbolSearchInfo::GetSymbolSearchInfo Method</span></span>
<span data-ttu-id="b4b50-103">Возвращает сведения о поиске символов.</span><span class="sxs-lookup"><span data-stu-id="b4b50-103">Gets symbol search information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b4b50-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b4b50-104">Syntax</span></span>  
  
```  
HRESULT GetSymbolSearchInfo(  
    [in]  ULONG32  cSearchInfo,  
    [out] ULONG32  *pcSearchInfo,  
    [out, size_is(cSearchInfo), length_is(*pcSearchInfo)]  
        ISymUnmanagedSymbolSearchInfo **rgpSearchInfo);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b4b50-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="b4b50-105">Parameters</span></span>  
 `cSearchInfo`  
 <span data-ttu-id="b4b50-106">[in] Объект `ULONG32` указывает размер `rgpSearchInfo`.</span><span class="sxs-lookup"><span data-stu-id="b4b50-106">[in] A `ULONG32` that indicates the size of `rgpSearchInfo`.</span></span>  
  
 `pcSearchInfo`  
 <span data-ttu-id="b4b50-107">[out] Указатель на `ULONG32` , получающий размер буфера, необходимый для хранения сведений для поиска.</span><span class="sxs-lookup"><span data-stu-id="b4b50-107">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the search information.</span></span>  
  
 `rgpSearchInfo`  
 <span data-ttu-id="b4b50-108">[out] Указатель, который задается в возвращаемую [ISymUnmanagedSymbolSearchInfo](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-interface.md) интерфейса.</span><span class="sxs-lookup"><span data-stu-id="b4b50-108">[out] A pointer that is set to the returned [ISymUnmanagedSymbolSearchInfo](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b4b50-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="b4b50-109">Return Value</span></span>  
 <span data-ttu-id="b4b50-110">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="b4b50-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b4b50-111">Требования</span><span class="sxs-lookup"><span data-stu-id="b4b50-111">Requirements</span></span>  
 <span data-ttu-id="b4b50-112">**Заголовок:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="b4b50-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4b50-113">См. также</span><span class="sxs-lookup"><span data-stu-id="b4b50-113">See Also</span></span>  
 [<span data-ttu-id="b4b50-114">Интерфейс ISymUnmanagedReaderSymbolSearchInfo</span><span class="sxs-lookup"><span data-stu-id="b4b50-114">ISymUnmanagedReaderSymbolSearchInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreadersymbolsearchinfo-interface.md)

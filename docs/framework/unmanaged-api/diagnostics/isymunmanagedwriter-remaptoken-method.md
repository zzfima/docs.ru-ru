---
title: "Метод ISymUnmanagedWriter::RemapToken"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedWriter.RemapToken
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedWriter::RemapToken
helpviewer_keywords:
- ISymUnmanagedWriter::RemapToken method [.NET Framework debugging]
- RemapToken method [.NET Framework debugging]
ms.assetid: bca92682-ee1e-467f-8fb0-d8d4617f82fe
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 857b68c0443e7b23af30ed64ecc9b78af0b40880
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedwriterremaptoken-method"></a><span data-ttu-id="219d5-102">Метод ISymUnmanagedWriter::RemapToken</span><span class="sxs-lookup"><span data-stu-id="219d5-102">ISymUnmanagedWriter::RemapToken Method</span></span>
<span data-ttu-id="219d5-103">Уведомляет модуля записи символов о том, что маркер метаданных был повторно сопоставлен при выдаче метаданных.</span><span class="sxs-lookup"><span data-stu-id="219d5-103">Notifies the symbol writer that a metadata token has been remapped as the metadata was emitted.</span></span> <span data-ttu-id="219d5-104">Если модуль записи символов с сохраненными старый токен в хранилище символов, его необходимо либо обновить хранимые маркеры новое значение, либо сохранить сопоставление для соответствующего средства чтения символов для повторного сопоставления на этапе считывания.</span><span class="sxs-lookup"><span data-stu-id="219d5-104">If the symbol writer has stored the old token within the symbol store, it must either update the stored token with the new value, or it must save the map for the corresponding symbol reader to remap during the read phase.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="219d5-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="219d5-105">Syntax</span></span>  
  
```  
HRESULT RemapToken(  
    [in] mdToken  oldToken,  
    [in] mdToken  newToken);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="219d5-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="219d5-106">Parameters</span></span>  
 `oldToken`  
 <span data-ttu-id="219d5-107">[in] Токен метаданных, которая была пересопоставлена.</span><span class="sxs-lookup"><span data-stu-id="219d5-107">[in] The metadata token that was remapped.</span></span>  
  
 `newToken`  
 <span data-ttu-id="219d5-108">[in] Токен метаданных для которой `oldToken` была пересопоставлена.</span><span class="sxs-lookup"><span data-stu-id="219d5-108">[in] The new metadata token to which `oldToken` was remapped.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="219d5-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="219d5-109">Return Value</span></span>  
 <span data-ttu-id="219d5-110">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="219d5-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="219d5-111">Требования</span><span class="sxs-lookup"><span data-stu-id="219d5-111">Requirements</span></span>  
 <span data-ttu-id="219d5-112">**Заголовок:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="219d5-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="219d5-113">См. также</span><span class="sxs-lookup"><span data-stu-id="219d5-113">See Also</span></span>  
 [<span data-ttu-id="219d5-114">ISymUnmanagedWriter-интерфейс</span><span class="sxs-lookup"><span data-stu-id="219d5-114">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)

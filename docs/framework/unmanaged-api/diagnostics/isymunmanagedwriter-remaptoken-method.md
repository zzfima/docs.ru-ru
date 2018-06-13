---
title: Метод ISymUnmanagedWriter::RemapToken
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.RemapToken
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::RemapToken
helpviewer_keywords:
- ISymUnmanagedWriter::RemapToken method [.NET Framework debugging]
- RemapToken method [.NET Framework debugging]
ms.assetid: bca92682-ee1e-467f-8fb0-d8d4617f82fe
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f37630c9631e2e76d9b98730b84086b8b86ec55d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33427838"
---
# <a name="isymunmanagedwriterremaptoken-method"></a><span data-ttu-id="f25dc-102">Метод ISymUnmanagedWriter::RemapToken</span><span class="sxs-lookup"><span data-stu-id="f25dc-102">ISymUnmanagedWriter::RemapToken Method</span></span>
<span data-ttu-id="f25dc-103">Уведомляет модуля записи символов о том, что маркер метаданных был повторно сопоставлен при выдаче метаданных.</span><span class="sxs-lookup"><span data-stu-id="f25dc-103">Notifies the symbol writer that a metadata token has been remapped as the metadata was emitted.</span></span> <span data-ttu-id="f25dc-104">Если модуль записи символов с сохраненными старый токен в хранилище символов, его необходимо либо обновить хранимые маркеры новое значение, либо сохранить сопоставление для соответствующего средства чтения символов для повторного сопоставления на этапе считывания.</span><span class="sxs-lookup"><span data-stu-id="f25dc-104">If the symbol writer has stored the old token within the symbol store, it must either update the stored token with the new value, or it must save the map for the corresponding symbol reader to remap during the read phase.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f25dc-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f25dc-105">Syntax</span></span>  
  
```  
HRESULT RemapToken(  
    [in] mdToken  oldToken,  
    [in] mdToken  newToken);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f25dc-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="f25dc-106">Parameters</span></span>  
 `oldToken`  
 <span data-ttu-id="f25dc-107">[in] Токен метаданных, которая была пересопоставлена.</span><span class="sxs-lookup"><span data-stu-id="f25dc-107">[in] The metadata token that was remapped.</span></span>  
  
 `newToken`  
 <span data-ttu-id="f25dc-108">[in] Токен метаданных для которой `oldToken` была пересопоставлена.</span><span class="sxs-lookup"><span data-stu-id="f25dc-108">[in] The new metadata token to which `oldToken` was remapped.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f25dc-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="f25dc-109">Return Value</span></span>  
 <span data-ttu-id="f25dc-110">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="f25dc-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f25dc-111">Требования</span><span class="sxs-lookup"><span data-stu-id="f25dc-111">Requirements</span></span>  
 <span data-ttu-id="f25dc-112">**Заголовок:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="f25dc-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f25dc-113">См. также</span><span class="sxs-lookup"><span data-stu-id="f25dc-113">See Also</span></span>  
 [<span data-ttu-id="f25dc-114">Интерфейс ISymUnmanagedWriter</span><span class="sxs-lookup"><span data-stu-id="f25dc-114">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)

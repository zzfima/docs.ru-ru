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
ms.openlocfilehash: 979d14b4c404c3bf12c427bd5b8b1d4997805e7b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61986015"
---
# <a name="isymunmanagedwriterremaptoken-method"></a><span data-ttu-id="8b027-102">Метод ISymUnmanagedWriter::RemapToken</span><span class="sxs-lookup"><span data-stu-id="8b027-102">ISymUnmanagedWriter::RemapToken Method</span></span>
<span data-ttu-id="8b027-103">Уведомляет модуль записи символов, что маркер метаданных был повторно сопоставлен при выдаче метаданных.</span><span class="sxs-lookup"><span data-stu-id="8b027-103">Notifies the symbol writer that a metadata token has been remapped as the metadata was emitted.</span></span> <span data-ttu-id="8b027-104">Если модуль записи символов хранимая старый токен в хранилище символов, его необходимо либо обновить хранимые маркеры новое значение, либо сохранить сопоставление для соответствующего средства чтения символов для повторного сопоставления на этапе считывания.</span><span class="sxs-lookup"><span data-stu-id="8b027-104">If the symbol writer has stored the old token within the symbol store, it must either update the stored token with the new value, or it must save the map for the corresponding symbol reader to remap during the read phase.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8b027-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8b027-105">Syntax</span></span>  
  
```  
HRESULT RemapToken(  
    [in] mdToken  oldToken,  
    [in] mdToken  newToken);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8b027-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="8b027-106">Parameters</span></span>  
 `oldToken`  
 <span data-ttu-id="8b027-107">[in] Токен метаданных, который был переназначен.</span><span class="sxs-lookup"><span data-stu-id="8b027-107">[in] The metadata token that was remapped.</span></span>  
  
 `newToken`  
 <span data-ttu-id="8b027-108">[in] Новый маркер метаданных, к которому `oldToken` был переназначен.</span><span class="sxs-lookup"><span data-stu-id="8b027-108">[in] The new metadata token to which `oldToken` was remapped.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8b027-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="8b027-109">Return Value</span></span>  
 <span data-ttu-id="8b027-110">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="8b027-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8b027-111">Требования</span><span class="sxs-lookup"><span data-stu-id="8b027-111">Requirements</span></span>  
 <span data-ttu-id="8b027-112">**Заголовок.** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="8b027-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b027-113">См. также</span><span class="sxs-lookup"><span data-stu-id="8b027-113">See also</span></span>

- [<span data-ttu-id="8b027-114">Интерфейс ISymUnmanagedWriter</span><span class="sxs-lookup"><span data-stu-id="8b027-114">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)

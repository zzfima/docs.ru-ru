---
title: Метод ISymUnmanagedDocumentWriter::SetSource
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocumentWriter.SetSource
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocumentWriter::SetSource
helpviewer_keywords:
- ISymUnmanagedDocumentWriter::SetSource method [.NET Framework debugging]
- SetSource method [.NET Framework debugging]
ms.assetid: ea5b9d9f-ff06-4bd3-8de5-6435343aba59
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: da19a77637e64fec676fdaac7ba56d47b5b07769
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54549893"
---
# <a name="isymunmanageddocumentwritersetsource-method"></a><span data-ttu-id="21765-102">Метод ISymUnmanagedDocumentWriter::SetSource</span><span class="sxs-lookup"><span data-stu-id="21765-102">ISymUnmanagedDocumentWriter::SetSource Method</span></span>
<span data-ttu-id="21765-103">Устанавливает внедренный источник документа, который выполняется запись.</span><span class="sxs-lookup"><span data-stu-id="21765-103">Sets embedded source for a document that is being written.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="21765-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="21765-104">Syntax</span></span>  
  
```  
HRESULT SetSource(  
    [in]  ULONG32  sourceSize,  
    [in, size_is(sourceSize)] BYTE  source[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="21765-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="21765-105">Parameters</span></span>  
 `sourceSize`  
 <span data-ttu-id="21765-106">[in] Объект `ULONG32` , содержащий размер `source` буфера.</span><span class="sxs-lookup"><span data-stu-id="21765-106">[in] A `ULONG32` that contains the size of the `source` buffer.</span></span>  
  
 `source`  
 <span data-ttu-id="21765-107">[in] Буфер, который хранит внедренного источника.</span><span class="sxs-lookup"><span data-stu-id="21765-107">[in] The buffer that stores the embedded source.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="21765-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="21765-108">Return Value</span></span>  
 <span data-ttu-id="21765-109">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="21765-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="21765-110">Требования</span><span class="sxs-lookup"><span data-stu-id="21765-110">Requirements</span></span>  
 <span data-ttu-id="21765-111">**Заголовок.** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="21765-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21765-112">См. также</span><span class="sxs-lookup"><span data-stu-id="21765-112">See also</span></span>
- [<span data-ttu-id="21765-113">Интерфейс ISymUnmanagedDocumentWriter</span><span class="sxs-lookup"><span data-stu-id="21765-113">ISymUnmanagedDocumentWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocumentwriter-interface.md)

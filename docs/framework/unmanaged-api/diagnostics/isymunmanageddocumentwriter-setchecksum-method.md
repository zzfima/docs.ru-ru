---
title: Метод ISymUnmanagedDocumentWriter::SetCheckSum
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocumentWriter.SetCheckSum
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocumentWriter::SetCheckSum
helpviewer_keywords:
- ISymUnmanagedDocumentWriter::SetCheckSum method [.NET Framework debugging]
- SetCheckSum method [.NET Framework debugging]
ms.assetid: c7e99879-421f-43ce-b193-34733cf30085
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3b9b77b94e466a4aab4a575501ac6922293b3410
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="isymunmanageddocumentwritersetchecksum-method"></a><span data-ttu-id="a9f3c-102">Метод ISymUnmanagedDocumentWriter::SetCheckSum</span><span class="sxs-lookup"><span data-stu-id="a9f3c-102">ISymUnmanagedDocumentWriter::SetCheckSum Method</span></span>
<span data-ttu-id="a9f3c-103">Задает сведения о контрольной сумме.</span><span class="sxs-lookup"><span data-stu-id="a9f3c-103">Sets checksum information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a9f3c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a9f3c-104">Syntax</span></span>  
  
```  
HRESULT SetCheckSum(  
    [in]  GUID     algorithmId,  
    [in]  ULONG32  checkSumSize,  
    [in, size_is(checkSumSize)]  BYTE checkSum[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a9f3c-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="a9f3c-105">Parameters</span></span>  
 `algorithmId`  
 <span data-ttu-id="a9f3c-106">[in] Идентификатор GUID, представляющий идентификатор алгоритма.</span><span class="sxs-lookup"><span data-stu-id="a9f3c-106">[in] The GUID that represents the algorithm identifier.</span></span>  
  
 `checkSumSize`  
 <span data-ttu-id="a9f3c-107">[in] Объект `ULONG32` указывает размер в байтах для `checkSum` буфера.</span><span class="sxs-lookup"><span data-stu-id="a9f3c-107">[in] A `ULONG32` that indicates the size, in bytes, of the `checkSum` buffer.</span></span>  
  
 `checkSum`  
 <span data-ttu-id="a9f3c-108">[in] Буфер, в которой хранятся сведения о контрольной сумме.</span><span class="sxs-lookup"><span data-stu-id="a9f3c-108">[in] The buffer that stores the checksum information.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a9f3c-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="a9f3c-109">Return Value</span></span>  
 <span data-ttu-id="a9f3c-110">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="a9f3c-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a9f3c-111">Требования</span><span class="sxs-lookup"><span data-stu-id="a9f3c-111">Requirements</span></span>  
 <span data-ttu-id="a9f3c-112">**Заголовок:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="a9f3c-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9f3c-113">См. также</span><span class="sxs-lookup"><span data-stu-id="a9f3c-113">See Also</span></span>  
 [<span data-ttu-id="a9f3c-114">Интерфейс ISymUnmanagedDocumentWriter</span><span class="sxs-lookup"><span data-stu-id="a9f3c-114">ISymUnmanagedDocumentWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocumentwriter-interface.md)

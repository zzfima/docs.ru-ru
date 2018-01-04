---
title: "Метод ISymUnmanagedDocumentWriter::SetCheckSum"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedDocumentWriter.SetCheckSum
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedDocumentWriter::SetCheckSum
helpviewer_keywords:
- ISymUnmanagedDocumentWriter::SetCheckSum method [.NET Framework debugging]
- SetCheckSum method [.NET Framework debugging]
ms.assetid: c7e99879-421f-43ce-b193-34733cf30085
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0e4f653ab7b2a1341af8917c6932ea8bdfd64d83
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanageddocumentwritersetchecksum-method"></a><span data-ttu-id="f6497-102">Метод ISymUnmanagedDocumentWriter::SetCheckSum</span><span class="sxs-lookup"><span data-stu-id="f6497-102">ISymUnmanagedDocumentWriter::SetCheckSum Method</span></span>
<span data-ttu-id="f6497-103">Задает сведения о контрольной сумме.</span><span class="sxs-lookup"><span data-stu-id="f6497-103">Sets checksum information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f6497-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f6497-104">Syntax</span></span>  
  
```  
HRESULT SetCheckSum(  
    [in]  GUID     algorithmId,  
    [in]  ULONG32  checkSumSize,  
    [in, size_is(checkSumSize)]  BYTE checkSum[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f6497-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="f6497-105">Parameters</span></span>  
 `algorithmId`  
 <span data-ttu-id="f6497-106">[in] Идентификатор GUID, представляющий идентификатор алгоритма.</span><span class="sxs-lookup"><span data-stu-id="f6497-106">[in] The GUID that represents the algorithm identifier.</span></span>  
  
 `checkSumSize`  
 <span data-ttu-id="f6497-107">[in] Объект `ULONG32` указывает размер в байтах для `checkSum` буфера.</span><span class="sxs-lookup"><span data-stu-id="f6497-107">[in] A `ULONG32` that indicates the size, in bytes, of the `checkSum` buffer.</span></span>  
  
 `checkSum`  
 <span data-ttu-id="f6497-108">[in] Буфер, в которой хранятся сведения о контрольной сумме.</span><span class="sxs-lookup"><span data-stu-id="f6497-108">[in] The buffer that stores the checksum information.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f6497-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="f6497-109">Return Value</span></span>  
 <span data-ttu-id="f6497-110">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="f6497-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f6497-111">Требования</span><span class="sxs-lookup"><span data-stu-id="f6497-111">Requirements</span></span>  
 <span data-ttu-id="f6497-112">**Заголовок:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="f6497-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6497-113">См. также</span><span class="sxs-lookup"><span data-stu-id="f6497-113">See Also</span></span>  
 [<span data-ttu-id="f6497-114">Интерфейс ISymUnmanagedDocumentWriter</span><span class="sxs-lookup"><span data-stu-id="f6497-114">ISymUnmanagedDocumentWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocumentwriter-interface.md)

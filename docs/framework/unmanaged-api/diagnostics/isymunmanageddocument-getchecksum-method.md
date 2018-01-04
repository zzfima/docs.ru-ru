---
title: "Метод ISymUnmanagedDocument::GetCheckSum"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedDocument.GetCheckSum
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedDocument::GetCheckSum
helpviewer_keywords:
- ISymUnmanagedDocument::GetCheckSum method [.NET Framework debugging]
- GetCheckSum method [.NET Framework debugging]
ms.assetid: 9bc881b3-e2ce-48a7-ad69-17eaaa304120
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 19cd8881bdbd482cb420717855593d7b9583ae51
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanageddocumentgetchecksum-method"></a><span data-ttu-id="21bbb-102">Метод ISymUnmanagedDocument::GetCheckSum</span><span class="sxs-lookup"><span data-stu-id="21bbb-102">ISymUnmanagedDocument::GetCheckSum Method</span></span>
<span data-ttu-id="21bbb-103">Возвращает контрольную сумму.</span><span class="sxs-lookup"><span data-stu-id="21bbb-103">Gets the checksum.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="21bbb-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="21bbb-104">Syntax</span></span>  
  
```  
HRESULT GetCheckSum(  
    [in]  ULONG32  cData,  
    [out] ULONG32  *pcData,  
    [out, size_is(cData), length_is(*pcData)] BYTE data[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="21bbb-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="21bbb-105">Parameters</span></span>  
 `cData`  
 <span data-ttu-id="21bbb-106">[in] Длина буфера, предоставляемые `data` параметр</span><span class="sxs-lookup"><span data-stu-id="21bbb-106">[in] The length of the buffer provided by the `data` parameter</span></span>  
  
 `pcData`  
 <span data-ttu-id="21bbb-107">[out] Размер и длина контрольной суммы, в байтах.</span><span class="sxs-lookup"><span data-stu-id="21bbb-107">[out] The size and length of the checksum, in bytes.</span></span>  
  
 `data`  
 <span data-ttu-id="21bbb-108">[out] Буфер, получающий контрольную сумму.</span><span class="sxs-lookup"><span data-stu-id="21bbb-108">[out] The buffer that receives the checksum.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="21bbb-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="21bbb-109">Return Value</span></span>  
 <span data-ttu-id="21bbb-110">Значение S_OK, если метод выполнен успешно; в противном случае — код ошибки.</span><span class="sxs-lookup"><span data-stu-id="21bbb-110">S_OK if the method succeeds; otherwise, an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21bbb-111">См. также</span><span class="sxs-lookup"><span data-stu-id="21bbb-111">See Also</span></span>  
 [<span data-ttu-id="21bbb-112">Интерфейс ISymUnmanagedDocument</span><span class="sxs-lookup"><span data-stu-id="21bbb-112">ISymUnmanagedDocument Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)

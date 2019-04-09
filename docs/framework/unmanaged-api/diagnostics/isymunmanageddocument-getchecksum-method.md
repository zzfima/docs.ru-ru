---
title: Метод ISymUnmanagedDocument::GetCheckSum
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocument.GetCheckSum
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument::GetCheckSum
helpviewer_keywords:
- ISymUnmanagedDocument::GetCheckSum method [.NET Framework debugging]
- GetCheckSum method [.NET Framework debugging]
ms.assetid: 9bc881b3-e2ce-48a7-ad69-17eaaa304120
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a60bf279c143559e7410d8dfd8213d3da1d05a6d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59127566"
---
# <a name="isymunmanageddocumentgetchecksum-method"></a><span data-ttu-id="28b31-102">Метод ISymUnmanagedDocument::GetCheckSum</span><span class="sxs-lookup"><span data-stu-id="28b31-102">ISymUnmanagedDocument::GetCheckSum Method</span></span>
<span data-ttu-id="28b31-103">Возвращает контрольную сумму.</span><span class="sxs-lookup"><span data-stu-id="28b31-103">Gets the checksum.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="28b31-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="28b31-104">Syntax</span></span>  
  
```  
HRESULT GetCheckSum(  
    [in]  ULONG32  cData,  
    [out] ULONG32  *pcData,  
    [out, size_is(cData), length_is(*pcData)] BYTE data[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="28b31-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="28b31-105">Parameters</span></span>  
 `cData`  
 <span data-ttu-id="28b31-106">[in] Длина буфера, предоставляемые `data` параметр</span><span class="sxs-lookup"><span data-stu-id="28b31-106">[in] The length of the buffer provided by the `data` parameter</span></span>  
  
 `pcData`  
 <span data-ttu-id="28b31-107">[out] Размер и длину контрольная сумма, в байтах.</span><span class="sxs-lookup"><span data-stu-id="28b31-107">[out] The size and length of the checksum, in bytes.</span></span>  
  
 `data`  
 <span data-ttu-id="28b31-108">[out] Буфер, получающий контрольную сумму.</span><span class="sxs-lookup"><span data-stu-id="28b31-108">[out] The buffer that receives the checksum.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="28b31-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="28b31-109">Return Value</span></span>  
 <span data-ttu-id="28b31-110">Значение S_OK, если метод выполнен успешно; в противном случае — код ошибки.</span><span class="sxs-lookup"><span data-stu-id="28b31-110">S_OK if the method succeeds; otherwise, an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28b31-111">См. также</span><span class="sxs-lookup"><span data-stu-id="28b31-111">See also</span></span>

- [<span data-ttu-id="28b31-112">Интерфейс ISymUnmanagedDocument</span><span class="sxs-lookup"><span data-stu-id="28b31-112">ISymUnmanagedDocument Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)

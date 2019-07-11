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
ms.openlocfilehash: b34f985f199542612bcdb9b30ebae28649438e1b
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67776767"
---
# <a name="isymunmanageddocumentgetchecksum-method"></a><span data-ttu-id="f9841-102">Метод ISymUnmanagedDocument::GetCheckSum</span><span class="sxs-lookup"><span data-stu-id="f9841-102">ISymUnmanagedDocument::GetCheckSum Method</span></span>
<span data-ttu-id="f9841-103">Возвращает контрольную сумму.</span><span class="sxs-lookup"><span data-stu-id="f9841-103">Gets the checksum.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f9841-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f9841-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCheckSum(  
    [in]  ULONG32  cData,  
    [out] ULONG32  *pcData,  
    [out, size_is(cData), length_is(*pcData)] BYTE data[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f9841-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="f9841-105">Parameters</span></span>  
 `cData`  
 <span data-ttu-id="f9841-106">[in] Длина буфера, предоставляемые `data` параметр</span><span class="sxs-lookup"><span data-stu-id="f9841-106">[in] The length of the buffer provided by the `data` parameter</span></span>  
  
 `pcData`  
 <span data-ttu-id="f9841-107">[out] Размер и длину контрольная сумма, в байтах.</span><span class="sxs-lookup"><span data-stu-id="f9841-107">[out] The size and length of the checksum, in bytes.</span></span>  
  
 `data`  
 <span data-ttu-id="f9841-108">[out] Буфер, получающий контрольную сумму.</span><span class="sxs-lookup"><span data-stu-id="f9841-108">[out] The buffer that receives the checksum.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f9841-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="f9841-109">Return Value</span></span>  
 <span data-ttu-id="f9841-110">Значение S_OK, если метод выполнен успешно; в противном случае — код ошибки.</span><span class="sxs-lookup"><span data-stu-id="f9841-110">S_OK if the method succeeds; otherwise, an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9841-111">См. также</span><span class="sxs-lookup"><span data-stu-id="f9841-111">See also</span></span>

- [<span data-ttu-id="f9841-112">Интерфейс ISymUnmanagedDocument</span><span class="sxs-lookup"><span data-stu-id="f9841-112">ISymUnmanagedDocument Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)

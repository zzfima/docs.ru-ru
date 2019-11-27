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
ms.openlocfilehash: 52e1fc20fbe1d8709c21cacde926cf8bebb49425
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449200"
---
# <a name="isymunmanageddocumentgetchecksum-method"></a><span data-ttu-id="2b214-102">Метод ISymUnmanagedDocument::GetCheckSum</span><span class="sxs-lookup"><span data-stu-id="2b214-102">ISymUnmanagedDocument::GetCheckSum Method</span></span>
<span data-ttu-id="2b214-103">Возвращает контрольную сумму.</span><span class="sxs-lookup"><span data-stu-id="2b214-103">Gets the checksum.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2b214-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2b214-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCheckSum(  
    [in]  ULONG32  cData,  
    [out] ULONG32  *pcData,  
    [out, size_is(cData), length_is(*pcData)] BYTE data[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2b214-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="2b214-105">Parameters</span></span>  
 `cData`  
 <span data-ttu-id="2b214-106">окне Длина буфера, предоставленного параметром `data`</span><span class="sxs-lookup"><span data-stu-id="2b214-106">[in] The length of the buffer provided by the `data` parameter</span></span>  
  
 `pcData`  
 <span data-ttu-id="2b214-107">заполняет Размер и длина контрольной суммы в байтах.</span><span class="sxs-lookup"><span data-stu-id="2b214-107">[out] The size and length of the checksum, in bytes.</span></span>  
  
 `data`  
 <span data-ttu-id="2b214-108">заполняет Буфер, получающий контрольную сумму.</span><span class="sxs-lookup"><span data-stu-id="2b214-108">[out] The buffer that receives the checksum.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2b214-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="2b214-109">Return Value</span></span>  
 <span data-ttu-id="2b214-110">S_OK, если метод выполнен. в противном случае — код ошибки.</span><span class="sxs-lookup"><span data-stu-id="2b214-110">S_OK if the method succeeds; otherwise, an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b214-111">См. также:</span><span class="sxs-lookup"><span data-stu-id="2b214-111">See also</span></span>

- [<span data-ttu-id="2b214-112">Интерфейс ISymUnmanagedDocument</span><span class="sxs-lookup"><span data-stu-id="2b214-112">ISymUnmanagedDocument Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)

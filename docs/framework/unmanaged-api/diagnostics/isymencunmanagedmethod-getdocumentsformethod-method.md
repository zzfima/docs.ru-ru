---
title: Метод ISymENCUnmanagedMethod::GetDocumentsForMethod
ms.date: 03/30/2017
api_name:
- ISymENCUnmanagedMethod.GetDocumentsForMethod
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymENCUnmanagedMethod::GetDocumentsForMethod
helpviewer_keywords:
- GetDocumentsForMethod method [.NET Framework debugging]
- ISymENCUnmanagedMethod::GetDocumentsForMethod method [.NET Framework debugging]
ms.assetid: bd6ccde5-d578-48d8-abed-b474fbd48d13
topic_type:
- apiref
ms.openlocfilehash: 97f0d81c389ffd0bd8a69df2ca39322d726f98bc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176634"
---
# <a name="isymencunmanagedmethodgetdocumentsformethod-method"></a><span data-ttu-id="0662e-102">Метод ISymENCUnmanagedMethod::GetDocumentsForMethod</span><span class="sxs-lookup"><span data-stu-id="0662e-102">ISymENCUnmanagedMethod::GetDocumentsForMethod Method</span></span>
<span data-ttu-id="0662e-103">Получает документы, в которые есть строки этого метода.</span><span class="sxs-lookup"><span data-stu-id="0662e-103">Gets the documents that this method has lines in.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0662e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0662e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetDocumentsForMethod(  
    [in]  ULONG32  cDocs,  
    [out] ULONG32  *pcDocs,
    [in, size_is(cDocs)] ISymUnmanagedDocument* documents[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0662e-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="0662e-105">Parameters</span></span>  
 `cDocs`  
 <span data-ttu-id="0662e-106">(в) Длина буфера, на `pcDocs`который указывает .</span><span class="sxs-lookup"><span data-stu-id="0662e-106">[in] The length of the buffer pointed to by `pcDocs`.</span></span>  
  
 `pcDocs`  
 <span data-ttu-id="0662e-107">(ваут) Указатель на `ULONG32` указатель, который получает размер в символах буфера, необходимого для хранения документов.</span><span class="sxs-lookup"><span data-stu-id="0662e-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the documents.</span></span>  
  
 `documents`  
 <span data-ttu-id="0662e-108">(в) Буфер, содержащий документы.</span><span class="sxs-lookup"><span data-stu-id="0662e-108">[in] The buffer that contains the documents.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0662e-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="0662e-109">Return Value</span></span>  
 <span data-ttu-id="0662e-110">S_OK, если метод удается; в противном случае код ошибки.</span><span class="sxs-lookup"><span data-stu-id="0662e-110">S_OK if the method succeeds; otherwise, an error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0662e-111">Требования</span><span class="sxs-lookup"><span data-stu-id="0662e-111">Requirements</span></span>  
 <span data-ttu-id="0662e-112">**Заголовок:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="0662e-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0662e-113">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="0662e-113">See also</span></span>

- [<span data-ttu-id="0662e-114">Интерфейс ISymENCUnmanagedMethod</span><span class="sxs-lookup"><span data-stu-id="0662e-114">ISymENCUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-interface.md)

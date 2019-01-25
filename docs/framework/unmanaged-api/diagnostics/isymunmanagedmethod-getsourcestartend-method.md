---
title: Метод ISymUnmanagedMethod::GetSourceStartEnd
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod.GetSourceStartEnd
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod::GetSourceStartEnd
helpviewer_keywords:
- GetSourceStartEnd method [.NET Framework debugging]
- ISymUnmanagedMethod::GetSourceStartEnd method [.NET Framework debugging]
ms.assetid: 2a420900-01f1-4461-8777-3a34a6dc1426
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4ecb726f275a694fded2c486448a60b28fadb168
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54561872"
---
# <a name="isymunmanagedmethodgetsourcestartend-method"></a><span data-ttu-id="80319-102">Метод ISymUnmanagedMethod::GetSourceStartEnd</span><span class="sxs-lookup"><span data-stu-id="80319-102">ISymUnmanagedMethod::GetSourceStartEnd Method</span></span>
<span data-ttu-id="80319-103">Получает начальное и конечное положение документа для источника этого метода.</span><span class="sxs-lookup"><span data-stu-id="80319-103">Gets the start and end document positions for the source of this method.</span></span> <span data-ttu-id="80319-104">Массив отсчитывается от начала, а вторая позиция массива является конечным.</span><span class="sxs-lookup"><span data-stu-id="80319-104">The first array position is the start, and the second array position is the end.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="80319-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="80319-105">Syntax</span></span>  
  
```  
HRESULT GetSourceStartEnd(  
    [in]  ISymUnmanagedDocument  *docs[2],  
    [in]  ULONG32                lines[2],  
    [in]  ULONG32                columns[2],  
    [out] BOOL                   *pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="80319-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="80319-106">Parameters</span></span>  
 `docs`  
 <span data-ttu-id="80319-107">[in] Начальный и конечный исходные документы.</span><span class="sxs-lookup"><span data-stu-id="80319-107">[in] The starting and ending source documents.</span></span>  
  
 `lines`  
 <span data-ttu-id="80319-108">[in] Начальная и конечная строки соответствующих исходных документов.</span><span class="sxs-lookup"><span data-stu-id="80319-108">[in] The starting and ending lines in the corresponding source documents.</span></span>  
  
 `columns`  
 <span data-ttu-id="80319-109">[in] Начальный и конечный столбцы соответствующих исходных документов.</span><span class="sxs-lookup"><span data-stu-id="80319-109">[in] The starting and ending columns in the corresponding source documents.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="80319-110">[out] `true` будто positions, определен; в противном случае — `false`.</span><span class="sxs-lookup"><span data-stu-id="80319-110">[out] `true` if positions were defined; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="80319-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="80319-111">Return Value</span></span>  
 <span data-ttu-id="80319-112">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="80319-112">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="80319-113">Требования</span><span class="sxs-lookup"><span data-stu-id="80319-113">Requirements</span></span>  
 <span data-ttu-id="80319-114">**Заголовок.** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="80319-114">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80319-115">См. также</span><span class="sxs-lookup"><span data-stu-id="80319-115">See also</span></span>
- [<span data-ttu-id="80319-116">Интерфейс ISymUnmanagedMethod</span><span class="sxs-lookup"><span data-stu-id="80319-116">ISymUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)

---
title: Метод ISymUnmanagedMethod::GetRanges
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod.GetRanges
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod::GetRanges
helpviewer_keywords:
- ISymUnmanagedMethod::GetRanges method [.NET Framework debugging]
- GetRanges method [.NET Framework debugging]
ms.assetid: a85283d8-379c-417a-9736-ddeeef9bcf50
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 308207e100a9770474dd896ea4cba42d7db5d241
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57485555"
---
# <a name="isymunmanagedmethodgetranges-method"></a><span data-ttu-id="b6ae0-102">Метод ISymUnmanagedMethod::GetRanges</span><span class="sxs-lookup"><span data-stu-id="b6ae0-102">ISymUnmanagedMethod::GetRanges Method</span></span>
<span data-ttu-id="b6ae0-103">Возвращает массив пар начального и конечного смещения, соответствующих диапазонам на языке MSIL, занимаемым позиция в этом методе обозначение позиции в документе.</span><span class="sxs-lookup"><span data-stu-id="b6ae0-103">Given a position in a document, returns an array of start and end offset pairs that correspond to the ranges of Microsoft intermediate language (MSIL) that the position covers within this method.</span></span> <span data-ttu-id="b6ae0-104">Массив представляет собой массив целых чисел и имеет формат [начало, конец, начало, конец].</span><span class="sxs-lookup"><span data-stu-id="b6ae0-104">The array is an array of integers and has the format [start, end, start, end].</span></span> <span data-ttu-id="b6ae0-105">Число пар "диапазон" — Длина массива, поделенную на 2.</span><span class="sxs-lookup"><span data-stu-id="b6ae0-105">The number of range pairs is the length of the array divided by 2.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b6ae0-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b6ae0-106">Syntax</span></span>  
  
```  
HRESULT GetRanges(  
    [in]  ISymUnmanagedDocument* document,  
    [in]  ULONG32                line,  
    [in]  ULONG32                column,  
    [in]  ULONG32                cRanges,  
    [out] ULONG32                *pcRanges,  
    [out, size_is(cRanges),  
        length_is(*pcRanges)] ULONG32 ranges[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b6ae0-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="b6ae0-107">Parameters</span></span>  
 `document`  
 <span data-ttu-id="b6ae0-108">[in] Документ, для которого запрашивается смещение.</span><span class="sxs-lookup"><span data-stu-id="b6ae0-108">[in] The document for which the offset is requested.</span></span>  
  
 `line`  
 <span data-ttu-id="b6ae0-109">[in] Строка документа, соответствующая этим диапазонам.</span><span class="sxs-lookup"><span data-stu-id="b6ae0-109">[in] The document line corresponding to the ranges.</span></span>  
  
 `column`  
 <span data-ttu-id="b6ae0-110">[in] Столбец документа, соответствующая этим диапазонам.</span><span class="sxs-lookup"><span data-stu-id="b6ae0-110">[in] The document column corresponding to the ranges.</span></span>  
  
 `cRanges`  
 <span data-ttu-id="b6ae0-111">[in] Размер массива `ranges`.</span><span class="sxs-lookup"><span data-stu-id="b6ae0-111">[in] The size of the `ranges` array.</span></span>  
  
 `pcRanges`  
 <span data-ttu-id="b6ae0-112">[out] Указатель на `ULONG32` , получающий размер буфера, необходимый для диапазонов.</span><span class="sxs-lookup"><span data-stu-id="b6ae0-112">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the ranges.</span></span>  
  
 `ranges`  
 <span data-ttu-id="b6ae0-113">[out] Указатель на буфер, получающий диапазоны.</span><span class="sxs-lookup"><span data-stu-id="b6ae0-113">[out] A pointer to the buffer that receives the ranges.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b6ae0-114">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="b6ae0-114">Return Value</span></span>  
 <span data-ttu-id="b6ae0-115">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="b6ae0-115">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b6ae0-116">Требования</span><span class="sxs-lookup"><span data-stu-id="b6ae0-116">Requirements</span></span>  
 <span data-ttu-id="b6ae0-117">**Заголовок.** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="b6ae0-117">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6ae0-118">См. также</span><span class="sxs-lookup"><span data-stu-id="b6ae0-118">See also</span></span>
- [<span data-ttu-id="b6ae0-119">Интерфейс ISymUnmanagedMethod</span><span class="sxs-lookup"><span data-stu-id="b6ae0-119">ISymUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)

---
title: Метод ISymUnmanagedWriter::DefineSequencePoints
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.DefineSequencePoints
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::DefineSequencePoints
helpviewer_keywords:
- DefineSequencePoints method [.NET Framework debugging]
- ISymUnmanagedWriter::DefineSequencePoints method [.NET Framework debugging]
ms.assetid: 64202baf-be6b-40ba-8162-8cc6c0c9b8e1
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4210dedd77c6ab041189fa287e192bb7038080b2
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57491425"
---
# <a name="isymunmanagedwriterdefinesequencepoints-method"></a><span data-ttu-id="31fde-102">Метод ISymUnmanagedWriter::DefineSequencePoints</span><span class="sxs-lookup"><span data-stu-id="31fde-102">ISymUnmanagedWriter::DefineSequencePoints Method</span></span>
<span data-ttu-id="31fde-103">Определяет группу точек следования в текущем методе.</span><span class="sxs-lookup"><span data-stu-id="31fde-103">Defines a group of sequence points within the current method.</span></span> <span data-ttu-id="31fde-104">Каждая Начальная строка и начальный столбец определяют начало оператора в методе.</span><span class="sxs-lookup"><span data-stu-id="31fde-104">Each starting line and starting column define the start of a statement within a method.</span></span> <span data-ttu-id="31fde-105">Каждая конечная строка и конечный столбец определяет конец оператора в методе.</span><span class="sxs-lookup"><span data-stu-id="31fde-105">Each ending line and ending column define the end of a statement within a method.</span></span> <span data-ttu-id="31fde-106">Массивы должны быть упорядочены по возрастанию смещений.</span><span class="sxs-lookup"><span data-stu-id="31fde-106">The arrays should be sorted in increasing order of offsets.</span></span> <span data-ttu-id="31fde-107">Смещение всегда измеряется от начала метода, в байтах.</span><span class="sxs-lookup"><span data-stu-id="31fde-107">The offset is always measured from the start of the method, in bytes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="31fde-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="31fde-108">Syntax</span></span>  
  
```  
HRESULT DefineSequencePoints(  
    [in] ISymUnmanagedDocumentWriter*  document,  
    [in] ULONG32 spCount,  
    [in, size_is(spCount)] ULONG32     offsets[],  
    [in, size_is(spCount)] ULONG32     lines[],  
    [in, size_is(spCount)] ULONG32     columns[],  
    [in, size_is(spCount)] ULONG32     endLines[],  
    [in, size_is(spCount)] ULONG32     endColumns[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="31fde-109">Параметры</span><span class="sxs-lookup"><span data-stu-id="31fde-109">Parameters</span></span>  
 `document`  
 <span data-ttu-id="31fde-110">[in] Объект документа, для которого определяются точки следования.</span><span class="sxs-lookup"><span data-stu-id="31fde-110">[in] The document object for which the sequence points are being defined.</span></span>  
  
 `spCount`  
 <span data-ttu-id="31fde-111">[in] Объект `ULONG32` указывает размер каждого из `offsets`, `lines`, `columns`, `endLines`, и `endColumns` буферов.</span><span class="sxs-lookup"><span data-stu-id="31fde-111">[in] A `ULONG32` that indicates the size of each of the `offsets`, `lines`, `columns`, `endLines`, and `endColumns` buffers.</span></span>  
  
 `offsets`  
 <span data-ttu-id="31fde-112">[in] Смещение точек следования определяются от начала метода.</span><span class="sxs-lookup"><span data-stu-id="31fde-112">[in] The offset of the sequence points measured from the beginning of the method.</span></span>  
  
 `lines`  
 <span data-ttu-id="31fde-113">[in] Начальная строка числа точек следования.</span><span class="sxs-lookup"><span data-stu-id="31fde-113">[in] The starting line numbers of the sequence points.</span></span>  
  
 `columns`  
 <span data-ttu-id="31fde-114">[in] Начальный номера столбцов точек следования.</span><span class="sxs-lookup"><span data-stu-id="31fde-114">[in] The starting column numbers of the sequence points.</span></span>  
  
 `endLines`  
 <span data-ttu-id="31fde-115">[in] Конечный номера строк точек следования.</span><span class="sxs-lookup"><span data-stu-id="31fde-115">[in] The ending line numbers of the sequence points.</span></span> <span data-ttu-id="31fde-116">Этот параметр является необязательным.</span><span class="sxs-lookup"><span data-stu-id="31fde-116">This parameter is optional.</span></span>  
  
 `endColumns`  
 <span data-ttu-id="31fde-117">[in] Номера конечных столбцов точек следования.</span><span class="sxs-lookup"><span data-stu-id="31fde-117">[in] The ending column numbers of the sequence points.</span></span> <span data-ttu-id="31fde-118">Этот параметр является необязательным.</span><span class="sxs-lookup"><span data-stu-id="31fde-118">This parameter is optional.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="31fde-119">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="31fde-119">Return Value</span></span>  
 <span data-ttu-id="31fde-120">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="31fde-120">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="31fde-121">Требования</span><span class="sxs-lookup"><span data-stu-id="31fde-121">Requirements</span></span>  
 <span data-ttu-id="31fde-122">**Заголовок.** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="31fde-122">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31fde-123">См. также</span><span class="sxs-lookup"><span data-stu-id="31fde-123">See also</span></span>
- [<span data-ttu-id="31fde-124">Интерфейс ISymUnmanagedWriter</span><span class="sxs-lookup"><span data-stu-id="31fde-124">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)

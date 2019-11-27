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
ms.openlocfilehash: 63ba108bc234e566450bb019afc63acb4e75ad1f
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74427981"
---
# <a name="isymunmanagedwriterdefinesequencepoints-method"></a><span data-ttu-id="c1ebd-102">Метод ISymUnmanagedWriter::DefineSequencePoints</span><span class="sxs-lookup"><span data-stu-id="c1ebd-102">ISymUnmanagedWriter::DefineSequencePoints Method</span></span>
<span data-ttu-id="c1ebd-103">Определяет группу точек следования в текущем методе.</span><span class="sxs-lookup"><span data-stu-id="c1ebd-103">Defines a group of sequence points within the current method.</span></span> <span data-ttu-id="c1ebd-104">Каждая начальная строка и начальный столбец определяют начало инструкции в методе.</span><span class="sxs-lookup"><span data-stu-id="c1ebd-104">Each starting line and starting column define the start of a statement within a method.</span></span> <span data-ttu-id="c1ebd-105">Каждая конечная строка и конечный столбец определяют конец оператора в методе.</span><span class="sxs-lookup"><span data-stu-id="c1ebd-105">Each ending line and ending column define the end of a statement within a method.</span></span> <span data-ttu-id="c1ebd-106">Массивы должны быть отсортированы в порядке возрастания смещений.</span><span class="sxs-lookup"><span data-stu-id="c1ebd-106">The arrays should be sorted in increasing order of offsets.</span></span> <span data-ttu-id="c1ebd-107">Смещение всегда измеряется от начала метода в байтах.</span><span class="sxs-lookup"><span data-stu-id="c1ebd-107">The offset is always measured from the start of the method, in bytes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c1ebd-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c1ebd-108">Syntax</span></span>  
  
```cpp  
HRESULT DefineSequencePoints(  
    [in] ISymUnmanagedDocumentWriter*  document,  
    [in] ULONG32 spCount,  
    [in, size_is(spCount)] ULONG32     offsets[],  
    [in, size_is(spCount)] ULONG32     lines[],  
    [in, size_is(spCount)] ULONG32     columns[],  
    [in, size_is(spCount)] ULONG32     endLines[],  
    [in, size_is(spCount)] ULONG32     endColumns[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c1ebd-109">Параметры</span><span class="sxs-lookup"><span data-stu-id="c1ebd-109">Parameters</span></span>  
 `document`  
 <span data-ttu-id="c1ebd-110">окне Объект документа, для которого определяются точки следования.</span><span class="sxs-lookup"><span data-stu-id="c1ebd-110">[in] The document object for which the sequence points are being defined.</span></span>  
  
 `spCount`  
 <span data-ttu-id="c1ebd-111">окне `ULONG32`, указывающий размер каждого из буферов `offsets`, `lines`, `columns`, `endLines`и `endColumns`.</span><span class="sxs-lookup"><span data-stu-id="c1ebd-111">[in] A `ULONG32` that indicates the size of each of the `offsets`, `lines`, `columns`, `endLines`, and `endColumns` buffers.</span></span>  
  
 `offsets`  
 <span data-ttu-id="c1ebd-112">окне Смещение точек последовательности, измеряемое от начала метода.</span><span class="sxs-lookup"><span data-stu-id="c1ebd-112">[in] The offset of the sequence points measured from the beginning of the method.</span></span>  
  
 `lines`  
 <span data-ttu-id="c1ebd-113">окне Начальные номера строк точек следования.</span><span class="sxs-lookup"><span data-stu-id="c1ebd-113">[in] The starting line numbers of the sequence points.</span></span>  
  
 `columns`  
 <span data-ttu-id="c1ebd-114">окне Начальные номера столбцов точек следования.</span><span class="sxs-lookup"><span data-stu-id="c1ebd-114">[in] The starting column numbers of the sequence points.</span></span>  
  
 `endLines`  
 <span data-ttu-id="c1ebd-115">окне Номера конечных строк точек следования.</span><span class="sxs-lookup"><span data-stu-id="c1ebd-115">[in] The ending line numbers of the sequence points.</span></span> <span data-ttu-id="c1ebd-116">Этот параметр является необязательным.</span><span class="sxs-lookup"><span data-stu-id="c1ebd-116">This parameter is optional.</span></span>  
  
 `endColumns`  
 <span data-ttu-id="c1ebd-117">окне Конечные номера столбцов точек следования.</span><span class="sxs-lookup"><span data-stu-id="c1ebd-117">[in] The ending column numbers of the sequence points.</span></span> <span data-ttu-id="c1ebd-118">Этот параметр является необязательным.</span><span class="sxs-lookup"><span data-stu-id="c1ebd-118">This parameter is optional.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c1ebd-119">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="c1ebd-119">Return Value</span></span>  
 <span data-ttu-id="c1ebd-120">S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.</span><span class="sxs-lookup"><span data-stu-id="c1ebd-120">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c1ebd-121">Требования</span><span class="sxs-lookup"><span data-stu-id="c1ebd-121">Requirements</span></span>  
 <span data-ttu-id="c1ebd-122">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="c1ebd-122">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1ebd-123">См. также</span><span class="sxs-lookup"><span data-stu-id="c1ebd-123">See also</span></span>

- [<span data-ttu-id="c1ebd-124">Интерфейс ISymUnmanagedWriter</span><span class="sxs-lookup"><span data-stu-id="c1ebd-124">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)

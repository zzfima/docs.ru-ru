---
title: "Метод ISymUnmanagedMethod::GetSequencePoints"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedMethod.GetSequencePoints
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedMethod::GetSequencePoints
helpviewer_keywords:
- ISymUnmanagedMethod::GetSequencePoints method [.NET Framework debugging]
- GetSequencePoints method [.NET Framework debugging]
ms.assetid: f909ac48-3d8f-49fb-a369-e3d9959151cd
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 3cde9de634534acdeafa40bd7a94c46624e49604
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedmethodgetsequencepoints-method"></a><span data-ttu-id="3ffd3-102">Метод ISymUnmanagedMethod::GetSequencePoints</span><span class="sxs-lookup"><span data-stu-id="3ffd3-102">ISymUnmanagedMethod::GetSequencePoints Method</span></span>
<span data-ttu-id="3ffd3-103">Возвращает все точки следования в методе.</span><span class="sxs-lookup"><span data-stu-id="3ffd3-103">Gets all the sequence points within this method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3ffd3-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3ffd3-104">Syntax</span></span>  
  
```  
HRESULT GetSequencePoints(  
    [in]  ULONG32  cPoints,  
    [out] ULONG32  *pcPoints,  
    [in, size_is(cPoints)] ULONG32  offsets[],  
    [in, size_is(cPoints)] ISymUnmanagedDocument* documents[],  
    [in, size_is(cPoints)] ULONG32  lines[],  
    [in, size_is(cPoints)] ULONG32  columns[],  
    [in, size_is(cPoints)] ULONG32  endLines[],  
    [in, size_is(cPoints)] ULONG32  endColumns[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3ffd3-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="3ffd3-105">Parameters</span></span>  
 `cPoints`  
 <span data-ttu-id="3ffd3-106">[in] Объект `ULONG32` , получающий размер `offsets`, `documents`, `lines`, `columns`, `endLines`, и `endColumns` массивов.</span><span class="sxs-lookup"><span data-stu-id="3ffd3-106">[in] A `ULONG32` that receives the size of the `offsets`, `documents`, `lines`, `columns`, `endLines`, and `endColumns` arrays.</span></span>  
  
 `pcPoints`  
 <span data-ttu-id="3ffd3-107">[out] Указатель на `ULONG32` , который получает длину буфера, требуемое для размещения точек следования.</span><span class="sxs-lookup"><span data-stu-id="3ffd3-107">[out] A pointer to a `ULONG32` that receives the length of the buffer required to contain the sequence points.</span></span>  
  
 `offsets`  
 <span data-ttu-id="3ffd3-108">[in] Массив, в котором для хранения промежуточных Microsoft (MSIL) смещений на языке от начала метода для точек следования.</span><span class="sxs-lookup"><span data-stu-id="3ffd3-108">[in] An array in which to store the Microsoft intermediate language (MSIL) offsets from the beginning of the method for the sequence points.</span></span>  
  
 `documents`  
 <span data-ttu-id="3ffd3-109">[in] Массив для хранения документов, в которых находятся точки следования.</span><span class="sxs-lookup"><span data-stu-id="3ffd3-109">[in] An array in which to store the documents in which the sequence points are located.</span></span>  
  
 `lines`  
 <span data-ttu-id="3ffd3-110">[in] Массив для сохранения строк в документах, в которых находятся точки следования.</span><span class="sxs-lookup"><span data-stu-id="3ffd3-110">[in] An array in which to store the lines in the documents at which the sequence points are located.</span></span>  
  
 `columns`  
 <span data-ttu-id="3ffd3-111">[in] Массив для хранения этих столбцов в документах, в которых находятся точки следования.</span><span class="sxs-lookup"><span data-stu-id="3ffd3-111">[in] An array in which to store the columns in the documents at which the sequence points are located.</span></span>  
  
 `endLines`  
 <span data-ttu-id="3ffd3-112">[in] Массив строк в документах, в которых заканчиваются точки следования.</span><span class="sxs-lookup"><span data-stu-id="3ffd3-112">[in] The array of lines in the documents at which the sequence points end.</span></span>  
  
 `endColumns`  
 <span data-ttu-id="3ffd3-113">[in] Массив столбцов в документах, в которых заканчиваются точки следования.</span><span class="sxs-lookup"><span data-stu-id="3ffd3-113">[in] The array of columns in the documents at which the sequence points end.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3ffd3-114">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="3ffd3-114">Return Value</span></span>  
 <span data-ttu-id="3ffd3-115">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="3ffd3-115">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3ffd3-116">Требования</span><span class="sxs-lookup"><span data-stu-id="3ffd3-116">Requirements</span></span>  
 <span data-ttu-id="3ffd3-117">**Заголовок:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="3ffd3-117">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ffd3-118">См. также</span><span class="sxs-lookup"><span data-stu-id="3ffd3-118">See Also</span></span>  
 [<span data-ttu-id="3ffd3-119">ISymUnmanagedMethod-интерфейс</span><span class="sxs-lookup"><span data-stu-id="3ffd3-119">ISymUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)

---
title: Метод ISymUnmanagedMethod::GetSequencePoints
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod.GetSequencePoints
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod::GetSequencePoints
helpviewer_keywords:
- ISymUnmanagedMethod::GetSequencePoints method [.NET Framework debugging]
- GetSequencePoints method [.NET Framework debugging]
ms.assetid: f909ac48-3d8f-49fb-a369-e3d9959151cd
topic_type:
- apiref
ms.openlocfilehash: 75d477af7395a9b7d3328b2a5787f810733f3749
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448874"
---
# <a name="isymunmanagedmethodgetsequencepoints-method"></a><span data-ttu-id="2c780-102">Метод ISymUnmanagedMethod::GetSequencePoints</span><span class="sxs-lookup"><span data-stu-id="2c780-102">ISymUnmanagedMethod::GetSequencePoints Method</span></span>
<span data-ttu-id="2c780-103">Возвращает все точки следования в этом методе.</span><span class="sxs-lookup"><span data-stu-id="2c780-103">Gets all the sequence points within this method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2c780-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2c780-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="parameters"></a><span data-ttu-id="2c780-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="2c780-105">Parameters</span></span>  
 `cPoints`  
 <span data-ttu-id="2c780-106">окне `ULONG32`, получающий размер массивов `offsets`, `documents`, `lines`, `columns`, `endLines`и `endColumns`.</span><span class="sxs-lookup"><span data-stu-id="2c780-106">[in] A `ULONG32` that receives the size of the `offsets`, `documents`, `lines`, `columns`, `endLines`, and `endColumns` arrays.</span></span>  
  
 `pcPoints`  
 <span data-ttu-id="2c780-107">заполняет Указатель на `ULONG32`, который получает длину буфера, необходимую для хранения точек следования.</span><span class="sxs-lookup"><span data-stu-id="2c780-107">[out] A pointer to a `ULONG32` that receives the length of the buffer required to contain the sequence points.</span></span>  
  
 `offsets`  
 <span data-ttu-id="2c780-108">окне Массив, в котором хранятся смещения MSIL от начала метода для точек следования.</span><span class="sxs-lookup"><span data-stu-id="2c780-108">[in] An array in which to store the Microsoft intermediate language (MSIL) offsets from the beginning of the method for the sequence points.</span></span>  
  
 `documents`  
 <span data-ttu-id="2c780-109">окне Массив, в котором хранятся документы, в которых находятся точки следования.</span><span class="sxs-lookup"><span data-stu-id="2c780-109">[in] An array in which to store the documents in which the sequence points are located.</span></span>  
  
 `lines`  
 <span data-ttu-id="2c780-110">окне Массив, в котором хранятся строки в документах, где находятся точки следования.</span><span class="sxs-lookup"><span data-stu-id="2c780-110">[in] An array in which to store the lines in the documents at which the sequence points are located.</span></span>  
  
 `columns`  
 <span data-ttu-id="2c780-111">окне Массив, в котором хранятся столбцы в документах, где находятся точки следования.</span><span class="sxs-lookup"><span data-stu-id="2c780-111">[in] An array in which to store the columns in the documents at which the sequence points are located.</span></span>  
  
 `endLines`  
 <span data-ttu-id="2c780-112">окне Массив строк в документах, в которых заканчивается точка следования.</span><span class="sxs-lookup"><span data-stu-id="2c780-112">[in] The array of lines in the documents at which the sequence points end.</span></span>  
  
 `endColumns`  
 <span data-ttu-id="2c780-113">окне Массив столбцов в документах, в которых находятся конечные точки последовательности.</span><span class="sxs-lookup"><span data-stu-id="2c780-113">[in] The array of columns in the documents at which the sequence points end.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2c780-114">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="2c780-114">Return Value</span></span>  
 <span data-ttu-id="2c780-115">S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.</span><span class="sxs-lookup"><span data-stu-id="2c780-115">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2c780-116">Требования</span><span class="sxs-lookup"><span data-stu-id="2c780-116">Requirements</span></span>  
 <span data-ttu-id="2c780-117">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="2c780-117">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c780-118">См. также:</span><span class="sxs-lookup"><span data-stu-id="2c780-118">See also</span></span>

- [<span data-ttu-id="2c780-119">Интерфейс ISymUnmanagedMethod</span><span class="sxs-lookup"><span data-stu-id="2c780-119">ISymUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)

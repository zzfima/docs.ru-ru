---
title: Метод ISymUnmanagedWriter::SetMethodSourceRange
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.SetMethodSourceRange
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::SetMethodSourceRange
helpviewer_keywords:
- SetMethodSourceRange method [.NET Framework debugging]
- ISymUnmanagedWriter::SetMethodSourceRange method [.NET Framework debugging]
ms.assetid: c698b86e-ace7-4b21-9549-f52d6a034959
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 46072718a7dafc0a00294757d5ccce6242a11e23
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57468368"
---
# <a name="isymunmanagedwritersetmethodsourcerange-method"></a><span data-ttu-id="d4668-102">Метод ISymUnmanagedWriter::SetMethodSourceRange</span><span class="sxs-lookup"><span data-stu-id="d4668-102">ISymUnmanagedWriter::SetMethodSourceRange Method</span></span>
<span data-ttu-id="d4668-103">Указывает истинные начало и конец метода в исходном файле.</span><span class="sxs-lookup"><span data-stu-id="d4668-103">Specifies the true start and end of a method within a source file.</span></span> <span data-ttu-id="d4668-104">Используйте этот метод для задания длины метода независимо от точек следования, имеющихся в методе.</span><span class="sxs-lookup"><span data-stu-id="d4668-104">Use this method to specify the extent of a method independently of the sequence points that exist within the method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d4668-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d4668-105">Syntax</span></span>  
  
```  
HRESULT SetMethodSourceRange(  
    [in] ISymUnmanagedDocumentWriter  *startDoc,  
    [in] ULONG32                      startLine,  
    [in] ULONG32                      startColumn,  
    [in] ISymUnmanagedDocumentWriter  *endDoc,  
    [in] ULONG32                      endLine,  
    [in] ULONG32                      endColumn);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d4668-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="d4668-106">Parameters</span></span>  
 `startDoc`  
 <span data-ttu-id="d4668-107">[in] Указатель на документ, содержащий начальную позицию.</span><span class="sxs-lookup"><span data-stu-id="d4668-107">[in] A pointer to the document containing the starting position.</span></span>  
  
 `startLine`  
 <span data-ttu-id="d4668-108">[in] Номер начальной строки.</span><span class="sxs-lookup"><span data-stu-id="d4668-108">[in] The starting line number.</span></span>  
  
 `startColumn`  
 <span data-ttu-id="d4668-109">[in] Начальный столбец.</span><span class="sxs-lookup"><span data-stu-id="d4668-109">[in] The starting column.</span></span>  
  
 `endDoc`  
 <span data-ttu-id="d4668-110">[in] Указатель на документ, содержащий конечное положение.</span><span class="sxs-lookup"><span data-stu-id="d4668-110">[in] A pointer to the document containing the ending position.</span></span>  
  
 `endLine`  
 <span data-ttu-id="d4668-111">[in] Номер конечной строки.</span><span class="sxs-lookup"><span data-stu-id="d4668-111">[in] The ending line number.</span></span>  
  
 `endColumn`  
 <span data-ttu-id="d4668-112">[in] Номер конечного столбца.</span><span class="sxs-lookup"><span data-stu-id="d4668-112">[in] The ending column number.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d4668-113">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="d4668-113">Return Value</span></span>  
 <span data-ttu-id="d4668-114">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="d4668-114">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d4668-115">Требования</span><span class="sxs-lookup"><span data-stu-id="d4668-115">Requirements</span></span>  
 <span data-ttu-id="d4668-116">**Заголовок.** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="d4668-116">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4668-117">См. также</span><span class="sxs-lookup"><span data-stu-id="d4668-117">See also</span></span>
- [<span data-ttu-id="d4668-118">Интерфейс ISymUnmanagedWriter</span><span class="sxs-lookup"><span data-stu-id="d4668-118">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)

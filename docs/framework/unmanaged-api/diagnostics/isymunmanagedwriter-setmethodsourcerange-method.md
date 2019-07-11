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
ms.openlocfilehash: 6e06695f5ba348315523c7414822ce87d594bdbc
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67776602"
---
# <a name="isymunmanagedwritersetmethodsourcerange-method"></a><span data-ttu-id="51fad-102">Метод ISymUnmanagedWriter::SetMethodSourceRange</span><span class="sxs-lookup"><span data-stu-id="51fad-102">ISymUnmanagedWriter::SetMethodSourceRange Method</span></span>
<span data-ttu-id="51fad-103">Указывает истинные начало и конец метода в исходном файле.</span><span class="sxs-lookup"><span data-stu-id="51fad-103">Specifies the true start and end of a method within a source file.</span></span> <span data-ttu-id="51fad-104">Используйте этот метод для задания длины метода независимо от точек следования, имеющихся в методе.</span><span class="sxs-lookup"><span data-stu-id="51fad-104">Use this method to specify the extent of a method independently of the sequence points that exist within the method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="51fad-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="51fad-105">Syntax</span></span>  
  
```cpp  
HRESULT SetMethodSourceRange(  
    [in] ISymUnmanagedDocumentWriter  *startDoc,  
    [in] ULONG32                      startLine,  
    [in] ULONG32                      startColumn,  
    [in] ISymUnmanagedDocumentWriter  *endDoc,  
    [in] ULONG32                      endLine,  
    [in] ULONG32                      endColumn);  
```  
  
## <a name="parameters"></a><span data-ttu-id="51fad-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="51fad-106">Parameters</span></span>  
 `startDoc`  
 <span data-ttu-id="51fad-107">[in] Указатель на документ, содержащий начальную позицию.</span><span class="sxs-lookup"><span data-stu-id="51fad-107">[in] A pointer to the document containing the starting position.</span></span>  
  
 `startLine`  
 <span data-ttu-id="51fad-108">[in] Номер начальной строки.</span><span class="sxs-lookup"><span data-stu-id="51fad-108">[in] The starting line number.</span></span>  
  
 `startColumn`  
 <span data-ttu-id="51fad-109">[in] Начальный столбец.</span><span class="sxs-lookup"><span data-stu-id="51fad-109">[in] The starting column.</span></span>  
  
 `endDoc`  
 <span data-ttu-id="51fad-110">[in] Указатель на документ, содержащий конечное положение.</span><span class="sxs-lookup"><span data-stu-id="51fad-110">[in] A pointer to the document containing the ending position.</span></span>  
  
 `endLine`  
 <span data-ttu-id="51fad-111">[in] Номер конечной строки.</span><span class="sxs-lookup"><span data-stu-id="51fad-111">[in] The ending line number.</span></span>  
  
 `endColumn`  
 <span data-ttu-id="51fad-112">[in] Номер конечного столбца.</span><span class="sxs-lookup"><span data-stu-id="51fad-112">[in] The ending column number.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="51fad-113">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="51fad-113">Return Value</span></span>  
 <span data-ttu-id="51fad-114">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="51fad-114">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="51fad-115">Требования</span><span class="sxs-lookup"><span data-stu-id="51fad-115">Requirements</span></span>  
 <span data-ttu-id="51fad-116">**Заголовок.** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="51fad-116">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51fad-117">См. также</span><span class="sxs-lookup"><span data-stu-id="51fad-117">See also</span></span>

- [<span data-ttu-id="51fad-118">Интерфейс ISymUnmanagedWriter</span><span class="sxs-lookup"><span data-stu-id="51fad-118">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)

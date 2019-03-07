---
title: Метод ISymUnmanagedDocument::GetSourceRange
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocument.GetSourceRange
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument::GetSourceRange
helpviewer_keywords:
- ISymUnmanagedDocument::GetSourceRange method [.NET Framework debugging]
- GetSourceRange method [.NET Framework debugging]
ms.assetid: 20fefee7-1040-41ba-93dc-bd42f68b90c2
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 767508e51660a161a7a6ff0b168a46178d66be99
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57474155"
---
# <a name="isymunmanageddocumentgetsourcerange-method"></a><span data-ttu-id="24b1f-102">Метод ISymUnmanagedDocument::GetSourceRange</span><span class="sxs-lookup"><span data-stu-id="24b1f-102">ISymUnmanagedDocument::GetSourceRange Method</span></span>
<span data-ttu-id="24b1f-103">Возвращает заданный диапазон внедренного источника в заданный буфер.</span><span class="sxs-lookup"><span data-stu-id="24b1f-103">Returns the specified range of the embedded source into the given buffer.</span></span> <span data-ttu-id="24b1f-104">Буфер должен быть достаточно большой для хранения источника.</span><span class="sxs-lookup"><span data-stu-id="24b1f-104">The buffer must be large enough to hold the source.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="24b1f-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="24b1f-105">Syntax</span></span>  
  
```  
HRESULT GetSourceRange(  
    [in]  ULONG32  startLine,  
    [in]  ULONG32  startColumn,  
    [in]  ULONG32  endLine,  
    [in]  ULONG32  endColumn,  
    [in]  ULONG32  cSourceBytes,  
    [out] ULONG32  *pcSourceBytes,  
    [out, size_is(cSourceBytes),  
        length_is(*pcSourceBytes)] BYTE source[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="24b1f-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="24b1f-106">Parameters</span></span>  
 `startLine`  
 <span data-ttu-id="24b1f-107">[in] Начальная строка текущего документа.</span><span class="sxs-lookup"><span data-stu-id="24b1f-107">[in] The starting line in the current document.</span></span>  
  
 `startColumn`  
 <span data-ttu-id="24b1f-108">[in] Начальный столбец текущего документа.</span><span class="sxs-lookup"><span data-stu-id="24b1f-108">[in] The starting column in the current document.</span></span>  
  
 `endLine`  
 <span data-ttu-id="24b1f-109">[in] Последняя строка в текущем документе.</span><span class="sxs-lookup"><span data-stu-id="24b1f-109">[in] The final line in the current document.</span></span>  
  
 `endColumn`  
 <span data-ttu-id="24b1f-110">[in] Последний столбец в текущем документе.</span><span class="sxs-lookup"><span data-stu-id="24b1f-110">[in] The final column in the current document.</span></span>  
  
 `cSourceBytes`  
 <span data-ttu-id="24b1f-111">[in] Размер источника, в байтах.</span><span class="sxs-lookup"><span data-stu-id="24b1f-111">[in] The size of the source, in bytes.</span></span>  
  
 `pcSourceBytes`  
 <span data-ttu-id="24b1f-112">[out] Указатель на переменную, которая получает размер источника.</span><span class="sxs-lookup"><span data-stu-id="24b1f-112">[out] A pointer to a variable that receives the source size.</span></span>  
  
 `source`  
 <span data-ttu-id="24b1f-113">[out] Размер и длина указанного диапазона исходного документа, в байтах.</span><span class="sxs-lookup"><span data-stu-id="24b1f-113">[out] The size and length of the specified range of the source document, in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="24b1f-114">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="24b1f-114">Return Value</span></span>  
 <span data-ttu-id="24b1f-115">Значение S_OK, если метод выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="24b1f-115">S_OK if the method succeeds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24b1f-116">См. также</span><span class="sxs-lookup"><span data-stu-id="24b1f-116">See also</span></span>
- [<span data-ttu-id="24b1f-117">Интерфейс ISymUnmanagedDocument</span><span class="sxs-lookup"><span data-stu-id="24b1f-117">ISymUnmanagedDocument Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)

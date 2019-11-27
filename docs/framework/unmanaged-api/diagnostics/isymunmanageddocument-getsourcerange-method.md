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
ms.openlocfilehash: 64ecbb56ab32ac8381a4864acd5fd40741786d30
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449136"
---
# <a name="isymunmanageddocumentgetsourcerange-method"></a><span data-ttu-id="11b45-102">Метод ISymUnmanagedDocument::GetSourceRange</span><span class="sxs-lookup"><span data-stu-id="11b45-102">ISymUnmanagedDocument::GetSourceRange Method</span></span>
<span data-ttu-id="11b45-103">Возвращает указанный диапазон внедренного источника в заданный буфер.</span><span class="sxs-lookup"><span data-stu-id="11b45-103">Returns the specified range of the embedded source into the given buffer.</span></span> <span data-ttu-id="11b45-104">Буфер должен быть достаточно большим, чтобы вместить исходный код.</span><span class="sxs-lookup"><span data-stu-id="11b45-104">The buffer must be large enough to hold the source.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="11b45-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="11b45-105">Syntax</span></span>  
  
```cpp  
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
  
## <a name="parameters"></a><span data-ttu-id="11b45-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="11b45-106">Parameters</span></span>  
 `startLine`  
 <span data-ttu-id="11b45-107">окне Начальная строка текущего документа.</span><span class="sxs-lookup"><span data-stu-id="11b45-107">[in] The starting line in the current document.</span></span>  
  
 `startColumn`  
 <span data-ttu-id="11b45-108">окне Начальный столбец в текущем документе.</span><span class="sxs-lookup"><span data-stu-id="11b45-108">[in] The starting column in the current document.</span></span>  
  
 `endLine`  
 <span data-ttu-id="11b45-109">окне Последняя строка в текущем документе.</span><span class="sxs-lookup"><span data-stu-id="11b45-109">[in] The final line in the current document.</span></span>  
  
 `endColumn`  
 <span data-ttu-id="11b45-110">окне Последний столбец в текущем документе.</span><span class="sxs-lookup"><span data-stu-id="11b45-110">[in] The final column in the current document.</span></span>  
  
 `cSourceBytes`  
 <span data-ttu-id="11b45-111">окне Размер источника в байтах.</span><span class="sxs-lookup"><span data-stu-id="11b45-111">[in] The size of the source, in bytes.</span></span>  
  
 `pcSourceBytes`  
 <span data-ttu-id="11b45-112">заполняет Указатель на переменную, которая получает исходный размер.</span><span class="sxs-lookup"><span data-stu-id="11b45-112">[out] A pointer to a variable that receives the source size.</span></span>  
  
 `source`  
 <span data-ttu-id="11b45-113">заполняет Размер и длина указанного диапазона исходного документа в байтах.</span><span class="sxs-lookup"><span data-stu-id="11b45-113">[out] The size and length of the specified range of the source document, in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="11b45-114">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="11b45-114">Return Value</span></span>  
 <span data-ttu-id="11b45-115">S_OK, если метод выполнен.</span><span class="sxs-lookup"><span data-stu-id="11b45-115">S_OK if the method succeeds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11b45-116">См. также</span><span class="sxs-lookup"><span data-stu-id="11b45-116">See also</span></span>

- [<span data-ttu-id="11b45-117">Интерфейс ISymUnmanagedDocument</span><span class="sxs-lookup"><span data-stu-id="11b45-117">ISymUnmanagedDocument Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)

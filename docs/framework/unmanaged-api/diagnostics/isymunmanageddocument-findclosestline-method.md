---
title: Метод ISymUnmanagedDocument::FindClosestLine
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocument.FindClosestLine
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument::FindClosestLine
helpviewer_keywords:
- FindClosestLine method [.NET Framework debugging]
- ISymUnmanagedDocument::FindClosestLine method [.NET Framework debugging]
ms.assetid: 628f2a04-e529-407d-841e-3b3da219a9cb
topic_type:
- apiref
ms.openlocfilehash: 0e95255479792c7056bee7ee4f6c507e0f41eb6a
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449216"
---
# <a name="isymunmanageddocumentfindclosestline-method"></a><span data-ttu-id="80dbf-102">Метод ISymUnmanagedDocument::FindClosestLine</span><span class="sxs-lookup"><span data-stu-id="80dbf-102">ISymUnmanagedDocument::FindClosestLine Method</span></span>
<span data-ttu-id="80dbf-103">Возвращает ближайшую строку, которая является точкой последовательности, с учетом строки в этом документе, которая может быть или не являться точкой последовательности.</span><span class="sxs-lookup"><span data-stu-id="80dbf-103">Returns the closest line that is a sequence point, given a line in this document that may or may not be a sequence point.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="80dbf-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="80dbf-104">Syntax</span></span>  
  
```cpp  
HRESULT FindClosestLine(  
    [in]  ULONG32  line,  
    [out, retval] ULONG32*  pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="80dbf-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="80dbf-105">Parameters</span></span>  
 `line`  
 <span data-ttu-id="80dbf-106">окне Строка в этом документе.</span><span class="sxs-lookup"><span data-stu-id="80dbf-106">[in] A line in this document.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="80dbf-107">заполняет Указатель на переменную, которая получает строку.</span><span class="sxs-lookup"><span data-stu-id="80dbf-107">[out] A pointer to a variable that receives the line.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="80dbf-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="80dbf-108">Return Value</span></span>  
 <span data-ttu-id="80dbf-109">S_OK, если метод выполнен. в противном случае — код ошибки.</span><span class="sxs-lookup"><span data-stu-id="80dbf-109">S_OK if the method succeeds; otherwise, an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80dbf-110">См. также:</span><span class="sxs-lookup"><span data-stu-id="80dbf-110">See also</span></span>

- [<span data-ttu-id="80dbf-111">Интерфейс ISymUnmanagedDocument</span><span class="sxs-lookup"><span data-stu-id="80dbf-111">ISymUnmanagedDocument Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)

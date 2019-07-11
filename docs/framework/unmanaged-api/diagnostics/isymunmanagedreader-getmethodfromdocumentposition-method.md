---
title: Метод ISymUnmanagedReader::GetMethodFromDocumentPosition
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetMethodFromDocumentPosition
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetMethodFromDocumentPosition
helpviewer_keywords:
- GetMethodFromDocumentPosition method [.NET Framework debugging]
- ISymUnmanagedReader::GetMethodFromDocumentPosition method [.NET Framework debugging]
ms.assetid: 55773dbc-9053-46e3-8a3c-86caa9d91fb4
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a1935b831902e975616557f512789c339baf49c5
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67776973"
---
# <a name="isymunmanagedreadergetmethodfromdocumentposition-method"></a><span data-ttu-id="59759-102">Метод ISymUnmanagedReader::GetMethodFromDocumentPosition</span><span class="sxs-lookup"><span data-stu-id="59759-102">ISymUnmanagedReader::GetMethodFromDocumentPosition Method</span></span>
<span data-ttu-id="59759-103">Возвращает метод, который содержит точку останова в заданной позиции в документе.</span><span class="sxs-lookup"><span data-stu-id="59759-103">Returns the method that contains the breakpoint at the given position in a document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="59759-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="59759-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMethodFromDocumentPosition (  
    [in]  ISymUnmanagedDocument*  document,  
    [in]  ULONG32  line,  
    [in]  ULONG32  column,  
    [out, retval] ISymUnmanagedMethod**  pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="59759-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="59759-105">Parameters</span></span>  
 `document`  
 <span data-ttu-id="59759-106">[in] Указанный документ.</span><span class="sxs-lookup"><span data-stu-id="59759-106">[in] The specified document.</span></span>  
  
 `line`  
 <span data-ttu-id="59759-107">[in] Строка указанного документа.</span><span class="sxs-lookup"><span data-stu-id="59759-107">[in] The line of the specified document.</span></span>  
  
 `column`  
 <span data-ttu-id="59759-108">[in] Столбец указанного документа.</span><span class="sxs-lookup"><span data-stu-id="59759-108">[in] The column of the specified document.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="59759-109">[out] Указатель на адрес [интерфейс ISymUnmanagedMethod](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md) , представляющий метод, содержащий точку останова.</span><span class="sxs-lookup"><span data-stu-id="59759-109">[out] A pointer to the address of a [ISymUnmanagedMethod Interface](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md) object that represents the method containing the breakpoint.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="59759-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="59759-110">Return Value</span></span>  
 <span data-ttu-id="59759-111">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="59759-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="59759-112">Требования</span><span class="sxs-lookup"><span data-stu-id="59759-112">Requirements</span></span>  
 <span data-ttu-id="59759-113">**Заголовок.** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="59759-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59759-114">См. также</span><span class="sxs-lookup"><span data-stu-id="59759-114">See also</span></span>

- [<span data-ttu-id="59759-115">Интерфейс ISymUnmanagedReader</span><span class="sxs-lookup"><span data-stu-id="59759-115">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)

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
ms.openlocfilehash: ebb1a13848b1c1336287413cdd7246da748ec864
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54503963"
---
# <a name="isymunmanagedreadergetmethodfromdocumentposition-method"></a><span data-ttu-id="157e8-102">Метод ISymUnmanagedReader::GetMethodFromDocumentPosition</span><span class="sxs-lookup"><span data-stu-id="157e8-102">ISymUnmanagedReader::GetMethodFromDocumentPosition Method</span></span>
<span data-ttu-id="157e8-103">Возвращает метод, который содержит точку останова в заданной позиции в документе.</span><span class="sxs-lookup"><span data-stu-id="157e8-103">Returns the method that contains the breakpoint at the given position in a document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="157e8-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="157e8-104">Syntax</span></span>  
  
```  
HRESULT GetMethodFromDocumentPosition (  
    [in]  ISymUnmanagedDocument*  document,  
    [in]  ULONG32  line,  
    [in]  ULONG32  column,  
    [out, retval] ISymUnmanagedMethod**  pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="157e8-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="157e8-105">Parameters</span></span>  
 `document`  
 <span data-ttu-id="157e8-106">[in] Указанный документ.</span><span class="sxs-lookup"><span data-stu-id="157e8-106">[in] The specified document.</span></span>  
  
 `line`  
 <span data-ttu-id="157e8-107">[in] Строка указанного документа.</span><span class="sxs-lookup"><span data-stu-id="157e8-107">[in] The line of the specified document.</span></span>  
  
 `column`  
 <span data-ttu-id="157e8-108">[in] Столбец указанного документа.</span><span class="sxs-lookup"><span data-stu-id="157e8-108">[in] The column of the specified document.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="157e8-109">[out] Указатель на адрес [интерфейс ISymUnmanagedMethod](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md) , представляющий метод, содержащий точку останова.</span><span class="sxs-lookup"><span data-stu-id="157e8-109">[out] A pointer to the address of a [ISymUnmanagedMethod Interface](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md) object that represents the method containing the breakpoint.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="157e8-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="157e8-110">Return Value</span></span>  
 <span data-ttu-id="157e8-111">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="157e8-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="157e8-112">Требования</span><span class="sxs-lookup"><span data-stu-id="157e8-112">Requirements</span></span>  
 <span data-ttu-id="157e8-113">**Заголовок.** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="157e8-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="157e8-114">См. также</span><span class="sxs-lookup"><span data-stu-id="157e8-114">See also</span></span>
- [<span data-ttu-id="157e8-115">Интерфейс ISymUnmanagedReader</span><span class="sxs-lookup"><span data-stu-id="157e8-115">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)

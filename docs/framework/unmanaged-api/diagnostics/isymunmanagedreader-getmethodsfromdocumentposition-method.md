---
title: Метод ISymUnmanagedReader::GetMethodsFromDocumentPosition
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetMethodsFromDocumentPosition
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetMethodsFromDocumentPosition
helpviewer_keywords:
- GetMethodsFromDocumentPosition method [.NET Framework debugging]
- ISymUnmanagedReader::GetMethodsFromDocumentPosition method [.NET Framework debugging]
ms.assetid: 83605f1e-e4f3-49e6-859b-f13cad68bb54
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f55c8986d2efc78b6fcd2840bad588af84228017
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54561782"
---
# <a name="isymunmanagedreadergetmethodsfromdocumentposition-method"></a><span data-ttu-id="7b0b0-102">Метод ISymUnmanagedReader::GetMethodsFromDocumentPosition</span><span class="sxs-lookup"><span data-stu-id="7b0b0-102">ISymUnmanagedReader::GetMethodsFromDocumentPosition Method</span></span>
<span data-ttu-id="7b0b0-103">Возвращает массив методов, каждый из которых содержит точку останова в заданной позиции в документе.</span><span class="sxs-lookup"><span data-stu-id="7b0b0-103">Returns an array of methods, each of which contains the breakpoint at the given position in a document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7b0b0-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7b0b0-104">Syntax</span></span>  
  
```  
HRESULT GetMethodsFromDocumentPosition (  
    [in]  ISymUnmanagedDocument* document,  
    [in]  ULONG32 line,  
    [in]  ULONG32 column,  
    [in]  ULONG32 cMethod,  
    [out] ULONG32* pcMethod,  
    [out, size_is (cMethod),  
        length_is (*pcMethod)] ISymUnmanagedMethod* pRetVal[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7b0b0-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="7b0b0-105">Parameters</span></span>  
 `document`  
 <span data-ttu-id="7b0b0-106">[in] Указанный документ.</span><span class="sxs-lookup"><span data-stu-id="7b0b0-106">[in] The specified document.</span></span>  
  
 `line`  
 <span data-ttu-id="7b0b0-107">[in] Строка указанного документа.</span><span class="sxs-lookup"><span data-stu-id="7b0b0-107">[in] The line of the specified document.</span></span>  
  
 `column`  
 <span data-ttu-id="7b0b0-108">[in] Столбец указанного документа.</span><span class="sxs-lookup"><span data-stu-id="7b0b0-108">[in] The column of the specified document.</span></span>  
  
 `cMethod`  
 <span data-ttu-id="7b0b0-109">[in] Размер массива `pRetVal`.</span><span class="sxs-lookup"><span data-stu-id="7b0b0-109">[in] The size of the `pRetVal` array.</span></span>  
  
 `pcMethod`  
 <span data-ttu-id="7b0b0-110">[out] Указатель на переменную, которая получает число элементов, возвращаемых в `pRetVal` массива.</span><span class="sxs-lookup"><span data-stu-id="7b0b0-110">[out] A pointer to a variable that receives the number of elements returned in the `pRetVal` array.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="7b0b0-111">[out] Массив указателей, каждый из которых указывает [ISymUnmanagedMethod](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md) , представляющий метод, содержащий точку останова.</span><span class="sxs-lookup"><span data-stu-id="7b0b0-111">[out] An array of pointers, each of which points to an [ISymUnmanagedMethod](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md) object that represents a method containing the breakpoint.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7b0b0-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="7b0b0-112">Return Value</span></span>  
 <span data-ttu-id="7b0b0-113">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="7b0b0-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7b0b0-114">Требования</span><span class="sxs-lookup"><span data-stu-id="7b0b0-114">Requirements</span></span>  
 <span data-ttu-id="7b0b0-115">**Заголовок.** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="7b0b0-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b0b0-116">См. также</span><span class="sxs-lookup"><span data-stu-id="7b0b0-116">See also</span></span>
- [<span data-ttu-id="7b0b0-117">Интерфейс ISymUnmanagedReader</span><span class="sxs-lookup"><span data-stu-id="7b0b0-117">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)

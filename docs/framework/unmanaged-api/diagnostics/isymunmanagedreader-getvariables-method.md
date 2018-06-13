---
title: Метод ISymUnmanagedReader::GetVariables
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetVariables
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetVariables
helpviewer_keywords:
- ISymUnmanagedReader::GetVariables method [.NET Framework debugging]
- GetVariables method, ISymUnmanagedReader interface [.NET Framework debugging]
ms.assetid: 16dc49cb-2c60-4ac8-9c35-020e9afba3f8
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 74df7ee71fc541c35bc393f637ad1d7b9f7aa2a0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33425530"
---
# <a name="isymunmanagedreadergetvariables-method"></a><span data-ttu-id="38ff5-102">Метод ISymUnmanagedReader::GetVariables</span><span class="sxs-lookup"><span data-stu-id="38ff5-102">ISymUnmanagedReader::GetVariables Method</span></span>
<span data-ttu-id="38ff5-103">Возвращает внешней переменной, ее родительскому объекту и имя.</span><span class="sxs-lookup"><span data-stu-id="38ff5-103">Returns a non-local variable, given its parent and name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="38ff5-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="38ff5-104">Syntax</span></span>  
  
```  
HRESULT GetVariables (  
    [in]  mdToken  parent,  
    [in]  ULONG32  cVars,  
    [out] ULONG32  *pcVars,  
    [out, size_is (cVars),  
        length_is (*pcVars)] ISymUnmanagedVariable *pVars[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="38ff5-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="38ff5-105">Parameters</span></span>  
 `parent`  
 <span data-ttu-id="38ff5-106">[in] Родительская переменная.</span><span class="sxs-lookup"><span data-stu-id="38ff5-106">[in] The parent of the variable.</span></span>  
  
 `cVars`  
 <span data-ttu-id="38ff5-107">[in] Размер массива `pVars`.</span><span class="sxs-lookup"><span data-stu-id="38ff5-107">[in] The size of the `pVars` array.</span></span>  
  
 `pcVars`  
 <span data-ttu-id="38ff5-108">[out] Указатель на переменную, которая получает количество переменных, возвращаемых в `pVars`.</span><span class="sxs-lookup"><span data-stu-id="38ff5-108">[out] A pointer to the variable that receives the number of variables returned in `pVars`.</span></span>  
  
 `pVars`  
 <span data-ttu-id="38ff5-109">[out] Указатель на переменную, которая получает переменные.</span><span class="sxs-lookup"><span data-stu-id="38ff5-109">[out] A pointer to the variable that receives the variables.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="38ff5-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="38ff5-110">Return Value</span></span>  
 <span data-ttu-id="38ff5-111">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="38ff5-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="38ff5-112">Требования</span><span class="sxs-lookup"><span data-stu-id="38ff5-112">Requirements</span></span>  
 <span data-ttu-id="38ff5-113">**Заголовок:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="38ff5-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38ff5-114">См. также</span><span class="sxs-lookup"><span data-stu-id="38ff5-114">See Also</span></span>  
 [<span data-ttu-id="38ff5-115">Интерфейс ISymUnmanagedReader</span><span class="sxs-lookup"><span data-stu-id="38ff5-115">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)

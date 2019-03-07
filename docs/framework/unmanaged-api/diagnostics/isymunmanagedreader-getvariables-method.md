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
ms.openlocfilehash: cca073cfccedacb037478903a603c375c876349c
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57475363"
---
# <a name="isymunmanagedreadergetvariables-method"></a><span data-ttu-id="4af28-102">Метод ISymUnmanagedReader::GetVariables</span><span class="sxs-lookup"><span data-stu-id="4af28-102">ISymUnmanagedReader::GetVariables Method</span></span>
<span data-ttu-id="4af28-103">Возвращает не являющейся локальной переменной, ее родительскому объекту и имя.</span><span class="sxs-lookup"><span data-stu-id="4af28-103">Returns a non-local variable, given its parent and name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4af28-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4af28-104">Syntax</span></span>  
  
```  
HRESULT GetVariables (  
    [in]  mdToken  parent,  
    [in]  ULONG32  cVars,  
    [out] ULONG32  *pcVars,  
    [out, size_is (cVars),  
        length_is (*pcVars)] ISymUnmanagedVariable *pVars[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4af28-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="4af28-105">Parameters</span></span>  
 `parent`  
 <span data-ttu-id="4af28-106">[in] Родительская переменная.</span><span class="sxs-lookup"><span data-stu-id="4af28-106">[in] The parent of the variable.</span></span>  
  
 `cVars`  
 <span data-ttu-id="4af28-107">[in] Размер массива `pVars`.</span><span class="sxs-lookup"><span data-stu-id="4af28-107">[in] The size of the `pVars` array.</span></span>  
  
 `pcVars`  
 <span data-ttu-id="4af28-108">[out] Указатель на переменную, которая получает количество переменных, возвращаемых в `pVars`.</span><span class="sxs-lookup"><span data-stu-id="4af28-108">[out] A pointer to the variable that receives the number of variables returned in `pVars`.</span></span>  
  
 `pVars`  
 <span data-ttu-id="4af28-109">[out] Указатель на переменную, которая получает переменные.</span><span class="sxs-lookup"><span data-stu-id="4af28-109">[out] A pointer to the variable that receives the variables.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4af28-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="4af28-110">Return Value</span></span>  
 <span data-ttu-id="4af28-111">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="4af28-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4af28-112">Требования</span><span class="sxs-lookup"><span data-stu-id="4af28-112">Requirements</span></span>  
 <span data-ttu-id="4af28-113">**Заголовок.** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="4af28-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4af28-114">См. также</span><span class="sxs-lookup"><span data-stu-id="4af28-114">See also</span></span>
- [<span data-ttu-id="4af28-115">Интерфейс ISymUnmanagedReader</span><span class="sxs-lookup"><span data-stu-id="4af28-115">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)

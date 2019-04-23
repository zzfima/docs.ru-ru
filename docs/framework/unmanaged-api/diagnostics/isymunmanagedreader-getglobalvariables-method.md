---
title: Метод ISymUnmanagedReader::GetGlobalVariables
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetGlobalVariables
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetGlobalVariables
helpviewer_keywords:
- GetGlobalVariables method [.NET Framework debugging]
- ISymUnmanagedReader::GetGlobalVariables method [.NET Framework debugging]
ms.assetid: a2dd5098-3e58-4be5-b7a2-e4160b3b505a
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e778a5a7baed52941a7f4b990b34d31f8ca84c24
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59092647"
---
# <a name="isymunmanagedreadergetglobalvariables-method"></a><span data-ttu-id="78b55-102">Метод ISymUnmanagedReader::GetGlobalVariables</span><span class="sxs-lookup"><span data-stu-id="78b55-102">ISymUnmanagedReader::GetGlobalVariables Method</span></span>
<span data-ttu-id="78b55-103">Возвращает все глобальные переменные.</span><span class="sxs-lookup"><span data-stu-id="78b55-103">Returns all global variables.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="78b55-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="78b55-104">Syntax</span></span>  
  
```  
HRESULT GetGlobalVariables(  
    [in]  ULONG32  cVars,  
    [out] ULONG32  *pcVars,  
    [out, size_is(cVars),  
        length_is(*pcVars)] ISymUnmanagedVariable *pVars[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="78b55-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="78b55-105">Parameters</span></span>  
 `cVars`  
 <span data-ttu-id="78b55-106">[in] Размер буфера, на который указывает `pcVars`.</span><span class="sxs-lookup"><span data-stu-id="78b55-106">[in] The length of the buffer pointed to by `pcVars`.</span></span>  
  
 `pcVars`  
 <span data-ttu-id="78b55-107">[out] Указатель на `ULONG32` , принимает размер буфера, требуемого для содержат переменные.</span><span class="sxs-lookup"><span data-stu-id="78b55-107">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the variables.</span></span>  
  
 `pVars`  
 <span data-ttu-id="78b55-108">[out] Буфер, содержащий переменные.</span><span class="sxs-lookup"><span data-stu-id="78b55-108">[out] A buffer that contains the variables.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="78b55-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="78b55-109">Return Value</span></span>  
 <span data-ttu-id="78b55-110">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="78b55-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="78b55-111">Требования</span><span class="sxs-lookup"><span data-stu-id="78b55-111">Requirements</span></span>  
 <span data-ttu-id="78b55-112">**Заголовок.** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="78b55-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78b55-113">См. также</span><span class="sxs-lookup"><span data-stu-id="78b55-113">See also</span></span>

- [<span data-ttu-id="78b55-114">Интерфейс ISymUnmanagedReader</span><span class="sxs-lookup"><span data-stu-id="78b55-114">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)

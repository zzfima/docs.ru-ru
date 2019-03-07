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
ms.openlocfilehash: 00078d1d405eb2abc0d34f7b455fa045ac17c261
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57485839"
---
# <a name="isymunmanagedreadergetglobalvariables-method"></a><span data-ttu-id="eabe7-102">Метод ISymUnmanagedReader::GetGlobalVariables</span><span class="sxs-lookup"><span data-stu-id="eabe7-102">ISymUnmanagedReader::GetGlobalVariables Method</span></span>
<span data-ttu-id="eabe7-103">Возвращает все глобальные переменные.</span><span class="sxs-lookup"><span data-stu-id="eabe7-103">Returns all global variables.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eabe7-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="eabe7-104">Syntax</span></span>  
  
```  
HRESULT GetGlobalVariables(  
    [in]  ULONG32  cVars,  
    [out] ULONG32  *pcVars,  
    [out, size_is(cVars),  
        length_is(*pcVars)] ISymUnmanagedVariable *pVars[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="eabe7-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="eabe7-105">Parameters</span></span>  
 `cVars`  
 <span data-ttu-id="eabe7-106">[in] Размер буфера, на который указывает `pcVars`.</span><span class="sxs-lookup"><span data-stu-id="eabe7-106">[in] The length of the buffer pointed to by `pcVars`.</span></span>  
  
 `pcVars`  
 <span data-ttu-id="eabe7-107">[out] Указатель на `ULONG32` , принимает размер буфера, требуемого для содержат переменные.</span><span class="sxs-lookup"><span data-stu-id="eabe7-107">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the variables.</span></span>  
  
 `pVars`  
 <span data-ttu-id="eabe7-108">[out] Буфер, содержащий переменные.</span><span class="sxs-lookup"><span data-stu-id="eabe7-108">[out] A buffer that contains the variables.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="eabe7-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="eabe7-109">Return Value</span></span>  
 <span data-ttu-id="eabe7-110">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="eabe7-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eabe7-111">Требования</span><span class="sxs-lookup"><span data-stu-id="eabe7-111">Requirements</span></span>  
 <span data-ttu-id="eabe7-112">**Заголовок.** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="eabe7-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eabe7-113">См. также</span><span class="sxs-lookup"><span data-stu-id="eabe7-113">See also</span></span>
- [<span data-ttu-id="eabe7-114">Интерфейс ISymUnmanagedReader</span><span class="sxs-lookup"><span data-stu-id="eabe7-114">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)

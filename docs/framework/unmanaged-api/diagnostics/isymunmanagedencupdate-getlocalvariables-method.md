---
title: Метод ISymUnmanagedENCUpdate::GetLocalVariables
ms.date: 03/30/2017
api_name:
- ISymUnmanagedENCUpdate.GetLocalVariables
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedENCUpdate::GetLocalVariables
helpviewer_keywords:
- ISymUnmanagedENCUpdate::GetLocalVariables method [.NET Framework debugging]
- GetLocalVariables method [.NET Framework debugging]
ms.assetid: 5c8840be-ffea-447f-9c8d-178f1eaf8d06
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a53493d666cb16fcc9b407ca3a46072afa306b97
ms.sourcegitcommit: 35316b768394e56087483cde93f854ba607b63bc
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2018
ms.locfileid: "52297560"
---
# <a name="isymunmanagedencupdategetlocalvariables-method"></a><span data-ttu-id="10011-102">Метод ISymUnmanagedENCUpdate::GetLocalVariables</span><span class="sxs-lookup"><span data-stu-id="10011-102">ISymUnmanagedENCUpdate::GetLocalVariables Method</span></span>
<span data-ttu-id="10011-103">Возвращает локальные переменные.</span><span class="sxs-lookup"><span data-stu-id="10011-103">Gets the local variables.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="10011-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="10011-104">Syntax</span></span>  
  
```  
HRESULT GetLocalVariables(  
    [in]  mdMethodDef  mdMethodToken,  
    [in]  ULONG        cLocals,  
    [out, size_is(cLocals), length_is(*pceltFetched)]  
        ISymUnmanagedVariable *rgLocals[],  
    [out] ULONG        *pceltFetched);  
```  
  
## <a name="parameters"></a><span data-ttu-id="10011-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="10011-105">Parameters</span></span>  
 `mdMethodToken`  
 <span data-ttu-id="10011-106">[in] Токен метаданных метода.</span><span class="sxs-lookup"><span data-stu-id="10011-106">[in] The metadata token of the method.</span></span>  
  
 `cLocals`  
 <span data-ttu-id="10011-107">[in] Объект `ULONG` указывает размер `rgLocals` параметра.</span><span class="sxs-lookup"><span data-stu-id="10011-107">[in] A `ULONG` that indicates the size of the `rgLocals` parameter.</span></span>  
  
 `rgLocals`  
 <span data-ttu-id="10011-108">[out] Возвращаемый массив [ISymUnmanagedVariable](isymunmanagedvariable-interface.md) экземпляров.</span><span class="sxs-lookup"><span data-stu-id="10011-108">[out] The returned array of [ISymUnmanagedVariable](isymunmanagedvariable-interface.md) instances.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="10011-109">[out] Указатель на `ULONG` , получающий размер `rgLocals` буфера, необходимый для "Локальные".</span><span class="sxs-lookup"><span data-stu-id="10011-109">[out] A pointer to a `ULONG` that receives the size of the `rgLocals` buffer required to contain the locals.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="10011-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="10011-110">Return Value</span></span>  
 <span data-ttu-id="10011-111">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="10011-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="10011-112">Требования</span><span class="sxs-lookup"><span data-stu-id="10011-112">Requirements</span></span>  
 <span data-ttu-id="10011-113">**Заголовок:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="10011-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10011-114">См. также</span><span class="sxs-lookup"><span data-stu-id="10011-114">See Also</span></span>  
 [<span data-ttu-id="10011-115">Интерфейс ISymUnmanagedENCUpdate</span><span class="sxs-lookup"><span data-stu-id="10011-115">ISymUnmanagedENCUpdate Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-interface.md)

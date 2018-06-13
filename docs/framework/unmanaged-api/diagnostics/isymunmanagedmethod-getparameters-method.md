---
title: Метод ISymUnmanagedMethod::GetParameters
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod.GetParameters
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod::GetParameters
helpviewer_keywords:
- ISymUnmanagedMethod::GetParameters method [.NET Framework debugging]
- GetParameters method [.NET Framework debugging]
ms.assetid: 3a8074f1-facc-4a3f-bb9b-d6574fc2fc74
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2fbedb7b1c10dcc2b9b9940db10aae7e4101436b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33426215"
---
# <a name="isymunmanagedmethodgetparameters-method"></a><span data-ttu-id="19f7e-102">Метод ISymUnmanagedMethod::GetParameters</span><span class="sxs-lookup"><span data-stu-id="19f7e-102">ISymUnmanagedMethod::GetParameters Method</span></span>
<span data-ttu-id="19f7e-103">Получает параметры для этого метода.</span><span class="sxs-lookup"><span data-stu-id="19f7e-103">Gets the parameters for this method.</span></span> <span data-ttu-id="19f7e-104">Параметры возвращаются в том порядке, в котором они определены в подписи метода.</span><span class="sxs-lookup"><span data-stu-id="19f7e-104">The parameters are returned in the order in which they are defined within the method's signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="19f7e-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="19f7e-105">Syntax</span></span>  
  
```  
HRESULT GetParameters(  
    [in]  ULONG32  cParams,  
    [out] ULONG32  *pcParams,  
    [out, size_is(cParams),  
        length_is(*pcParams)] ISymUnmanagedVariable*  params[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="19f7e-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="19f7e-106">Parameters</span></span>  
 `cParams`  
 <span data-ttu-id="19f7e-107">[in] Размер массива `params`.</span><span class="sxs-lookup"><span data-stu-id="19f7e-107">[in] The size of the `params` array.</span></span>  
  
 `pcParams`  
 <span data-ttu-id="19f7e-108">[in] Указатель на `ULONG32` , получающий размер буфера, который должен содержать параметры.</span><span class="sxs-lookup"><span data-stu-id="19f7e-108">[in] A pointer to a `ULONG32` that receives the size of the buffer that is required to contain the parameters.</span></span>  
  
 `params`  
 <span data-ttu-id="19f7e-109">[out] Указатель буфера, принимающего параметры.</span><span class="sxs-lookup"><span data-stu-id="19f7e-109">[out] A pointer to the buffer that receives the parameters.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="19f7e-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="19f7e-110">Return Value</span></span>  
 <span data-ttu-id="19f7e-111">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="19f7e-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="19f7e-112">Требования</span><span class="sxs-lookup"><span data-stu-id="19f7e-112">Requirements</span></span>  
 <span data-ttu-id="19f7e-113">**Заголовок:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="19f7e-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19f7e-114">См. также</span><span class="sxs-lookup"><span data-stu-id="19f7e-114">See Also</span></span>  
 [<span data-ttu-id="19f7e-115">Интерфейс ISymUnmanagedMethod</span><span class="sxs-lookup"><span data-stu-id="19f7e-115">ISymUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)

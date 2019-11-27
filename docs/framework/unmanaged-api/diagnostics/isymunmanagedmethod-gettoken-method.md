---
title: Метод ISymUnmanagedMethod::GetToken
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod.GetToken
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod::GetToken
helpviewer_keywords:
- ISymUnmanagedMethod::GetToken method [.NET Framework debugging]
- GetToken method, ISymUnmanagedMethod interface [.NET Framework debugging]
ms.assetid: 4effbe95-c36e-4a45-8b2a-ee21339415fb
topic_type:
- apiref
ms.openlocfilehash: 048d784a55fd7c29c837a54fbd5adcdcf62a7a2c
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448858"
---
# <a name="isymunmanagedmethodgettoken-method"></a><span data-ttu-id="8a5f4-102">Метод ISymUnmanagedMethod::GetToken</span><span class="sxs-lookup"><span data-stu-id="8a5f4-102">ISymUnmanagedMethod::GetToken Method</span></span>
<span data-ttu-id="8a5f4-103">Возвращает маркер метаданных для этого метода.</span><span class="sxs-lookup"><span data-stu-id="8a5f4-103">Returns the metadata token for this method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8a5f4-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8a5f4-104">Syntax</span></span>  
  
```cpp  
HRESULT GetToken(  
   [out, retval]  mdMethodDef  *pToken);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8a5f4-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="8a5f4-105">Parameters</span></span>  
 `pToken`  
 <span data-ttu-id="8a5f4-106">заполняет Указатель на `mdMethodDef`, который получает размер буфера (в символах), необходимого для хранения метаданных.</span><span class="sxs-lookup"><span data-stu-id="8a5f4-106">[out] A pointer to a `mdMethodDef` that receives the size, in characters, of the buffer required to contain the metadata.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8a5f4-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="8a5f4-107">Return Value</span></span>  
 <span data-ttu-id="8a5f4-108">S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.</span><span class="sxs-lookup"><span data-stu-id="8a5f4-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8a5f4-109">Требования</span><span class="sxs-lookup"><span data-stu-id="8a5f4-109">Requirements</span></span>  
 <span data-ttu-id="8a5f4-110">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="8a5f4-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a5f4-111">См. также</span><span class="sxs-lookup"><span data-stu-id="8a5f4-111">See also</span></span>

- [<span data-ttu-id="8a5f4-112">Интерфейс ISymUnmanagedMethod</span><span class="sxs-lookup"><span data-stu-id="8a5f4-112">ISymUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)

---
title: Метод ISymUnmanagedMethod::GetNamespace
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod.GetNamespace
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod::GetNamespace
helpviewer_keywords:
- ISymUnmanagedMethod::GetNamespace method [.NET Framework debugging]
- GetNamespace method [.NET Framework debugging]
ms.assetid: 7fbbac42-b966-406d-9ae9-67bf3aea74ce
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 53a47cf67edb36b06c92be83cb23c2e1dd1e75cf
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33424434"
---
# <a name="isymunmanagedmethodgetnamespace-method"></a><span data-ttu-id="55c19-102">Метод ISymUnmanagedMethod::GetNamespace</span><span class="sxs-lookup"><span data-stu-id="55c19-102">ISymUnmanagedMethod::GetNamespace Method</span></span>
<span data-ttu-id="55c19-103">Возвращает пространство имен, в котором определен этот метод.</span><span class="sxs-lookup"><span data-stu-id="55c19-103">Gets the namespace within which this method is defined.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="55c19-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="55c19-104">Syntax</span></span>  
  
```  
HRESULT GetNamespace(  
   [out] ISymUnmanagedNamespace  **pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="55c19-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="55c19-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="55c19-106">[out] Указатель, который задается в возвращаемую [ISymUnmanagedNamespace](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagednamespace-interface.md) интерфейса.</span><span class="sxs-lookup"><span data-stu-id="55c19-106">[out] A pointer that is set to the returned [ISymUnmanagedNamespace](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagednamespace-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="55c19-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="55c19-107">Return Value</span></span>  
 <span data-ttu-id="55c19-108">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="55c19-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="55c19-109">Требования</span><span class="sxs-lookup"><span data-stu-id="55c19-109">Requirements</span></span>  
 <span data-ttu-id="55c19-110">**Заголовок:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="55c19-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55c19-111">См. также</span><span class="sxs-lookup"><span data-stu-id="55c19-111">See Also</span></span>  
 [<span data-ttu-id="55c19-112">Интерфейс ISymUnmanagedMethod</span><span class="sxs-lookup"><span data-stu-id="55c19-112">ISymUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)

---
title: Метод ISymUnmanagedMethod::GetRootScope
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod.GetRootScope
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod::GetRootScope
helpviewer_keywords:
- ISymUnmanagedMethod::GetRootScope method [.NET Framework debugging]
- GetRootScope method [.NET Framework debugging]
ms.assetid: 7d58caac-2e75-4dfa-9249-32d8a624b247
topic_type:
- apiref
ms.openlocfilehash: c956f5d68c992f1b08988e59038e8667b391f734
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448912"
---
# <a name="isymunmanagedmethodgetrootscope-method"></a><span data-ttu-id="d9597-102">Метод ISymUnmanagedMethod::GetRootScope</span><span class="sxs-lookup"><span data-stu-id="d9597-102">ISymUnmanagedMethod::GetRootScope Method</span></span>
<span data-ttu-id="d9597-103">Возвращает корневую лексическую область внутри этого метода.</span><span class="sxs-lookup"><span data-stu-id="d9597-103">Gets the root lexical scope within this method.</span></span> <span data-ttu-id="d9597-104">Эта область включает весь метод.</span><span class="sxs-lookup"><span data-stu-id="d9597-104">This scope encloses the entire method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d9597-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d9597-105">Syntax</span></span>  
  
```cpp  
HRESULT GetRootScope(  
    [out, retval] ISymUnmanagedScope** pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d9597-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="d9597-106">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="d9597-107">заполняет Указатель, которому присваивается возвращаемый интерфейс [исимунманажедскопе](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="d9597-107">[out] A pointer that is set to the returned [ISymUnmanagedScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d9597-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="d9597-108">Return Value</span></span>  
 <span data-ttu-id="d9597-109">S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.</span><span class="sxs-lookup"><span data-stu-id="d9597-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d9597-110">Требования</span><span class="sxs-lookup"><span data-stu-id="d9597-110">Requirements</span></span>  
 <span data-ttu-id="d9597-111">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="d9597-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9597-112">См. также:</span><span class="sxs-lookup"><span data-stu-id="d9597-112">See also</span></span>

- [<span data-ttu-id="d9597-113">Интерфейс ISymUnmanagedMethod</span><span class="sxs-lookup"><span data-stu-id="d9597-113">ISymUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)

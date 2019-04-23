---
title: Метод ISymUnmanagedScope::GetStartOffset
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope.GetStartOffset
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope::GetStartOffset
helpviewer_keywords:
- GetStartOffset method, ISymUnmanagedScope interface [.NET Framework debugging]
- ISymUnmanagedScope::GetStartOffset method [.NET Framework debugging]
ms.assetid: da6bbc75-94d1-4354-9722-0d455b4428fb
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: faab55199a3b921ea8b995e2a0f9823fb4da9cc7
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59230594"
---
# <a name="isymunmanagedscopegetstartoffset-method"></a><span data-ttu-id="2cefa-102">Метод ISymUnmanagedScope::GetStartOffset</span><span class="sxs-lookup"><span data-stu-id="2cefa-102">ISymUnmanagedScope::GetStartOffset Method</span></span>
<span data-ttu-id="2cefa-103">Возвращает начальное смещение для этой области.</span><span class="sxs-lookup"><span data-stu-id="2cefa-103">Gets the start offset for this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2cefa-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2cefa-104">Syntax</span></span>  
  
```  
HRESULT GetStartOffset(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2cefa-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="2cefa-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="2cefa-106">[out] Указатель на `ULONG32` , содержащий начальное смещение.</span><span class="sxs-lookup"><span data-stu-id="2cefa-106">[out] A pointer to a `ULONG32` that contains the starting offset.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2cefa-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="2cefa-107">Return Value</span></span>  
 <span data-ttu-id="2cefa-108">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="2cefa-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2cefa-109">Требования</span><span class="sxs-lookup"><span data-stu-id="2cefa-109">Requirements</span></span>  
 <span data-ttu-id="2cefa-110">**Заголовок.** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="2cefa-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2cefa-111">См. также</span><span class="sxs-lookup"><span data-stu-id="2cefa-111">See also</span></span>

- [<span data-ttu-id="2cefa-112">Интерфейс ISymUnmanagedScope</span><span class="sxs-lookup"><span data-stu-id="2cefa-112">ISymUnmanagedScope Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)
- [<span data-ttu-id="2cefa-113">Метод GetEndOffset</span><span class="sxs-lookup"><span data-stu-id="2cefa-113">GetEndOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getendoffset-method.md)

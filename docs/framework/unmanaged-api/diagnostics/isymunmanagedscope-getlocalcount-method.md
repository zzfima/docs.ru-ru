---
title: Метод ISymUnmanagedScope::GetLocalCount
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope.GetLocalCount
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope::GetLocalCount
helpviewer_keywords:
- GetLocalCount method [.NET Framework debugging]
- ISymUnmanagedScope::GetLocalCount method [.NET Framework debugging]
ms.assetid: 3ede8fb5-f655-4088-8e19-9c53812588a8
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 809b9033c784954374065a901f34f7542f41e7ab
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54549946"
---
# <a name="isymunmanagedscopegetlocalcount-method"></a><span data-ttu-id="9cc9f-102">Метод ISymUnmanagedScope::GetLocalCount</span><span class="sxs-lookup"><span data-stu-id="9cc9f-102">ISymUnmanagedScope::GetLocalCount Method</span></span>
<span data-ttu-id="9cc9f-103">Возвращает число локальных переменных, определенных в данной области.</span><span class="sxs-lookup"><span data-stu-id="9cc9f-103">Gets a count of the local variables defined within this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9cc9f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9cc9f-104">Syntax</span></span>  
  
```  
HRESULT GetLocalCount(  
    [out, retval] ULONG32 *pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9cc9f-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="9cc9f-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="9cc9f-106">[out] Указатель на `ULONG32` , Получает число локальных переменных.</span><span class="sxs-lookup"><span data-stu-id="9cc9f-106">[out] A pointer to a `ULONG32` that receives the count of local variables.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9cc9f-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="9cc9f-107">Return Value</span></span>  
 <span data-ttu-id="9cc9f-108">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="9cc9f-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9cc9f-109">Требования</span><span class="sxs-lookup"><span data-stu-id="9cc9f-109">Requirements</span></span>  
 <span data-ttu-id="9cc9f-110">**Заголовок.** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="9cc9f-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9cc9f-111">См. также</span><span class="sxs-lookup"><span data-stu-id="9cc9f-111">See also</span></span>
- [<span data-ttu-id="9cc9f-112">Интерфейс ISymUnmanagedScope</span><span class="sxs-lookup"><span data-stu-id="9cc9f-112">ISymUnmanagedScope Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)

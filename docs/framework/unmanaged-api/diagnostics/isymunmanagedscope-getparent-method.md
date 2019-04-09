---
title: Метод ISymUnmanagedScope::GetParent
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope.GetParent
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope::GetParent
helpviewer_keywords:
- GetParent method [.NET Framework debugging]
- ISymUnmanagedScope::GetParent method [.NET Framework debugging]
ms.assetid: c7963c87-6ec5-49b3-a5cd-e0fe0c43f9b4
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d90aeb22a945f4fa1576009c700c420704dd891b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59144785"
---
# <a name="isymunmanagedscopegetparent-method"></a><span data-ttu-id="4c3d6-102">Метод ISymUnmanagedScope::GetParent</span><span class="sxs-lookup"><span data-stu-id="4c3d6-102">ISymUnmanagedScope::GetParent Method</span></span>
<span data-ttu-id="4c3d6-103">Получает родительскую область этой области.</span><span class="sxs-lookup"><span data-stu-id="4c3d6-103">Gets the parent scope of this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4c3d6-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4c3d6-104">Syntax</span></span>  
  
```  
HRESULT GetParent(  
    [out, retval] ISymUnmanagedScope** pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4c3d6-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="4c3d6-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="4c3d6-106">[out] Указатель на возвращенный [ISymUnmanagedScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md) интерфейс.</span><span class="sxs-lookup"><span data-stu-id="4c3d6-106">[out] A pointer to the returned [ISymUnmanagedScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4c3d6-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="4c3d6-107">Return Value</span></span>  
 <span data-ttu-id="4c3d6-108">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="4c3d6-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4c3d6-109">Требования</span><span class="sxs-lookup"><span data-stu-id="4c3d6-109">Requirements</span></span>  
 <span data-ttu-id="4c3d6-110">**Заголовок.** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="4c3d6-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c3d6-111">См. также</span><span class="sxs-lookup"><span data-stu-id="4c3d6-111">See also</span></span>

- [<span data-ttu-id="4c3d6-112">Интерфейс ISymUnmanagedScope</span><span class="sxs-lookup"><span data-stu-id="4c3d6-112">ISymUnmanagedScope Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)
- [<span data-ttu-id="4c3d6-113">Метод GetChildren</span><span class="sxs-lookup"><span data-stu-id="4c3d6-113">GetChildren Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getchildren-method.md)

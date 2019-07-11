---
title: Метод ISymUnmanagedWriter3::OpenMethod2
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter3.OpenMethod2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter3::OpenMethod2
helpviewer_keywords:
- ISymUnmanagedWriter3::OpenMethod2 method [.NET Framework debugging]
- OpenMethod2 method [.NET Framework debugging]
ms.assetid: 025e358c-448f-4423-a2f2-57acf437c8a5
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2e686e332cf1d35537e5d4306a3a9cbf9d46c47e
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67752366"
---
# <a name="isymunmanagedwriter3openmethod2-method"></a><span data-ttu-id="01c28-102">Метод ISymUnmanagedWriter3::OpenMethod2</span><span class="sxs-lookup"><span data-stu-id="01c28-102">ISymUnmanagedWriter3::OpenMethod2 Method</span></span>
<span data-ttu-id="01c28-103">Открывает метод и предоставляет его фактическое смещение раздела в образе.</span><span class="sxs-lookup"><span data-stu-id="01c28-103">Opens a method and provides its real section offset in the image.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="01c28-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="01c28-104">Syntax</span></span>  
  
```cpp  
HRESULT OpenMethod2(   
    [in] mdMethodDef method,  
    [in] ULONG32 isect,  
    [in] ULONG32 offset);  
```  
  
## <a name="parameters"></a><span data-ttu-id="01c28-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="01c28-105">Parameters</span></span>  
 `method`  
 <span data-ttu-id="01c28-106">[in] Токен метаданных для открываемого метода.</span><span class="sxs-lookup"><span data-stu-id="01c28-106">[in] The metadata token for the method to be opened.</span></span>  
  
 `isect`  
 <span data-ttu-id="01c28-107">[in] Смещение раздела в образе.</span><span class="sxs-lookup"><span data-stu-id="01c28-107">[in] The section offset in the image.</span></span>  
  
 `offset`  
 <span data-ttu-id="01c28-108">[in] Смещение в образе.</span><span class="sxs-lookup"><span data-stu-id="01c28-108">[in] The offset in the image.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="01c28-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="01c28-109">Return Value</span></span>  
 <span data-ttu-id="01c28-110">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="01c28-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="01c28-111">Требования</span><span class="sxs-lookup"><span data-stu-id="01c28-111">Requirements</span></span>  
 <span data-ttu-id="01c28-112">**Заголовок.** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="01c28-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01c28-113">См. также</span><span class="sxs-lookup"><span data-stu-id="01c28-113">See also</span></span>

- [<span data-ttu-id="01c28-114">Интерфейс ISymUnmanagedWriter3</span><span class="sxs-lookup"><span data-stu-id="01c28-114">ISymUnmanagedWriter3 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-interface.md)
- [<span data-ttu-id="01c28-115">Метод OpenMethod</span><span class="sxs-lookup"><span data-stu-id="01c28-115">OpenMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openmethod-method.md)

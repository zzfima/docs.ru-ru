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
ms.openlocfilehash: 3a628aec0823c5db07d31d33813a020606906163
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74438122"
---
# <a name="isymunmanagedwriter3openmethod2-method"></a><span data-ttu-id="66e82-102">Метод ISymUnmanagedWriter3::OpenMethod2</span><span class="sxs-lookup"><span data-stu-id="66e82-102">ISymUnmanagedWriter3::OpenMethod2 Method</span></span>
<span data-ttu-id="66e82-103">Opens a method and provides its real section offset in the image.</span><span class="sxs-lookup"><span data-stu-id="66e82-103">Opens a method and provides its real section offset in the image.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="66e82-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="66e82-104">Syntax</span></span>  
  
```cpp  
HRESULT OpenMethod2(   
    [in] mdMethodDef method,  
    [in] ULONG32 isect,  
    [in] ULONG32 offset);  
```  
  
## <a name="parameters"></a><span data-ttu-id="66e82-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="66e82-105">Parameters</span></span>  
 `method`  
 <span data-ttu-id="66e82-106">[in] The metadata token for the method to be opened.</span><span class="sxs-lookup"><span data-stu-id="66e82-106">[in] The metadata token for the method to be opened.</span></span>  
  
 `isect`  
 <span data-ttu-id="66e82-107">[in] The section offset in the image.</span><span class="sxs-lookup"><span data-stu-id="66e82-107">[in] The section offset in the image.</span></span>  
  
 `offset`  
 <span data-ttu-id="66e82-108">[in] The offset in the image.</span><span class="sxs-lookup"><span data-stu-id="66e82-108">[in] The offset in the image.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="66e82-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="66e82-109">Return Value</span></span>  
 <span data-ttu-id="66e82-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span><span class="sxs-lookup"><span data-stu-id="66e82-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="66e82-111">Требования</span><span class="sxs-lookup"><span data-stu-id="66e82-111">Requirements</span></span>  
 <span data-ttu-id="66e82-112">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="66e82-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66e82-113">См. также</span><span class="sxs-lookup"><span data-stu-id="66e82-113">See also</span></span>

- [<span data-ttu-id="66e82-114">Интерфейс ISymUnmanagedWriter3</span><span class="sxs-lookup"><span data-stu-id="66e82-114">ISymUnmanagedWriter3 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-interface.md)
- [<span data-ttu-id="66e82-115">Метод OpenMethod</span><span class="sxs-lookup"><span data-stu-id="66e82-115">OpenMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openmethod-method.md)

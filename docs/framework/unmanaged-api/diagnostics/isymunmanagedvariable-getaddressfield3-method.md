---
title: Метод ISymUnmanagedVariable::GetAddressField3
ms.date: 03/30/2017
api_name:
- ISymUnmanagedVariable.GetAddressField3
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedVariable::GetAddressField3
helpviewer_keywords:
- ISymUnmanagedVariable::GetAddressField3 method [.NET Framework debugging]
- GetAddressField3 method [.NET Framework debugging]
ms.assetid: 4d834721-ad8d-439d-b356-c6b4aef022fc
topic_type:
- apiref
ms.openlocfilehash: 3bdc79a6b6d81f6f0998f052f8bea1bf8af55402
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446103"
---
# <a name="isymunmanagedvariablegetaddressfield3-method"></a><span data-ttu-id="ef7ed-102">Метод ISymUnmanagedVariable::GetAddressField3</span><span class="sxs-lookup"><span data-stu-id="ef7ed-102">ISymUnmanagedVariable::GetAddressField3 Method</span></span>
<span data-ttu-id="ef7ed-103">Gets the third address field for this variable.</span><span class="sxs-lookup"><span data-stu-id="ef7ed-103">Gets the third address field for this variable.</span></span> <span data-ttu-id="ef7ed-104">Its meaning depends on the kind of address.</span><span class="sxs-lookup"><span data-stu-id="ef7ed-104">Its meaning depends on the kind of address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ef7ed-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ef7ed-105">Syntax</span></span>  
  
```cpp  
HRESULT GetAddressField3(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ef7ed-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="ef7ed-106">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="ef7ed-107">[out] A pointer to a `ULONG32` that receives the third address field.</span><span class="sxs-lookup"><span data-stu-id="ef7ed-107">[out] A pointer to a `ULONG32` that receives the third address field.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ef7ed-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="ef7ed-108">Return Value</span></span>  
 <span data-ttu-id="ef7ed-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span><span class="sxs-lookup"><span data-stu-id="ef7ed-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ef7ed-110">Требования</span><span class="sxs-lookup"><span data-stu-id="ef7ed-110">Requirements</span></span>  
 <span data-ttu-id="ef7ed-111">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="ef7ed-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef7ed-112">См. также</span><span class="sxs-lookup"><span data-stu-id="ef7ed-112">See also</span></span>

- [<span data-ttu-id="ef7ed-113">Интерфейс ISymUnmanagedVariable</span><span class="sxs-lookup"><span data-stu-id="ef7ed-113">ISymUnmanagedVariable Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)
- [<span data-ttu-id="ef7ed-114">Метод GetAddressField1</span><span class="sxs-lookup"><span data-stu-id="ef7ed-114">GetAddressField1 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield1-method.md)
- [<span data-ttu-id="ef7ed-115">Метод GetAddressField2</span><span class="sxs-lookup"><span data-stu-id="ef7ed-115">GetAddressField2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield2-method.md)
- [<span data-ttu-id="ef7ed-116">Метод GetAddressKind</span><span class="sxs-lookup"><span data-stu-id="ef7ed-116">GetAddressKind Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddresskind-method.md)

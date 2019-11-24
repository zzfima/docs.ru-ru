---
title: Метод ISymUnmanagedReader::GetMethodVersion
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetMethodVersion
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetMethodVersion
helpviewer_keywords:
- GetMethodVersion method [.NET Framework debugging]
- ISymUnmanagedReader::GetMethodVersion method [.NET Framework debugging]
ms.assetid: d6f9ac84-302a-4f5e-b990-e76f4269fceb
topic_type:
- apiref
ms.openlocfilehash: fcaf748413321f684336543e60f735af69894b51
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74436009"
---
# <a name="isymunmanagedreadergetmethodversion-method"></a><span data-ttu-id="2b9b6-102">Метод ISymUnmanagedReader::GetMethodVersion</span><span class="sxs-lookup"><span data-stu-id="2b9b6-102">ISymUnmanagedReader::GetMethodVersion Method</span></span>
<span data-ttu-id="2b9b6-103">Gets the method version.</span><span class="sxs-lookup"><span data-stu-id="2b9b6-103">Gets the method version.</span></span> <span data-ttu-id="2b9b6-104">The method version starts at 1 and is incremented each time the method is recompiled.</span><span class="sxs-lookup"><span data-stu-id="2b9b6-104">The method version starts at 1 and is incremented each time the method is recompiled.</span></span> <span data-ttu-id="2b9b6-105">Recompilation can happen without changes to the method.</span><span class="sxs-lookup"><span data-stu-id="2b9b6-105">Recompilation can happen without changes to the method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2b9b6-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2b9b6-106">Syntax</span></span>  
  
```cpp  
HRESULT GetMethodVersion (  
    [in]  ISymUnmanagedMethod* pMethod,  
    [out] int* version);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2b9b6-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="2b9b6-107">Parameters</span></span>  
 `pMethod`  
 <span data-ttu-id="2b9b6-108">[in] The method for which to get the version.</span><span class="sxs-lookup"><span data-stu-id="2b9b6-108">[in] The method for which to get the version.</span></span>  
  
 `version`  
 <span data-ttu-id="2b9b6-109">[out] A pointer to a variable that receives the method version.</span><span class="sxs-lookup"><span data-stu-id="2b9b6-109">[out] A pointer to a variable that receives the method version.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2b9b6-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="2b9b6-110">Return Value</span></span>  
 <span data-ttu-id="2b9b6-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span><span class="sxs-lookup"><span data-stu-id="2b9b6-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2b9b6-112">Требования</span><span class="sxs-lookup"><span data-stu-id="2b9b6-112">Requirements</span></span>  
 <span data-ttu-id="2b9b6-113">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="2b9b6-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b9b6-114">См. также</span><span class="sxs-lookup"><span data-stu-id="2b9b6-114">See also</span></span>

- [<span data-ttu-id="2b9b6-115">Интерфейс ISymUnmanagedReader</span><span class="sxs-lookup"><span data-stu-id="2b9b6-115">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)

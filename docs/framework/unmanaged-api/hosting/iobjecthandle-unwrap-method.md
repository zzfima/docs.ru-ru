---
title: Метод IObjectHandle::Unwrap
ms.date: 03/30/2017
api_name:
- IObjectHandle.Unwrap
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- Unwrap
helpviewer_keywords:
- Unwrap method [.NET Framework hosting]
- IObjectHandle::Unwrap method [.NET Framework hosting]
ms.assetid: 794c6f8e-ed58-416b-b756-e864f2c958f7
topic_type:
- apiref
ms.openlocfilehash: be488ebe663169cabc5b569335dfc784fdf30556
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73102695"
---
# <a name="iobjecthandleunwrap-method"></a><span data-ttu-id="ee0fc-102">Метод IObjectHandle::Unwrap</span><span class="sxs-lookup"><span data-stu-id="ee0fc-102">IObjectHandle::Unwrap Method</span></span>
<span data-ttu-id="ee0fc-103">Распаковывает объект по значению из косвенного обращения.</span><span class="sxs-lookup"><span data-stu-id="ee0fc-103">Unwraps a marshal-by-value object from indirection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ee0fc-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ee0fc-104">Syntax</span></span>  
  
```cpp  
HRESULT Unwrap (  
    [out, retval] VARIANT *ppv  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ee0fc-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="ee0fc-105">Parameters</span></span>  
 `ppv`  
 <span data-ttu-id="ee0fc-106">заполняет Указатель на объект, который необходимо распаковать.</span><span class="sxs-lookup"><span data-stu-id="ee0fc-106">[out] A pointer to the object to be unwrapped.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ee0fc-107">Требования</span><span class="sxs-lookup"><span data-stu-id="ee0fc-107">Requirements</span></span>  
 <span data-ttu-id="ee0fc-108">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ee0fc-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ee0fc-109">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="ee0fc-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ee0fc-110">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="ee0fc-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ee0fc-111">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ee0fc-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  

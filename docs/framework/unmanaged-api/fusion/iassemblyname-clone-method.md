---
title: Метод IAssemblyName::Clone
ms.date: 03/30/2017
api_name:
- IAssemblyName.Clone
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyName::Clone
helpviewer_keywords:
- Clone method, IAssemblyName interface [.NET Framework fusion]
- IAssemblyName::Clone method [.NET Framework fusion]
ms.assetid: 7b345e08-5e16-4e3d-a044-4e19d0892943
topic_type:
- apiref
ms.openlocfilehash: 1236a574a85c01e3e1be5df9644bd04bbf0753ea
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134410"
---
# <a name="iassemblynameclone-method"></a><span data-ttu-id="c9e10-102">Метод IAssemblyName::Clone</span><span class="sxs-lookup"><span data-stu-id="c9e10-102">IAssemblyName::Clone Method</span></span>
<span data-ttu-id="c9e10-103">Создает неполную копию этого объекта [IAssemblyName](iassemblyname-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="c9e10-103">Creates a shallow copy of this [IAssemblyName](iassemblyname-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c9e10-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c9e10-104">Syntax</span></span>  
  
```cpp  
HRESULT Clone (  
    [out] IAssemblyName **pName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c9e10-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c9e10-105">Parameters</span></span>  
 `pName`  
 <span data-ttu-id="c9e10-106">заполняет Возвращенная копия объекта `IAssemblyName`.</span><span class="sxs-lookup"><span data-stu-id="c9e10-106">[out] The returned copy of this `IAssemblyName` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c9e10-107">Требования</span><span class="sxs-lookup"><span data-stu-id="c9e10-107">Requirements</span></span>  
 <span data-ttu-id="c9e10-108">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c9e10-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c9e10-109">**Заголовок:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="c9e10-109">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="c9e10-110">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c9e10-110">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9e10-111">См. также</span><span class="sxs-lookup"><span data-stu-id="c9e10-111">See also</span></span>

- [<span data-ttu-id="c9e10-112">Интерфейс IAssemblyName</span><span class="sxs-lookup"><span data-stu-id="c9e10-112">IAssemblyName Interface</span></span>](iassemblyname-interface.md)

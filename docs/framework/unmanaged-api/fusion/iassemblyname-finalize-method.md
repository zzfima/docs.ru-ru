---
title: Метод IAssemblyName::Finalize
ms.date: 03/30/2017
api_name:
- IAssemblyName.Finalize
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyName::Finalize
helpviewer_keywords:
- Finalize method [.NET Framework fusion]
- IAssemblyName::Finalize method [.NET Framework fusion]
ms.assetid: 610e792d-98ef-411f-90b0-5b9a3813f547
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4c5ea24594f5c7547dc75e6be9d53dd632513ff8
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67754011"
---
# <a name="iassemblynamefinalize-method"></a><span data-ttu-id="021bc-102">Метод IAssemblyName::Finalize</span><span class="sxs-lookup"><span data-stu-id="021bc-102">IAssemblyName::Finalize Method</span></span>
<span data-ttu-id="021bc-103">Это позволяет [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) объект освободить ресурсы и выполнить другие операции очистки, прежде чем его деструктора.</span><span class="sxs-lookup"><span data-stu-id="021bc-103">Allows this [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) object to release resources and perform other cleanup operations before its destructor is called.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="021bc-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="021bc-104">Syntax</span></span>  
  
```cpp  
HRESULT Finalize ();  
```  
  
## <a name="requirements"></a><span data-ttu-id="021bc-105">Требования</span><span class="sxs-lookup"><span data-stu-id="021bc-105">Requirements</span></span>  
 <span data-ttu-id="021bc-106">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="021bc-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="021bc-107">**Заголовок.** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="021bc-107">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="021bc-108">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="021bc-108">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="021bc-109">См. также</span><span class="sxs-lookup"><span data-stu-id="021bc-109">See also</span></span>

- [<span data-ttu-id="021bc-110">Интерфейс IAssemblyName</span><span class="sxs-lookup"><span data-stu-id="021bc-110">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)

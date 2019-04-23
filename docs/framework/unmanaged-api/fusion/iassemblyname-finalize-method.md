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
ms.openlocfilehash: f4db24977d46277bc16a8800b0c4f7a550747cb9
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59206529"
---
# <a name="iassemblynamefinalize-method"></a><span data-ttu-id="abf0e-102">Метод IAssemblyName::Finalize</span><span class="sxs-lookup"><span data-stu-id="abf0e-102">IAssemblyName::Finalize Method</span></span>
<span data-ttu-id="abf0e-103">Это позволяет [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) объект освободить ресурсы и выполнить другие операции очистки, прежде чем его деструктора.</span><span class="sxs-lookup"><span data-stu-id="abf0e-103">Allows this [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) object to release resources and perform other cleanup operations before its destructor is called.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="abf0e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="abf0e-104">Syntax</span></span>  
  
```  
HRESULT Finalize ();  
```  
  
## <a name="requirements"></a><span data-ttu-id="abf0e-105">Требования</span><span class="sxs-lookup"><span data-stu-id="abf0e-105">Requirements</span></span>  
 <span data-ttu-id="abf0e-106">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="abf0e-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="abf0e-107">**Заголовок.** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="abf0e-107">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="abf0e-108">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="abf0e-108">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="abf0e-109">См. также</span><span class="sxs-lookup"><span data-stu-id="abf0e-109">See also</span></span>

- [<span data-ttu-id="abf0e-110">Интерфейс IAssemblyName</span><span class="sxs-lookup"><span data-stu-id="abf0e-110">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)

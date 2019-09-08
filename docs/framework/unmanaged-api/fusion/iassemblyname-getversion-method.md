---
title: Метод IAssemblyName::GetVersion
ms.date: 03/30/2017
api_name:
- IAssemblyName.GetVersion
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyName::GetVersion
helpviewer_keywords:
- IAssemblyName::GetVersion method [.NET Framework fusion]
- GetVersion method, IAssemblyName interface [.NET Framework fusion]
ms.assetid: 42230928-2c33-41fd-9519-d96efef6c7af
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 58919936bdc62d52437f429146f04c66d49294b2
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796579"
---
# <a name="iassemblynamegetversion-method"></a><span data-ttu-id="11d30-102">Метод IAssemblyName::GetVersion</span><span class="sxs-lookup"><span data-stu-id="11d30-102">IAssemblyName::GetVersion Method</span></span>
<span data-ttu-id="11d30-103">Возвращает сведения о версии для сборки, на которую ссылается этот объект [IAssemblyName](iassemblyname-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="11d30-103">Gets the version information for the assembly referenced by this [IAssemblyName](iassemblyname-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="11d30-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="11d30-104">Syntax</span></span>  
  
```cpp  
HRESULT GetVersion (  
    [out] LPDWORD pdwVersionHi,  
    [out] LPDWORD pdwVersionLow  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="11d30-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="11d30-105">Parameters</span></span>  
 `pdwVersionHi`  
 <span data-ttu-id="11d30-106">заполняет Старшие 32 бит версии.</span><span class="sxs-lookup"><span data-stu-id="11d30-106">[out] The high 32 bits of the version.</span></span>  
  
 `pdwVersionLow`  
 <span data-ttu-id="11d30-107">заполняет Младшие 32 разрядов версии.</span><span class="sxs-lookup"><span data-stu-id="11d30-107">[out] The low 32 bits of the version.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="11d30-108">Требования</span><span class="sxs-lookup"><span data-stu-id="11d30-108">Requirements</span></span>  
 <span data-ttu-id="11d30-109">**Платформ** См. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="11d30-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="11d30-110">**Заголовок.** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="11d30-110">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="11d30-111">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="11d30-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11d30-112">См. также</span><span class="sxs-lookup"><span data-stu-id="11d30-112">See also</span></span>

- [<span data-ttu-id="11d30-113">Интерфейс IAssemblyName</span><span class="sxs-lookup"><span data-stu-id="11d30-113">IAssemblyName Interface</span></span>](iassemblyname-interface.md)

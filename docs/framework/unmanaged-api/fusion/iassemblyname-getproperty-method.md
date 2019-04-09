---
title: Метод IAssemblyName::GetProperty
ms.date: 03/30/2017
api_name:
- IAssemblyName.GetProperty
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyName::GetProperty
helpviewer_keywords:
- IAssemblyName::GetProperty method [.NET Framework fusion]
- GetProperty method [.NET Framework fusion]
ms.assetid: e59fda62-77d5-4e37-89cb-ce7ae4627975
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9af0773c2ef066c103f823e4d28c0fd6e9eadc24
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59086563"
---
# <a name="iassemblynamegetproperty-method"></a><span data-ttu-id="fe899-102">Метод IAssemblyName::GetProperty</span><span class="sxs-lookup"><span data-stu-id="fe899-102">IAssemblyName::GetProperty Method</span></span>
<span data-ttu-id="fe899-103">Возвращает указатель на свойство, заданное с помощью идентификатора указанного свойства.</span><span class="sxs-lookup"><span data-stu-id="fe899-103">Gets a pointer to the property referenced by the specified property identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fe899-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fe899-104">Syntax</span></span>  
  
```  
HRESULT GetProperty (  
    [in]      DWORD    PropertyId,  
    [out]     LPVOID   pvProperty,  
    [in, out] LPDWORD  pcbProperty  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fe899-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="fe899-105">Parameters</span></span>  
 `PropertyId`  
 <span data-ttu-id="fe899-106">[in] Уникальный идентификатор для запрошенного свойства.</span><span class="sxs-lookup"><span data-stu-id="fe899-106">[in] The unique identifier for the requested property.</span></span>  
  
 `pvProperty`  
 <span data-ttu-id="fe899-107">[out] Данные, возвращаемое свойство.</span><span class="sxs-lookup"><span data-stu-id="fe899-107">[out] The returned property data.</span></span>  
  
 `pcbProperty`  
 <span data-ttu-id="fe899-108">[in, out] Размер в байтах из `pvProperty`.</span><span class="sxs-lookup"><span data-stu-id="fe899-108">[in, out] The size, in bytes, of `pvProperty`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fe899-109">Требования</span><span class="sxs-lookup"><span data-stu-id="fe899-109">Requirements</span></span>  
 <span data-ttu-id="fe899-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fe899-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fe899-111">**Заголовок.** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="fe899-111">**Header:** Fusion.h</span></span>  
  
 **<span data-ttu-id="fe899-112">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="fe899-112">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="fe899-113">См. также</span><span class="sxs-lookup"><span data-stu-id="fe899-113">See also</span></span>

- [<span data-ttu-id="fe899-114">Интерфейс IAssemblyName</span><span class="sxs-lookup"><span data-stu-id="fe899-114">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)

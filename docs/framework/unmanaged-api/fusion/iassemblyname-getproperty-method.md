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
ms.openlocfilehash: 6c297c2476cb35fef861cda77f4f6f536fd85557
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33428195"
---
# <a name="iassemblynamegetproperty-method"></a><span data-ttu-id="4c3f1-102">Метод IAssemblyName::GetProperty</span><span class="sxs-lookup"><span data-stu-id="4c3f1-102">IAssemblyName::GetProperty Method</span></span>
<span data-ttu-id="4c3f1-103">Возвращает указатель на свойство ссылается указанный идентификатор свойства.</span><span class="sxs-lookup"><span data-stu-id="4c3f1-103">Gets a pointer to the property referenced by the specified property identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4c3f1-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4c3f1-104">Syntax</span></span>  
  
```  
HRESULT GetProperty (  
    [in]      DWORD    PropertyId,  
    [out]     LPVOID   pvProperty,  
    [in, out] LPDWORD  pcbProperty  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4c3f1-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="4c3f1-105">Parameters</span></span>  
 `PropertyId`  
 <span data-ttu-id="4c3f1-106">[in] Уникальный идентификатор для запрашиваемого свойства.</span><span class="sxs-lookup"><span data-stu-id="4c3f1-106">[in] The unique identifier for the requested property.</span></span>  
  
 `pvProperty`  
 <span data-ttu-id="4c3f1-107">[out] Данные возвращаемого свойства.</span><span class="sxs-lookup"><span data-stu-id="4c3f1-107">[out] The returned property data.</span></span>  
  
 `pcbProperty`  
 <span data-ttu-id="4c3f1-108">[in, out] Размер в байтах для `pvProperty`.</span><span class="sxs-lookup"><span data-stu-id="4c3f1-108">[in, out] The size, in bytes, of `pvProperty`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4c3f1-109">Требования</span><span class="sxs-lookup"><span data-stu-id="4c3f1-109">Requirements</span></span>  
 <span data-ttu-id="4c3f1-110">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4c3f1-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4c3f1-111">**Заголовок:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="4c3f1-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="4c3f1-112">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4c3f1-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c3f1-113">См. также</span><span class="sxs-lookup"><span data-stu-id="4c3f1-113">See Also</span></span>  
 [<span data-ttu-id="4c3f1-114">Интерфейс IAssemblyName</span><span class="sxs-lookup"><span data-stu-id="4c3f1-114">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)

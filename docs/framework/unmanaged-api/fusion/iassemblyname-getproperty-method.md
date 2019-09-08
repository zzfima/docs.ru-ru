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
ms.openlocfilehash: 351d540d226f46f180b46323e83eb1bcc71da4f0
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796588"
---
# <a name="iassemblynamegetproperty-method"></a><span data-ttu-id="04767-102">Метод IAssemblyName::GetProperty</span><span class="sxs-lookup"><span data-stu-id="04767-102">IAssemblyName::GetProperty Method</span></span>
<span data-ttu-id="04767-103">Возвращает указатель на свойство, на которое ссылается указанный идентификатор свойства.</span><span class="sxs-lookup"><span data-stu-id="04767-103">Gets a pointer to the property referenced by the specified property identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="04767-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="04767-104">Syntax</span></span>  
  
```cpp  
HRESULT GetProperty (  
    [in]      DWORD    PropertyId,  
    [out]     LPVOID   pvProperty,  
    [in, out] LPDWORD  pcbProperty  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="04767-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="04767-105">Parameters</span></span>  
 `PropertyId`  
 <span data-ttu-id="04767-106">окне Уникальный идентификатор запрошенного свойства.</span><span class="sxs-lookup"><span data-stu-id="04767-106">[in] The unique identifier for the requested property.</span></span>  
  
 `pvProperty`  
 <span data-ttu-id="04767-107">заполняет Возвращаемые данные свойства.</span><span class="sxs-lookup"><span data-stu-id="04767-107">[out] The returned property data.</span></span>  
  
 `pcbProperty`  
 <span data-ttu-id="04767-108">[вход, выход] Размер (в байтах `pvProperty`).</span><span class="sxs-lookup"><span data-stu-id="04767-108">[in, out] The size, in bytes, of `pvProperty`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="04767-109">Требования</span><span class="sxs-lookup"><span data-stu-id="04767-109">Requirements</span></span>  
 <span data-ttu-id="04767-110">**Платформ** См. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="04767-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="04767-111">**Заголовок.** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="04767-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="04767-112">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="04767-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04767-113">См. также</span><span class="sxs-lookup"><span data-stu-id="04767-113">See also</span></span>

- [<span data-ttu-id="04767-114">Интерфейс IAssemblyName</span><span class="sxs-lookup"><span data-stu-id="04767-114">IAssemblyName Interface</span></span>](iassemblyname-interface.md)

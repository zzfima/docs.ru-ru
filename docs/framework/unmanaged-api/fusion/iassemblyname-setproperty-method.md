---
title: Метод IAssemblyName::SetProperty
ms.date: 03/30/2017
api_name:
- IAssemblyName.SetProperty
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyName::SetProperty
helpviewer_keywords:
- IAssemblyName::SetProperty method [.NET Framework fusion]
- SetProperty method [.NET Framework fusion]
ms.assetid: 496c3add-f60b-4073-943f-d1bcf33330cb
topic_type:
- apiref
ms.openlocfilehash: ffa1fa2f5e141728a56f1b598a1aae9602b2ac86
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73108218"
---
# <a name="iassemblynamesetproperty-method"></a><span data-ttu-id="7f2fb-102">Метод IAssemblyName::SetProperty</span><span class="sxs-lookup"><span data-stu-id="7f2fb-102">IAssemblyName::SetProperty Method</span></span>
<span data-ttu-id="7f2fb-103">Задает значение свойства, на которое ссылается указанный идентификатор свойства.</span><span class="sxs-lookup"><span data-stu-id="7f2fb-103">Sets the value of the property referenced by the specified property identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7f2fb-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7f2fb-104">Syntax</span></span>  
  
```cpp  
HRESULT SetProperty (  
    [in] DWORD  PropertyId,  
    [in] LPVOID pvProperty,  
    [in] DWORD  cbProperty  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7f2fb-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="7f2fb-105">Parameters</span></span>  
 `PropertyId`  
 <span data-ttu-id="7f2fb-106">окне Уникальный идентификатор свойства, значение которого будет задано.</span><span class="sxs-lookup"><span data-stu-id="7f2fb-106">[in] The unique identifier of the property whose value will be set.</span></span>  
  
 `pvProperty`  
 <span data-ttu-id="7f2fb-107">окне Значение, для которого задается свойство, на которое ссылается `PropertyId`.</span><span class="sxs-lookup"><span data-stu-id="7f2fb-107">[in] The value to which to set the property referenced by `PropertyId`.</span></span>  
  
 `cbProperty`  
 <span data-ttu-id="7f2fb-108">окне Размер `pvProperty`в байтах.</span><span class="sxs-lookup"><span data-stu-id="7f2fb-108">[in] The size, in bytes, of `pvProperty`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7f2fb-109">Требования</span><span class="sxs-lookup"><span data-stu-id="7f2fb-109">Requirements</span></span>  
 <span data-ttu-id="7f2fb-110">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7f2fb-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7f2fb-111">**Заголовок:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="7f2fb-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="7f2fb-112">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7f2fb-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f2fb-113">См. также</span><span class="sxs-lookup"><span data-stu-id="7f2fb-113">See also</span></span>

- [<span data-ttu-id="7f2fb-114">Интерфейс IAssemblyName</span><span class="sxs-lookup"><span data-stu-id="7f2fb-114">IAssemblyName Interface</span></span>](iassemblyname-interface.md)

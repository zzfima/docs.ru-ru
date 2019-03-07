---
title: Метод IManagedObject::GetSerializedBuffer
ms.date: 03/30/2017
api_name:
- IManagedObject.GetSerializedBuffer
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- GetSerializedBuffer
helpviewer_keywords:
- IManagedObject::GetSerializedBuffer method [.NET Framework hosting]
- GetSerializedBuffer method [.NET Framework hosting]
ms.assetid: c17105bb-b49f-434e-8f9b-77f8c85b9220
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7930e993640e1ae88ce65b6c2025a5b62a0d0999
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57502466"
---
# <a name="imanagedobjectgetserializedbuffer-method"></a><span data-ttu-id="feeae-102">Метод IManagedObject::GetSerializedBuffer</span><span class="sxs-lookup"><span data-stu-id="feeae-102">IManagedObject::GetSerializedBuffer Method</span></span>
<span data-ttu-id="feeae-103">Возвращает строковое представление этого управляемого объекта.</span><span class="sxs-lookup"><span data-stu-id="feeae-103">Gets the string representation of this managed object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="feeae-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="feeae-104">Syntax</span></span>  
  
```  
HRESULT GetSerializedBuffer (  
    [out] BSTR *pBSTR  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="feeae-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="feeae-105">Parameters</span></span>  
 `pBSTR`  
 <span data-ttu-id="feeae-106">[out] Указатель на строку, являющуюся сериализованного объекта.</span><span class="sxs-lookup"><span data-stu-id="feeae-106">[out] A pointer to a string that is the serialized object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="feeae-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="feeae-107">Remarks</span></span>  
 <span data-ttu-id="feeae-108">`GetSerializedBuffer` Метод сериализует объект, поэтому он может маршалироваться клиенту.</span><span class="sxs-lookup"><span data-stu-id="feeae-108">The `GetSerializedBuffer` method serializes the object so it can be marshaled to the client.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="feeae-109">Требования</span><span class="sxs-lookup"><span data-stu-id="feeae-109">Requirements</span></span>  
 <span data-ttu-id="feeae-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="feeae-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="feeae-111">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="feeae-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="feeae-112">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="feeae-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="feeae-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="feeae-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="feeae-114">См. также</span><span class="sxs-lookup"><span data-stu-id="feeae-114">See also</span></span>
- [<span data-ttu-id="feeae-115">Интерфейс IManagedObject</span><span class="sxs-lookup"><span data-stu-id="feeae-115">IManagedObject Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/imanagedobject-interface.md)

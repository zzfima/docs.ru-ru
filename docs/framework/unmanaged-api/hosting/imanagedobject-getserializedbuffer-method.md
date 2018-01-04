---
title: "Метод IManagedObject::GetSerializedBuffer"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IManagedObject.GetSerializedBuffer
api_location: mscoree.dll
api_type: COM
f1_keywords: GetSerializedBuffer
helpviewer_keywords:
- IManagedObject::GetSerializedBuffer method [.NET Framework hosting]
- GetSerializedBuffer method [.NET Framework hosting]
ms.assetid: c17105bb-b49f-434e-8f9b-77f8c85b9220
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d8ae9edab2ca943fc6fb265ab698c2c82d6c531b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="imanagedobjectgetserializedbuffer-method"></a><span data-ttu-id="e2c13-102">Метод IManagedObject::GetSerializedBuffer</span><span class="sxs-lookup"><span data-stu-id="e2c13-102">IManagedObject::GetSerializedBuffer Method</span></span>
<span data-ttu-id="e2c13-103">Возвращает строковое представление данного управляемого объекта.</span><span class="sxs-lookup"><span data-stu-id="e2c13-103">Gets the string representation of this managed object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e2c13-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e2c13-104">Syntax</span></span>  
  
```  
HRESULT GetSerializedBuffer (  
    [out] BSTR *pBSTR  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e2c13-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="e2c13-105">Parameters</span></span>  
 `pBSTR`  
 <span data-ttu-id="e2c13-106">[out] Указатель на строку, являющуюся сериализованный объект.</span><span class="sxs-lookup"><span data-stu-id="e2c13-106">[out] A pointer to a string that is the serialized object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e2c13-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="e2c13-107">Remarks</span></span>  
 <span data-ttu-id="e2c13-108">`GetSerializedBuffer` Метод сериализует объект, поэтому он может быть маршалирован клиенту.</span><span class="sxs-lookup"><span data-stu-id="e2c13-108">The `GetSerializedBuffer` method serializes the object so it can be marshaled to the client.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e2c13-109">Требования</span><span class="sxs-lookup"><span data-stu-id="e2c13-109">Requirements</span></span>  
 <span data-ttu-id="e2c13-110">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e2c13-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e2c13-111">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="e2c13-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e2c13-112">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e2c13-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e2c13-113">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e2c13-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2c13-114">См. также</span><span class="sxs-lookup"><span data-stu-id="e2c13-114">See Also</span></span>  
 [<span data-ttu-id="e2c13-115">Интерфейс IManagedObject</span><span class="sxs-lookup"><span data-stu-id="e2c13-115">IManagedObject Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/imanagedobject-interface.md)

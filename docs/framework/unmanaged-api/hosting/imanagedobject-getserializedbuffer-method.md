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
ms.openlocfilehash: 53e8180fb55336eb05d0737110fd2fe07a4c5894
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33441605"
---
# <a name="imanagedobjectgetserializedbuffer-method"></a><span data-ttu-id="c82fa-102">Метод IManagedObject::GetSerializedBuffer</span><span class="sxs-lookup"><span data-stu-id="c82fa-102">IManagedObject::GetSerializedBuffer Method</span></span>
<span data-ttu-id="c82fa-103">Возвращает строковое представление данного управляемого объекта.</span><span class="sxs-lookup"><span data-stu-id="c82fa-103">Gets the string representation of this managed object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c82fa-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c82fa-104">Syntax</span></span>  
  
```  
HRESULT GetSerializedBuffer (  
    [out] BSTR *pBSTR  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c82fa-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c82fa-105">Parameters</span></span>  
 `pBSTR`  
 <span data-ttu-id="c82fa-106">[out] Указатель на строку, являющуюся сериализованный объект.</span><span class="sxs-lookup"><span data-stu-id="c82fa-106">[out] A pointer to a string that is the serialized object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c82fa-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="c82fa-107">Remarks</span></span>  
 <span data-ttu-id="c82fa-108">`GetSerializedBuffer` Метод сериализует объект, поэтому он может быть маршалирован клиенту.</span><span class="sxs-lookup"><span data-stu-id="c82fa-108">The `GetSerializedBuffer` method serializes the object so it can be marshaled to the client.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c82fa-109">Требования</span><span class="sxs-lookup"><span data-stu-id="c82fa-109">Requirements</span></span>  
 <span data-ttu-id="c82fa-110">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c82fa-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c82fa-111">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="c82fa-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c82fa-112">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c82fa-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c82fa-113">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c82fa-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c82fa-114">См. также</span><span class="sxs-lookup"><span data-stu-id="c82fa-114">See Also</span></span>  
 [<span data-ttu-id="c82fa-115">Интерфейс IManagedObject</span><span class="sxs-lookup"><span data-stu-id="c82fa-115">IManagedObject Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/imanagedobject-interface.md)

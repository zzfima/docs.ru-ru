---
title: Интерфейс IIdentityAuthority
ms.date: 03/30/2017
api_name:
- IIdentityAuthority
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IIdentityAuthority
helpviewer_keywords:
- IIdentityAuthority interface [.NET Framework fusion]
ms.assetid: 6277f914-51a8-49be-bec6-52d6d648527d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ab8965ca5d6c9c96cea5f5b351547ce2d4dfacc7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54546284"
---
# <a name="iidentityauthority-interface"></a><span data-ttu-id="e642b-102">Интерфейс IIdentityAuthority</span><span class="sxs-lookup"><span data-stu-id="e642b-102">IIdentityAuthority Interface</span></span>
<span data-ttu-id="e642b-103">Управляет идентификационные ключи для объектов кода.</span><span class="sxs-lookup"><span data-stu-id="e642b-103">Manages identity keys for code objects.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e642b-104">Методы</span><span class="sxs-lookup"><span data-stu-id="e642b-104">Methods</span></span>  
  
|<span data-ttu-id="e642b-105">Метод</span><span class="sxs-lookup"><span data-stu-id="e642b-105">Method</span></span>|<span data-ttu-id="e642b-106">Описание</span><span class="sxs-lookup"><span data-stu-id="e642b-106">Description</span></span>|  
|------------|-----------------|  
|`IIdentityAuthority::AreDefinitionsEqual`|<span data-ttu-id="e642b-107">Получает значение, указывающее, являются ли два заданных [IDefinitionIdentity](../../../../docs/framework/unmanaged-api/fusion/idefinitionidentity-interface.md) они равны.</span><span class="sxs-lookup"><span data-stu-id="e642b-107">Gets a value that indicates whether the two specified [IDefinitionIdentity](../../../../docs/framework/unmanaged-api/fusion/idefinitionidentity-interface.md) instances are equal.</span></span>|  
|`IIdentityAuthority::AreReferencesEqual`|<span data-ttu-id="e642b-108">Получает значение, указывающее, являются ли два заданных [IReferenceIdentity](../../../../docs/framework/unmanaged-api/fusion/ireferenceidentity-interface.md) они равны.</span><span class="sxs-lookup"><span data-stu-id="e642b-108">Gets a value that indicates whether the two specified [IReferenceIdentity](../../../../docs/framework/unmanaged-api/fusion/ireferenceidentity-interface.md) instances are equal.</span></span>|  
|`IIdentityAuthority::AreTextualDefinitionsEqual`|<span data-ttu-id="e642b-109">Получает значение, указывающее, равны ли два представления идентификации определение указанной строки.</span><span class="sxs-lookup"><span data-stu-id="e642b-109">Gets a value that indicates whether the two specified string definition identity representations are equal.</span></span>|  
|`IIdentityAuthority::AreTextualReferencesEqual`|<span data-ttu-id="e642b-110">Получает значение, указывающее, равны ли два указанные строковые представления идентификации ссылки.</span><span class="sxs-lookup"><span data-stu-id="e642b-110">Gets a value that indicates whether the two specified string reference identity representations are equal.</span></span>|  
|`IIdentityAuthority::CreateDefinition`|<span data-ttu-id="e642b-111">Возвращает указатель на новый `IDefinitionIdentity` экземпляр, представляющий объект кода в текущей области.</span><span class="sxs-lookup"><span data-stu-id="e642b-111">Gets a pointer to a new `IDefinitionIdentity` instance that represents the code object in the current scope.</span></span>|  
|`IIdentityAuthority::CreateReference`|<span data-ttu-id="e642b-112">Возвращает указатель на новый `IReferenceIdentity` экземпляр, представляющий объект кода в текущей области.</span><span class="sxs-lookup"><span data-stu-id="e642b-112">Gets a pointer to a new `IReferenceIdentity` instance that represents the code object in the current scope.</span></span>|  
|`IIdentityAuthority::DefinitionToText`|<span data-ttu-id="e642b-113">Получает форматированное строковое представление указанного `IDefinitionIdentity`.</span><span class="sxs-lookup"><span data-stu-id="e642b-113">Gets a formatted string version of the specified `IDefinitionIdentity`.</span></span>|  
|`IIdentityAuthority::DefinitionToTextBuffer`|<span data-ttu-id="e642b-114">Заполняет буфер указанного расширенный символ строковую версию указанного `IDefinitionIdentity`.</span><span class="sxs-lookup"><span data-stu-id="e642b-114">Fills the specified wide character buffer with a string version of the specified `IDefinitionIdentity`.</span></span>|  
|`IIdentityAuthority::DoesDefinitionMatchReference`|<span data-ttu-id="e642b-115">Получает значение, указывающее ли указанный `IDefinitionIdentity` и `IReferenceIdentity` ссылаются экземпляра на один и тот же объект кода.</span><span class="sxs-lookup"><span data-stu-id="e642b-115">Gets a value that indicates whether the specified `IDefinitionIdentity` and `IReferenceIdentity` instances refer to the same code object.</span></span>|  
|`IIdentityAuthority::DoesTextualDefinitionMatchTextualReference`|<span data-ttu-id="e642b-116">Получает значение, указывающее, ссылаются ли указанные строки на один и тот же объект кода.</span><span class="sxs-lookup"><span data-stu-id="e642b-116">Gets a value that indicates whether the specified strings refer to the same code object.</span></span>|  
|`IIdentityAuthority::GenerateDefinitionKey`|<span data-ttu-id="e642b-117">Возвращает указатель на только что созданный строковый ключ для указанного `IDefinitionIdentity`.</span><span class="sxs-lookup"><span data-stu-id="e642b-117">Gets a pointer to a newly created string key for the specified `IDefinitionIdentity`.</span></span>|  
|`IIdentityAuthority::GenerateReferenceKey`|<span data-ttu-id="e642b-118">Возвращает указатель на только что созданный строковый ключ для указанного `IReferenceIdentity`.</span><span class="sxs-lookup"><span data-stu-id="e642b-118">Gets a pointer to a newly created string key for the specified `IReferenceIdentity`.</span></span>|  
|`IIdentityAuthority::HashDefinition`|<span data-ttu-id="e642b-119">Возвращает хэш-значение для указанного `IDefinitionIdentity`.</span><span class="sxs-lookup"><span data-stu-id="e642b-119">Gets a hash value for the specified `IDefinitionIdentity`.</span></span>|  
|`IIdentityAuthority::HashReference`|<span data-ttu-id="e642b-120">Возвращает хэш-значение для указанного `IreferenceIdentity`.</span><span class="sxs-lookup"><span data-stu-id="e642b-120">Gets a hash value for the specified `IreferenceIdentity`.</span></span>|  
|`IIdentityAuthority::ReferenceToText`|<span data-ttu-id="e642b-121">Получает форматированное строковое представление указанного `IReferenceIdentity`.</span><span class="sxs-lookup"><span data-stu-id="e642b-121">Gets a formatted string version of the specified `IReferenceIdentity`.</span></span>|  
|`IIdentityAuthority::ReferenceToTextBuffer`|<span data-ttu-id="e642b-122">Заполняет буфер указанного расширенный символ строковую версию указанного `IReferenceIdentity`.</span><span class="sxs-lookup"><span data-stu-id="e642b-122">Fills the specified wide character buffer with a string version of the specified `IReferenceIdentity`.</span></span>|  
|`IIdentityAuthority::TextToDefinition`|<span data-ttu-id="e642b-123">Получает указатель интерфейса на `IDefinitionIdentity` экземпляр, созданный из указанного форматированную строку.</span><span class="sxs-lookup"><span data-stu-id="e642b-123">Gets an interface pointer to an `IDefinitionIdentity` instance generated from the specified formatted string.</span></span>|  
|`IIdentityAuthority::TextToReference`|<span data-ttu-id="e642b-124">Получает указатель интерфейса на `IReferenceIdentity` экземпляр, созданный из указанного форматированную строку.</span><span class="sxs-lookup"><span data-stu-id="e642b-124">Gets an interface pointer to an `IReferenceIdentity` instance generated from the specified formatted string.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e642b-125">Требования</span><span class="sxs-lookup"><span data-stu-id="e642b-125">Requirements</span></span>  
 <span data-ttu-id="e642b-126">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e642b-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e642b-127">**Заголовок.** Isolation.h</span><span class="sxs-lookup"><span data-stu-id="e642b-127">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="e642b-128">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e642b-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e642b-129">См. также</span><span class="sxs-lookup"><span data-stu-id="e642b-129">See also</span></span>
- [<span data-ttu-id="e642b-130">Интерфейсы Fusion</span><span class="sxs-lookup"><span data-stu-id="e642b-130">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)

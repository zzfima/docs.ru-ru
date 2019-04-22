---
title: Интерфейс IAppIdAuthority
ms.date: 03/30/2017
api_name:
- IAppIdAuthority
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAppIdAuthority
helpviewer_keywords:
- IAppIdAuthority interface [.NET Framework fusion]
ms.assetid: ec354fa1-1efd-41b0-bc43-b90597b6e253
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 724ee01e91f1e9f4e34d2262610152a977ed4f53
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59206659"
---
# <a name="iappidauthority-interface"></a><span data-ttu-id="e52bb-102">Интерфейс IAppIdAuthority</span><span class="sxs-lookup"><span data-stu-id="e52bb-102">IAppIdAuthority Interface</span></span>
<span data-ttu-id="e52bb-103">Предоставляет методы, формирующие и сравнения ключей для идентификаторов и ссылок приложения.</span><span class="sxs-lookup"><span data-stu-id="e52bb-103">Provides methods that generate and compare keys for application identities and references.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e52bb-104">Методы</span><span class="sxs-lookup"><span data-stu-id="e52bb-104">Methods</span></span>  
  
|<span data-ttu-id="e52bb-105">Метод</span><span class="sxs-lookup"><span data-stu-id="e52bb-105">Method</span></span>|<span data-ttu-id="e52bb-106">Описание</span><span class="sxs-lookup"><span data-stu-id="e52bb-106">Description</span></span>|  
|------------|-----------------|  
|`IAppIdAuthority::AreDefinitionsEqual`|<span data-ttu-id="e52bb-107">Получает значение, указывающее, являются ли два заданных [IDefinitionAppId](../../../../docs/framework/unmanaged-api/fusion/idefinitionappid-interface.md) они равны.</span><span class="sxs-lookup"><span data-stu-id="e52bb-107">Gets a value that indicates whether the two specified [IDefinitionAppId](../../../../docs/framework/unmanaged-api/fusion/idefinitionappid-interface.md) instances are equal.</span></span> <span data-ttu-id="e52bb-108">Вы можете передать значение флага IAPPIDAUTHORITY_ARE_DEFINITIONS_EQUAL_FLAG_IGNORE_VERSION игнорировать информацию о соответствующей версии.</span><span class="sxs-lookup"><span data-stu-id="e52bb-108">You can pass the flag value IAPPIDAUTHORITY_ARE_DEFINITIONS_EQUAL_FLAG_IGNORE_VERSION to ignore their respective version information.</span></span>|  
|`IAppIdAuthority::AreReferencesEqual`|<span data-ttu-id="e52bb-109">Получает значение, указывающее, являются ли два заданных [IReferenceAppId](../../../../docs/framework/unmanaged-api/fusion/ireferenceappid-interface.md) они равны.</span><span class="sxs-lookup"><span data-stu-id="e52bb-109">Gets a value that indicates whether the two specified [IReferenceAppId](../../../../docs/framework/unmanaged-api/fusion/ireferenceappid-interface.md) instances are equal.</span></span> <span data-ttu-id="e52bb-110">Вы можете передать значение флага IAPPIDAUTHORITY_ARE_REFERENCES_EQUAL_FLAG_IGNORE_VERSION игнорировать информацию о соответствующей версии.</span><span class="sxs-lookup"><span data-stu-id="e52bb-110">You can pass the flag value IAPPIDAUTHORITY_ARE_REFERENCES_EQUAL_FLAG_IGNORE_VERSION to ignore their respective version information.</span></span>|  
|`IAppIdAuthority::AreTextualDefinitionsEqual`|<span data-ttu-id="e52bb-111">Получает значение, указывающее, равны ли два определения указанную строку.</span><span class="sxs-lookup"><span data-stu-id="e52bb-111">Gets a value that indicates whether the two specified string definitions are equal.</span></span> <span data-ttu-id="e52bb-112">Вы можете передать значение флага IAPPIDAUTHORITY_ARE_DEFINITIONS_EQUAL_FLAG_IGNORE_VERSION игнорировать информацию о соответствующей версии.</span><span class="sxs-lookup"><span data-stu-id="e52bb-112">You can pass the flag value IAPPIDAUTHORITY_ARE_DEFINITIONS_EQUAL_FLAG_IGNORE_VERSION to ignore their respective version information.</span></span>|  
|`IAppIdAuthority::AreTextualReferencesEqual`|<span data-ttu-id="e52bb-113">Получает значение, указывающее, равны ли две ссылки на указанную строку.</span><span class="sxs-lookup"><span data-stu-id="e52bb-113">Gets a value that indicates whether the two specified string references are equal.</span></span> <span data-ttu-id="e52bb-114">Вы можете передать значение флага IAPPIDAUTHORITY_ARE_REFERENCES_EQUAL_FLAG_IGNORE_VERSION игнорировать информацию о соответствующей версии.</span><span class="sxs-lookup"><span data-stu-id="e52bb-114">You can pass the flag value IAPPIDAUTHORITY_ARE_REFERENCES_EQUAL_FLAG_IGNORE_VERSION to ignore their respective version information.</span></span>|  
|`IAppIdAuthority::CreateDefinition`|<span data-ttu-id="e52bb-115">Получает указатель интерфейса на вновь созданным `IDefinitionAppId` экземпляр, представляющий сборку в текущей области.</span><span class="sxs-lookup"><span data-stu-id="e52bb-115">Gets an interface pointer to a newly generated `IDefinitionAppId` instance that represents the assembly in the current scope.</span></span>|  
|`IAppIdAuthority::CreateReference`|<span data-ttu-id="e52bb-116">Получает указатель интерфейса на только что созданный `IReferenceAppId` , представляющий сборку в текущей области.</span><span class="sxs-lookup"><span data-stu-id="e52bb-116">Gets an interface pointer to a newly created `IReferenceAppId` that represents the assembly in the current scope.</span></span>|  
|`IAppIdAuthority::DefinitionToText`|<span data-ttu-id="e52bb-117">Получает строковое представление указанного `IDefinitionAppId`, используя заданные значения флага.</span><span class="sxs-lookup"><span data-stu-id="e52bb-117">Gets a string version of the specified `IDefinitionAppId`, using the specified flag values.</span></span>|  
|`IAppIdAuthority::DoesDefinitionMatchReference`|<span data-ttu-id="e52bb-118">Получает значение, указывающее, является ли указанный `IDefinitionAppId` и `IReferenceAppId` представляют ту же сборку.</span><span class="sxs-lookup"><span data-stu-id="e52bb-118">Gets a value that indicates whether the specified `IDefinitionAppId` and `IReferenceAppId` represent the same assembly.</span></span>|  
|`IAppIdAuthority::DoesTextualDefinitionMatchTextualReference`|<span data-ttu-id="e52bb-119">Получает значение, указывающее, представляют ли заданная строка определения и строка ссылки той же сборки.</span><span class="sxs-lookup"><span data-stu-id="e52bb-119">Gets a value that indicates whether the specified definition string and reference string represent the same assembly.</span></span>|  
|`IAppIdAuthority::GenerateDefinitionKey`|<span data-ttu-id="e52bb-120">Возвращает строковый ключ, представляющий указанный `IDefinitionAppId` экземпляра.</span><span class="sxs-lookup"><span data-stu-id="e52bb-120">Gets a string key that represents the specified `IDefinitionAppId` instance.</span></span>|  
|`IAppIdAuthority::GenerateReferenceKey`|<span data-ttu-id="e52bb-121">Возвращает строковый ключ, представляющий указанный `IReferenceAppId` экземпляра.</span><span class="sxs-lookup"><span data-stu-id="e52bb-121">Gets a string key that represents the specified `IReferenceAppId` instance.</span></span>|  
|`IAppIdAuthority::HashDefinition`|<span data-ttu-id="e52bb-122">Возвращает хэш-ключа для указанного `IDefinitionAppId` экземпляра.</span><span class="sxs-lookup"><span data-stu-id="e52bb-122">Gets a hash key for the specified `IDefinitionAppId` instance.</span></span>|  
|`IAppIdAuthority::HashReference`|<span data-ttu-id="e52bb-123">Возвращает хэш-ключа для указанного `IReferenceAppId` экземпляра.</span><span class="sxs-lookup"><span data-stu-id="e52bb-123">Gets a hash key for the specified `IReferenceAppId` instance.</span></span>|  
|`IAppIdAuthority::ReferenceToText`|<span data-ttu-id="e52bb-124">Получает строковое представление указанного `IReferenceAppId`, используя заданные значения флага.</span><span class="sxs-lookup"><span data-stu-id="e52bb-124">Gets a string version of the specified `IReferenceAppId`, using the specified flag values.</span></span>|  
|`IAppIdAuthority::TextToDefinition`|<span data-ttu-id="e52bb-125">Получает указатель интерфейса на `IDefinitionAppId` экземпляр, который представляет сборки, упоминаемой в указанный ключ строки.</span><span class="sxs-lookup"><span data-stu-id="e52bb-125">Gets an interface pointer to an `IDefinitionAppId` instance that represents the assembly referenced by the specified string key.</span></span>|  
|`IAppIdAuthority::TextToReference`|<span data-ttu-id="e52bb-126">Получает указатель интерфейса на `IReferenceAppId` экземпляр, который представляет сборки, упоминаемой в указанный ключ строки.</span><span class="sxs-lookup"><span data-stu-id="e52bb-126">Gets an interface pointer to an `IReferenceAppId` instance that represents the assembly referenced by the specified string key.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e52bb-127">Требования</span><span class="sxs-lookup"><span data-stu-id="e52bb-127">Requirements</span></span>  
 <span data-ttu-id="e52bb-128">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e52bb-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e52bb-129">**Заголовок.** Isolation.h</span><span class="sxs-lookup"><span data-stu-id="e52bb-129">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="e52bb-130">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e52bb-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e52bb-131">См. также</span><span class="sxs-lookup"><span data-stu-id="e52bb-131">See also</span></span>

- [<span data-ttu-id="e52bb-132">Интерфейсы Fusion</span><span class="sxs-lookup"><span data-stu-id="e52bb-132">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)

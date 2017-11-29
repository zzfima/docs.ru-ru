---
title: "Интерфейс IAppIdAuthority"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IAppIdAuthority
api_location: fusion.dll
api_type: COM
f1_keywords: IAppIdAuthority
helpviewer_keywords: IAppIdAuthority interface [.NET Framework fusion]
ms.assetid: ec354fa1-1efd-41b0-bc43-b90597b6e253
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 07bfd26a43d264babc9854b0fd0da909dd329405
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="iappidauthority-interface"></a><span data-ttu-id="0395d-102">Интерфейс IAppIdAuthority</span><span class="sxs-lookup"><span data-stu-id="0395d-102">IAppIdAuthority Interface</span></span>
<span data-ttu-id="0395d-103">Предоставляет методы, создающие и сравнения ключей для идентификаторов и ссылок приложения.</span><span class="sxs-lookup"><span data-stu-id="0395d-103">Provides methods that generate and compare keys for application identities and references.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0395d-104">Методы</span><span class="sxs-lookup"><span data-stu-id="0395d-104">Methods</span></span>  
  
|<span data-ttu-id="0395d-105">Метод</span><span class="sxs-lookup"><span data-stu-id="0395d-105">Method</span></span>|<span data-ttu-id="0395d-106">Описание</span><span class="sxs-lookup"><span data-stu-id="0395d-106">Description</span></span>|  
|------------|-----------------|  
|`IAppIdAuthority::AreDefinitionsEqual`|<span data-ttu-id="0395d-107">Возвращает значение, указывающее, являются ли два заданных [IDefinitionAppId](../../../../docs/framework/unmanaged-api/fusion/idefinitionappid-interface.md) они равны.</span><span class="sxs-lookup"><span data-stu-id="0395d-107">Gets a value that indicates whether the two specified [IDefinitionAppId](../../../../docs/framework/unmanaged-api/fusion/idefinitionappid-interface.md) instances are equal.</span></span> <span data-ttu-id="0395d-108">Можно передать значение флага IAPPIDAUTHORITY_ARE_DEFINITIONS_EQUAL_FLAG_IGNORE_VERSION, чтобы не учитывать свои сведения о соответствующей версии.</span><span class="sxs-lookup"><span data-stu-id="0395d-108">You can pass the flag value IAPPIDAUTHORITY_ARE_DEFINITIONS_EQUAL_FLAG_IGNORE_VERSION to ignore their respective version information.</span></span>|  
|`IAppIdAuthority::AreReferencesEqual`|<span data-ttu-id="0395d-109">Возвращает значение, указывающее, являются ли два заданных [IReferenceAppId](../../../../docs/framework/unmanaged-api/fusion/ireferenceappid-interface.md) они равны.</span><span class="sxs-lookup"><span data-stu-id="0395d-109">Gets a value that indicates whether the two specified [IReferenceAppId](../../../../docs/framework/unmanaged-api/fusion/ireferenceappid-interface.md) instances are equal.</span></span> <span data-ttu-id="0395d-110">Можно передать значение флага IAPPIDAUTHORITY_ARE_REFERENCES_EQUAL_FLAG_IGNORE_VERSION, чтобы не учитывать свои сведения о соответствующей версии.</span><span class="sxs-lookup"><span data-stu-id="0395d-110">You can pass the flag value IAPPIDAUTHORITY_ARE_REFERENCES_EQUAL_FLAG_IGNORE_VERSION to ignore their respective version information.</span></span>|  
|`IAppIdAuthority::AreTextualDefinitionsEqual`|<span data-ttu-id="0395d-111">Возвращает значение, указывающее, равны ли два указанных определения строки.</span><span class="sxs-lookup"><span data-stu-id="0395d-111">Gets a value that indicates whether the two specified string definitions are equal.</span></span> <span data-ttu-id="0395d-112">Можно передать значение флага IAPPIDAUTHORITY_ARE_DEFINITIONS_EQUAL_FLAG_IGNORE_VERSION, чтобы не учитывать свои сведения о соответствующей версии.</span><span class="sxs-lookup"><span data-stu-id="0395d-112">You can pass the flag value IAPPIDAUTHORITY_ARE_DEFINITIONS_EQUAL_FLAG_IGNORE_VERSION to ignore their respective version information.</span></span>|  
|`IAppIdAuthority::AreTextualReferencesEqual`|<span data-ttu-id="0395d-113">Возвращает значение, указывающее, равны ли две ссылки указанной строки.</span><span class="sxs-lookup"><span data-stu-id="0395d-113">Gets a value that indicates whether the two specified string references are equal.</span></span> <span data-ttu-id="0395d-114">Можно передать значение флага IAPPIDAUTHORITY_ARE_REFERENCES_EQUAL_FLAG_IGNORE_VERSION, чтобы не учитывать свои сведения о соответствующей версии.</span><span class="sxs-lookup"><span data-stu-id="0395d-114">You can pass the flag value IAPPIDAUTHORITY_ARE_REFERENCES_EQUAL_FLAG_IGNORE_VERSION to ignore their respective version information.</span></span>|  
|`IAppIdAuthority::CreateDefinition`|<span data-ttu-id="0395d-115">Получает указатель интерфейса на вновь созданный `IDefinitionAppId` экземпляр, представляющий сборку в текущей области.</span><span class="sxs-lookup"><span data-stu-id="0395d-115">Gets an interface pointer to a newly generated `IDefinitionAppId` instance that represents the assembly in the current scope.</span></span>|  
|`IAppIdAuthority::CreateReference`|<span data-ttu-id="0395d-116">Получает указатель интерфейса на только что созданный `IReferenceAppId` , представляющий сборку в текущей области.</span><span class="sxs-lookup"><span data-stu-id="0395d-116">Gets an interface pointer to a newly created `IReferenceAppId` that represents the assembly in the current scope.</span></span>|  
|`IAppIdAuthority::DefinitionToText`|<span data-ttu-id="0395d-117">Получает версию строки указанного `IDefinitionAppId`, используя заданные значения флага.</span><span class="sxs-lookup"><span data-stu-id="0395d-117">Gets a string version of the specified `IDefinitionAppId`, using the specified flag values.</span></span>|  
|`IAppIdAuthority::DoesDefinitionMatchReference`|<span data-ttu-id="0395d-118">Возвращает значение, указывающее, является ли указанный `IDefinitionAppId` и `IReferenceAppId` представляют той же сборки.</span><span class="sxs-lookup"><span data-stu-id="0395d-118">Gets a value that indicates whether the specified `IDefinitionAppId` and `IReferenceAppId` represent the same assembly.</span></span>|  
|`IAppIdAuthority::DoesTextualDefinitionMatchTextualReference`|<span data-ttu-id="0395d-119">Возвращает значение, указывающее, представляют ли заданная строка определения и строка ссылки той же сборки.</span><span class="sxs-lookup"><span data-stu-id="0395d-119">Gets a value that indicates whether the specified definition string and reference string represent the same assembly.</span></span>|  
|`IAppIdAuthority::GenerateDefinitionKey`|<span data-ttu-id="0395d-120">Возвращает строковый ключ, представляющий указанный `IDefinitionAppId` экземпляра.</span><span class="sxs-lookup"><span data-stu-id="0395d-120">Gets a string key that represents the specified `IDefinitionAppId` instance.</span></span>|  
|`IAppIdAuthority::GenerateReferenceKey`|<span data-ttu-id="0395d-121">Возвращает строковый ключ, представляющий указанный `IReferenceAppId` экземпляра.</span><span class="sxs-lookup"><span data-stu-id="0395d-121">Gets a string key that represents the specified `IReferenceAppId` instance.</span></span>|  
|`IAppIdAuthority::HashDefinition`|<span data-ttu-id="0395d-122">Возвращает хэш-ключ для указанного `IDefinitionAppId` экземпляра.</span><span class="sxs-lookup"><span data-stu-id="0395d-122">Gets a hash key for the specified `IDefinitionAppId` instance.</span></span>|  
|`IAppIdAuthority::HashReference`|<span data-ttu-id="0395d-123">Возвращает хэш-ключ для указанного `IReferenceAppId` экземпляра.</span><span class="sxs-lookup"><span data-stu-id="0395d-123">Gets a hash key for the specified `IReferenceAppId` instance.</span></span>|  
|`IAppIdAuthority::ReferenceToText`|<span data-ttu-id="0395d-124">Получает версию строки указанного `IReferenceAppId`, используя заданные значения флага.</span><span class="sxs-lookup"><span data-stu-id="0395d-124">Gets a string version of the specified `IReferenceAppId`, using the specified flag values.</span></span>|  
|`IAppIdAuthority::TextToDefinition`|<span data-ttu-id="0395d-125">Возвращает указатель интерфейса `IDefinitionAppId` экземпляр, представляющий сборку ссылается указанный ключ строки.</span><span class="sxs-lookup"><span data-stu-id="0395d-125">Gets an interface pointer to an `IDefinitionAppId` instance that represents the assembly referenced by the specified string key.</span></span>|  
|`IAppIdAuthority::TextToReference`|<span data-ttu-id="0395d-126">Возвращает указатель интерфейса `IReferenceAppId` экземпляр, представляющий сборку ссылается указанный ключ строки.</span><span class="sxs-lookup"><span data-stu-id="0395d-126">Gets an interface pointer to an `IReferenceAppId` instance that represents the assembly referenced by the specified string key.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0395d-127">Требования</span><span class="sxs-lookup"><span data-stu-id="0395d-127">Requirements</span></span>  
 <span data-ttu-id="0395d-128">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0395d-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0395d-129">**Заголовок:** Isolation.h</span><span class="sxs-lookup"><span data-stu-id="0395d-129">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="0395d-130">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0395d-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0395d-131">См. также</span><span class="sxs-lookup"><span data-stu-id="0395d-131">See Also</span></span>  
 [<span data-ttu-id="0395d-132">Фьюжн-интерфейсы</span><span class="sxs-lookup"><span data-stu-id="0395d-132">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)

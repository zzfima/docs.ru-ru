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
ms.openlocfilehash: 004e4f70e3385e7a71c356cce38e64d0253dcfa4
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127134"
---
# <a name="iappidauthority-interface"></a><span data-ttu-id="c9917-102">Интерфейс IAppIdAuthority</span><span class="sxs-lookup"><span data-stu-id="c9917-102">IAppIdAuthority Interface</span></span>
<span data-ttu-id="c9917-103">Предоставляет методы, создающие и сравнивающие ключи для удостоверений приложений и ссылок.</span><span class="sxs-lookup"><span data-stu-id="c9917-103">Provides methods that generate and compare keys for application identities and references.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c9917-104">Методы</span><span class="sxs-lookup"><span data-stu-id="c9917-104">Methods</span></span>  
  
|<span data-ttu-id="c9917-105">Метод</span><span class="sxs-lookup"><span data-stu-id="c9917-105">Method</span></span>|<span data-ttu-id="c9917-106">Описание</span><span class="sxs-lookup"><span data-stu-id="c9917-106">Description</span></span>|  
|------------|-----------------|  
|`IAppIdAuthority::AreDefinitionsEqual`|<span data-ttu-id="c9917-107">Возвращает значение, указывающее, равны ли два указанных экземпляра [IDefinitionAppId](idefinitionappid-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="c9917-107">Gets a value that indicates whether the two specified [IDefinitionAppId](idefinitionappid-interface.md) instances are equal.</span></span> <span data-ttu-id="c9917-108">Можно передать значение флага IAPPIDAUTHORITY_ARE_DEFINITIONS_EQUAL_FLAG_IGNORE_VERSION, чтобы игнорировать соответствующие сведения о версии.</span><span class="sxs-lookup"><span data-stu-id="c9917-108">You can pass the flag value IAPPIDAUTHORITY_ARE_DEFINITIONS_EQUAL_FLAG_IGNORE_VERSION to ignore their respective version information.</span></span>|  
|`IAppIdAuthority::AreReferencesEqual`|<span data-ttu-id="c9917-109">Возвращает значение, указывающее, равны ли два указанных экземпляра [иреференцеаппид](ireferenceappid-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="c9917-109">Gets a value that indicates whether the two specified [IReferenceAppId](ireferenceappid-interface.md) instances are equal.</span></span> <span data-ttu-id="c9917-110">Можно передать значение флага IAPPIDAUTHORITY_ARE_REFERENCES_EQUAL_FLAG_IGNORE_VERSION, чтобы игнорировать соответствующие сведения о версии.</span><span class="sxs-lookup"><span data-stu-id="c9917-110">You can pass the flag value IAPPIDAUTHORITY_ARE_REFERENCES_EQUAL_FLAG_IGNORE_VERSION to ignore their respective version information.</span></span>|  
|`IAppIdAuthority::AreTextualDefinitionsEqual`|<span data-ttu-id="c9917-111">Возвращает значение, указывающее, равны ли два указанных строковые определения.</span><span class="sxs-lookup"><span data-stu-id="c9917-111">Gets a value that indicates whether the two specified string definitions are equal.</span></span> <span data-ttu-id="c9917-112">Можно передать значение флага IAPPIDAUTHORITY_ARE_DEFINITIONS_EQUAL_FLAG_IGNORE_VERSION, чтобы игнорировать соответствующие сведения о версии.</span><span class="sxs-lookup"><span data-stu-id="c9917-112">You can pass the flag value IAPPIDAUTHORITY_ARE_DEFINITIONS_EQUAL_FLAG_IGNORE_VERSION to ignore their respective version information.</span></span>|  
|`IAppIdAuthority::AreTextualReferencesEqual`|<span data-ttu-id="c9917-113">Возвращает значение, указывающее, равны ли две указанные строковые ссылки.</span><span class="sxs-lookup"><span data-stu-id="c9917-113">Gets a value that indicates whether the two specified string references are equal.</span></span> <span data-ttu-id="c9917-114">Можно передать значение флага IAPPIDAUTHORITY_ARE_REFERENCES_EQUAL_FLAG_IGNORE_VERSION, чтобы игнорировать соответствующие сведения о версии.</span><span class="sxs-lookup"><span data-stu-id="c9917-114">You can pass the flag value IAPPIDAUTHORITY_ARE_REFERENCES_EQUAL_FLAG_IGNORE_VERSION to ignore their respective version information.</span></span>|  
|`IAppIdAuthority::CreateDefinition`|<span data-ttu-id="c9917-115">Возвращает указатель интерфейса на вновь созданный экземпляр `IDefinitionAppId`, представляющий сборку в текущей области.</span><span class="sxs-lookup"><span data-stu-id="c9917-115">Gets an interface pointer to a newly generated `IDefinitionAppId` instance that represents the assembly in the current scope.</span></span>|  
|`IAppIdAuthority::CreateReference`|<span data-ttu-id="c9917-116">Возвращает указатель интерфейса на вновь созданный `IReferenceAppId`, представляющий сборку в текущей области.</span><span class="sxs-lookup"><span data-stu-id="c9917-116">Gets an interface pointer to a newly created `IReferenceAppId` that represents the assembly in the current scope.</span></span>|  
|`IAppIdAuthority::DefinitionToText`|<span data-ttu-id="c9917-117">Возвращает строковую версию указанного `IDefinitionAppId`, используя указанные значения флага.</span><span class="sxs-lookup"><span data-stu-id="c9917-117">Gets a string version of the specified `IDefinitionAppId`, using the specified flag values.</span></span>|  
|`IAppIdAuthority::DoesDefinitionMatchReference`|<span data-ttu-id="c9917-118">Возвращает значение, указывающее, представляют ли указанные `IDefinitionAppId` и `IReferenceAppId` одну и ту же сборку.</span><span class="sxs-lookup"><span data-stu-id="c9917-118">Gets a value that indicates whether the specified `IDefinitionAppId` and `IReferenceAppId` represent the same assembly.</span></span>|  
|`IAppIdAuthority::DoesTextualDefinitionMatchTextualReference`|<span data-ttu-id="c9917-119">Возвращает значение, указывающее, представляет ли указанная строка определения и ссылочную строку одну и ту же сборку.</span><span class="sxs-lookup"><span data-stu-id="c9917-119">Gets a value that indicates whether the specified definition string and reference string represent the same assembly.</span></span>|  
|`IAppIdAuthority::GenerateDefinitionKey`|<span data-ttu-id="c9917-120">Возвращает строковый ключ, представляющий указанный экземпляр `IDefinitionAppId`.</span><span class="sxs-lookup"><span data-stu-id="c9917-120">Gets a string key that represents the specified `IDefinitionAppId` instance.</span></span>|  
|`IAppIdAuthority::GenerateReferenceKey`|<span data-ttu-id="c9917-121">Возвращает строковый ключ, представляющий указанный экземпляр `IReferenceAppId`.</span><span class="sxs-lookup"><span data-stu-id="c9917-121">Gets a string key that represents the specified `IReferenceAppId` instance.</span></span>|  
|`IAppIdAuthority::HashDefinition`|<span data-ttu-id="c9917-122">Возвращает хэш-ключ для указанного `IDefinitionAppId` экземпляра.</span><span class="sxs-lookup"><span data-stu-id="c9917-122">Gets a hash key for the specified `IDefinitionAppId` instance.</span></span>|  
|`IAppIdAuthority::HashReference`|<span data-ttu-id="c9917-123">Возвращает хэш-ключ для указанного `IReferenceAppId` экземпляра.</span><span class="sxs-lookup"><span data-stu-id="c9917-123">Gets a hash key for the specified `IReferenceAppId` instance.</span></span>|  
|`IAppIdAuthority::ReferenceToText`|<span data-ttu-id="c9917-124">Возвращает строковую версию указанного `IReferenceAppId`, используя указанные значения флага.</span><span class="sxs-lookup"><span data-stu-id="c9917-124">Gets a string version of the specified `IReferenceAppId`, using the specified flag values.</span></span>|  
|`IAppIdAuthority::TextToDefinition`|<span data-ttu-id="c9917-125">Возвращает указатель интерфейса на экземпляр `IDefinitionAppId`, представляющий сборку, на которую ссылается указанный ключ строки.</span><span class="sxs-lookup"><span data-stu-id="c9917-125">Gets an interface pointer to an `IDefinitionAppId` instance that represents the assembly referenced by the specified string key.</span></span>|  
|`IAppIdAuthority::TextToReference`|<span data-ttu-id="c9917-126">Возвращает указатель интерфейса на экземпляр `IReferenceAppId`, представляющий сборку, на которую ссылается указанный ключ строки.</span><span class="sxs-lookup"><span data-stu-id="c9917-126">Gets an interface pointer to an `IReferenceAppId` instance that represents the assembly referenced by the specified string key.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c9917-127">Требования</span><span class="sxs-lookup"><span data-stu-id="c9917-127">Requirements</span></span>  
 <span data-ttu-id="c9917-128">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c9917-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c9917-129">**Заголовок:** Изоляция. h</span><span class="sxs-lookup"><span data-stu-id="c9917-129">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="c9917-130">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c9917-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9917-131">См. также</span><span class="sxs-lookup"><span data-stu-id="c9917-131">See also</span></span>

- [<span data-ttu-id="c9917-132">Интерфейсы Fusion</span><span class="sxs-lookup"><span data-stu-id="c9917-132">Fusion Interfaces</span></span>](fusion-interfaces.md)

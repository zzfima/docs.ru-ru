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
ms.openlocfilehash: 263dc0f9d686440aaa23e359c26db1b4d3d09b1e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61609104"
---
# <a name="iidentityauthority-interface"></a><span data-ttu-id="c6455-102">Интерфейс IIdentityAuthority</span><span class="sxs-lookup"><span data-stu-id="c6455-102">IIdentityAuthority Interface</span></span>

<span data-ttu-id="c6455-103">Управляет идентификационные ключи для объектов кода.</span><span class="sxs-lookup"><span data-stu-id="c6455-103">Manages identity keys for code objects.</span></span>

## <a name="methods"></a><span data-ttu-id="c6455-104">Методы</span><span class="sxs-lookup"><span data-stu-id="c6455-104">Methods</span></span>

|<span data-ttu-id="c6455-105">Метод</span><span class="sxs-lookup"><span data-stu-id="c6455-105">Method</span></span>|<span data-ttu-id="c6455-106">Описание</span><span class="sxs-lookup"><span data-stu-id="c6455-106">Description</span></span>|
|------------|-----------------|
|`IIdentityAuthority::AreDefinitionsEqual`|<span data-ttu-id="c6455-107">Получает значение, указывающее, являются ли два заданных [IDefinitionIdentity](../../../../docs/framework/unmanaged-api/fusion/idefinitionidentity-interface.md) они равны.</span><span class="sxs-lookup"><span data-stu-id="c6455-107">Gets a value that indicates whether the two specified [IDefinitionIdentity](../../../../docs/framework/unmanaged-api/fusion/idefinitionidentity-interface.md) instances are equal.</span></span>|
|`IIdentityAuthority::AreReferencesEqual`|<span data-ttu-id="c6455-108">Получает значение, указывающее, являются ли два заданных [IReferenceIdentity](../../../../docs/framework/unmanaged-api/fusion/ireferenceidentity-interface.md) они равны.</span><span class="sxs-lookup"><span data-stu-id="c6455-108">Gets a value that indicates whether the two specified [IReferenceIdentity](../../../../docs/framework/unmanaged-api/fusion/ireferenceidentity-interface.md) instances are equal.</span></span>|
|`IIdentityAuthority::AreTextualDefinitionsEqual`|<span data-ttu-id="c6455-109">Получает значение, указывающее, равны ли два представления идентификации определение указанной строки.</span><span class="sxs-lookup"><span data-stu-id="c6455-109">Gets a value that indicates whether the two specified string definition identity representations are equal.</span></span>|
|`IIdentityAuthority::AreTextualReferencesEqual`|<span data-ttu-id="c6455-110">Получает значение, указывающее, равны ли два указанные строковые представления идентификации ссылки.</span><span class="sxs-lookup"><span data-stu-id="c6455-110">Gets a value that indicates whether the two specified string reference identity representations are equal.</span></span>|
|`IIdentityAuthority::CreateDefinition`|<span data-ttu-id="c6455-111">Возвращает указатель на новый `IDefinitionIdentity` экземпляр, представляющий объект кода в текущей области.</span><span class="sxs-lookup"><span data-stu-id="c6455-111">Gets a pointer to a new `IDefinitionIdentity` instance that represents the code object in the current scope.</span></span>|
|`IIdentityAuthority::CreateReference`|<span data-ttu-id="c6455-112">Возвращает указатель на новый `IReferenceIdentity` экземпляр, представляющий объект кода в текущей области.</span><span class="sxs-lookup"><span data-stu-id="c6455-112">Gets a pointer to a new `IReferenceIdentity` instance that represents the code object in the current scope.</span></span>|
|`IIdentityAuthority::DefinitionToText`|<span data-ttu-id="c6455-113">Получает форматированное строковое представление указанного `IDefinitionIdentity`.</span><span class="sxs-lookup"><span data-stu-id="c6455-113">Gets a formatted string version of the specified `IDefinitionIdentity`.</span></span>|
|`IIdentityAuthority::DefinitionToTextBuffer`|<span data-ttu-id="c6455-114">Заполняет буфер указанного расширенный символ строковую версию указанного `IDefinitionIdentity`.</span><span class="sxs-lookup"><span data-stu-id="c6455-114">Fills the specified wide character buffer with a string version of the specified `IDefinitionIdentity`.</span></span>|
|`IIdentityAuthority::DoesDefinitionMatchReference`|<span data-ttu-id="c6455-115">Получает значение, указывающее ли указанный `IDefinitionIdentity` и `IReferenceIdentity` ссылаются экземпляра на один и тот же объект кода.</span><span class="sxs-lookup"><span data-stu-id="c6455-115">Gets a value that indicates whether the specified `IDefinitionIdentity` and `IReferenceIdentity` instances refer to the same code object.</span></span>|
|`IIdentityAuthority::DoesTextualDefinitionMatchTextualReference`|<span data-ttu-id="c6455-116">Получает значение, указывающее, ссылаются ли указанные строки на один и тот же объект кода.</span><span class="sxs-lookup"><span data-stu-id="c6455-116">Gets a value that indicates whether the specified strings refer to the same code object.</span></span>|
|`IIdentityAuthority::GenerateDefinitionKey`|<span data-ttu-id="c6455-117">Возвращает указатель на только что созданный строковый ключ для указанного `IDefinitionIdentity`.</span><span class="sxs-lookup"><span data-stu-id="c6455-117">Gets a pointer to a newly created string key for the specified `IDefinitionIdentity`.</span></span>|
|`IIdentityAuthority::GenerateReferenceKey`|<span data-ttu-id="c6455-118">Возвращает указатель на только что созданный строковый ключ для указанного `IReferenceIdentity`.</span><span class="sxs-lookup"><span data-stu-id="c6455-118">Gets a pointer to a newly created string key for the specified `IReferenceIdentity`.</span></span>|
|`IIdentityAuthority::HashDefinition`|<span data-ttu-id="c6455-119">Возвращает хэш-значение для указанного `IDefinitionIdentity`.</span><span class="sxs-lookup"><span data-stu-id="c6455-119">Gets a hash value for the specified `IDefinitionIdentity`.</span></span>|
|`IIdentityAuthority::HashReference`|<span data-ttu-id="c6455-120">Возвращает хэш-значение для указанного `IReferenceIdentity`.</span><span class="sxs-lookup"><span data-stu-id="c6455-120">Gets a hash value for the specified `IReferenceIdentity`.</span></span>|
|`IIdentityAuthority::ReferenceToText`|<span data-ttu-id="c6455-121">Получает форматированное строковое представление указанного `IReferenceIdentity`.</span><span class="sxs-lookup"><span data-stu-id="c6455-121">Gets a formatted string version of the specified `IReferenceIdentity`.</span></span>|
|`IIdentityAuthority::ReferenceToTextBuffer`|<span data-ttu-id="c6455-122">Заполняет буфер указанного расширенный символ строковую версию указанного `IReferenceIdentity`.</span><span class="sxs-lookup"><span data-stu-id="c6455-122">Fills the specified wide character buffer with a string version of the specified `IReferenceIdentity`.</span></span>|
|`IIdentityAuthority::TextToDefinition`|<span data-ttu-id="c6455-123">Получает указатель интерфейса на `IDefinitionIdentity` экземпляр, созданный из указанного форматированную строку.</span><span class="sxs-lookup"><span data-stu-id="c6455-123">Gets an interface pointer to an `IDefinitionIdentity` instance generated from the specified formatted string.</span></span>|
|`IIdentityAuthority::TextToReference`|<span data-ttu-id="c6455-124">Получает указатель интерфейса на `IReferenceIdentity` экземпляр, созданный из указанного форматированную строку.</span><span class="sxs-lookup"><span data-stu-id="c6455-124">Gets an interface pointer to an `IReferenceIdentity` instance generated from the specified formatted string.</span></span>|

## <a name="requirements"></a><span data-ttu-id="c6455-125">Требования</span><span class="sxs-lookup"><span data-stu-id="c6455-125">Requirements</span></span>

<span data-ttu-id="c6455-126">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c6455-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="c6455-127">**Заголовок.** Isolation.h</span><span class="sxs-lookup"><span data-stu-id="c6455-127">**Header:** Isolation.h</span></span>

<span data-ttu-id="c6455-128">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c6455-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="c6455-129">См. также</span><span class="sxs-lookup"><span data-stu-id="c6455-129">See also</span></span>

- [<span data-ttu-id="c6455-130">Интерфейсы Fusion</span><span class="sxs-lookup"><span data-stu-id="c6455-130">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)

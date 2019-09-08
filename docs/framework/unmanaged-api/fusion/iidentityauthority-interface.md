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
ms.openlocfilehash: 7421e0d0e1a1f0e1a5fbe0d0eb7d5a0ab2a48b9a
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796422"
---
# <a name="iidentityauthority-interface"></a><span data-ttu-id="14a95-102">Интерфейс IIdentityAuthority</span><span class="sxs-lookup"><span data-stu-id="14a95-102">IIdentityAuthority Interface</span></span>

<span data-ttu-id="14a95-103">Управляет ключами удостоверений для объектов кода.</span><span class="sxs-lookup"><span data-stu-id="14a95-103">Manages identity keys for code objects.</span></span>

## <a name="methods"></a><span data-ttu-id="14a95-104">Методы</span><span class="sxs-lookup"><span data-stu-id="14a95-104">Methods</span></span>

|<span data-ttu-id="14a95-105">Метод</span><span class="sxs-lookup"><span data-stu-id="14a95-105">Method</span></span>|<span data-ttu-id="14a95-106">Описание</span><span class="sxs-lookup"><span data-stu-id="14a95-106">Description</span></span>|
|------------|-----------------|
|`IIdentityAuthority::AreDefinitionsEqual`|<span data-ttu-id="14a95-107">Возвращает значение, указывающее, равны ли два указанных экземпляра [идефинитионидентити](idefinitionidentity-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="14a95-107">Gets a value that indicates whether the two specified [IDefinitionIdentity](idefinitionidentity-interface.md) instances are equal.</span></span>|
|`IIdentityAuthority::AreReferencesEqual`|<span data-ttu-id="14a95-108">Возвращает значение, указывающее, равны ли два указанных экземпляра [иреференцеидентити](ireferenceidentity-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="14a95-108">Gets a value that indicates whether the two specified [IReferenceIdentity](ireferenceidentity-interface.md) instances are equal.</span></span>|
|`IIdentityAuthority::AreTextualDefinitionsEqual`|<span data-ttu-id="14a95-109">Возвращает значение, указывающее, равны ли два указанных представления идентификаторов определения строки.</span><span class="sxs-lookup"><span data-stu-id="14a95-109">Gets a value that indicates whether the two specified string definition identity representations are equal.</span></span>|
|`IIdentityAuthority::AreTextualReferencesEqual`|<span data-ttu-id="14a95-110">Возвращает значение, указывающее, равны ли два указанных строковых представления идентификаторов ссылки.</span><span class="sxs-lookup"><span data-stu-id="14a95-110">Gets a value that indicates whether the two specified string reference identity representations are equal.</span></span>|
|`IIdentityAuthority::CreateDefinition`|<span data-ttu-id="14a95-111">Возвращает указатель на новый `IDefinitionIdentity` экземпляр, представляющий объект кода в текущей области.</span><span class="sxs-lookup"><span data-stu-id="14a95-111">Gets a pointer to a new `IDefinitionIdentity` instance that represents the code object in the current scope.</span></span>|
|`IIdentityAuthority::CreateReference`|<span data-ttu-id="14a95-112">Возвращает указатель на новый `IReferenceIdentity` экземпляр, представляющий объект кода в текущей области.</span><span class="sxs-lookup"><span data-stu-id="14a95-112">Gets a pointer to a new `IReferenceIdentity` instance that represents the code object in the current scope.</span></span>|
|`IIdentityAuthority::DefinitionToText`|<span data-ttu-id="14a95-113">Возвращает форматированную строковую версию указанного `IDefinitionIdentity`.</span><span class="sxs-lookup"><span data-stu-id="14a95-113">Gets a formatted string version of the specified `IDefinitionIdentity`.</span></span>|
|`IIdentityAuthority::DefinitionToTextBuffer`|<span data-ttu-id="14a95-114">Заполняет указанный буфер расширенных символов строковой версией указанного `IDefinitionIdentity`.</span><span class="sxs-lookup"><span data-stu-id="14a95-114">Fills the specified wide character buffer with a string version of the specified `IDefinitionIdentity`.</span></span>|
|`IIdentityAuthority::DoesDefinitionMatchReference`|<span data-ttu-id="14a95-115">Возвращает значение, указывающее, ссылаются ли указанные `IDefinitionIdentity` экземпляры `IReferenceIdentity` и на один и тот же объект кода.</span><span class="sxs-lookup"><span data-stu-id="14a95-115">Gets a value that indicates whether the specified `IDefinitionIdentity` and `IReferenceIdentity` instances refer to the same code object.</span></span>|
|`IIdentityAuthority::DoesTextualDefinitionMatchTextualReference`|<span data-ttu-id="14a95-116">Возвращает значение, указывающее, ссылаются ли указанные строки на один и тот же объект кода.</span><span class="sxs-lookup"><span data-stu-id="14a95-116">Gets a value that indicates whether the specified strings refer to the same code object.</span></span>|
|`IIdentityAuthority::GenerateDefinitionKey`|<span data-ttu-id="14a95-117">Возвращает указатель на вновь созданный строковый ключ для указанного `IDefinitionIdentity`.</span><span class="sxs-lookup"><span data-stu-id="14a95-117">Gets a pointer to a newly created string key for the specified `IDefinitionIdentity`.</span></span>|
|`IIdentityAuthority::GenerateReferenceKey`|<span data-ttu-id="14a95-118">Возвращает указатель на вновь созданный строковый ключ для указанного `IReferenceIdentity`.</span><span class="sxs-lookup"><span data-stu-id="14a95-118">Gets a pointer to a newly created string key for the specified `IReferenceIdentity`.</span></span>|
|`IIdentityAuthority::HashDefinition`|<span data-ttu-id="14a95-119">Возвращает значение хэша для указанного `IDefinitionIdentity`.</span><span class="sxs-lookup"><span data-stu-id="14a95-119">Gets a hash value for the specified `IDefinitionIdentity`.</span></span>|
|`IIdentityAuthority::HashReference`|<span data-ttu-id="14a95-120">Возвращает значение хэша для указанного `IReferenceIdentity`.</span><span class="sxs-lookup"><span data-stu-id="14a95-120">Gets a hash value for the specified `IReferenceIdentity`.</span></span>|
|`IIdentityAuthority::ReferenceToText`|<span data-ttu-id="14a95-121">Возвращает форматированную строковую версию указанного `IReferenceIdentity`.</span><span class="sxs-lookup"><span data-stu-id="14a95-121">Gets a formatted string version of the specified `IReferenceIdentity`.</span></span>|
|`IIdentityAuthority::ReferenceToTextBuffer`|<span data-ttu-id="14a95-122">Заполняет указанный буфер расширенных символов строковой версией указанного `IReferenceIdentity`.</span><span class="sxs-lookup"><span data-stu-id="14a95-122">Fills the specified wide character buffer with a string version of the specified `IReferenceIdentity`.</span></span>|
|`IIdentityAuthority::TextToDefinition`|<span data-ttu-id="14a95-123">Возвращает указатель интерфейса на экземпляр, `IDefinitionIdentity` созданный из указанной форматируемой строки.</span><span class="sxs-lookup"><span data-stu-id="14a95-123">Gets an interface pointer to an `IDefinitionIdentity` instance generated from the specified formatted string.</span></span>|
|`IIdentityAuthority::TextToReference`|<span data-ttu-id="14a95-124">Возвращает указатель интерфейса на экземпляр, `IReferenceIdentity` созданный из указанной форматируемой строки.</span><span class="sxs-lookup"><span data-stu-id="14a95-124">Gets an interface pointer to an `IReferenceIdentity` instance generated from the specified formatted string.</span></span>|

## <a name="requirements"></a><span data-ttu-id="14a95-125">Требования</span><span class="sxs-lookup"><span data-stu-id="14a95-125">Requirements</span></span>

<span data-ttu-id="14a95-126">**Платформ** См. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="14a95-126">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="14a95-127">**Заголовок.** Изоляция. h</span><span class="sxs-lookup"><span data-stu-id="14a95-127">**Header:** Isolation.h</span></span>

<span data-ttu-id="14a95-128">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="14a95-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="14a95-129">См. также</span><span class="sxs-lookup"><span data-stu-id="14a95-129">See also</span></span>

- [<span data-ttu-id="14a95-130">Интерфейсы Fusion</span><span class="sxs-lookup"><span data-stu-id="14a95-130">Fusion Interfaces</span></span>](fusion-interfaces.md)

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
ms.openlocfilehash: 3e2d2335e37ced9139ea44092f10b19566894681
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127093"
---
# <a name="iidentityauthority-interface"></a><span data-ttu-id="f0469-102">Интерфейс IIdentityAuthority</span><span class="sxs-lookup"><span data-stu-id="f0469-102">IIdentityAuthority Interface</span></span>

<span data-ttu-id="f0469-103">Управляет ключами удостоверений для объектов кода.</span><span class="sxs-lookup"><span data-stu-id="f0469-103">Manages identity keys for code objects.</span></span>

## <a name="methods"></a><span data-ttu-id="f0469-104">Методы</span><span class="sxs-lookup"><span data-stu-id="f0469-104">Methods</span></span>

|<span data-ttu-id="f0469-105">Метод</span><span class="sxs-lookup"><span data-stu-id="f0469-105">Method</span></span>|<span data-ttu-id="f0469-106">Описание</span><span class="sxs-lookup"><span data-stu-id="f0469-106">Description</span></span>|
|------------|-----------------|
|`IIdentityAuthority::AreDefinitionsEqual`|<span data-ttu-id="f0469-107">Возвращает значение, указывающее, равны ли два указанных экземпляра [идефинитионидентити](idefinitionidentity-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="f0469-107">Gets a value that indicates whether the two specified [IDefinitionIdentity](idefinitionidentity-interface.md) instances are equal.</span></span>|
|`IIdentityAuthority::AreReferencesEqual`|<span data-ttu-id="f0469-108">Возвращает значение, указывающее, равны ли два указанных экземпляра [иреференцеидентити](ireferenceidentity-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="f0469-108">Gets a value that indicates whether the two specified [IReferenceIdentity](ireferenceidentity-interface.md) instances are equal.</span></span>|
|`IIdentityAuthority::AreTextualDefinitionsEqual`|<span data-ttu-id="f0469-109">Возвращает значение, указывающее, равны ли два указанных представления идентификаторов определения строки.</span><span class="sxs-lookup"><span data-stu-id="f0469-109">Gets a value that indicates whether the two specified string definition identity representations are equal.</span></span>|
|`IIdentityAuthority::AreTextualReferencesEqual`|<span data-ttu-id="f0469-110">Возвращает значение, указывающее, равны ли два указанных строковых представления идентификаторов ссылки.</span><span class="sxs-lookup"><span data-stu-id="f0469-110">Gets a value that indicates whether the two specified string reference identity representations are equal.</span></span>|
|`IIdentityAuthority::CreateDefinition`|<span data-ttu-id="f0469-111">Возвращает указатель на новый экземпляр `IDefinitionIdentity`, представляющий объект кода в текущей области.</span><span class="sxs-lookup"><span data-stu-id="f0469-111">Gets a pointer to a new `IDefinitionIdentity` instance that represents the code object in the current scope.</span></span>|
|`IIdentityAuthority::CreateReference`|<span data-ttu-id="f0469-112">Возвращает указатель на новый экземпляр `IReferenceIdentity`, представляющий объект кода в текущей области.</span><span class="sxs-lookup"><span data-stu-id="f0469-112">Gets a pointer to a new `IReferenceIdentity` instance that represents the code object in the current scope.</span></span>|
|`IIdentityAuthority::DefinitionToText`|<span data-ttu-id="f0469-113">Возвращает форматированную строковую версию указанного `IDefinitionIdentity`.</span><span class="sxs-lookup"><span data-stu-id="f0469-113">Gets a formatted string version of the specified `IDefinitionIdentity`.</span></span>|
|`IIdentityAuthority::DefinitionToTextBuffer`|<span data-ttu-id="f0469-114">Заполняет указанный буфер расширенных символов строковой версией указанного `IDefinitionIdentity`.</span><span class="sxs-lookup"><span data-stu-id="f0469-114">Fills the specified wide character buffer with a string version of the specified `IDefinitionIdentity`.</span></span>|
|`IIdentityAuthority::DoesDefinitionMatchReference`|<span data-ttu-id="f0469-115">Возвращает значение, указывающее, ссылаются ли указанные `IDefinitionIdentity` и `IReferenceIdentity` экземпляры на один и тот же объект кода.</span><span class="sxs-lookup"><span data-stu-id="f0469-115">Gets a value that indicates whether the specified `IDefinitionIdentity` and `IReferenceIdentity` instances refer to the same code object.</span></span>|
|`IIdentityAuthority::DoesTextualDefinitionMatchTextualReference`|<span data-ttu-id="f0469-116">Возвращает значение, указывающее, ссылаются ли указанные строки на один и тот же объект кода.</span><span class="sxs-lookup"><span data-stu-id="f0469-116">Gets a value that indicates whether the specified strings refer to the same code object.</span></span>|
|`IIdentityAuthority::GenerateDefinitionKey`|<span data-ttu-id="f0469-117">Возвращает указатель на вновь созданный ключ строки для указанного `IDefinitionIdentity`.</span><span class="sxs-lookup"><span data-stu-id="f0469-117">Gets a pointer to a newly created string key for the specified `IDefinitionIdentity`.</span></span>|
|`IIdentityAuthority::GenerateReferenceKey`|<span data-ttu-id="f0469-118">Возвращает указатель на вновь созданный ключ строки для указанного `IReferenceIdentity`.</span><span class="sxs-lookup"><span data-stu-id="f0469-118">Gets a pointer to a newly created string key for the specified `IReferenceIdentity`.</span></span>|
|`IIdentityAuthority::HashDefinition`|<span data-ttu-id="f0469-119">Возвращает значение хэша для указанного `IDefinitionIdentity`.</span><span class="sxs-lookup"><span data-stu-id="f0469-119">Gets a hash value for the specified `IDefinitionIdentity`.</span></span>|
|`IIdentityAuthority::HashReference`|<span data-ttu-id="f0469-120">Возвращает значение хэша для указанного `IReferenceIdentity`.</span><span class="sxs-lookup"><span data-stu-id="f0469-120">Gets a hash value for the specified `IReferenceIdentity`.</span></span>|
|`IIdentityAuthority::ReferenceToText`|<span data-ttu-id="f0469-121">Возвращает форматированную строковую версию указанного `IReferenceIdentity`.</span><span class="sxs-lookup"><span data-stu-id="f0469-121">Gets a formatted string version of the specified `IReferenceIdentity`.</span></span>|
|`IIdentityAuthority::ReferenceToTextBuffer`|<span data-ttu-id="f0469-122">Заполняет указанный буфер расширенных символов строковой версией указанного `IReferenceIdentity`.</span><span class="sxs-lookup"><span data-stu-id="f0469-122">Fills the specified wide character buffer with a string version of the specified `IReferenceIdentity`.</span></span>|
|`IIdentityAuthority::TextToDefinition`|<span data-ttu-id="f0469-123">Возвращает указатель интерфейса на экземпляр `IDefinitionIdentity`, созданный из указанной форматируемой строки.</span><span class="sxs-lookup"><span data-stu-id="f0469-123">Gets an interface pointer to an `IDefinitionIdentity` instance generated from the specified formatted string.</span></span>|
|`IIdentityAuthority::TextToReference`|<span data-ttu-id="f0469-124">Возвращает указатель интерфейса на экземпляр `IReferenceIdentity`, созданный из указанной форматируемой строки.</span><span class="sxs-lookup"><span data-stu-id="f0469-124">Gets an interface pointer to an `IReferenceIdentity` instance generated from the specified formatted string.</span></span>|

## <a name="requirements"></a><span data-ttu-id="f0469-125">Требования</span><span class="sxs-lookup"><span data-stu-id="f0469-125">Requirements</span></span>

<span data-ttu-id="f0469-126">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f0469-126">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="f0469-127">**Заголовок:** Изоляция. h</span><span class="sxs-lookup"><span data-stu-id="f0469-127">**Header:** Isolation.h</span></span>

<span data-ttu-id="f0469-128">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f0469-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="f0469-129">См. также</span><span class="sxs-lookup"><span data-stu-id="f0469-129">See also</span></span>

- [<span data-ttu-id="f0469-130">Интерфейсы Fusion</span><span class="sxs-lookup"><span data-stu-id="f0469-130">Fusion Interfaces</span></span>](fusion-interfaces.md)

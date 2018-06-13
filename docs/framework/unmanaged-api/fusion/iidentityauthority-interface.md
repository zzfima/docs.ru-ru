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
ms.openlocfilehash: 692ac4ef4fe8ea64c6a63dc2f02cc04244a842c3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33432536"
---
# <a name="iidentityauthority-interface"></a><span data-ttu-id="05c76-102">Интерфейс IIdentityAuthority</span><span class="sxs-lookup"><span data-stu-id="05c76-102">IIdentityAuthority Interface</span></span>
<span data-ttu-id="05c76-103">Управляет ключами идентификации для объектов кода.</span><span class="sxs-lookup"><span data-stu-id="05c76-103">Manages identity keys for code objects.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="05c76-104">Методы</span><span class="sxs-lookup"><span data-stu-id="05c76-104">Methods</span></span>  
  
|<span data-ttu-id="05c76-105">Метод</span><span class="sxs-lookup"><span data-stu-id="05c76-105">Method</span></span>|<span data-ttu-id="05c76-106">Описание</span><span class="sxs-lookup"><span data-stu-id="05c76-106">Description</span></span>|  
|------------|-----------------|  
|`IIdentityAuthority::AreDefinitionsEqual`|<span data-ttu-id="05c76-107">Возвращает значение, указывающее, являются ли два заданных [IDefinitionIdentity](../../../../docs/framework/unmanaged-api/fusion/idefinitionidentity-interface.md) они равны.</span><span class="sxs-lookup"><span data-stu-id="05c76-107">Gets a value that indicates whether the two specified [IDefinitionIdentity](../../../../docs/framework/unmanaged-api/fusion/idefinitionidentity-interface.md) instances are equal.</span></span>|  
|`IIdentityAuthority::AreReferencesEqual`|<span data-ttu-id="05c76-108">Возвращает значение, указывающее, являются ли два заданных [IReferenceIdentity](../../../../docs/framework/unmanaged-api/fusion/ireferenceidentity-interface.md) они равны.</span><span class="sxs-lookup"><span data-stu-id="05c76-108">Gets a value that indicates whether the two specified [IReferenceIdentity](../../../../docs/framework/unmanaged-api/fusion/ireferenceidentity-interface.md) instances are equal.</span></span>|  
|`IIdentityAuthority::AreTextualDefinitionsEqual`|<span data-ttu-id="05c76-109">Возвращает значение, указывающее, равны ли два указанные строковые представления идентификации определения.</span><span class="sxs-lookup"><span data-stu-id="05c76-109">Gets a value that indicates whether the two specified string definition identity representations are equal.</span></span>|  
|`IIdentityAuthority::AreTextualReferencesEqual`|<span data-ttu-id="05c76-110">Возвращает значение, указывающее, равны ли два указанные строковые представления идентификации ссылки.</span><span class="sxs-lookup"><span data-stu-id="05c76-110">Gets a value that indicates whether the two specified string reference identity representations are equal.</span></span>|  
|`IIdentityAuthority::CreateDefinition`|<span data-ttu-id="05c76-111">Возвращает указатель на новый `IDefinitionIdentity` экземпляр, представляющий объект кода в текущей области.</span><span class="sxs-lookup"><span data-stu-id="05c76-111">Gets a pointer to a new `IDefinitionIdentity` instance that represents the code object in the current scope.</span></span>|  
|`IIdentityAuthority::CreateReference`|<span data-ttu-id="05c76-112">Возвращает указатель на новый `IReferenceIdentity` экземпляр, представляющий объект кода в текущей области.</span><span class="sxs-lookup"><span data-stu-id="05c76-112">Gets a pointer to a new `IReferenceIdentity` instance that represents the code object in the current scope.</span></span>|  
|`IIdentityAuthority::DefinitionToText`|<span data-ttu-id="05c76-113">Возвращает версию форматируемой строки указанного `IDefinitionIdentity`.</span><span class="sxs-lookup"><span data-stu-id="05c76-113">Gets a formatted string version of the specified `IDefinitionIdentity`.</span></span>|  
|`IIdentityAuthority::DefinitionToTextBuffer`|<span data-ttu-id="05c76-114">Заполняет буфер указанного расширенный символ строковую версию указанного `IDefinitionIdentity`.</span><span class="sxs-lookup"><span data-stu-id="05c76-114">Fills the specified wide character buffer with a string version of the specified `IDefinitionIdentity`.</span></span>|  
|`IIdentityAuthority::DoesDefinitionMatchReference`|<span data-ttu-id="05c76-115">Возвращает значение, указывающее, является ли указанный `IDefinitionIdentity` и `IReferenceIdentity` экземпляры ссылаются на один и тот же объект кода.</span><span class="sxs-lookup"><span data-stu-id="05c76-115">Gets a value that indicates whether the specified `IDefinitionIdentity` and `IReferenceIdentity` instances refer to the same code object.</span></span>|  
|`IIdentityAuthority::DoesTextualDefinitionMatchTextualReference`|<span data-ttu-id="05c76-116">Возвращает значение, указывающее, ссылаются ли указанные строки на один и тот же объект кода.</span><span class="sxs-lookup"><span data-stu-id="05c76-116">Gets a value that indicates whether the specified strings refer to the same code object.</span></span>|  
|`IIdentityAuthority::GenerateDefinitionKey`|<span data-ttu-id="05c76-117">Возвращает указатель на только что созданный строковый ключ для указанного `IDefinitionIdentity`.</span><span class="sxs-lookup"><span data-stu-id="05c76-117">Gets a pointer to a newly created string key for the specified `IDefinitionIdentity`.</span></span>|  
|`IIdentityAuthority::GenerateReferenceKey`|<span data-ttu-id="05c76-118">Возвращает указатель на только что созданный строковый ключ для указанного `IReferenceIdentity`.</span><span class="sxs-lookup"><span data-stu-id="05c76-118">Gets a pointer to a newly created string key for the specified `IReferenceIdentity`.</span></span>|  
|`IIdentityAuthority::HashDefinition`|<span data-ttu-id="05c76-119">Возвращает хэш-значение для указанного `IDefinitionIdentity`.</span><span class="sxs-lookup"><span data-stu-id="05c76-119">Gets a hash value for the specified `IDefinitionIdentity`.</span></span>|  
|`IIdentityAuthority::HashReference`|<span data-ttu-id="05c76-120">Возвращает хэш-значение для указанного `IreferenceIdentity`.</span><span class="sxs-lookup"><span data-stu-id="05c76-120">Gets a hash value for the specified `IreferenceIdentity`.</span></span>|  
|`IIdentityAuthority::ReferenceToText`|<span data-ttu-id="05c76-121">Возвращает версию форматируемой строки указанного `IReferenceIdentity`.</span><span class="sxs-lookup"><span data-stu-id="05c76-121">Gets a formatted string version of the specified `IReferenceIdentity`.</span></span>|  
|`IIdentityAuthority::ReferenceToTextBuffer`|<span data-ttu-id="05c76-122">Заполняет буфер указанного расширенный символ строковую версию указанного `IReferenceIdentity`.</span><span class="sxs-lookup"><span data-stu-id="05c76-122">Fills the specified wide character buffer with a string version of the specified `IReferenceIdentity`.</span></span>|  
|`IIdentityAuthority::TextToDefinition`|<span data-ttu-id="05c76-123">Возвращает указатель интерфейса `IDefinitionIdentity` экземпляра, созданный из указанного форматированную строку.</span><span class="sxs-lookup"><span data-stu-id="05c76-123">Gets an interface pointer to an `IDefinitionIdentity` instance generated from the specified formatted string.</span></span>|  
|`IIdentityAuthority::TextToReference`|<span data-ttu-id="05c76-124">Возвращает указатель интерфейса `IReferenceIdentity` экземпляра, созданный из указанного форматированную строку.</span><span class="sxs-lookup"><span data-stu-id="05c76-124">Gets an interface pointer to an `IReferenceIdentity` instance generated from the specified formatted string.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="05c76-125">Требования</span><span class="sxs-lookup"><span data-stu-id="05c76-125">Requirements</span></span>  
 <span data-ttu-id="05c76-126">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="05c76-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="05c76-127">**Заголовок:** Isolation.h</span><span class="sxs-lookup"><span data-stu-id="05c76-127">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="05c76-128">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="05c76-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05c76-129">См. также</span><span class="sxs-lookup"><span data-stu-id="05c76-129">See Also</span></span>  
 [<span data-ttu-id="05c76-130">Интерфейсы Fusion</span><span class="sxs-lookup"><span data-stu-id="05c76-130">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)

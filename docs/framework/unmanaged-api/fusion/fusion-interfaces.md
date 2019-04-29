---
title: Fusion-интерфейсы
ms.date: 03/30/2017
helpviewer_keywords:
- interfaces [.NET Framework fusion]
- fusion interfaces [.NET Framework]
- unmanaged interfaces [.NET Framework], fusion
ms.assetid: e2cf98b7-40c1-4f74-86c7-8a76dd9da677
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ec2fd3b309820f2bfb7f6091cc3db720db497408
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61697671"
---
# <a name="fusion-interfaces"></a><span data-ttu-id="7624d-102">Fusion-интерфейсы</span><span class="sxs-lookup"><span data-stu-id="7624d-102">Fusion Interfaces</span></span>
<span data-ttu-id="7624d-103">В этом разделе описываются неуправляемые интерфейсы, используемые API Fusion для доступа к свойствам ресурсов приложения и найти правильные версии этих ресурсов для приложения.</span><span class="sxs-lookup"><span data-stu-id="7624d-103">This section describes the unmanaged interfaces that the fusion API uses to access the properties of an application's resources and to locate the correct versions of those resources for the application.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7624d-104">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="7624d-104">In This Section</span></span>  
 [<span data-ttu-id="7624d-105">Интерфейс IAppIdAuthority</span><span class="sxs-lookup"><span data-stu-id="7624d-105">IAppIdAuthority Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iappidauthority-interface.md)  
 <span data-ttu-id="7624d-106">Предоставляет методы, формирующие и сравнения ключей для идентификаторов и ссылок приложения.</span><span class="sxs-lookup"><span data-stu-id="7624d-106">Provides methods that generate and compare keys for application identities and references.</span></span>  
  
 [<span data-ttu-id="7624d-107">Интерфейс IAssemblyCache</span><span class="sxs-lookup"><span data-stu-id="7624d-107">IAssemblyCache Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-interface.md)  
 <span data-ttu-id="7624d-108">Предоставляет представление в глобальный кэш сборок.</span><span class="sxs-lookup"><span data-stu-id="7624d-108">Provides a representation of the global assembly cache.</span></span>  
  
 [<span data-ttu-id="7624d-109">Интерфейс IAssemblyCacheItem</span><span class="sxs-lookup"><span data-stu-id="7624d-109">IAssemblyCacheItem Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md)  
 <span data-ttu-id="7624d-110">Представляет одну сборку в глобальный кэш сборок.</span><span class="sxs-lookup"><span data-stu-id="7624d-110">Represents a single assembly in the global assembly cache.</span></span>  
  
 [<span data-ttu-id="7624d-111">Интерфейс IAssemblyEnum</span><span class="sxs-lookup"><span data-stu-id="7624d-111">IAssemblyEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyenum-interface.md)  
 <span data-ttu-id="7624d-112">Представляет перечислитель для массива `IAssemblyName` объектов.</span><span class="sxs-lookup"><span data-stu-id="7624d-112">Represents an enumerator for an array of `IAssemblyName` objects.</span></span>  
  
 [<span data-ttu-id="7624d-113">Интерфейс IAssemblyName</span><span class="sxs-lookup"><span data-stu-id="7624d-113">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)  
 <span data-ttu-id="7624d-114">Предоставляет методы для описания и работа с уникальное удостоверение сборки.</span><span class="sxs-lookup"><span data-stu-id="7624d-114">Provides methods for describing and working with an assembly's unique identity.</span></span>  
  
 [<span data-ttu-id="7624d-115">Интерфейс IDefinitionAppId</span><span class="sxs-lookup"><span data-stu-id="7624d-115">IDefinitionAppId Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/idefinitionappid-interface.md)  
 <span data-ttu-id="7624d-116">Представляет уникальный идентификатор для кода, который определяет приложение в текущей области.</span><span class="sxs-lookup"><span data-stu-id="7624d-116">Represents a unique identifier for the code that defines the application in the current scope.</span></span>  
  
 [<span data-ttu-id="7624d-117">Интерфейс IDefinitionIdentity</span><span class="sxs-lookup"><span data-stu-id="7624d-117">IDefinitionIdentity Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/idefinitionidentity-interface.md)  
 <span data-ttu-id="7624d-118">Представляет уникальную подпись кода, определяющего приложение в текущей области.</span><span class="sxs-lookup"><span data-stu-id="7624d-118">Represents the unique signature of the code that defines the application in the current scope.</span></span>  
  
 [<span data-ttu-id="7624d-119">Интерфейс IEnumDefinitionIdentity</span><span class="sxs-lookup"><span data-stu-id="7624d-119">IEnumDefinitionIdentity Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/ienumdefinitionidentity-interface.md)  
 <span data-ttu-id="7624d-120">Служит в качестве перечислителя для коллекции `IDefinitionIdentity` объектов.</span><span class="sxs-lookup"><span data-stu-id="7624d-120">Serves as the enumerator for a collection of `IDefinitionIdentity` objects.</span></span>  
  
 [<span data-ttu-id="7624d-121">Интерфейс IEnumIDENTITY_ATTRIBUTE</span><span class="sxs-lookup"><span data-stu-id="7624d-121">IEnumIDENTITY_ATTRIBUTE Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/ienumidentity-attribute-interface.md)  
 <span data-ttu-id="7624d-122">Служит в качестве перечислителя для атрибутов объекта кода в текущей области.</span><span class="sxs-lookup"><span data-stu-id="7624d-122">Serves as an enumerator for the attributes of the code object in the current scope.</span></span>  
  
 [<span data-ttu-id="7624d-123">Интерфейс IEnumReferenceIdentity</span><span class="sxs-lookup"><span data-stu-id="7624d-123">IEnumReferenceIdentity Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/ienumreferenceidentity-interface.md)  
 <span data-ttu-id="7624d-124">Служит в качестве перечислителя для коллекции `IReferenceIdentity` объектов.</span><span class="sxs-lookup"><span data-stu-id="7624d-124">Serves as an enumerator for a collection of `IReferenceIdentity` objects.</span></span>  
  
 [<span data-ttu-id="7624d-125">Интерфейс IIdentityAuthority</span><span class="sxs-lookup"><span data-stu-id="7624d-125">IIdentityAuthority Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iidentityauthority-interface.md)  
 <span data-ttu-id="7624d-126">Управляет идентификационные ключи для объектов кода.</span><span class="sxs-lookup"><span data-stu-id="7624d-126">Manages identity keys for code objects.</span></span>  
  
 [<span data-ttu-id="7624d-127">Интерфейс IInstallReferenceEnum</span><span class="sxs-lookup"><span data-stu-id="7624d-127">IInstallReferenceEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceenum-interface.md)  
 <span data-ttu-id="7624d-128">Представляет перечислитель для упоминаемой сборок, установленных в глобальном кэше сборок.</span><span class="sxs-lookup"><span data-stu-id="7624d-128">Represents an enumerator for the referenced assemblies installed in the global assembly cache.</span></span>  
  
 [<span data-ttu-id="7624d-129">Интерфейс IInstallReferenceItem</span><span class="sxs-lookup"><span data-stu-id="7624d-129">IInstallReferenceItem Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceitem-interface.md)  
 <span data-ttu-id="7624d-130">Представляет элемент, установленный в глобальном кэше сборок.</span><span class="sxs-lookup"><span data-stu-id="7624d-130">Represents an item installed in the global assembly cache.</span></span>  
  
 [<span data-ttu-id="7624d-131">Интерфейс IReferenceAppId</span><span class="sxs-lookup"><span data-stu-id="7624d-131">IReferenceAppId Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/ireferenceappid-interface.md)  
 <span data-ttu-id="7624d-132">Представляет ссылку на уникальный идентификатор для приложения в текущей области.</span><span class="sxs-lookup"><span data-stu-id="7624d-132">Represents a reference to the unique identifier for the application in the current scope.</span></span>  
  
 [<span data-ttu-id="7624d-133">Интерфейс IReferenceIdentity</span><span class="sxs-lookup"><span data-stu-id="7624d-133">IReferenceIdentity Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/ireferenceidentity-interface.md)  
 <span data-ttu-id="7624d-134">Представляет ссылку на уникальную подпись объекта кода.</span><span class="sxs-lookup"><span data-stu-id="7624d-134">Represents a reference to the unique signature of a code object.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="7624d-135">Ссылка</span><span class="sxs-lookup"><span data-stu-id="7624d-135">Reference</span></span>  
 <xref:System.Reflection>  
  
 <xref:System.Reflection.Emit>  
  
## <a name="related-sections"></a><span data-ttu-id="7624d-136">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="7624d-136">Related Sections</span></span>  
 [<span data-ttu-id="7624d-137">Глобальные статические функции Fusion</span><span class="sxs-lookup"><span data-stu-id="7624d-137">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)  
  
 [<span data-ttu-id="7624d-138">Перечисления Fusion</span><span class="sxs-lookup"><span data-stu-id="7624d-138">Fusion Enumerations</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-enumerations.md)  
  
 [<span data-ttu-id="7624d-139">Структуры Fusion</span><span class="sxs-lookup"><span data-stu-id="7624d-139">Fusion Structures</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-structures.md)

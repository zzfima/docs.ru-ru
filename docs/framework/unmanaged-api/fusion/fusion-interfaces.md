---
title: Fusion-интерфейсы
ms.date: 03/30/2017
helpviewer_keywords:
- interfaces [.NET Framework fusion]
- fusion interfaces [.NET Framework]
- unmanaged interfaces [.NET Framework], fusion
ms.assetid: e2cf98b7-40c1-4f74-86c7-8a76dd9da677
ms.openlocfilehash: 81c66825e69d9526abddfe06133426a2274ad08f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73108196"
---
# <a name="fusion-interfaces"></a><span data-ttu-id="ecc33-102">Fusion-интерфейсы</span><span class="sxs-lookup"><span data-stu-id="ecc33-102">Fusion Interfaces</span></span>
<span data-ttu-id="ecc33-103">В этом разделе описываются неуправляемые интерфейсы, используемые API Fusion для доступа к свойствам ресурсов приложения и для размещения правильных версий этих ресурсов для приложения.</span><span class="sxs-lookup"><span data-stu-id="ecc33-103">This section describes the unmanaged interfaces that the fusion API uses to access the properties of an application's resources and to locate the correct versions of those resources for the application.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ecc33-104">Содержание</span><span class="sxs-lookup"><span data-stu-id="ecc33-104">In This Section</span></span>  
 [<span data-ttu-id="ecc33-105">Интерфейс IAppIdAuthority</span><span class="sxs-lookup"><span data-stu-id="ecc33-105">IAppIdAuthority Interface</span></span>](iappidauthority-interface.md)  
 <span data-ttu-id="ecc33-106">Предоставляет методы, создающие и сравнивающие ключи для удостоверений приложений и ссылок.</span><span class="sxs-lookup"><span data-stu-id="ecc33-106">Provides methods that generate and compare keys for application identities and references.</span></span>  
  
 [<span data-ttu-id="ecc33-107">Интерфейс IAssemblyCache</span><span class="sxs-lookup"><span data-stu-id="ecc33-107">IAssemblyCache Interface</span></span>](iassemblycache-interface.md)  
 <span data-ttu-id="ecc33-108">Предоставляет представление глобального кэша сборок.</span><span class="sxs-lookup"><span data-stu-id="ecc33-108">Provides a representation of the global assembly cache.</span></span>  
  
 [<span data-ttu-id="ecc33-109">Интерфейс IAssemblyCacheItem</span><span class="sxs-lookup"><span data-stu-id="ecc33-109">IAssemblyCacheItem Interface</span></span>](iassemblycacheitem-interface.md)  
 <span data-ttu-id="ecc33-110">Представляет отдельную сборку в глобальном кэше сборок.</span><span class="sxs-lookup"><span data-stu-id="ecc33-110">Represents a single assembly in the global assembly cache.</span></span>  
  
 [<span data-ttu-id="ecc33-111">Интерфейс IAssemblyEnum</span><span class="sxs-lookup"><span data-stu-id="ecc33-111">IAssemblyEnum Interface</span></span>](iassemblyenum-interface.md)  
 <span data-ttu-id="ecc33-112">Представляет перечислитель для массива объектов `IAssemblyName`.</span><span class="sxs-lookup"><span data-stu-id="ecc33-112">Represents an enumerator for an array of `IAssemblyName` objects.</span></span>  
  
 [<span data-ttu-id="ecc33-113">Интерфейс IAssemblyName</span><span class="sxs-lookup"><span data-stu-id="ecc33-113">IAssemblyName Interface</span></span>](iassemblyname-interface.md)  
 <span data-ttu-id="ecc33-114">Предоставляет методы для описания и работы с уникальным удостоверением сборки.</span><span class="sxs-lookup"><span data-stu-id="ecc33-114">Provides methods for describing and working with an assembly's unique identity.</span></span>  
  
 [<span data-ttu-id="ecc33-115">Интерфейс IDefinitionAppId</span><span class="sxs-lookup"><span data-stu-id="ecc33-115">IDefinitionAppId Interface</span></span>](idefinitionappid-interface.md)  
 <span data-ttu-id="ecc33-116">Представляет уникальный идентификатор для кода, определяющего приложение в текущей области.</span><span class="sxs-lookup"><span data-stu-id="ecc33-116">Represents a unique identifier for the code that defines the application in the current scope.</span></span>  
  
 [<span data-ttu-id="ecc33-117">Интерфейс IDefinitionIdentity</span><span class="sxs-lookup"><span data-stu-id="ecc33-117">IDefinitionIdentity Interface</span></span>](idefinitionidentity-interface.md)  
 <span data-ttu-id="ecc33-118">Представляет уникальную сигнатуру кода, определяющего приложение в текущей области.</span><span class="sxs-lookup"><span data-stu-id="ecc33-118">Represents the unique signature of the code that defines the application in the current scope.</span></span>  
  
 [<span data-ttu-id="ecc33-119">Интерфейс IEnumDefinitionIdentity</span><span class="sxs-lookup"><span data-stu-id="ecc33-119">IEnumDefinitionIdentity Interface</span></span>](ienumdefinitionidentity-interface.md)  
 <span data-ttu-id="ecc33-120">Служит в качестве перечислителя для коллекции объектов `IDefinitionIdentity`.</span><span class="sxs-lookup"><span data-stu-id="ecc33-120">Serves as the enumerator for a collection of `IDefinitionIdentity` objects.</span></span>  
  
 [<span data-ttu-id="ecc33-121">Интерфейс IEnumIDENTITY_ATTRIBUTE</span><span class="sxs-lookup"><span data-stu-id="ecc33-121">IEnumIDENTITY_ATTRIBUTE Interface</span></span>](ienumidentity-attribute-interface.md)  
 <span data-ttu-id="ecc33-122">Служит в качестве перечислителя для атрибутов объекта Code в текущей области.</span><span class="sxs-lookup"><span data-stu-id="ecc33-122">Serves as an enumerator for the attributes of the code object in the current scope.</span></span>  
  
 [<span data-ttu-id="ecc33-123">Интерфейс IEnumReferenceIdentity</span><span class="sxs-lookup"><span data-stu-id="ecc33-123">IEnumReferenceIdentity Interface</span></span>](ienumreferenceidentity-interface.md)  
 <span data-ttu-id="ecc33-124">Служит перечислителем для коллекции объектов `IReferenceIdentity`.</span><span class="sxs-lookup"><span data-stu-id="ecc33-124">Serves as an enumerator for a collection of `IReferenceIdentity` objects.</span></span>  
  
 [<span data-ttu-id="ecc33-125">Интерфейс IIdentityAuthority</span><span class="sxs-lookup"><span data-stu-id="ecc33-125">IIdentityAuthority Interface</span></span>](iidentityauthority-interface.md)  
 <span data-ttu-id="ecc33-126">Управляет ключами удостоверений для объектов кода.</span><span class="sxs-lookup"><span data-stu-id="ecc33-126">Manages identity keys for code objects.</span></span>  
  
 [<span data-ttu-id="ecc33-127">Интерфейс IInstallReferenceEnum</span><span class="sxs-lookup"><span data-stu-id="ecc33-127">IInstallReferenceEnum Interface</span></span>](iinstallreferenceenum-interface.md)  
 <span data-ttu-id="ecc33-128">Представляет перечислитель для сборок, на которые имеются ссылки, установленных в глобальном кэше сборок.</span><span class="sxs-lookup"><span data-stu-id="ecc33-128">Represents an enumerator for the referenced assemblies installed in the global assembly cache.</span></span>  
  
 [<span data-ttu-id="ecc33-129">Интерфейс IInstallReferenceItem</span><span class="sxs-lookup"><span data-stu-id="ecc33-129">IInstallReferenceItem Interface</span></span>](iinstallreferenceitem-interface.md)  
 <span data-ttu-id="ecc33-130">Представляет элемент, установленный в глобальном кэше сборок.</span><span class="sxs-lookup"><span data-stu-id="ecc33-130">Represents an item installed in the global assembly cache.</span></span>  
  
 [<span data-ttu-id="ecc33-131">Интерфейс IReferenceAppId</span><span class="sxs-lookup"><span data-stu-id="ecc33-131">IReferenceAppId Interface</span></span>](ireferenceappid-interface.md)  
 <span data-ttu-id="ecc33-132">Представляет ссылку на уникальный идентификатор приложения в текущей области.</span><span class="sxs-lookup"><span data-stu-id="ecc33-132">Represents a reference to the unique identifier for the application in the current scope.</span></span>  
  
 [<span data-ttu-id="ecc33-133">Интерфейс IReferenceIdentity</span><span class="sxs-lookup"><span data-stu-id="ecc33-133">IReferenceIdentity Interface</span></span>](ireferenceidentity-interface.md)  
 <span data-ttu-id="ecc33-134">Представляет ссылку на уникальную сигнатуру объекта кода.</span><span class="sxs-lookup"><span data-stu-id="ecc33-134">Represents a reference to the unique signature of a code object.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="ecc33-135">Справочники</span><span class="sxs-lookup"><span data-stu-id="ecc33-135">Reference</span></span>  
 <xref:System.Reflection>  
  
 <xref:System.Reflection.Emit>  
  
## <a name="related-sections"></a><span data-ttu-id="ecc33-136">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="ecc33-136">Related Sections</span></span>  
 [<span data-ttu-id="ecc33-137">Глобальные статические функции Fusion</span><span class="sxs-lookup"><span data-stu-id="ecc33-137">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)  
  
 [<span data-ttu-id="ecc33-138">Перечисления Fusion</span><span class="sxs-lookup"><span data-stu-id="ecc33-138">Fusion Enumerations</span></span>](fusion-enumerations.md)  
  
 [<span data-ttu-id="ecc33-139">Структуры Fusion</span><span class="sxs-lookup"><span data-stu-id="ecc33-139">Fusion Structures</span></span>](fusion-structures.md)

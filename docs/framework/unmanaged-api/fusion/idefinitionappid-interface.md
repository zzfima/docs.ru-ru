---
title: Интерфейс IDefinitionAppId
ms.date: 03/30/2017
api_name:
- IDefinitionAppId
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IDefinitionAppId
helpviewer_keywords:
- IDefinitionAppId interface [.NET Framework fusion]
ms.assetid: e72f2550-bdec-4a20-a2f4-2e14847266c1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 929909a7f2c4fa1799c8fed94787b8f853c7eac2
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796519"
---
# <a name="idefinitionappid-interface"></a><span data-ttu-id="a5d38-102">Интерфейс IDefinitionAppId</span><span class="sxs-lookup"><span data-stu-id="a5d38-102">IDefinitionAppId Interface</span></span>
<span data-ttu-id="a5d38-103">Представляет уникальный идентификатор для кода, определяющего приложение в текущей области.</span><span class="sxs-lookup"><span data-stu-id="a5d38-103">Represents a unique identifier for the code that defines the application in the current scope.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a5d38-104">Методы</span><span class="sxs-lookup"><span data-stu-id="a5d38-104">Methods</span></span>  
  
|<span data-ttu-id="a5d38-105">Метод</span><span class="sxs-lookup"><span data-stu-id="a5d38-105">Method</span></span>|<span data-ttu-id="a5d38-106">Описание</span><span class="sxs-lookup"><span data-stu-id="a5d38-106">Description</span></span>|  
|------------|-----------------|  
|`IDefinitionAppId::get_Codebase`|<span data-ttu-id="a5d38-107">Возвращает отформатированную строку, которая представляет код в `IDefinitionAppId` этом объекте.</span><span class="sxs-lookup"><span data-stu-id="a5d38-107">Gets a formatted string that represents the code in this `IDefinitionAppId` object.</span></span>|  
|`IDefinitionAppId::put_Codebase`|<span data-ttu-id="a5d38-108">Задает код этого `IDefinitionAppId` объекта в указанном форматированном строковом значении.</span><span class="sxs-lookup"><span data-stu-id="a5d38-108">Sets the code of this `IDefinitionAppId` object to the specified formatted string value.</span></span>|  
|`IDefinitionAppId::EnumAppPath`|<span data-ttu-id="a5d38-109">Возвращает указатель интерфейса на объект [иенумдефинитионидентити](ienumdefinitionidentity-interface.md) , содержащий сборки в текущем пути приложения.</span><span class="sxs-lookup"><span data-stu-id="a5d38-109">Gets an interface pointer to an [IEnumDefinitionIdentity](ienumdefinitionidentity-interface.md) object that contains the assemblies in the current application path.</span></span>|  
|`IDefinitionAppId::SetAppPath`|<span data-ttu-id="a5d38-110">Задает путь приложения для сборки в текущей области к значению, на которое ссылается указанный объект [идефинитионидентити](idefinitionidentity-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="a5d38-110">Sets the application path for the assembly in the current scope to the value referenced by the specified [IDefinitionIdentity](idefinitionidentity-interface.md) object.</span></span>|  
|`IDefinitionAppId::get_SubscriptionId`|<span data-ttu-id="a5d38-111">Возвращает указатель на строковое представление идентификатора маркера для подписки на этот `IDefinitionAppId` объект.</span><span class="sxs-lookup"><span data-stu-id="a5d38-111">Gets a pointer to a string representation of the token identifier for a subscription to this `IDefinitionAppId` object.</span></span>|  
|`IDefinitionAppId::put_SubscriptionId`|<span data-ttu-id="a5d38-112">Устанавливает идентификатор маркера для подписки на этот `IDefinitionAppId` объект в указанном строковом значении.</span><span class="sxs-lookup"><span data-stu-id="a5d38-112">Sets the token identifier for a subscription to this `IDefinitionAppId` object to the specified string value.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a5d38-113">Требования</span><span class="sxs-lookup"><span data-stu-id="a5d38-113">Requirements</span></span>  
 <span data-ttu-id="a5d38-114">**Платформ** См. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a5d38-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a5d38-115">**Заголовок.** Изоляция. h</span><span class="sxs-lookup"><span data-stu-id="a5d38-115">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="a5d38-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a5d38-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5d38-117">См. также</span><span class="sxs-lookup"><span data-stu-id="a5d38-117">See also</span></span>

- [<span data-ttu-id="a5d38-118">Интерфейсы Fusion</span><span class="sxs-lookup"><span data-stu-id="a5d38-118">Fusion Interfaces</span></span>](fusion-interfaces.md)

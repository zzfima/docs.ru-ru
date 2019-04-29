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
ms.openlocfilehash: 5bd705ef549de3a8018efe731ef8735ef7b6b915
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61697242"
---
# <a name="idefinitionappid-interface"></a><span data-ttu-id="0bb0c-102">Интерфейс IDefinitionAppId</span><span class="sxs-lookup"><span data-stu-id="0bb0c-102">IDefinitionAppId Interface</span></span>
<span data-ttu-id="0bb0c-103">Представляет уникальный идентификатор для кода, который определяет приложение в текущей области.</span><span class="sxs-lookup"><span data-stu-id="0bb0c-103">Represents a unique identifier for the code that defines the application in the current scope.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0bb0c-104">Методы</span><span class="sxs-lookup"><span data-stu-id="0bb0c-104">Methods</span></span>  
  
|<span data-ttu-id="0bb0c-105">Метод</span><span class="sxs-lookup"><span data-stu-id="0bb0c-105">Method</span></span>|<span data-ttu-id="0bb0c-106">Описание</span><span class="sxs-lookup"><span data-stu-id="0bb0c-106">Description</span></span>|  
|------------|-----------------|  
|`IDefinitionAppId::get_Codebase`|<span data-ttu-id="0bb0c-107">Возвращает форматированную строку, представляющее код в этом `IDefinitionAppId` объекта.</span><span class="sxs-lookup"><span data-stu-id="0bb0c-107">Gets a formatted string that represents the code in this `IDefinitionAppId` object.</span></span>|  
|`IDefinitionAppId::put_Codebase`|<span data-ttu-id="0bb0c-108">Задает код это `IDefinitionAppId` строковое значение в объект в указанном формате.</span><span class="sxs-lookup"><span data-stu-id="0bb0c-108">Sets the code of this `IDefinitionAppId` object to the specified formatted string value.</span></span>|  
|`IDefinitionAppId::EnumAppPath`|<span data-ttu-id="0bb0c-109">Получает указатель интерфейса на [IEnumDefinitionIdentity](../../../../docs/framework/unmanaged-api/fusion/ienumdefinitionidentity-interface.md) , содержащий сборки в путь текущего приложения.</span><span class="sxs-lookup"><span data-stu-id="0bb0c-109">Gets an interface pointer to an [IEnumDefinitionIdentity](../../../../docs/framework/unmanaged-api/fusion/ienumdefinitionidentity-interface.md) object that contains the assemblies in the current application path.</span></span>|  
|`IDefinitionAppId::SetAppPath`|<span data-ttu-id="0bb0c-110">Задает путь к приложению для сборки в текущей области к значению, который ссылается заданный [IDefinitionIdentity](../../../../docs/framework/unmanaged-api/fusion/idefinitionidentity-interface.md) объекта.</span><span class="sxs-lookup"><span data-stu-id="0bb0c-110">Sets the application path for the assembly in the current scope to the value referenced by the specified [IDefinitionIdentity](../../../../docs/framework/unmanaged-api/fusion/idefinitionidentity-interface.md) object.</span></span>|  
|`IDefinitionAppId::get_SubscriptionId`|<span data-ttu-id="0bb0c-111">Получает указатель на строковое представление идентификатора маркера для подписки на это `IDefinitionAppId` объекта.</span><span class="sxs-lookup"><span data-stu-id="0bb0c-111">Gets a pointer to a string representation of the token identifier for a subscription to this `IDefinitionAppId` object.</span></span>|  
|`IDefinitionAppId::put_SubscriptionId`|<span data-ttu-id="0bb0c-112">Задает идентификатор токена для подписки на это `IDefinitionAppId` объекта указанному строковому значению.</span><span class="sxs-lookup"><span data-stu-id="0bb0c-112">Sets the token identifier for a subscription to this `IDefinitionAppId` object to the specified string value.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0bb0c-113">Требования</span><span class="sxs-lookup"><span data-stu-id="0bb0c-113">Requirements</span></span>  
 <span data-ttu-id="0bb0c-114">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0bb0c-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0bb0c-115">**Заголовок.** Isolation.h</span><span class="sxs-lookup"><span data-stu-id="0bb0c-115">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="0bb0c-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0bb0c-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0bb0c-117">См. также</span><span class="sxs-lookup"><span data-stu-id="0bb0c-117">See also</span></span>

- [<span data-ttu-id="0bb0c-118">Интерфейсы Fusion</span><span class="sxs-lookup"><span data-stu-id="0bb0c-118">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)

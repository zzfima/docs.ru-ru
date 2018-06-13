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
ms.openlocfilehash: 2735355097a1f3f581b3a4bc74f08d8f2ebf3bd8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33430384"
---
# <a name="idefinitionappid-interface"></a><span data-ttu-id="8c35b-102">Интерфейс IDefinitionAppId</span><span class="sxs-lookup"><span data-stu-id="8c35b-102">IDefinitionAppId Interface</span></span>
<span data-ttu-id="8c35b-103">Представляет уникальный идентификатор для кода, определяющего приложение в текущей области.</span><span class="sxs-lookup"><span data-stu-id="8c35b-103">Represents a unique identifier for the code that defines the application in the current scope.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8c35b-104">Методы</span><span class="sxs-lookup"><span data-stu-id="8c35b-104">Methods</span></span>  
  
|<span data-ttu-id="8c35b-105">Метод</span><span class="sxs-lookup"><span data-stu-id="8c35b-105">Method</span></span>|<span data-ttu-id="8c35b-106">Описание</span><span class="sxs-lookup"><span data-stu-id="8c35b-106">Description</span></span>|  
|------------|-----------------|  
|`IDefinitionAppId::get_Codebase`|<span data-ttu-id="8c35b-107">Возвращает строку форматирования, которая представляет код, в этом `IDefinitionAppId` объекта.</span><span class="sxs-lookup"><span data-stu-id="8c35b-107">Gets a formatted string that represents the code in this `IDefinitionAppId` object.</span></span>|  
|`IDefinitionAppId::put_Codebase`|<span data-ttu-id="8c35b-108">Задает код это `IDefinitionAppId` объекта на указанное значение форматированной строки.</span><span class="sxs-lookup"><span data-stu-id="8c35b-108">Sets the code of this `IDefinitionAppId` object to the specified formatted string value.</span></span>|  
|`IDefinitionAppId::EnumAppPath`|<span data-ttu-id="8c35b-109">Возвращает указатель интерфейса [IEnumDefinitionIdentity](../../../../docs/framework/unmanaged-api/fusion/ienumdefinitionidentity-interface.md) , содержащий сборки в путь текущего приложения.</span><span class="sxs-lookup"><span data-stu-id="8c35b-109">Gets an interface pointer to an [IEnumDefinitionIdentity](../../../../docs/framework/unmanaged-api/fusion/ienumdefinitionidentity-interface.md) object that contains the assemblies in the current application path.</span></span>|  
|`IDefinitionAppId::SetAppPath`|<span data-ttu-id="8c35b-110">Задает путь приложения для сборки в текущей области, на которое ссылается указанный [IDefinitionIdentity](../../../../docs/framework/unmanaged-api/fusion/idefinitionidentity-interface.md) объекта.</span><span class="sxs-lookup"><span data-stu-id="8c35b-110">Sets the application path for the assembly in the current scope to the value referenced by the specified [IDefinitionIdentity](../../../../docs/framework/unmanaged-api/fusion/idefinitionidentity-interface.md) object.</span></span>|  
|`IDefinitionAppId::get_SubscriptionId`|<span data-ttu-id="8c35b-111">Получает указатель на строковое представление идентификатора маркера для подписки на это `IDefinitionAppId` объекта.</span><span class="sxs-lookup"><span data-stu-id="8c35b-111">Gets a pointer to a string representation of the token identifier for a subscription to this `IDefinitionAppId` object.</span></span>|  
|`IDefinitionAppId::put_SubscriptionId`|<span data-ttu-id="8c35b-112">Задает идентификатор маркера для подписки на этот `IDefinitionAppId` объекта указанному строковому значению.</span><span class="sxs-lookup"><span data-stu-id="8c35b-112">Sets the token identifier for a subscription to this `IDefinitionAppId` object to the specified string value.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8c35b-113">Требования</span><span class="sxs-lookup"><span data-stu-id="8c35b-113">Requirements</span></span>  
 <span data-ttu-id="8c35b-114">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8c35b-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8c35b-115">**Заголовок:** Isolation.h</span><span class="sxs-lookup"><span data-stu-id="8c35b-115">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="8c35b-116">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8c35b-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c35b-117">См. также</span><span class="sxs-lookup"><span data-stu-id="8c35b-117">See Also</span></span>  
 [<span data-ttu-id="8c35b-118">Интерфейсы Fusion</span><span class="sxs-lookup"><span data-stu-id="8c35b-118">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)

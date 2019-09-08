---
title: Интерфейс IDefinitionIdentity
ms.date: 03/30/2017
api_name:
- IDefinitionIdentity
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IDefinitionIdentity
helpviewer_keywords:
- IDefinitionIdentity interface [.NET Framework fusion]
ms.assetid: ce5ba888-5fbe-4efd-91cf-f0ff94d8428b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 84c595bfdcca84ee43a53e2ea913cc978ae0953e
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796524"
---
# <a name="idefinitionidentity-interface"></a><span data-ttu-id="9d757-102">Интерфейс IDefinitionIdentity</span><span class="sxs-lookup"><span data-stu-id="9d757-102">IDefinitionIdentity Interface</span></span>
<span data-ttu-id="9d757-103">Представляет уникальную сигнатуру кода, определяющего приложение в текущей области.</span><span class="sxs-lookup"><span data-stu-id="9d757-103">Represents the unique signature of the code that defines the application in the current scope.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="9d757-104">Методы</span><span class="sxs-lookup"><span data-stu-id="9d757-104">Methods</span></span>  
  
|<span data-ttu-id="9d757-105">Метод</span><span class="sxs-lookup"><span data-stu-id="9d757-105">Method</span></span>|<span data-ttu-id="9d757-106">Описание</span><span class="sxs-lookup"><span data-stu-id="9d757-106">Description</span></span>|  
|------------|-----------------|  
|`IDefinitionIdentity::Clone`|<span data-ttu-id="9d757-107">Получает указатель интерфейса на новый `IDefinitionIdentity` объект, идентичный этому `IDefinitionIdentity`объекту, за исключением изменений указанного атрибута.</span><span class="sxs-lookup"><span data-stu-id="9d757-107">Gets an interface pointer to a new `IDefinitionIdentity` object that is identical to this `IDefinitionIdentity`, except for the specified attribute changes.</span></span>|  
|`IDefinitionIdentity::EnumAttributes`|<span data-ttu-id="9d757-108">Возвращает указатель интерфейса на объект [IEnumIDENTITY_ATTRIBUTE](ienumidentity-attribute-interface.md) , содержащий атрибуты, связанные с этим `IDefinitionIdentity`объектом.</span><span class="sxs-lookup"><span data-stu-id="9d757-108">Gets an interface pointer to an [IEnumIDENTITY_ATTRIBUTE](ienumidentity-attribute-interface.md) object that contains the attributes associated with this `IDefinitionIdentity`.</span></span>|  
|`IDefinitionIdentity::GetAttribute`|<span data-ttu-id="9d757-109">Возвращает значение атрибута с указанным именем в указанном пространстве имен.</span><span class="sxs-lookup"><span data-stu-id="9d757-109">Gets the value of the attribute with the specified name in the specified namespace.</span></span>|  
|`IDefinitionIdentity::SetAttribute`|<span data-ttu-id="9d757-110">Задает для атрибута с указанным именем в указанном пространстве имен указанное значение.</span><span class="sxs-lookup"><span data-stu-id="9d757-110">Sets the attribute that has the specified name in the specified namespace to the specified value.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9d757-111">Требования</span><span class="sxs-lookup"><span data-stu-id="9d757-111">Requirements</span></span>  
 <span data-ttu-id="9d757-112">**Платформ** См. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9d757-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9d757-113">**Заголовок.** Изоляция. h</span><span class="sxs-lookup"><span data-stu-id="9d757-113">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="9d757-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9d757-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d757-115">См. также</span><span class="sxs-lookup"><span data-stu-id="9d757-115">See also</span></span>

- [<span data-ttu-id="9d757-116">Интерфейсы Fusion</span><span class="sxs-lookup"><span data-stu-id="9d757-116">Fusion Interfaces</span></span>](fusion-interfaces.md)

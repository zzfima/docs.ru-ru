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
ms.openlocfilehash: 4ff23330f307c10eac134048de39a6e19a67c75b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61697541"
---
# <a name="idefinitionidentity-interface"></a><span data-ttu-id="4a74b-102">Интерфейс IDefinitionIdentity</span><span class="sxs-lookup"><span data-stu-id="4a74b-102">IDefinitionIdentity Interface</span></span>
<span data-ttu-id="4a74b-103">Представляет уникальную подпись кода, определяющего приложение в текущей области.</span><span class="sxs-lookup"><span data-stu-id="4a74b-103">Represents the unique signature of the code that defines the application in the current scope.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="4a74b-104">Методы</span><span class="sxs-lookup"><span data-stu-id="4a74b-104">Methods</span></span>  
  
|<span data-ttu-id="4a74b-105">Метод</span><span class="sxs-lookup"><span data-stu-id="4a74b-105">Method</span></span>|<span data-ttu-id="4a74b-106">Описание</span><span class="sxs-lookup"><span data-stu-id="4a74b-106">Description</span></span>|  
|------------|-----------------|  
|`IDefinitionIdentity::Clone`|<span data-ttu-id="4a74b-107">Получает указатель интерфейса на новый `IDefinitionIdentity` , идентичный данному `IDefinitionIdentity`, за исключением изменения указанного атрибута.</span><span class="sxs-lookup"><span data-stu-id="4a74b-107">Gets an interface pointer to a new `IDefinitionIdentity` object that is identical to this `IDefinitionIdentity`, except for the specified attribute changes.</span></span>|  
|`IDefinitionIdentity::EnumAttributes`|<span data-ttu-id="4a74b-108">Получает указатель интерфейса на [IEnumIDENTITY_ATTRIBUTE](../../../../docs/framework/unmanaged-api/fusion/ienumidentity-attribute-interface.md) , содержащий атрибуты, связанные с этим `IDefinitionIdentity`.</span><span class="sxs-lookup"><span data-stu-id="4a74b-108">Gets an interface pointer to an [IEnumIDENTITY_ATTRIBUTE](../../../../docs/framework/unmanaged-api/fusion/ienumidentity-attribute-interface.md) object that contains the attributes associated with this `IDefinitionIdentity`.</span></span>|  
|`IDefinitionIdentity::GetAttribute`|<span data-ttu-id="4a74b-109">Получает значение атрибута с указанным именем в указанном пространстве имен.</span><span class="sxs-lookup"><span data-stu-id="4a74b-109">Gets the value of the attribute with the specified name in the specified namespace.</span></span>|  
|`IDefinitionIdentity::SetAttribute`|<span data-ttu-id="4a74b-110">Задает атрибут с указанным именем в указанное пространство имен для указанного значения.</span><span class="sxs-lookup"><span data-stu-id="4a74b-110">Sets the attribute that has the specified name in the specified namespace to the specified value.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4a74b-111">Требования</span><span class="sxs-lookup"><span data-stu-id="4a74b-111">Requirements</span></span>  
 <span data-ttu-id="4a74b-112">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4a74b-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4a74b-113">**Заголовок.** Isolation.h</span><span class="sxs-lookup"><span data-stu-id="4a74b-113">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="4a74b-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4a74b-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a74b-115">См. также</span><span class="sxs-lookup"><span data-stu-id="4a74b-115">See also</span></span>

- [<span data-ttu-id="4a74b-116">Интерфейсы Fusion</span><span class="sxs-lookup"><span data-stu-id="4a74b-116">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)

---
title: Интерфейс IReferenceIdentity
ms.date: 03/30/2017
api_name:
- IReferenceIdentity
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IReferenceIdentity
helpviewer_keywords:
- IReferenceIdentity interface [.NET Framework fusion]
ms.assetid: 9180ac5a-7019-4716-9f83-8a91d157239a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: dd46ea26532074c9ea42da4d07a38ed583aad076
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61789686"
---
# <a name="ireferenceidentity-interface"></a><span data-ttu-id="144e8-102">Интерфейс IReferenceIdentity</span><span class="sxs-lookup"><span data-stu-id="144e8-102">IReferenceIdentity Interface</span></span>
<span data-ttu-id="144e8-103">Представляет ссылку на уникальную подпись объекта кода.</span><span class="sxs-lookup"><span data-stu-id="144e8-103">Represents a reference to the unique signature of a code object.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="144e8-104">Методы</span><span class="sxs-lookup"><span data-stu-id="144e8-104">Methods</span></span>  
  
|<span data-ttu-id="144e8-105">Метод</span><span class="sxs-lookup"><span data-stu-id="144e8-105">Method</span></span>|<span data-ttu-id="144e8-106">Описание</span><span class="sxs-lookup"><span data-stu-id="144e8-106">Description</span></span>|  
|------------|-----------------|  
|`IReferenceIdentity::Clone`|<span data-ttu-id="144e8-107">Получает указатель интерфейса на новый `IReferenceIdentity` экземпляр, который является идентичным этому `IReferenceIdentity`, за исключением изменения указанного атрибута.</span><span class="sxs-lookup"><span data-stu-id="144e8-107">Gets an interface pointer to a new `IReferenceIdentity` instance that is identical to this `IReferenceIdentity`, except for the specified attribute changes.</span></span>|  
|`IReferenceIdentity::EnumAttributes`|<span data-ttu-id="144e8-108">Получает указатель интерфейса на `IEnumIDENTITY_ATTRIBUTE` экземпляр, содержащий атрибуты, связанные с этим `IReferenceIdentity`.</span><span class="sxs-lookup"><span data-stu-id="144e8-108">Gets an interface pointer to an `IEnumIDENTITY_ATTRIBUTE` instance that contains the attributes associated with this `IReferenceIdentity`.</span></span>|  
|`IReferenceIdentity::GetAttribute`|<span data-ttu-id="144e8-109">Получает значение атрибута в указанного пространства имен, с указанным именем.</span><span class="sxs-lookup"><span data-stu-id="144e8-109">Gets the value of the attribute in the specified namespace, with the specified name.</span></span>|  
|`IReferenceIdentity::SetAttribute`|<span data-ttu-id="144e8-110">Задает атрибут, имеющий указанное пространство имен и указанное имя, указанное значение.</span><span class="sxs-lookup"><span data-stu-id="144e8-110">Sets the attribute that has the specified namespace and the specified name to the specified value.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="144e8-111">Требования</span><span class="sxs-lookup"><span data-stu-id="144e8-111">Requirements</span></span>  
 <span data-ttu-id="144e8-112">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="144e8-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="144e8-113">**Заголовок.** Isolation.h</span><span class="sxs-lookup"><span data-stu-id="144e8-113">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="144e8-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="144e8-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="144e8-115">См. также</span><span class="sxs-lookup"><span data-stu-id="144e8-115">See also</span></span>

- [<span data-ttu-id="144e8-116">Интерфейсы Fusion</span><span class="sxs-lookup"><span data-stu-id="144e8-116">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
- [<span data-ttu-id="144e8-117">Интерфейс IEnumIDENTITY_ATTRIBUTE</span><span class="sxs-lookup"><span data-stu-id="144e8-117">IEnumIDENTITY_ATTRIBUTE Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/ienumidentity-attribute-interface.md)

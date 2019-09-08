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
ms.openlocfilehash: 2bb151d7c77104d8e24acefaac2e1f109b67f168
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796354"
---
# <a name="ireferenceidentity-interface"></a><span data-ttu-id="d6291-102">Интерфейс IReferenceIdentity</span><span class="sxs-lookup"><span data-stu-id="d6291-102">IReferenceIdentity Interface</span></span>
<span data-ttu-id="d6291-103">Представляет ссылку на уникальную сигнатуру объекта кода.</span><span class="sxs-lookup"><span data-stu-id="d6291-103">Represents a reference to the unique signature of a code object.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d6291-104">Методы</span><span class="sxs-lookup"><span data-stu-id="d6291-104">Methods</span></span>  
  
|<span data-ttu-id="d6291-105">Метод</span><span class="sxs-lookup"><span data-stu-id="d6291-105">Method</span></span>|<span data-ttu-id="d6291-106">Описание</span><span class="sxs-lookup"><span data-stu-id="d6291-106">Description</span></span>|  
|------------|-----------------|  
|`IReferenceIdentity::Clone`|<span data-ttu-id="d6291-107">Возвращает указатель интерфейса на новый `IReferenceIdentity` экземпляр, идентичный этому `IReferenceIdentity`, за исключением изменения указанного атрибута.</span><span class="sxs-lookup"><span data-stu-id="d6291-107">Gets an interface pointer to a new `IReferenceIdentity` instance that is identical to this `IReferenceIdentity`, except for the specified attribute changes.</span></span>|  
|`IReferenceIdentity::EnumAttributes`|<span data-ttu-id="d6291-108">Возвращает указатель интерфейса на `IEnumIDENTITY_ATTRIBUTE` экземпляр, содержащий атрибуты, связанные с этим. `IReferenceIdentity`</span><span class="sxs-lookup"><span data-stu-id="d6291-108">Gets an interface pointer to an `IEnumIDENTITY_ATTRIBUTE` instance that contains the attributes associated with this `IReferenceIdentity`.</span></span>|  
|`IReferenceIdentity::GetAttribute`|<span data-ttu-id="d6291-109">Возвращает значение атрибута в указанном пространстве имен с указанным именем.</span><span class="sxs-lookup"><span data-stu-id="d6291-109">Gets the value of the attribute in the specified namespace, with the specified name.</span></span>|  
|`IReferenceIdentity::SetAttribute`|<span data-ttu-id="d6291-110">Задает для атрибута, имеющего указанное пространство имен и указанное имя, указанное значение.</span><span class="sxs-lookup"><span data-stu-id="d6291-110">Sets the attribute that has the specified namespace and the specified name to the specified value.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d6291-111">Требования</span><span class="sxs-lookup"><span data-stu-id="d6291-111">Requirements</span></span>  
 <span data-ttu-id="d6291-112">**Платформ** См. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d6291-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d6291-113">**Заголовок.** Изоляция. h</span><span class="sxs-lookup"><span data-stu-id="d6291-113">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="d6291-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d6291-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6291-115">См. также</span><span class="sxs-lookup"><span data-stu-id="d6291-115">See also</span></span>

- [<span data-ttu-id="d6291-116">Интерфейсы Fusion</span><span class="sxs-lookup"><span data-stu-id="d6291-116">Fusion Interfaces</span></span>](fusion-interfaces.md)
- [<span data-ttu-id="d6291-117">Интерфейс IEnumIDENTITY_ATTRIBUTE</span><span class="sxs-lookup"><span data-stu-id="d6291-117">IEnumIDENTITY_ATTRIBUTE Interface</span></span>](ienumidentity-attribute-interface.md)

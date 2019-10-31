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
ms.openlocfilehash: 8f6a117d1e2fe76c271b0b014e6079370c8b4fe4
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127064"
---
# <a name="ireferenceidentity-interface"></a><span data-ttu-id="538aa-102">Интерфейс IReferenceIdentity</span><span class="sxs-lookup"><span data-stu-id="538aa-102">IReferenceIdentity Interface</span></span>
<span data-ttu-id="538aa-103">Представляет ссылку на уникальную сигнатуру объекта кода.</span><span class="sxs-lookup"><span data-stu-id="538aa-103">Represents a reference to the unique signature of a code object.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="538aa-104">Методы</span><span class="sxs-lookup"><span data-stu-id="538aa-104">Methods</span></span>  
  
|<span data-ttu-id="538aa-105">Метод</span><span class="sxs-lookup"><span data-stu-id="538aa-105">Method</span></span>|<span data-ttu-id="538aa-106">Описание</span><span class="sxs-lookup"><span data-stu-id="538aa-106">Description</span></span>|  
|------------|-----------------|  
|`IReferenceIdentity::Clone`|<span data-ttu-id="538aa-107">Получает указатель интерфейса на новый экземпляр `IReferenceIdentity`, идентичный этому `IReferenceIdentity`, за исключением изменения указанного атрибута.</span><span class="sxs-lookup"><span data-stu-id="538aa-107">Gets an interface pointer to a new `IReferenceIdentity` instance that is identical to this `IReferenceIdentity`, except for the specified attribute changes.</span></span>|  
|`IReferenceIdentity::EnumAttributes`|<span data-ttu-id="538aa-108">Возвращает указатель интерфейса на экземпляр `IEnumIDENTITY_ATTRIBUTE`, содержащий атрибуты, связанные с этим `IReferenceIdentity`.</span><span class="sxs-lookup"><span data-stu-id="538aa-108">Gets an interface pointer to an `IEnumIDENTITY_ATTRIBUTE` instance that contains the attributes associated with this `IReferenceIdentity`.</span></span>|  
|`IReferenceIdentity::GetAttribute`|<span data-ttu-id="538aa-109">Возвращает значение атрибута в указанном пространстве имен с указанным именем.</span><span class="sxs-lookup"><span data-stu-id="538aa-109">Gets the value of the attribute in the specified namespace, with the specified name.</span></span>|  
|`IReferenceIdentity::SetAttribute`|<span data-ttu-id="538aa-110">Задает для атрибута, имеющего указанное пространство имен и указанное имя, указанное значение.</span><span class="sxs-lookup"><span data-stu-id="538aa-110">Sets the attribute that has the specified namespace and the specified name to the specified value.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="538aa-111">Требования</span><span class="sxs-lookup"><span data-stu-id="538aa-111">Requirements</span></span>  
 <span data-ttu-id="538aa-112">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="538aa-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="538aa-113">**Заголовок:** Изоляция. h</span><span class="sxs-lookup"><span data-stu-id="538aa-113">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="538aa-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="538aa-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="538aa-115">См. также</span><span class="sxs-lookup"><span data-stu-id="538aa-115">See also</span></span>

- [<span data-ttu-id="538aa-116">Интерфейсы Fusion</span><span class="sxs-lookup"><span data-stu-id="538aa-116">Fusion Interfaces</span></span>](fusion-interfaces.md)
- [<span data-ttu-id="538aa-117">Интерфейс IEnumIDENTITY_ATTRIBUTE</span><span class="sxs-lookup"><span data-stu-id="538aa-117">IEnumIDENTITY_ATTRIBUTE Interface</span></span>](ienumidentity-attribute-interface.md)

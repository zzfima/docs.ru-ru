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
ms.openlocfilehash: 59578e1d3a66809c86f7daad1b208df2ae09568d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73108031"
---
# <a name="idefinitionidentity-interface"></a><span data-ttu-id="73399-102">Интерфейс IDefinitionIdentity</span><span class="sxs-lookup"><span data-stu-id="73399-102">IDefinitionIdentity Interface</span></span>
<span data-ttu-id="73399-103">Представляет уникальную сигнатуру кода, определяющего приложение в текущей области.</span><span class="sxs-lookup"><span data-stu-id="73399-103">Represents the unique signature of the code that defines the application in the current scope.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="73399-104">Методы</span><span class="sxs-lookup"><span data-stu-id="73399-104">Methods</span></span>  
  
|<span data-ttu-id="73399-105">Метод</span><span class="sxs-lookup"><span data-stu-id="73399-105">Method</span></span>|<span data-ttu-id="73399-106">Описание</span><span class="sxs-lookup"><span data-stu-id="73399-106">Description</span></span>|  
|------------|-----------------|  
|`IDefinitionIdentity::Clone`|<span data-ttu-id="73399-107">Получает указатель интерфейса на новый объект `IDefinitionIdentity`, идентичный этому `IDefinitionIdentity`, за исключением изменения указанного атрибута.</span><span class="sxs-lookup"><span data-stu-id="73399-107">Gets an interface pointer to a new `IDefinitionIdentity` object that is identical to this `IDefinitionIdentity`, except for the specified attribute changes.</span></span>|  
|`IDefinitionIdentity::EnumAttributes`|<span data-ttu-id="73399-108">Возвращает указатель интерфейса на объект [IEnumIDENTITY_ATTRIBUTE](ienumidentity-attribute-interface.md) , содержащий атрибуты, связанные с этим `IDefinitionIdentity`.</span><span class="sxs-lookup"><span data-stu-id="73399-108">Gets an interface pointer to an [IEnumIDENTITY_ATTRIBUTE](ienumidentity-attribute-interface.md) object that contains the attributes associated with this `IDefinitionIdentity`.</span></span>|  
|`IDefinitionIdentity::GetAttribute`|<span data-ttu-id="73399-109">Возвращает значение атрибута с указанным именем в указанном пространстве имен.</span><span class="sxs-lookup"><span data-stu-id="73399-109">Gets the value of the attribute with the specified name in the specified namespace.</span></span>|  
|`IDefinitionIdentity::SetAttribute`|<span data-ttu-id="73399-110">Задает для атрибута с указанным именем в указанном пространстве имен указанное значение.</span><span class="sxs-lookup"><span data-stu-id="73399-110">Sets the attribute that has the specified name in the specified namespace to the specified value.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="73399-111">Требования</span><span class="sxs-lookup"><span data-stu-id="73399-111">Requirements</span></span>  
 <span data-ttu-id="73399-112">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="73399-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="73399-113">**Заголовок:** Изоляция. h</span><span class="sxs-lookup"><span data-stu-id="73399-113">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="73399-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="73399-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73399-115">См. также</span><span class="sxs-lookup"><span data-stu-id="73399-115">See also</span></span>

- [<span data-ttu-id="73399-116">Интерфейсы Fusion</span><span class="sxs-lookup"><span data-stu-id="73399-116">Fusion Interfaces</span></span>](fusion-interfaces.md)

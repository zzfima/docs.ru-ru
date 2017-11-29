---
title: "Интерфейс IDefinitionIdentity"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IDefinitionIdentity
api_location: fusion.dll
api_type: COM
f1_keywords: IDefinitionIdentity
helpviewer_keywords: IDefinitionIdentity interface [.NET Framework fusion]
ms.assetid: ce5ba888-5fbe-4efd-91cf-f0ff94d8428b
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: a63436f107a2604fd5620854339447a4af254e52
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="idefinitionidentity-interface"></a><span data-ttu-id="21abe-102">Интерфейс IDefinitionIdentity</span><span class="sxs-lookup"><span data-stu-id="21abe-102">IDefinitionIdentity Interface</span></span>
<span data-ttu-id="21abe-103">Представляет уникальную подпись кода, определяющего приложение в текущей области.</span><span class="sxs-lookup"><span data-stu-id="21abe-103">Represents the unique signature of the code that defines the application in the current scope.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="21abe-104">Методы</span><span class="sxs-lookup"><span data-stu-id="21abe-104">Methods</span></span>  
  
|<span data-ttu-id="21abe-105">Метод</span><span class="sxs-lookup"><span data-stu-id="21abe-105">Method</span></span>|<span data-ttu-id="21abe-106">Описание</span><span class="sxs-lookup"><span data-stu-id="21abe-106">Description</span></span>|  
|------------|-----------------|  
|`IDefinitionIdentity::Clone`|<span data-ttu-id="21abe-107">Получает указатель интерфейса на новый `IDefinitionIdentity` объекта, идентичным этому `IDefinitionIdentity`, за исключением изменения указанного атрибута.</span><span class="sxs-lookup"><span data-stu-id="21abe-107">Gets an interface pointer to a new `IDefinitionIdentity` object that is identical to this `IDefinitionIdentity`, except for the specified attribute changes.</span></span>|  
|`IDefinitionIdentity::EnumAttributes`|<span data-ttu-id="21abe-108">Возвращает указатель интерфейса [IEnumIDENTITY_ATTRIBUTE](../../../../docs/framework/unmanaged-api/fusion/ienumidentity-attribute-interface.md) объект, содержащий атрибуты, связанные с этим `IDefinitionIdentity`.</span><span class="sxs-lookup"><span data-stu-id="21abe-108">Gets an interface pointer to an [IEnumIDENTITY_ATTRIBUTE](../../../../docs/framework/unmanaged-api/fusion/ienumidentity-attribute-interface.md) object that contains the attributes associated with this `IDefinitionIdentity`.</span></span>|  
|`IDefinitionIdentity::GetAttribute`|<span data-ttu-id="21abe-109">Возвращает значение атрибута с заданным именем в указанном пространстве имен.</span><span class="sxs-lookup"><span data-stu-id="21abe-109">Gets the value of the attribute with the specified name in the specified namespace.</span></span>|  
|`IDefinitionIdentity::SetAttribute`|<span data-ttu-id="21abe-110">Устанавливает атрибут с указанным именем в указанное пространство имен с указанным значением.</span><span class="sxs-lookup"><span data-stu-id="21abe-110">Sets the attribute that has the specified name in the specified namespace to the specified value.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="21abe-111">Требования</span><span class="sxs-lookup"><span data-stu-id="21abe-111">Requirements</span></span>  
 <span data-ttu-id="21abe-112">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="21abe-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="21abe-113">**Заголовок:** Isolation.h</span><span class="sxs-lookup"><span data-stu-id="21abe-113">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="21abe-114">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="21abe-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21abe-115">См. также</span><span class="sxs-lookup"><span data-stu-id="21abe-115">See Also</span></span>  
 [<span data-ttu-id="21abe-116">Фьюжн-интерфейсы</span><span class="sxs-lookup"><span data-stu-id="21abe-116">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)

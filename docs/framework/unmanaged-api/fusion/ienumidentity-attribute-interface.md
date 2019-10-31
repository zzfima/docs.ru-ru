---
title: Интерфейс IEnumIDENTITY_ATTRIBUTE
ms.date: 03/30/2017
api_name:
- IEnumIDENTITY_ATTRIBUTE
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IEnumIDENTITY_ATTRIBUTE
helpviewer_keywords:
- IEnumIDENTITY_ATTRIBUTE interface [.NET Framework fusion]
ms.assetid: c2ec2748-e9ae-4e1b-80db-6fcec5cb81a1
topic_type:
- apiref
ms.openlocfilehash: 7e6bc57fb470a5c12549bb5f9445ecf1551425a4
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73107841"
---
# <a name="ienumidentity_attribute-interface"></a><span data-ttu-id="ab480-102">Интерфейс IEnumIDENTITY_ATTRIBUTE</span><span class="sxs-lookup"><span data-stu-id="ab480-102">IEnumIDENTITY_ATTRIBUTE Interface</span></span>
<span data-ttu-id="ab480-103">Служит в качестве перечислителя для атрибутов объекта Code в текущей области.</span><span class="sxs-lookup"><span data-stu-id="ab480-103">Serves as an enumerator for the attributes of the code object in the current scope.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ab480-104">Методы</span><span class="sxs-lookup"><span data-stu-id="ab480-104">Methods</span></span>  
  
|<span data-ttu-id="ab480-105">Метод</span><span class="sxs-lookup"><span data-stu-id="ab480-105">Method</span></span>|<span data-ttu-id="ab480-106">Описание</span><span class="sxs-lookup"><span data-stu-id="ab480-106">Description</span></span>|  
|------------|-----------------|  
|`IEnumIDENTITY_ATTRIBUTE::Clone`|<span data-ttu-id="ab480-107">Возвращает указатель интерфейса на новый `IEnumIDENTITY_ATTRIBUTE`, содержащий те же элементы, что и этот `IEnumIDENTITY_ATTRIBUTE`.</span><span class="sxs-lookup"><span data-stu-id="ab480-107">Gets an interface pointer to a new `IEnumIDENTITY_ATTRIBUTE` that contains the same members as this `IEnumIDENTITY_ATTRIBUTE`.</span></span>|  
|`IEnumIDENTITY_ATTRIBUTE::CurrentIntoBuffer`|<span data-ttu-id="ab480-108">Записывает данные, содержащиеся в элементах этого `IEnumIDENTITY_ATTRIBUTE`, в указанный буфер данных.</span><span class="sxs-lookup"><span data-stu-id="ab480-108">Writes the data contained in the elements of this `IEnumIDENTITY_ATTRIBUTE` to the specified data buffer.</span></span>|  
|`IEnumIDENTITY_ATTRIBUTE::Next`|<span data-ttu-id="ab480-109">Возвращает указанное число атрибутов, начиная с текущей позиции.</span><span class="sxs-lookup"><span data-stu-id="ab480-109">Gets the specified number of attributes, starting at the current position.</span></span>|  
|`IEnumIDENTITY_ATTRIBUTE::Reset`|<span data-ttu-id="ab480-110">Перемещает указатель инструкции в начало этого `IEnumIDENTITY_ATTRIBUTE`.</span><span class="sxs-lookup"><span data-stu-id="ab480-110">Moves the instruction pointer to the beginning of this `IEnumIDENTITY_ATTRIBUTE`.</span></span>|  
|`IEnumIDENTITY_ATTRIBUTE::Skip`|<span data-ttu-id="ab480-111">Перемещает указатель инструкции вперед на указанное число элементов, начиная с текущей позиции.</span><span class="sxs-lookup"><span data-stu-id="ab480-111">Moves the instruction pointer forward by the specified number of elements, starting at the current position.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ab480-112">Требования</span><span class="sxs-lookup"><span data-stu-id="ab480-112">Requirements</span></span>  
 <span data-ttu-id="ab480-113">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ab480-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ab480-114">**Заголовок:** Изоляция. h</span><span class="sxs-lookup"><span data-stu-id="ab480-114">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="ab480-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ab480-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab480-116">См. также</span><span class="sxs-lookup"><span data-stu-id="ab480-116">See also</span></span>

- [<span data-ttu-id="ab480-117">Интерфейсы Fusion</span><span class="sxs-lookup"><span data-stu-id="ab480-117">Fusion Interfaces</span></span>](fusion-interfaces.md)

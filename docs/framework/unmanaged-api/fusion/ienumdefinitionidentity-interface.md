---
title: Интерфейс IEnumDefinitionIdentity
ms.date: 03/30/2017
api_name:
- IEnumDefinitionIdentity
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IEnumDefinitionIdentity
helpviewer_keywords:
- IEnumDefinitionIdentity interface [.NET Framework fusion]
ms.assetid: 8263e75d-251b-4abc-8a1a-c62884142232
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 88c2513229b6a4183cadbdc78e505910e01e152c
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796475"
---
# <a name="ienumdefinitionidentity-interface"></a><span data-ttu-id="ab1a2-102">Интерфейс IEnumDefinitionIdentity</span><span class="sxs-lookup"><span data-stu-id="ab1a2-102">IEnumDefinitionIdentity Interface</span></span>
<span data-ttu-id="ab1a2-103">Служит в качестве перечислителя для коллекции `IDefinitionIdentity` объектов.</span><span class="sxs-lookup"><span data-stu-id="ab1a2-103">Serves as the enumerator for a collection of `IDefinitionIdentity` objects.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ab1a2-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ab1a2-104">Syntax</span></span>  
  
```cpp  
IEnumDefinitionIdentity : IUnknown {  
  
    HRESULT Clone (  
        [out] IEnumDefinitionIdentity **ppIEnumDefinitionIdentity  
    );  
  
    HRESULT Next (  
        [in]  ULONG               celt,  
        [out, length_is(celt), size_is(*pceltWritten)]  
              IDefinitionIdentity *rgpIDefinitionIdentity[],  
        [out] ULONG               *pceltWritten  
    );  
  
    HRESULT Reset ();  
  
    HRESULT Skip (  
        [in] ULONG celt  
    );  
  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="ab1a2-105">Методы</span><span class="sxs-lookup"><span data-stu-id="ab1a2-105">Methods</span></span>  
  
|<span data-ttu-id="ab1a2-106">Метод</span><span class="sxs-lookup"><span data-stu-id="ab1a2-106">Method</span></span>|<span data-ttu-id="ab1a2-107">Описание</span><span class="sxs-lookup"><span data-stu-id="ab1a2-107">Description</span></span>|  
|------------|-----------------|  
|`IEnumDefinitionIdentity::Clone`|<span data-ttu-id="ab1a2-108">Возвращает указатель интерфейса на новый `IEnumDefinitionIdentity` объект, содержащий те же элементы, что и этот. `IEnumDefinitionIdentity`</span><span class="sxs-lookup"><span data-stu-id="ab1a2-108">Gets an interface pointer to a new `IEnumDefinitionIdentity` object that contains the same members as this `IEnumDefinitionIdentity`.</span></span>|  
|`IEnumDefinitionIdentity::Next`|<span data-ttu-id="ab1a2-109">Возвращает указанное число `IDefinitionIdentity` объектов, начиная с текущей позиции.</span><span class="sxs-lookup"><span data-stu-id="ab1a2-109">Gets the specified number of `IDefinitionIdentity` objects, starting at the current position.</span></span>|  
|`IEnumDefinitionIdentity::Reset`|<span data-ttu-id="ab1a2-110">Перемещает указатель инструкций в начало `IEnumDefinitionIdentity`.</span><span class="sxs-lookup"><span data-stu-id="ab1a2-110">Moves the instruction pointer to the beginning of this `IEnumDefinitionIdentity`.</span></span>|  
|`IEnumDefinitionIdentity::Skip`|<span data-ttu-id="ab1a2-111">Перемещает указатель инструкции вперед на указанное число элементов, начиная с текущей позиции.</span><span class="sxs-lookup"><span data-stu-id="ab1a2-111">Moves the instruction pointer forward by the specified number of elements, starting at the current position.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ab1a2-112">Требования</span><span class="sxs-lookup"><span data-stu-id="ab1a2-112">Requirements</span></span>  
 <span data-ttu-id="ab1a2-113">**Платформ** См. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ab1a2-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ab1a2-114">**Заголовок.** Изоляция. h</span><span class="sxs-lookup"><span data-stu-id="ab1a2-114">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="ab1a2-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ab1a2-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab1a2-116">См. также</span><span class="sxs-lookup"><span data-stu-id="ab1a2-116">See also</span></span>

- [<span data-ttu-id="ab1a2-117">Интерфейсы Fusion</span><span class="sxs-lookup"><span data-stu-id="ab1a2-117">Fusion Interfaces</span></span>](fusion-interfaces.md)
- [<span data-ttu-id="ab1a2-118">Интерфейс IDefinitionIdentity</span><span class="sxs-lookup"><span data-stu-id="ab1a2-118">IDefinitionIdentity Interface</span></span>](idefinitionidentity-interface.md)

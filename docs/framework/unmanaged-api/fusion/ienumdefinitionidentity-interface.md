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
ms.openlocfilehash: 09c6431ec885c8b797dc9bb5f5c3ffe21890ccc7
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73107942"
---
# <a name="ienumdefinitionidentity-interface"></a><span data-ttu-id="54e95-102">Интерфейс IEnumDefinitionIdentity</span><span class="sxs-lookup"><span data-stu-id="54e95-102">IEnumDefinitionIdentity Interface</span></span>
<span data-ttu-id="54e95-103">Служит в качестве перечислителя для коллекции объектов `IDefinitionIdentity`.</span><span class="sxs-lookup"><span data-stu-id="54e95-103">Serves as the enumerator for a collection of `IDefinitionIdentity` objects.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="54e95-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="54e95-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="54e95-105">Методы</span><span class="sxs-lookup"><span data-stu-id="54e95-105">Methods</span></span>  
  
|<span data-ttu-id="54e95-106">Метод</span><span class="sxs-lookup"><span data-stu-id="54e95-106">Method</span></span>|<span data-ttu-id="54e95-107">Описание</span><span class="sxs-lookup"><span data-stu-id="54e95-107">Description</span></span>|  
|------------|-----------------|  
|`IEnumDefinitionIdentity::Clone`|<span data-ttu-id="54e95-108">Возвращает указатель интерфейса на новый объект `IEnumDefinitionIdentity`, который содержит те же члены, что и этот `IEnumDefinitionIdentity`.</span><span class="sxs-lookup"><span data-stu-id="54e95-108">Gets an interface pointer to a new `IEnumDefinitionIdentity` object that contains the same members as this `IEnumDefinitionIdentity`.</span></span>|  
|`IEnumDefinitionIdentity::Next`|<span data-ttu-id="54e95-109">Возвращает указанное число объектов `IDefinitionIdentity`, начиная с текущей позиции.</span><span class="sxs-lookup"><span data-stu-id="54e95-109">Gets the specified number of `IDefinitionIdentity` objects, starting at the current position.</span></span>|  
|`IEnumDefinitionIdentity::Reset`|<span data-ttu-id="54e95-110">Перемещает указатель инструкции в начало этого `IEnumDefinitionIdentity`.</span><span class="sxs-lookup"><span data-stu-id="54e95-110">Moves the instruction pointer to the beginning of this `IEnumDefinitionIdentity`.</span></span>|  
|`IEnumDefinitionIdentity::Skip`|<span data-ttu-id="54e95-111">Перемещает указатель инструкции вперед на указанное число элементов, начиная с текущей позиции.</span><span class="sxs-lookup"><span data-stu-id="54e95-111">Moves the instruction pointer forward by the specified number of elements, starting at the current position.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="54e95-112">Требования</span><span class="sxs-lookup"><span data-stu-id="54e95-112">Requirements</span></span>  
 <span data-ttu-id="54e95-113">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="54e95-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="54e95-114">**Заголовок:** Изоляция. h</span><span class="sxs-lookup"><span data-stu-id="54e95-114">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="54e95-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="54e95-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54e95-116">См. также</span><span class="sxs-lookup"><span data-stu-id="54e95-116">See also</span></span>

- [<span data-ttu-id="54e95-117">Интерфейсы Fusion</span><span class="sxs-lookup"><span data-stu-id="54e95-117">Fusion Interfaces</span></span>](fusion-interfaces.md)
- [<span data-ttu-id="54e95-118">Интерфейс IDefinitionIdentity</span><span class="sxs-lookup"><span data-stu-id="54e95-118">IDefinitionIdentity Interface</span></span>](idefinitionidentity-interface.md)

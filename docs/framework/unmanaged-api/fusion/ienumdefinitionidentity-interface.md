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
ms.openlocfilehash: d19ca92db6f57a004dca54f6e22db10603c9498a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59214849"
---
# <a name="ienumdefinitionidentity-interface"></a><span data-ttu-id="16653-102">Интерфейс IEnumDefinitionIdentity</span><span class="sxs-lookup"><span data-stu-id="16653-102">IEnumDefinitionIdentity Interface</span></span>
<span data-ttu-id="16653-103">Служит в качестве перечислителя для коллекции `IDefinitionIdentity` объектов.</span><span class="sxs-lookup"><span data-stu-id="16653-103">Serves as the enumerator for a collection of `IDefinitionIdentity` objects.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="16653-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="16653-104">Syntax</span></span>  
  
```  
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
  
## <a name="methods"></a><span data-ttu-id="16653-105">Методы</span><span class="sxs-lookup"><span data-stu-id="16653-105">Methods</span></span>  
  
|<span data-ttu-id="16653-106">Метод</span><span class="sxs-lookup"><span data-stu-id="16653-106">Method</span></span>|<span data-ttu-id="16653-107">Описание</span><span class="sxs-lookup"><span data-stu-id="16653-107">Description</span></span>|  
|------------|-----------------|  
|`IEnumDefinitionIdentity::Clone`|<span data-ttu-id="16653-108">Получает указатель интерфейса на новый `IEnumDefinitionIdentity` , содержащий те же члены, что это `IEnumDefinitionIdentity`.</span><span class="sxs-lookup"><span data-stu-id="16653-108">Gets an interface pointer to a new `IEnumDefinitionIdentity` object that contains the same members as this `IEnumDefinitionIdentity`.</span></span>|  
|`IEnumDefinitionIdentity::Next`|<span data-ttu-id="16653-109">Возвращает заданное число `IDefinitionIdentity` объектов, начиная с текущей позиции.</span><span class="sxs-lookup"><span data-stu-id="16653-109">Gets the specified number of `IDefinitionIdentity` objects, starting at the current position.</span></span>|  
|`IEnumDefinitionIdentity::Reset`|<span data-ttu-id="16653-110">Перемещает указатель инструкций в начале `IEnumDefinitionIdentity`.</span><span class="sxs-lookup"><span data-stu-id="16653-110">Moves the instruction pointer to the beginning of this `IEnumDefinitionIdentity`.</span></span>|  
|`IEnumDefinitionIdentity::Skip`|<span data-ttu-id="16653-111">Перемещает указатель инструкций вперед на указанное число элементов, начиная с текущей позиции.</span><span class="sxs-lookup"><span data-stu-id="16653-111">Moves the instruction pointer forward by the specified number of elements, starting at the current position.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="16653-112">Требования</span><span class="sxs-lookup"><span data-stu-id="16653-112">Requirements</span></span>  
 <span data-ttu-id="16653-113">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="16653-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="16653-114">**Заголовок.** Isolation.h</span><span class="sxs-lookup"><span data-stu-id="16653-114">**Header:** Isolation.h</span></span>  
  
 **<span data-ttu-id="16653-115">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="16653-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="16653-116">См. также</span><span class="sxs-lookup"><span data-stu-id="16653-116">See also</span></span>

- [<span data-ttu-id="16653-117">Fusion-интерфейсы</span><span class="sxs-lookup"><span data-stu-id="16653-117">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
- [<span data-ttu-id="16653-118">Интерфейс IDefinitionIdentity</span><span class="sxs-lookup"><span data-stu-id="16653-118">IDefinitionIdentity Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/idefinitionidentity-interface.md)

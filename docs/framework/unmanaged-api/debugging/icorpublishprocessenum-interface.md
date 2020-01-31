---
title: Интерфейс ICorPublishProcessEnum
ms.date: 03/30/2017
api_name:
- ICorPublishProcessEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishProcessEnum
helpviewer_keywords:
- ICorPublishProcessEnum interface [.NET Framework debugging]
ms.assetid: aac8fcf9-ac09-437c-bd5c-2fda14ae1007
topic_type:
- apiref
ms.openlocfilehash: 188ff8feabd704d828256a09aca20f9db2227f2c
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790499"
---
# <a name="icorpublishprocessenum-interface"></a><span data-ttu-id="aba41-102">Интерфейс ICorPublishProcessEnum</span><span class="sxs-lookup"><span data-stu-id="aba41-102">ICorPublishProcessEnum Interface</span></span>
<span data-ttu-id="aba41-103">Подкласс интерфейса [ICorPublishEnum](icorpublishenum-interface.md) , предоставляющий методы для прохода по коллекции объектов [ICorPublishProcess](icorpublishprocess-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="aba41-103">A subclass of the [ICorPublishEnum](icorpublishenum-interface.md) interface that provides methods to traverse a collection of [ICorPublishProcess](icorpublishprocess-interface.md) objects.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="aba41-104">Методы</span><span class="sxs-lookup"><span data-stu-id="aba41-104">Methods</span></span>  
  
|<span data-ttu-id="aba41-105">Метод</span><span class="sxs-lookup"><span data-stu-id="aba41-105">Method</span></span>|<span data-ttu-id="aba41-106">Описание</span><span class="sxs-lookup"><span data-stu-id="aba41-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="aba41-107">Метод Next</span><span class="sxs-lookup"><span data-stu-id="aba41-107">Next Method</span></span>](icorpublishprocessenum-next-method.md)|<span data-ttu-id="aba41-108">Возвращает указанное число экземпляров `ICorPublishProcess` из коллекции, начиная с текущей позиции.</span><span class="sxs-lookup"><span data-stu-id="aba41-108">Gets the specified number of `ICorPublishProcess` instances from the collection, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="aba41-109">Заметки</span><span class="sxs-lookup"><span data-stu-id="aba41-109">Remarks</span></span>  
 <span data-ttu-id="aba41-110">Интерфейс `ICorPublishProcessEnum` реализует методы абстрактного интерфейса [ICorPublishEnum](icorpublishenum-interface.md).</span><span class="sxs-lookup"><span data-stu-id="aba41-110">The `ICorPublishProcessEnum` interface implements the methods of the abstract interface, [ICorPublishEnum](icorpublishenum-interface.md).</span></span>  
  
 <span data-ttu-id="aba41-111">Экземпляр `ICorPublishProcessEnum` создается методом [ICorPublish:: EnumProcesses](icorpublish-enumprocesses-method.md) .</span><span class="sxs-lookup"><span data-stu-id="aba41-111">An `ICorPublishProcessEnum` instance is created by the [ICorPublish::EnumProcesses](icorpublish-enumprocesses-method.md) method.</span></span> <span data-ttu-id="aba41-112">Обход коллекции объектов `ICorPublishProcess` основан на условиях фильтра, заданных во время создания `ICorPublishProcessEnum` экземпляра.</span><span class="sxs-lookup"><span data-stu-id="aba41-112">The traversal of the collection of `ICorPublishProcess` objects is based on the filter criteria given at the time the `ICorPublishProcessEnum` instance was created.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aba41-113">Требования</span><span class="sxs-lookup"><span data-stu-id="aba41-113">Requirements</span></span>  
 <span data-ttu-id="aba41-114">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="aba41-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aba41-115">**Заголовок:** Корпуб. idl, Корпуб. h</span><span class="sxs-lookup"><span data-stu-id="aba41-115">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="aba41-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="aba41-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="aba41-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aba41-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aba41-118">См. также:</span><span class="sxs-lookup"><span data-stu-id="aba41-118">See also</span></span>

- [<span data-ttu-id="aba41-119">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="aba41-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="aba41-120">Кокласс CorpubPublish</span><span class="sxs-lookup"><span data-stu-id="aba41-120">CorpubPublish Coclass</span></span>](corpubpublish-coclass.md)

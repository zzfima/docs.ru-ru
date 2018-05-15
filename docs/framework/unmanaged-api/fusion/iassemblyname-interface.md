---
title: Интерфейс IAssemblyName
ms.date: 03/30/2017
api_name:
- IAssemblyName
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyName
helpviewer_keywords:
- IAssemblyName interface [.NET Framework fusion]
ms.assetid: f7f8e605-6b67-4151-936f-f04ecd671d90
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: aa12252c4f2a8e710a4a880af103aa324f8118ac
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="iassemblyname-interface"></a><span data-ttu-id="f478d-102">Интерфейс IAssemblyName</span><span class="sxs-lookup"><span data-stu-id="f478d-102">IAssemblyName Interface</span></span>
<span data-ttu-id="f478d-103">Предоставляет методы для описания и работы с уникальный идентификатор сборки.</span><span class="sxs-lookup"><span data-stu-id="f478d-103">Provides methods for describing and working with an assembly's unique identity.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f478d-104">Методы</span><span class="sxs-lookup"><span data-stu-id="f478d-104">Methods</span></span>  
  
|<span data-ttu-id="f478d-105">Метод</span><span class="sxs-lookup"><span data-stu-id="f478d-105">Method</span></span>|<span data-ttu-id="f478d-106">Описание</span><span class="sxs-lookup"><span data-stu-id="f478d-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f478d-107">Метод Clone</span><span class="sxs-lookup"><span data-stu-id="f478d-107">Clone Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-clone-method.md)|<span data-ttu-id="f478d-108">Создает неполную копию `IAssemblyName` объекта.</span><span class="sxs-lookup"><span data-stu-id="f478d-108">Creates a shallow copy of this `IAssemblyName` object.</span></span>|  
|[<span data-ttu-id="f478d-109">Метод Finalize</span><span class="sxs-lookup"><span data-stu-id="f478d-109">Finalize Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-finalize-method.md)|<span data-ttu-id="f478d-110">Это позволяет `IAssemblyName` объект освободить ресурсы и выполнить другие операции очистки, перед его деструктора.</span><span class="sxs-lookup"><span data-stu-id="f478d-110">Allows this `IAssemblyName` object to release resources and perform other cleanup operations before its destructor is called.</span></span>|  
|[<span data-ttu-id="f478d-111">Метод GetDisplayName</span><span class="sxs-lookup"><span data-stu-id="f478d-111">GetDisplayName Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-getdisplayname-method.md)|<span data-ttu-id="f478d-112">Возвращает понятное имя сборки, упоминаемой в этом `IAssemblyName` объекта.</span><span class="sxs-lookup"><span data-stu-id="f478d-112">Gets the human-readable name of the assembly referenced by this `IAssemblyName` object.</span></span>|  
|[<span data-ttu-id="f478d-113">Метод GetName</span><span class="sxs-lookup"><span data-stu-id="f478d-113">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-getname-method.md)|<span data-ttu-id="f478d-114">Получает простое, нешифрованное имя сборки, упоминаемой в этом `IAssemblyName` объекта.</span><span class="sxs-lookup"><span data-stu-id="f478d-114">Gets the simple, unencrypted name of the assembly referenced by this `IAssemblyName` object.</span></span>|  
|[<span data-ttu-id="f478d-115">Метод GetProperty</span><span class="sxs-lookup"><span data-stu-id="f478d-115">GetProperty Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-getproperty-method.md)|<span data-ttu-id="f478d-116">Получает указатель ссылается заданный дескриптор свойства `PropertyId`.</span><span class="sxs-lookup"><span data-stu-id="f478d-116">Gets a pointer to the property referenced by the specified `PropertyId`.</span></span>|  
|[<span data-ttu-id="f478d-117">Метод GetVersion</span><span class="sxs-lookup"><span data-stu-id="f478d-117">GetVersion Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-getversion-method.md)|<span data-ttu-id="f478d-118">Возвращает сведения о версии для сборки, упоминаемой в этом `IAssemblyName` объекта.</span><span class="sxs-lookup"><span data-stu-id="f478d-118">Gets the version information for the assembly referenced by this `IAssemblyName` object.</span></span>|  
|[<span data-ttu-id="f478d-119">Метод IsEqual</span><span class="sxs-lookup"><span data-stu-id="f478d-119">IsEqual Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-isequal-method.md)|<span data-ttu-id="f478d-120">Определяет, является ли заданное `IAssemblyName` объект равен этому `IAssemblyName`, основываясь на флаги сравнения указанного.</span><span class="sxs-lookup"><span data-stu-id="f478d-120">Determines whether a specified `IAssemblyName` object is equal to this `IAssemblyName`, based on the specified comparison flags.</span></span>|  
|[<span data-ttu-id="f478d-121">Метод SetProperty</span><span class="sxs-lookup"><span data-stu-id="f478d-121">SetProperty Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-setproperty-method.md)|<span data-ttu-id="f478d-122">Задает значение свойства, который ссылается заданный дескриптор `PropertyId`.</span><span class="sxs-lookup"><span data-stu-id="f478d-122">Sets the value of the property referenced by the specified `PropertyId`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f478d-123">Требования</span><span class="sxs-lookup"><span data-stu-id="f478d-123">Requirements</span></span>  
 <span data-ttu-id="f478d-124">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f478d-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f478d-125">**Заголовок:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="f478d-125">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="f478d-126">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f478d-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f478d-127">См. также</span><span class="sxs-lookup"><span data-stu-id="f478d-127">See Also</span></span>  
 [<span data-ttu-id="f478d-128">Интерфейсы Fusion</span><span class="sxs-lookup"><span data-stu-id="f478d-128">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)  
 [<span data-ttu-id="f478d-129">Интерфейс IAssemblyEnum</span><span class="sxs-lookup"><span data-stu-id="f478d-129">IAssemblyEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyenum-interface.md)

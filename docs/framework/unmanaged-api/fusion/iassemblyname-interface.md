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
ms.openlocfilehash: aee9b986c1e26c1b2e34dac7151a00172451bbad
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796550"
---
# <a name="iassemblyname-interface"></a><span data-ttu-id="c8116-102">Интерфейс IAssemblyName</span><span class="sxs-lookup"><span data-stu-id="c8116-102">IAssemblyName Interface</span></span>
<span data-ttu-id="c8116-103">Предоставляет методы для описания и работы с уникальным удостоверением сборки.</span><span class="sxs-lookup"><span data-stu-id="c8116-103">Provides methods for describing and working with an assembly's unique identity.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c8116-104">Методы</span><span class="sxs-lookup"><span data-stu-id="c8116-104">Methods</span></span>  
  
|<span data-ttu-id="c8116-105">Метод</span><span class="sxs-lookup"><span data-stu-id="c8116-105">Method</span></span>|<span data-ttu-id="c8116-106">Описание</span><span class="sxs-lookup"><span data-stu-id="c8116-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c8116-107">Метод Clone</span><span class="sxs-lookup"><span data-stu-id="c8116-107">Clone Method</span></span>](iassemblyname-clone-method.md)|<span data-ttu-id="c8116-108">Создает неполную копию этого `IAssemblyName` объекта.</span><span class="sxs-lookup"><span data-stu-id="c8116-108">Creates a shallow copy of this `IAssemblyName` object.</span></span>|  
|[<span data-ttu-id="c8116-109">Метод Finalize</span><span class="sxs-lookup"><span data-stu-id="c8116-109">Finalize Method</span></span>](iassemblyname-finalize-method.md)|<span data-ttu-id="c8116-110">Разрешает этому `IAssemblyName` объекту освобождать ресурсы и выполнять другие операции очистки перед вызовом деструктора.</span><span class="sxs-lookup"><span data-stu-id="c8116-110">Allows this `IAssemblyName` object to release resources and perform other cleanup operations before its destructor is called.</span></span>|  
|[<span data-ttu-id="c8116-111">Метод GetDisplayName</span><span class="sxs-lookup"><span data-stu-id="c8116-111">GetDisplayName Method</span></span>](iassemblyname-getdisplayname-method.md)|<span data-ttu-id="c8116-112">Возвращает удобное для восприятия имя сборки, на которую ссылается `IAssemblyName` этот объект.</span><span class="sxs-lookup"><span data-stu-id="c8116-112">Gets the human-readable name of the assembly referenced by this `IAssemblyName` object.</span></span>|  
|[<span data-ttu-id="c8116-113">Метод GetName</span><span class="sxs-lookup"><span data-stu-id="c8116-113">GetName Method</span></span>](iassemblyname-getname-method.md)|<span data-ttu-id="c8116-114">Возвращает простое незашифрованное имя сборки, на которую ссылается этот `IAssemblyName` объект.</span><span class="sxs-lookup"><span data-stu-id="c8116-114">Gets the simple, unencrypted name of the assembly referenced by this `IAssemblyName` object.</span></span>|  
|[<span data-ttu-id="c8116-115">Метод GetProperty</span><span class="sxs-lookup"><span data-stu-id="c8116-115">GetProperty Method</span></span>](iassemblyname-getproperty-method.md)|<span data-ttu-id="c8116-116">Возвращает указатель на свойство, на которое ссылается указанный `PropertyId`объект.</span><span class="sxs-lookup"><span data-stu-id="c8116-116">Gets a pointer to the property referenced by the specified `PropertyId`.</span></span>|  
|[<span data-ttu-id="c8116-117">Метод GetVersion</span><span class="sxs-lookup"><span data-stu-id="c8116-117">GetVersion Method</span></span>](iassemblyname-getversion-method.md)|<span data-ttu-id="c8116-118">Возвращает сведения о версии для сборки, на которую ссылается `IAssemblyName` этот объект.</span><span class="sxs-lookup"><span data-stu-id="c8116-118">Gets the version information for the assembly referenced by this `IAssemblyName` object.</span></span>|  
|[<span data-ttu-id="c8116-119">Метод IsEqual</span><span class="sxs-lookup"><span data-stu-id="c8116-119">IsEqual Method</span></span>](iassemblyname-isequal-method.md)|<span data-ttu-id="c8116-120">Определяет, равен ли `IAssemblyName` указанный объект этому `IAssemblyName`объекту на основе указанных флагов сравнения.</span><span class="sxs-lookup"><span data-stu-id="c8116-120">Determines whether a specified `IAssemblyName` object is equal to this `IAssemblyName`, based on the specified comparison flags.</span></span>|  
|[<span data-ttu-id="c8116-121">Метод SetProperty</span><span class="sxs-lookup"><span data-stu-id="c8116-121">SetProperty Method</span></span>](iassemblyname-setproperty-method.md)|<span data-ttu-id="c8116-122">Задает значение свойства, на которое ссылается указанный `PropertyId`объект.</span><span class="sxs-lookup"><span data-stu-id="c8116-122">Sets the value of the property referenced by the specified `PropertyId`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c8116-123">Требования</span><span class="sxs-lookup"><span data-stu-id="c8116-123">Requirements</span></span>  
 <span data-ttu-id="c8116-124">**Платформ** См. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c8116-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c8116-125">**Заголовок.** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="c8116-125">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="c8116-126">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c8116-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8116-127">См. также</span><span class="sxs-lookup"><span data-stu-id="c8116-127">See also</span></span>

- [<span data-ttu-id="c8116-128">Интерфейсы Fusion</span><span class="sxs-lookup"><span data-stu-id="c8116-128">Fusion Interfaces</span></span>](fusion-interfaces.md)
- [<span data-ttu-id="c8116-129">Интерфейс IAssemblyEnum</span><span class="sxs-lookup"><span data-stu-id="c8116-129">IAssemblyEnum Interface</span></span>](iassemblyenum-interface.md)

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
ms.openlocfilehash: de49d66667033dfc6918b139f90cd5523661597f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134313"
---
# <a name="iassemblyname-interface"></a><span data-ttu-id="53e37-102">Интерфейс IAssemblyName</span><span class="sxs-lookup"><span data-stu-id="53e37-102">IAssemblyName Interface</span></span>
<span data-ttu-id="53e37-103">Предоставляет методы для описания и работы с уникальным удостоверением сборки.</span><span class="sxs-lookup"><span data-stu-id="53e37-103">Provides methods for describing and working with an assembly's unique identity.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="53e37-104">Методы</span><span class="sxs-lookup"><span data-stu-id="53e37-104">Methods</span></span>  
  
|<span data-ttu-id="53e37-105">Метод</span><span class="sxs-lookup"><span data-stu-id="53e37-105">Method</span></span>|<span data-ttu-id="53e37-106">Описание</span><span class="sxs-lookup"><span data-stu-id="53e37-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="53e37-107">Метод Clone</span><span class="sxs-lookup"><span data-stu-id="53e37-107">Clone Method</span></span>](iassemblyname-clone-method.md)|<span data-ttu-id="53e37-108">Создает неполную копию этого объекта `IAssemblyName`.</span><span class="sxs-lookup"><span data-stu-id="53e37-108">Creates a shallow copy of this `IAssemblyName` object.</span></span>|  
|[<span data-ttu-id="53e37-109">Метод Finalize</span><span class="sxs-lookup"><span data-stu-id="53e37-109">Finalize Method</span></span>](iassemblyname-finalize-method.md)|<span data-ttu-id="53e37-110">Позволяет этому объекту `IAssemblyName` освобождать ресурсы и выполнять другие операции очистки перед вызовом деструктора.</span><span class="sxs-lookup"><span data-stu-id="53e37-110">Allows this `IAssemblyName` object to release resources and perform other cleanup operations before its destructor is called.</span></span>|  
|[<span data-ttu-id="53e37-111">Метод GetDisplayName</span><span class="sxs-lookup"><span data-stu-id="53e37-111">GetDisplayName Method</span></span>](iassemblyname-getdisplayname-method.md)|<span data-ttu-id="53e37-112">Возвращает удобное для восприятия имя сборки, на которую ссылается этот объект `IAssemblyName`.</span><span class="sxs-lookup"><span data-stu-id="53e37-112">Gets the human-readable name of the assembly referenced by this `IAssemblyName` object.</span></span>|  
|[<span data-ttu-id="53e37-113">Метод GetName</span><span class="sxs-lookup"><span data-stu-id="53e37-113">GetName Method</span></span>](iassemblyname-getname-method.md)|<span data-ttu-id="53e37-114">Возвращает простое незашифрованное имя сборки, на которую ссылается данный объект `IAssemblyName`.</span><span class="sxs-lookup"><span data-stu-id="53e37-114">Gets the simple, unencrypted name of the assembly referenced by this `IAssemblyName` object.</span></span>|  
|[<span data-ttu-id="53e37-115">Метод GetProperty</span><span class="sxs-lookup"><span data-stu-id="53e37-115">GetProperty Method</span></span>](iassemblyname-getproperty-method.md)|<span data-ttu-id="53e37-116">Возвращает указатель на свойство, на которое ссылается заданный `PropertyId`.</span><span class="sxs-lookup"><span data-stu-id="53e37-116">Gets a pointer to the property referenced by the specified `PropertyId`.</span></span>|  
|[<span data-ttu-id="53e37-117">Метод GetVersion</span><span class="sxs-lookup"><span data-stu-id="53e37-117">GetVersion Method</span></span>](iassemblyname-getversion-method.md)|<span data-ttu-id="53e37-118">Возвращает сведения о версии для сборки, на которую ссылается данный объект `IAssemblyName`.</span><span class="sxs-lookup"><span data-stu-id="53e37-118">Gets the version information for the assembly referenced by this `IAssemblyName` object.</span></span>|  
|[<span data-ttu-id="53e37-119">Метод IsEqual</span><span class="sxs-lookup"><span data-stu-id="53e37-119">IsEqual Method</span></span>](iassemblyname-isequal-method.md)|<span data-ttu-id="53e37-120">Определяет, равен ли указанный объект `IAssemblyName` этому `IAssemblyName`на основе указанных флагов сравнения.</span><span class="sxs-lookup"><span data-stu-id="53e37-120">Determines whether a specified `IAssemblyName` object is equal to this `IAssemblyName`, based on the specified comparison flags.</span></span>|  
|[<span data-ttu-id="53e37-121">Метод SetProperty</span><span class="sxs-lookup"><span data-stu-id="53e37-121">SetProperty Method</span></span>](iassemblyname-setproperty-method.md)|<span data-ttu-id="53e37-122">Задает значение свойства, на которое ссылается заданная `PropertyId`.</span><span class="sxs-lookup"><span data-stu-id="53e37-122">Sets the value of the property referenced by the specified `PropertyId`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="53e37-123">Требования</span><span class="sxs-lookup"><span data-stu-id="53e37-123">Requirements</span></span>  
 <span data-ttu-id="53e37-124">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="53e37-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="53e37-125">**Заголовок:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="53e37-125">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="53e37-126">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="53e37-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53e37-127">См. также</span><span class="sxs-lookup"><span data-stu-id="53e37-127">See also</span></span>

- [<span data-ttu-id="53e37-128">Интерфейсы Fusion</span><span class="sxs-lookup"><span data-stu-id="53e37-128">Fusion Interfaces</span></span>](fusion-interfaces.md)
- [<span data-ttu-id="53e37-129">Интерфейс IAssemblyEnum</span><span class="sxs-lookup"><span data-stu-id="53e37-129">IAssemblyEnum Interface</span></span>](iassemblyenum-interface.md)

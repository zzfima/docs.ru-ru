---
title: "Структуры размещения"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- hosting structures [.NET Framework]
- unmanaged structures [.NET Framework], hosting
- structures [.NET Framework hosting]
ms.assetid: 492e010f-7493-4134-9505-f7008ccdaae6
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 24f6d667399d788d12d368832ed4d8638d29a0f5
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="hosting-structures"></a><span data-ttu-id="e16f6-102">Структуры размещения</span><span class="sxs-lookup"><span data-stu-id="e16f6-102">Hosting Structures</span></span>
<span data-ttu-id="e16f6-103">В этом разделе описываются неуправляемые структуры, которые использует API размещения.</span><span class="sxs-lookup"><span data-stu-id="e16f6-103">This section describes the unmanaged structures that the hosting API uses.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e16f6-104">Содержание</span><span class="sxs-lookup"><span data-stu-id="e16f6-104">In This Section</span></span>  
 [<span data-ttu-id="e16f6-105">Assemblybindinfo-структура</span><span class="sxs-lookup"><span data-stu-id="e16f6-105">AssemblyBindInfo Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/assemblybindinfo-structure.md)  
 <span data-ttu-id="e16f6-106">Содержит подробные сведения о сборке, на которую указывает ссылка.</span><span class="sxs-lookup"><span data-stu-id="e16f6-106">Provides detailed information about the referenced assembly.</span></span>  
  
 [<span data-ttu-id="e16f6-107">Bucketparameters-структура</span><span class="sxs-lookup"><span data-stu-id="e16f6-107">BucketParameters Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/bucketparameters-structure.md)  
 <span data-ttu-id="e16f6-108">Хранит имя типа события и параметры для текущего исключения, связанного с событием.</span><span class="sxs-lookup"><span data-stu-id="e16f6-108">Stores the type name of an event and the parameters for the current exception that is associated with the event.</span></span>  
  
 [<span data-ttu-id="e16f6-109">COR_GC_STATS-структура</span><span class="sxs-lookup"><span data-stu-id="e16f6-109">COR_GC_STATS Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md)  
 <span data-ttu-id="e16f6-110">Предоставляет статистику по механизм сборки мусора среды common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="e16f6-110">Provides statistics about the garbage collection mechanism of the common language runtime (CLR).</span></span>  
  
 [<span data-ttu-id="e16f6-111">COR_GC_THREAD_STATS-структура</span><span class="sxs-lookup"><span data-stu-id="e16f6-111">COR_GC_THREAD_STATS Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/cor-gc-thread-stats-structure.md)  
 <span data-ttu-id="e16f6-112">Содержит статистику потоков сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="e16f6-112">Contains per-thread statistics pertaining to garbage collection.</span></span>  
  
 [<span data-ttu-id="e16f6-113">CustomDumpItem-структура</span><span class="sxs-lookup"><span data-stu-id="e16f6-113">CustomDumpItem Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/customdumpitem-structure.md)  
 <span data-ttu-id="e16f6-114">Описывает элемент, добавляемый в пользовательский дамп отчеты об ошибках.</span><span class="sxs-lookup"><span data-stu-id="e16f6-114">Describes an item to be added to a custom dump in error reporting.</span></span>  
  
 [<span data-ttu-id="e16f6-115">MDAInfo-структура</span><span class="sxs-lookup"><span data-stu-id="e16f6-115">MDAInfo Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/mdainfo-structure.md)  
 <span data-ttu-id="e16f6-116">Предоставляет подробные сведения о `Event_MDAFired` событие, которое инициирует создание управляемого помощника по отладке (MDA).</span><span class="sxs-lookup"><span data-stu-id="e16f6-116">Provides details about the `Event_MDAFired` event, which triggers the creation of a managed debugging assistant (MDA).</span></span>  
  
 [<span data-ttu-id="e16f6-117">Modulebindinfo-структура</span><span class="sxs-lookup"><span data-stu-id="e16f6-117">ModuleBindInfo Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/modulebindinfo-structure.md)  
 <span data-ttu-id="e16f6-118">Предоставляет подробные сведения о модуле, на который указывает ссылка и сборки, содержащей его.</span><span class="sxs-lookup"><span data-stu-id="e16f6-118">Provides detailed information about the referenced module and the assembly that contains it.</span></span>  
  
 [<span data-ttu-id="e16f6-119">Stackoverflowinfo-структура</span><span class="sxs-lookup"><span data-stu-id="e16f6-119">StackOverflowInfo Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/stackoverflowinfo-structure.md)  
 <span data-ttu-id="e16f6-120">Сохраняет тип произошедшего переполнения и сведения о исключение возникло из-за переполнения.</span><span class="sxs-lookup"><span data-stu-id="e16f6-120">Stores the type of overflow that occurred and information on the exception that was thrown due to the overflow.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="e16f6-121">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="e16f6-121">Related Sections</span></span>  
 [<span data-ttu-id="e16f6-122">Размещение компонентных классов</span><span class="sxs-lookup"><span data-stu-id="e16f6-122">Hosting Coclasses</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-coclasses.md)  
  
 [<span data-ttu-id="e16f6-123">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="e16f6-123">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
  
 [<span data-ttu-id="e16f6-124">Устаревшие функции размещения CLR</span><span class="sxs-lookup"><span data-stu-id="e16f6-124">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)  
  
 [<span data-ttu-id="e16f6-125">Перечисления размещения</span><span class="sxs-lookup"><span data-stu-id="e16f6-125">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)

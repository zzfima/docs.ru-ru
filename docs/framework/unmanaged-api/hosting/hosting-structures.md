---
title: Структуры размещения
ms.date: 03/30/2017
helpviewer_keywords:
- hosting structures [.NET Framework]
- unmanaged structures [.NET Framework], hosting
- structures [.NET Framework hosting]
ms.assetid: 492e010f-7493-4134-9505-f7008ccdaae6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 01b12af8c3c3a2f834827ff14665050e07b31467
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61985599"
---
# <a name="hosting-structures"></a><span data-ttu-id="128d4-102">Структуры размещения</span><span class="sxs-lookup"><span data-stu-id="128d4-102">Hosting Structures</span></span>
<span data-ttu-id="128d4-103">В этом разделе описаны неуправляемые структуры, которые использует API размещения.</span><span class="sxs-lookup"><span data-stu-id="128d4-103">This section describes the unmanaged structures that the hosting API uses.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="128d4-104">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="128d4-104">In This Section</span></span>  
 [<span data-ttu-id="128d4-105">Структура AssemblyBindInfo</span><span class="sxs-lookup"><span data-stu-id="128d4-105">AssemblyBindInfo Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/assemblybindinfo-structure.md)  
 <span data-ttu-id="128d4-106">Содержит подробные сведения о сборке, на которую указывает ссылка.</span><span class="sxs-lookup"><span data-stu-id="128d4-106">Provides detailed information about the referenced assembly.</span></span>  
  
 [<span data-ttu-id="128d4-107">Структура BucketParameters</span><span class="sxs-lookup"><span data-stu-id="128d4-107">BucketParameters Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/bucketparameters-structure.md)  
 <span data-ttu-id="128d4-108">Хранит имя типа события и параметры для текущего исключения, связанного с событием.</span><span class="sxs-lookup"><span data-stu-id="128d4-108">Stores the type name of an event and the parameters for the current exception that is associated with the event.</span></span>  
  
 [<span data-ttu-id="128d4-109">Структура COR_GC_STATS</span><span class="sxs-lookup"><span data-stu-id="128d4-109">COR_GC_STATS Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md)  
 <span data-ttu-id="128d4-110">Предоставляет статистику механизм сбора мусора общеязыковой среды выполнения (CLR).</span><span class="sxs-lookup"><span data-stu-id="128d4-110">Provides statistics about the garbage collection mechanism of the common language runtime (CLR).</span></span>  
  
 [<span data-ttu-id="128d4-111">Структура COR_GC_THREAD_STATS</span><span class="sxs-lookup"><span data-stu-id="128d4-111">COR_GC_THREAD_STATS Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/cor-gc-thread-stats-structure.md)  
 <span data-ttu-id="128d4-112">Содержит статистику по потокам, относящиеся к сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="128d4-112">Contains per-thread statistics pertaining to garbage collection.</span></span>  
  
 [<span data-ttu-id="128d4-113">Структура CustomDumpItem</span><span class="sxs-lookup"><span data-stu-id="128d4-113">CustomDumpItem Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/customdumpitem-structure.md)  
 <span data-ttu-id="128d4-114">Описывает элемент, добавляемый в пользовательский дамп отчеты об ошибках.</span><span class="sxs-lookup"><span data-stu-id="128d4-114">Describes an item to be added to a custom dump in error reporting.</span></span>  
  
 [<span data-ttu-id="128d4-115">Структура MDAInfo</span><span class="sxs-lookup"><span data-stu-id="128d4-115">MDAInfo Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/mdainfo-structure.md)  
 <span data-ttu-id="128d4-116">Предоставляет сведения о `Event_MDAFired` событие, которое инициирует создание помощник по отладке управляемого (кода MDA).</span><span class="sxs-lookup"><span data-stu-id="128d4-116">Provides details about the `Event_MDAFired` event, which triggers the creation of a managed debugging assistant (MDA).</span></span>  
  
 [<span data-ttu-id="128d4-117">Структура ModuleBindInfo</span><span class="sxs-lookup"><span data-stu-id="128d4-117">ModuleBindInfo Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/modulebindinfo-structure.md)  
 <span data-ttu-id="128d4-118">Предоставляет подробные сведения о модуле, на которые имеются ссылки и сборки, содержащей его.</span><span class="sxs-lookup"><span data-stu-id="128d4-118">Provides detailed information about the referenced module and the assembly that contains it.</span></span>  
  
 [<span data-ttu-id="128d4-119">Структура StackOverflowInfo</span><span class="sxs-lookup"><span data-stu-id="128d4-119">StackOverflowInfo Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/stackoverflowinfo-structure.md)  
 <span data-ttu-id="128d4-120">Сохраняет тип произошедшего переполнения и сведения на исключение, вызванное исключение из-за переполнения.</span><span class="sxs-lookup"><span data-stu-id="128d4-120">Stores the type of overflow that occurred and information on the exception that was thrown due to the overflow.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="128d4-121">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="128d4-121">Related Sections</span></span>  
 [<span data-ttu-id="128d4-122">Размещение коклассов</span><span class="sxs-lookup"><span data-stu-id="128d4-122">Hosting Coclasses</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-coclasses.md)  
  
 [<span data-ttu-id="128d4-123">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="128d4-123">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
  
 [<span data-ttu-id="128d4-124">Устаревшие функции размещения CLR</span><span class="sxs-lookup"><span data-stu-id="128d4-124">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)  
  
 [<span data-ttu-id="128d4-125">Размещение перечислений</span><span class="sxs-lookup"><span data-stu-id="128d4-125">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)

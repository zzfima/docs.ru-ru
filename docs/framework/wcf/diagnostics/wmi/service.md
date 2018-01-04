---
title: "Служба"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 999806e1-6376-409e-b998-b0af391adfe7
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f7b631ede7bd011a92003dc5f6083c1c427d990e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="service"></a><span data-ttu-id="1948c-102">Служба</span><span class="sxs-lookup"><span data-stu-id="1948c-102">Service</span></span>
<span data-ttu-id="1948c-103">Служба</span><span class="sxs-lookup"><span data-stu-id="1948c-103">Service</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1948c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1948c-104">Syntax</span></span>  
  
```  
class Service  
{  
  string BaseAddresses[];  
  Behavior Behaviors[];  
  string ConfigurationName;  
  string CounterInstanceName;  
  string DistinguishedName;  
  string Extensions[];  
  string Metadata[];  
  string Name;  
  string Namespace;  
  datetime Opened;  
  Channel OutgoingChannels[];  
  sint32 ProcessId;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="1948c-105">Методы</span><span class="sxs-lookup"><span data-stu-id="1948c-105">Methods</span></span>  
 <span data-ttu-id="1948c-106">Класс Service не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="1948c-106">The Service class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="1948c-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="1948c-107">Properties</span></span>  
 <span data-ttu-id="1948c-108">Класс Service имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="1948c-108">The Service class has the following properties:</span></span>  
  
### <a name="baseaddresses"></a><span data-ttu-id="1948c-109">BaseAddresses</span><span class="sxs-lookup"><span data-stu-id="1948c-109">BaseAddresses</span></span>  
 <span data-ttu-id="1948c-110">Тип данных: массив строк</span><span class="sxs-lookup"><span data-stu-id="1948c-110">Data type: string array</span></span>  
  
 <span data-ttu-id="1948c-111">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="1948c-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="1948c-112">Базовые адреса, используемые службой.</span><span class="sxs-lookup"><span data-stu-id="1948c-112">The base addresses used by the service.</span></span>  
  
### <a name="behaviors"></a><span data-ttu-id="1948c-113">поведения</span><span class="sxs-lookup"><span data-stu-id="1948c-113">Behaviors</span></span>  
 <span data-ttu-id="1948c-114">Тип данных: массив Behavior</span><span class="sxs-lookup"><span data-stu-id="1948c-114">Data type: Behavior array</span></span>  
  
 <span data-ttu-id="1948c-115">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="1948c-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="1948c-116">Поведения, связанные с этой службой.</span><span class="sxs-lookup"><span data-stu-id="1948c-116">The behaviors associated with this service.</span></span>  
  
### <a name="configurationname"></a><span data-ttu-id="1948c-117">ConfigurationName</span><span class="sxs-lookup"><span data-stu-id="1948c-117">ConfigurationName</span></span>  
 <span data-ttu-id="1948c-118">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="1948c-118">Data type: string</span></span>  
  
 <span data-ttu-id="1948c-119">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="1948c-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="1948c-120">ServiceElement_BehaviorConfiguration</span><span class="sxs-lookup"><span data-stu-id="1948c-120">ServiceElement_BehaviorConfiguration</span></span>  
  
### <a name="counterinstancename"></a><span data-ttu-id="1948c-121">CounterInstanceName</span><span class="sxs-lookup"><span data-stu-id="1948c-121">CounterInstanceName</span></span>  
 <span data-ttu-id="1948c-122">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="1948c-122">Data type: string</span></span>  
  
 <span data-ttu-id="1948c-123">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="1948c-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="1948c-124">Имя экземпляра счетчиков производительности службы.</span><span class="sxs-lookup"><span data-stu-id="1948c-124">Instance name of the instance of the performance counters of the service.</span></span>  
  
### <a name="distinguishedname"></a><span data-ttu-id="1948c-125">DistinguishedName</span><span class="sxs-lookup"><span data-stu-id="1948c-125">DistinguishedName</span></span>  
 <span data-ttu-id="1948c-126">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="1948c-126">Data type: string</span></span>  
  
 <span data-ttu-id="1948c-127">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="1948c-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="1948c-128">Имя службы по адресу.</span><span class="sxs-lookup"><span data-stu-id="1948c-128">Service name at the address.</span></span>  
  
### <a name="extensions"></a><span data-ttu-id="1948c-129">Расширения</span><span class="sxs-lookup"><span data-stu-id="1948c-129">Extensions</span></span>  
 <span data-ttu-id="1948c-130">Тип данных: массив строк</span><span class="sxs-lookup"><span data-stu-id="1948c-130">Data type: string array</span></span>  
  
 <span data-ttu-id="1948c-131">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="1948c-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="1948c-132">Контексты экземпляра для расширений экземпляра службы.</span><span class="sxs-lookup"><span data-stu-id="1948c-132">The instance contexts for the extensions of the service instance.</span></span>  
  
### <a name="metadata"></a><span data-ttu-id="1948c-133">Метаданные</span><span class="sxs-lookup"><span data-stu-id="1948c-133">Metadata</span></span>  
 <span data-ttu-id="1948c-134">Тип данных: массив строк</span><span class="sxs-lookup"><span data-stu-id="1948c-134">Data type: string array</span></span>  
  
 <span data-ttu-id="1948c-135">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="1948c-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="1948c-136">Параметры метаданных службы.</span><span class="sxs-lookup"><span data-stu-id="1948c-136">The service metadata settings.</span></span>  
  
### <a name="name"></a><span data-ttu-id="1948c-137">name</span><span class="sxs-lookup"><span data-stu-id="1948c-137">Name</span></span>  
 <span data-ttu-id="1948c-138">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="1948c-138">Data type: string</span></span>  
  
 <span data-ttu-id="1948c-139">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="1948c-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="1948c-140">Уникальное имя службы.</span><span class="sxs-lookup"><span data-stu-id="1948c-140">The unique name of this service.</span></span>  
  
### <a name="namespace"></a><span data-ttu-id="1948c-141">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="1948c-141">Namespace</span></span>  
 <span data-ttu-id="1948c-142">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="1948c-142">Data type: string</span></span>  
  
 <span data-ttu-id="1948c-143">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="1948c-143">Access type: Read-only</span></span>  
  
 <span data-ttu-id="1948c-144">Пространство имен службы.</span><span class="sxs-lookup"><span data-stu-id="1948c-144">The namespace of the service.</span></span>  
  
### <a name="opened"></a><span data-ttu-id="1948c-145">Открыто</span><span class="sxs-lookup"><span data-stu-id="1948c-145">Opened</span></span>  
 <span data-ttu-id="1948c-146">Тип данных: datetime</span><span class="sxs-lookup"><span data-stu-id="1948c-146">Data type: datetime</span></span>  
  
 <span data-ttu-id="1948c-147">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="1948c-147">Access type: Read-only</span></span>  
  
 <span data-ttu-id="1948c-148">Время открытия службы.</span><span class="sxs-lookup"><span data-stu-id="1948c-148">The time the service was opened.</span></span>  
  
### <a name="outgoingchannels"></a><span data-ttu-id="1948c-149">OutgoingChannels</span><span class="sxs-lookup"><span data-stu-id="1948c-149">OutgoingChannels</span></span>  
 <span data-ttu-id="1948c-150">Тип данных: массив Channel</span><span class="sxs-lookup"><span data-stu-id="1948c-150">Data type: Channel array</span></span>  
  
 <span data-ttu-id="1948c-151">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="1948c-151">Access type: Read-only</span></span>  
  
 <span data-ttu-id="1948c-152">Каналы, исходящие из экземпляра службы.</span><span class="sxs-lookup"><span data-stu-id="1948c-152">The channels that are outgoing from the service instance.</span></span>  
  
### <a name="processid"></a><span data-ttu-id="1948c-153">ProcessId</span><span class="sxs-lookup"><span data-stu-id="1948c-153">ProcessId</span></span>  
 <span data-ttu-id="1948c-154">Тип данных: sint32</span><span class="sxs-lookup"><span data-stu-id="1948c-154">Data type: sint32</span></span>  
  
 <span data-ttu-id="1948c-155">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="1948c-155">Access type: Read-only</span></span>  
  
 <span data-ttu-id="1948c-156">Возвращает ИД процесса, который размещает службу.</span><span class="sxs-lookup"><span data-stu-id="1948c-156">The process id of the process that hosts the service.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1948c-157">Требования</span><span class="sxs-lookup"><span data-stu-id="1948c-157">Requirements</span></span>  
  
|<span data-ttu-id="1948c-158">MOF</span><span class="sxs-lookup"><span data-stu-id="1948c-158">MOF</span></span>|<span data-ttu-id="1948c-159">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="1948c-159">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="1948c-160">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="1948c-160">Namespace</span></span>|<span data-ttu-id="1948c-161">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="1948c-161">Defined in root\ServiceModel</span></span>|

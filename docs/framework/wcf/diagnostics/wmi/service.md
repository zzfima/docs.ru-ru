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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: bd784b470810e16b86ba7537b1f45681ac3e1ed1
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="service"></a><span data-ttu-id="73d31-102">Служба</span><span class="sxs-lookup"><span data-stu-id="73d31-102">Service</span></span>
<span data-ttu-id="73d31-103">Служба</span><span class="sxs-lookup"><span data-stu-id="73d31-103">Service</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="73d31-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="73d31-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="73d31-105">Методы</span><span class="sxs-lookup"><span data-stu-id="73d31-105">Methods</span></span>  
 <span data-ttu-id="73d31-106">Класс Service не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="73d31-106">The Service class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="73d31-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="73d31-107">Properties</span></span>  
 <span data-ttu-id="73d31-108">Класс Service имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="73d31-108">The Service class has the following properties:</span></span>  
  
### <a name="baseaddresses"></a><span data-ttu-id="73d31-109">BaseAddresses</span><span class="sxs-lookup"><span data-stu-id="73d31-109">BaseAddresses</span></span>  
 <span data-ttu-id="73d31-110">Тип данных: массив строк</span><span class="sxs-lookup"><span data-stu-id="73d31-110">Data type: string array</span></span>  
  
 <span data-ttu-id="73d31-111">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="73d31-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="73d31-112">Базовые адреса, используемые службой.</span><span class="sxs-lookup"><span data-stu-id="73d31-112">The base addresses used by the service.</span></span>  
  
### <a name="behaviors"></a><span data-ttu-id="73d31-113">Расширения функциональности</span><span class="sxs-lookup"><span data-stu-id="73d31-113">Behaviors</span></span>  
 <span data-ttu-id="73d31-114">Тип данных: массив Behavior</span><span class="sxs-lookup"><span data-stu-id="73d31-114">Data type: Behavior array</span></span>  
  
 <span data-ttu-id="73d31-115">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="73d31-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="73d31-116">Поведения, связанные с этой службой.</span><span class="sxs-lookup"><span data-stu-id="73d31-116">The behaviors associated with this service.</span></span>  
  
### <a name="configurationname"></a><span data-ttu-id="73d31-117">ConfigurationName</span><span class="sxs-lookup"><span data-stu-id="73d31-117">ConfigurationName</span></span>  
 <span data-ttu-id="73d31-118">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="73d31-118">Data type: string</span></span>  
  
 <span data-ttu-id="73d31-119">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="73d31-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="73d31-120">ServiceElement_BehaviorConfiguration</span><span class="sxs-lookup"><span data-stu-id="73d31-120">ServiceElement_BehaviorConfiguration</span></span>  
  
### <a name="counterinstancename"></a><span data-ttu-id="73d31-121">CounterInstanceName</span><span class="sxs-lookup"><span data-stu-id="73d31-121">CounterInstanceName</span></span>  
 <span data-ttu-id="73d31-122">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="73d31-122">Data type: string</span></span>  
  
 <span data-ttu-id="73d31-123">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="73d31-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="73d31-124">Имя экземпляра счетчиков производительности службы.</span><span class="sxs-lookup"><span data-stu-id="73d31-124">Instance name of the instance of the performance counters of the service.</span></span>  
  
### <a name="distinguishedname"></a><span data-ttu-id="73d31-125">DistinguishedName</span><span class="sxs-lookup"><span data-stu-id="73d31-125">DistinguishedName</span></span>  
 <span data-ttu-id="73d31-126">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="73d31-126">Data type: string</span></span>  
  
 <span data-ttu-id="73d31-127">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="73d31-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="73d31-128">Имя службы по адресу.</span><span class="sxs-lookup"><span data-stu-id="73d31-128">Service name at the address.</span></span>  
  
### <a name="extensions"></a><span data-ttu-id="73d31-129">Расширения</span><span class="sxs-lookup"><span data-stu-id="73d31-129">Extensions</span></span>  
 <span data-ttu-id="73d31-130">Тип данных: массив строк</span><span class="sxs-lookup"><span data-stu-id="73d31-130">Data type: string array</span></span>  
  
 <span data-ttu-id="73d31-131">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="73d31-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="73d31-132">Контексты экземпляра для расширений экземпляра службы.</span><span class="sxs-lookup"><span data-stu-id="73d31-132">The instance contexts for the extensions of the service instance.</span></span>  
  
### <a name="metadata"></a><span data-ttu-id="73d31-133">Метаданные</span><span class="sxs-lookup"><span data-stu-id="73d31-133">Metadata</span></span>  
 <span data-ttu-id="73d31-134">Тип данных: массив строк</span><span class="sxs-lookup"><span data-stu-id="73d31-134">Data type: string array</span></span>  
  
 <span data-ttu-id="73d31-135">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="73d31-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="73d31-136">Параметры метаданных службы.</span><span class="sxs-lookup"><span data-stu-id="73d31-136">The service metadata settings.</span></span>  
  
### <a name="name"></a><span data-ttu-id="73d31-137">Имя</span><span class="sxs-lookup"><span data-stu-id="73d31-137">Name</span></span>  
 <span data-ttu-id="73d31-138">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="73d31-138">Data type: string</span></span>  
  
 <span data-ttu-id="73d31-139">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="73d31-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="73d31-140">Уникальное имя службы.</span><span class="sxs-lookup"><span data-stu-id="73d31-140">The unique name of this service.</span></span>  
  
### <a name="namespace"></a><span data-ttu-id="73d31-141">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="73d31-141">Namespace</span></span>  
 <span data-ttu-id="73d31-142">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="73d31-142">Data type: string</span></span>  
  
 <span data-ttu-id="73d31-143">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="73d31-143">Access type: Read-only</span></span>  
  
 <span data-ttu-id="73d31-144">Пространство имен службы.</span><span class="sxs-lookup"><span data-stu-id="73d31-144">The namespace of the service.</span></span>  
  
### <a name="opened"></a><span data-ttu-id="73d31-145">Открыто</span><span class="sxs-lookup"><span data-stu-id="73d31-145">Opened</span></span>  
 <span data-ttu-id="73d31-146">Тип данных: datetime</span><span class="sxs-lookup"><span data-stu-id="73d31-146">Data type: datetime</span></span>  
  
 <span data-ttu-id="73d31-147">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="73d31-147">Access type: Read-only</span></span>  
  
 <span data-ttu-id="73d31-148">Время открытия службы.</span><span class="sxs-lookup"><span data-stu-id="73d31-148">The time the service was opened.</span></span>  
  
### <a name="outgoingchannels"></a><span data-ttu-id="73d31-149">OutgoingChannels</span><span class="sxs-lookup"><span data-stu-id="73d31-149">OutgoingChannels</span></span>  
 <span data-ttu-id="73d31-150">Тип данных: массив Channel</span><span class="sxs-lookup"><span data-stu-id="73d31-150">Data type: Channel array</span></span>  
  
 <span data-ttu-id="73d31-151">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="73d31-151">Access type: Read-only</span></span>  
  
 <span data-ttu-id="73d31-152">Каналы, исходящие из экземпляра службы.</span><span class="sxs-lookup"><span data-stu-id="73d31-152">The channels that are outgoing from the service instance.</span></span>  
  
### <a name="processid"></a><span data-ttu-id="73d31-153">ProcessId</span><span class="sxs-lookup"><span data-stu-id="73d31-153">ProcessId</span></span>  
 <span data-ttu-id="73d31-154">Тип данных: sint32</span><span class="sxs-lookup"><span data-stu-id="73d31-154">Data type: sint32</span></span>  
  
 <span data-ttu-id="73d31-155">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="73d31-155">Access type: Read-only</span></span>  
  
 <span data-ttu-id="73d31-156">Возвращает ИД процесса, который размещает службу.</span><span class="sxs-lookup"><span data-stu-id="73d31-156">The process id of the process that hosts the service.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="73d31-157">Требования</span><span class="sxs-lookup"><span data-stu-id="73d31-157">Requirements</span></span>  
  
|<span data-ttu-id="73d31-158">MOF</span><span class="sxs-lookup"><span data-stu-id="73d31-158">MOF</span></span>|<span data-ttu-id="73d31-159">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="73d31-159">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="73d31-160">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="73d31-160">Namespace</span></span>|<span data-ttu-id="73d31-161">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="73d31-161">Defined in root\ServiceModel</span></span>|

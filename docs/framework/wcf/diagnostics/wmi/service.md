---
title: Служба
ms.date: 03/30/2017
ms.assetid: 999806e1-6376-409e-b998-b0af391adfe7
ms.openlocfilehash: 0cfeb178e26f6c93e29210accf5d7866cc1fca02
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="service"></a><span data-ttu-id="8f54f-102">Служба</span><span class="sxs-lookup"><span data-stu-id="8f54f-102">Service</span></span>
<span data-ttu-id="8f54f-103">Служба</span><span class="sxs-lookup"><span data-stu-id="8f54f-103">Service</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8f54f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8f54f-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="8f54f-105">Методы</span><span class="sxs-lookup"><span data-stu-id="8f54f-105">Methods</span></span>  
 <span data-ttu-id="8f54f-106">Класс Service не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="8f54f-106">The Service class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="8f54f-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="8f54f-107">Properties</span></span>  
 <span data-ttu-id="8f54f-108">Класс Service имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="8f54f-108">The Service class has the following properties:</span></span>  
  
### <a name="baseaddresses"></a><span data-ttu-id="8f54f-109">BaseAddresses</span><span class="sxs-lookup"><span data-stu-id="8f54f-109">BaseAddresses</span></span>  
 <span data-ttu-id="8f54f-110">Тип данных: массив строк</span><span class="sxs-lookup"><span data-stu-id="8f54f-110">Data type: string array</span></span>  
  
 <span data-ttu-id="8f54f-111">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="8f54f-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="8f54f-112">Базовые адреса, используемые службой.</span><span class="sxs-lookup"><span data-stu-id="8f54f-112">The base addresses used by the service.</span></span>  
  
### <a name="behaviors"></a><span data-ttu-id="8f54f-113">поведения</span><span class="sxs-lookup"><span data-stu-id="8f54f-113">Behaviors</span></span>  
 <span data-ttu-id="8f54f-114">Тип данных: массив Behavior</span><span class="sxs-lookup"><span data-stu-id="8f54f-114">Data type: Behavior array</span></span>  
  
 <span data-ttu-id="8f54f-115">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="8f54f-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="8f54f-116">Поведения, связанные с этой службой.</span><span class="sxs-lookup"><span data-stu-id="8f54f-116">The behaviors associated with this service.</span></span>  
  
### <a name="configurationname"></a><span data-ttu-id="8f54f-117">ConfigurationName</span><span class="sxs-lookup"><span data-stu-id="8f54f-117">ConfigurationName</span></span>  
 <span data-ttu-id="8f54f-118">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="8f54f-118">Data type: string</span></span>  
  
 <span data-ttu-id="8f54f-119">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="8f54f-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="8f54f-120">ServiceElement_BehaviorConfiguration</span><span class="sxs-lookup"><span data-stu-id="8f54f-120">ServiceElement_BehaviorConfiguration</span></span>  
  
### <a name="counterinstancename"></a><span data-ttu-id="8f54f-121">CounterInstanceName</span><span class="sxs-lookup"><span data-stu-id="8f54f-121">CounterInstanceName</span></span>  
 <span data-ttu-id="8f54f-122">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="8f54f-122">Data type: string</span></span>  
  
 <span data-ttu-id="8f54f-123">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="8f54f-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="8f54f-124">Имя экземпляра счетчиков производительности службы.</span><span class="sxs-lookup"><span data-stu-id="8f54f-124">Instance name of the instance of the performance counters of the service.</span></span>  
  
### <a name="distinguishedname"></a><span data-ttu-id="8f54f-125">DistinguishedName</span><span class="sxs-lookup"><span data-stu-id="8f54f-125">DistinguishedName</span></span>  
 <span data-ttu-id="8f54f-126">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="8f54f-126">Data type: string</span></span>  
  
 <span data-ttu-id="8f54f-127">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="8f54f-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="8f54f-128">Имя службы по адресу.</span><span class="sxs-lookup"><span data-stu-id="8f54f-128">Service name at the address.</span></span>  
  
### <a name="extensions"></a><span data-ttu-id="8f54f-129">Расширения</span><span class="sxs-lookup"><span data-stu-id="8f54f-129">Extensions</span></span>  
 <span data-ttu-id="8f54f-130">Тип данных: массив строк</span><span class="sxs-lookup"><span data-stu-id="8f54f-130">Data type: string array</span></span>  
  
 <span data-ttu-id="8f54f-131">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="8f54f-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="8f54f-132">Контексты экземпляра для расширений экземпляра службы.</span><span class="sxs-lookup"><span data-stu-id="8f54f-132">The instance contexts for the extensions of the service instance.</span></span>  
  
### <a name="metadata"></a><span data-ttu-id="8f54f-133">Метаданные</span><span class="sxs-lookup"><span data-stu-id="8f54f-133">Metadata</span></span>  
 <span data-ttu-id="8f54f-134">Тип данных: массив строк</span><span class="sxs-lookup"><span data-stu-id="8f54f-134">Data type: string array</span></span>  
  
 <span data-ttu-id="8f54f-135">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="8f54f-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="8f54f-136">Параметры метаданных службы.</span><span class="sxs-lookup"><span data-stu-id="8f54f-136">The service metadata settings.</span></span>  
  
### <a name="name"></a><span data-ttu-id="8f54f-137">name</span><span class="sxs-lookup"><span data-stu-id="8f54f-137">Name</span></span>  
 <span data-ttu-id="8f54f-138">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="8f54f-138">Data type: string</span></span>  
  
 <span data-ttu-id="8f54f-139">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="8f54f-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="8f54f-140">Уникальное имя службы.</span><span class="sxs-lookup"><span data-stu-id="8f54f-140">The unique name of this service.</span></span>  
  
### <a name="namespace"></a><span data-ttu-id="8f54f-141">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="8f54f-141">Namespace</span></span>  
 <span data-ttu-id="8f54f-142">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="8f54f-142">Data type: string</span></span>  
  
 <span data-ttu-id="8f54f-143">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="8f54f-143">Access type: Read-only</span></span>  
  
 <span data-ttu-id="8f54f-144">Пространство имен службы.</span><span class="sxs-lookup"><span data-stu-id="8f54f-144">The namespace of the service.</span></span>  
  
### <a name="opened"></a><span data-ttu-id="8f54f-145">Открыто</span><span class="sxs-lookup"><span data-stu-id="8f54f-145">Opened</span></span>  
 <span data-ttu-id="8f54f-146">Тип данных: datetime</span><span class="sxs-lookup"><span data-stu-id="8f54f-146">Data type: datetime</span></span>  
  
 <span data-ttu-id="8f54f-147">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="8f54f-147">Access type: Read-only</span></span>  
  
 <span data-ttu-id="8f54f-148">Время открытия службы.</span><span class="sxs-lookup"><span data-stu-id="8f54f-148">The time the service was opened.</span></span>  
  
### <a name="outgoingchannels"></a><span data-ttu-id="8f54f-149">OutgoingChannels</span><span class="sxs-lookup"><span data-stu-id="8f54f-149">OutgoingChannels</span></span>  
 <span data-ttu-id="8f54f-150">Тип данных: массив Channel</span><span class="sxs-lookup"><span data-stu-id="8f54f-150">Data type: Channel array</span></span>  
  
 <span data-ttu-id="8f54f-151">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="8f54f-151">Access type: Read-only</span></span>  
  
 <span data-ttu-id="8f54f-152">Каналы, исходящие из экземпляра службы.</span><span class="sxs-lookup"><span data-stu-id="8f54f-152">The channels that are outgoing from the service instance.</span></span>  
  
### <a name="processid"></a><span data-ttu-id="8f54f-153">ProcessId</span><span class="sxs-lookup"><span data-stu-id="8f54f-153">ProcessId</span></span>  
 <span data-ttu-id="8f54f-154">Тип данных: sint32</span><span class="sxs-lookup"><span data-stu-id="8f54f-154">Data type: sint32</span></span>  
  
 <span data-ttu-id="8f54f-155">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="8f54f-155">Access type: Read-only</span></span>  
  
 <span data-ttu-id="8f54f-156">Возвращает ИД процесса, который размещает службу.</span><span class="sxs-lookup"><span data-stu-id="8f54f-156">The process id of the process that hosts the service.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8f54f-157">Требования</span><span class="sxs-lookup"><span data-stu-id="8f54f-157">Requirements</span></span>  
  
|<span data-ttu-id="8f54f-158">MOF</span><span class="sxs-lookup"><span data-stu-id="8f54f-158">MOF</span></span>|<span data-ttu-id="8f54f-159">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="8f54f-159">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="8f54f-160">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="8f54f-160">Namespace</span></span>|<span data-ttu-id="8f54f-161">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="8f54f-161">Defined in root\ServiceModel</span></span>|

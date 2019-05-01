---
title: Служба
ms.date: 03/30/2017
ms.assetid: 999806e1-6376-409e-b998-b0af391adfe7
ms.openlocfilehash: c59672b3b7617d9c28d99f7d534b6e7f2f2e9fbb
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61991449"
---
# <a name="service"></a><span data-ttu-id="6b375-102">Служба</span><span class="sxs-lookup"><span data-stu-id="6b375-102">Service</span></span>
<span data-ttu-id="6b375-103">Служба</span><span class="sxs-lookup"><span data-stu-id="6b375-103">Service</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6b375-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6b375-104">Syntax</span></span>  
  
```csharp
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
  
## <a name="methods"></a><span data-ttu-id="6b375-105">Методы</span><span class="sxs-lookup"><span data-stu-id="6b375-105">Methods</span></span>  
 <span data-ttu-id="6b375-106">Класс Service не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="6b375-106">The Service class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="6b375-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="6b375-107">Properties</span></span>  
 <span data-ttu-id="6b375-108">Класс Service имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="6b375-108">The Service class has the following properties:</span></span>  
  
### <a name="baseaddresses"></a><span data-ttu-id="6b375-109">BaseAddresses</span><span class="sxs-lookup"><span data-stu-id="6b375-109">BaseAddresses</span></span>  
 <span data-ttu-id="6b375-110">Тип данных: массив строк</span><span class="sxs-lookup"><span data-stu-id="6b375-110">Data type: string array</span></span>  
  
 <span data-ttu-id="6b375-111">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="6b375-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="6b375-112">Базовые адреса, используемые службой.</span><span class="sxs-lookup"><span data-stu-id="6b375-112">The base addresses used by the service.</span></span>  
  
### <a name="behaviors"></a><span data-ttu-id="6b375-113">поведения</span><span class="sxs-lookup"><span data-stu-id="6b375-113">Behaviors</span></span>  
 <span data-ttu-id="6b375-114">Тип данных: Массив Behavior</span><span class="sxs-lookup"><span data-stu-id="6b375-114">Data type: Behavior array</span></span>  
  
 <span data-ttu-id="6b375-115">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="6b375-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="6b375-116">Поведения, связанные с этой службой.</span><span class="sxs-lookup"><span data-stu-id="6b375-116">The behaviors associated with this service.</span></span>  
  
### <a name="configurationname"></a><span data-ttu-id="6b375-117">ConfigurationName</span><span class="sxs-lookup"><span data-stu-id="6b375-117">ConfigurationName</span></span>  
 <span data-ttu-id="6b375-118">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="6b375-118">Data type: string</span></span>  
  
 <span data-ttu-id="6b375-119">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="6b375-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="6b375-120">ServiceElement_BehaviorConfiguration</span><span class="sxs-lookup"><span data-stu-id="6b375-120">ServiceElement_BehaviorConfiguration</span></span>  
  
### <a name="counterinstancename"></a><span data-ttu-id="6b375-121">CounterInstanceName</span><span class="sxs-lookup"><span data-stu-id="6b375-121">CounterInstanceName</span></span>  
 <span data-ttu-id="6b375-122">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="6b375-122">Data type: string</span></span>  
  
 <span data-ttu-id="6b375-123">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="6b375-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="6b375-124">Имя экземпляра счетчиков производительности службы.</span><span class="sxs-lookup"><span data-stu-id="6b375-124">Instance name of the instance of the performance counters of the service.</span></span>  
  
### <a name="distinguishedname"></a><span data-ttu-id="6b375-125">DistinguishedName</span><span class="sxs-lookup"><span data-stu-id="6b375-125">DistinguishedName</span></span>  
 <span data-ttu-id="6b375-126">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="6b375-126">Data type: string</span></span>  
  
 <span data-ttu-id="6b375-127">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="6b375-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="6b375-128">Имя службы по адресу.</span><span class="sxs-lookup"><span data-stu-id="6b375-128">Service name at the address.</span></span>  
  
### <a name="extensions"></a><span data-ttu-id="6b375-129">Расширения</span><span class="sxs-lookup"><span data-stu-id="6b375-129">Extensions</span></span>  
 <span data-ttu-id="6b375-130">Тип данных: массив строк</span><span class="sxs-lookup"><span data-stu-id="6b375-130">Data type: string array</span></span>  
  
 <span data-ttu-id="6b375-131">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="6b375-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="6b375-132">Контексты экземпляра для расширений экземпляра службы.</span><span class="sxs-lookup"><span data-stu-id="6b375-132">The instance contexts for the extensions of the service instance.</span></span>  
  
### <a name="metadata"></a><span data-ttu-id="6b375-133">Метаданные</span><span class="sxs-lookup"><span data-stu-id="6b375-133">Metadata</span></span>  
 <span data-ttu-id="6b375-134">Тип данных: массив строк</span><span class="sxs-lookup"><span data-stu-id="6b375-134">Data type: string array</span></span>  
  
 <span data-ttu-id="6b375-135">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="6b375-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="6b375-136">Параметры метаданных службы.</span><span class="sxs-lookup"><span data-stu-id="6b375-136">The service metadata settings.</span></span>  
  
### <a name="name"></a><span data-ttu-id="6b375-137">name</span><span class="sxs-lookup"><span data-stu-id="6b375-137">Name</span></span>  
 <span data-ttu-id="6b375-138">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="6b375-138">Data type: string</span></span>  
  
 <span data-ttu-id="6b375-139">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="6b375-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="6b375-140">Уникальное имя службы.</span><span class="sxs-lookup"><span data-stu-id="6b375-140">The unique name of this service.</span></span>  
  
### <a name="namespace"></a><span data-ttu-id="6b375-141">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="6b375-141">Namespace</span></span>  
 <span data-ttu-id="6b375-142">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="6b375-142">Data type: string</span></span>  
  
 <span data-ttu-id="6b375-143">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="6b375-143">Access type: Read-only</span></span>  
  
 <span data-ttu-id="6b375-144">Пространство имен службы.</span><span class="sxs-lookup"><span data-stu-id="6b375-144">The namespace of the service.</span></span>  
  
### <a name="opened"></a><span data-ttu-id="6b375-145">Открыто</span><span class="sxs-lookup"><span data-stu-id="6b375-145">Opened</span></span>  
 <span data-ttu-id="6b375-146">Тип данных: datetime</span><span class="sxs-lookup"><span data-stu-id="6b375-146">Data type: datetime</span></span>  
  
 <span data-ttu-id="6b375-147">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="6b375-147">Access type: Read-only</span></span>  
  
 <span data-ttu-id="6b375-148">Время открытия службы.</span><span class="sxs-lookup"><span data-stu-id="6b375-148">The time the service was opened.</span></span>  
  
### <a name="outgoingchannels"></a><span data-ttu-id="6b375-149">OutgoingChannels</span><span class="sxs-lookup"><span data-stu-id="6b375-149">OutgoingChannels</span></span>  
 <span data-ttu-id="6b375-150">Тип данных: Массив Channel</span><span class="sxs-lookup"><span data-stu-id="6b375-150">Data type: Channel array</span></span>  
  
 <span data-ttu-id="6b375-151">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="6b375-151">Access type: Read-only</span></span>  
  
 <span data-ttu-id="6b375-152">Каналы, исходящие из экземпляра службы.</span><span class="sxs-lookup"><span data-stu-id="6b375-152">The channels that are outgoing from the service instance.</span></span>  
  
### <a name="processid"></a><span data-ttu-id="6b375-153">ProcessId</span><span class="sxs-lookup"><span data-stu-id="6b375-153">ProcessId</span></span>  
 <span data-ttu-id="6b375-154">Тип данных: sint32</span><span class="sxs-lookup"><span data-stu-id="6b375-154">Data type: sint32</span></span>  
  
 <span data-ttu-id="6b375-155">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="6b375-155">Access type: Read-only</span></span>  
  
 <span data-ttu-id="6b375-156">Возвращает ИД процесса, который размещает службу.</span><span class="sxs-lookup"><span data-stu-id="6b375-156">The process id of the process that hosts the service.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6b375-157">Требования</span><span class="sxs-lookup"><span data-stu-id="6b375-157">Requirements</span></span>  
  
|<span data-ttu-id="6b375-158">MOF</span><span class="sxs-lookup"><span data-stu-id="6b375-158">MOF</span></span>|<span data-ttu-id="6b375-159">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="6b375-159">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="6b375-160">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="6b375-160">Namespace</span></span>|<span data-ttu-id="6b375-161">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="6b375-161">Defined in root\ServiceModel</span></span>|

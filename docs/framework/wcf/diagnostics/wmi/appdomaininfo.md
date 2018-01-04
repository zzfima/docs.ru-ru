---
title: AppDomainInfo
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6610b7d8-81eb-4bec-a543-9b72ad7b6f73
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ed5053dd69628a9f5ff7318ce7fe772f42de6e24
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="appdomaininfo"></a><span data-ttu-id="cf234-102">AppDomainInfo</span><span class="sxs-lookup"><span data-stu-id="cf234-102">AppDomainInfo</span></span>
<span data-ttu-id="cf234-103">Сведения о домене приложения</span><span class="sxs-lookup"><span data-stu-id="cf234-103">Application domain information</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cf234-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cf234-104">Syntax</span></span>  
  
```  
class AppDomainInfo  
{  
  sint32 AppDomainId;  
  boolean IsDefault;  
  boolean LogMalformedMessages;  
  boolean LogMessagesAtServiceLevel;  
  boolean LogMessagesAtTransportLevel;  
  TraceListener MessageLoggingTraceListeners[];  
  string Name;  
  string PerformanceCounters;  
  sint32 ProcessId;  
  string ServiceConfigPath;  
  string TraceLevel;  
  TraceListener wmiTraceListeners[];  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="cf234-105">Методы</span><span class="sxs-lookup"><span data-stu-id="cf234-105">Methods</span></span>  
 <span data-ttu-id="cf234-106">Класс AppDomainInfo не определяет никакие методы.</span><span class="sxs-lookup"><span data-stu-id="cf234-106">The AppDomainInfo class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="cf234-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="cf234-107">Properties</span></span>  
 <span data-ttu-id="cf234-108">Класс AppDomainInfo имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="cf234-108">The AppDomainInfo class has the following properties:</span></span>  
  
### <a name="appdomainid"></a><span data-ttu-id="cf234-109">AppDomainId</span><span class="sxs-lookup"><span data-stu-id="cf234-109">AppDomainId</span></span>  
 <span data-ttu-id="cf234-110">Тип данных: sint32</span><span class="sxs-lookup"><span data-stu-id="cf234-110">Data type: sint32</span></span>  
  
 <span data-ttu-id="cf234-111">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="cf234-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="cf234-112">Идентификатор домена приложения.</span><span class="sxs-lookup"><span data-stu-id="cf234-112">The Id of the appdomain.</span></span>  
  
### <a name="isdefault"></a><span data-ttu-id="cf234-113">IsDefault</span><span class="sxs-lookup"><span data-stu-id="cf234-113">IsDefault</span></span>  
 <span data-ttu-id="cf234-114">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="cf234-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="cf234-115">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="cf234-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="cf234-116">Указывает, является ли домен приложения доменом приложения, используемым по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="cf234-116">Indicates whether the appdomain is the default appdomain.</span></span>  
  
### <a name="logmalformedmessages"></a><span data-ttu-id="cf234-117">LogMalformedMessages</span><span class="sxs-lookup"><span data-stu-id="cf234-117">LogMalformedMessages</span></span>  
 <span data-ttu-id="cf234-118">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="cf234-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="cf234-119">Тип доступа: чтение/запись</span><span class="sxs-lookup"><span data-stu-id="cf234-119">Access type: Read/Write</span></span>  
  
 <span data-ttu-id="cf234-120">Значение, указывающее, заносятся ли в журнал неправильные сообщения.</span><span class="sxs-lookup"><span data-stu-id="cf234-120">A value that specifies whether malformed messages are logged.</span></span>  
  
### <a name="logmessagesatservicelevel"></a><span data-ttu-id="cf234-121">LogMessagesAtServiceLevel</span><span class="sxs-lookup"><span data-stu-id="cf234-121">LogMessagesAtServiceLevel</span></span>  
 <span data-ttu-id="cf234-122">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="cf234-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="cf234-123">Тип доступа: чтение/запись</span><span class="sxs-lookup"><span data-stu-id="cf234-123">Access type: Read/Write</span></span>  
  
 <span data-ttu-id="cf234-124">Значение, указывающее, трассируются ли сообщения на уровне службы (перед шифрованием и преобразованиями, связанными с транспортом).</span><span class="sxs-lookup"><span data-stu-id="cf234-124">A value that specifies whether messages are traced at the service level (before encryption and transport-related transforms).</span></span>  
  
### <a name="logmessagesattransportlevel"></a><span data-ttu-id="cf234-125">LogMessagesAtTransportLevel</span><span class="sxs-lookup"><span data-stu-id="cf234-125">LogMessagesAtTransportLevel</span></span>  
 <span data-ttu-id="cf234-126">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="cf234-126">Data type: boolean</span></span>  
  
 <span data-ttu-id="cf234-127">Тип доступа: чтение/запись</span><span class="sxs-lookup"><span data-stu-id="cf234-127">Access type: Read/Write</span></span>  
  
 <span data-ttu-id="cf234-128">Значение, указывающее, трассируются ли сообщения на уровне транспорта.</span><span class="sxs-lookup"><span data-stu-id="cf234-128">A value that specifies whether messages are traced at the transport level.</span></span>  
  
### <a name="messageloggingtracelisteners"></a><span data-ttu-id="cf234-129">MessageLoggingTraceListeners</span><span class="sxs-lookup"><span data-stu-id="cf234-129">MessageLoggingTraceListeners</span></span>  
 <span data-ttu-id="cf234-130">Тип данных: массив TraceListener</span><span class="sxs-lookup"><span data-stu-id="cf234-130">Data type: TraceListener array</span></span>  
  
 <span data-ttu-id="cf234-131">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="cf234-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="cf234-132">Коллекция прослушивателей трассировки, которые ожидают передачи данных источнику трассировки System.Wmi.MessageLogging.</span><span class="sxs-lookup"><span data-stu-id="cf234-132">The collection trace listeners that listen to the System.Wmi.MessageLogging trace source.</span></span>  
  
### <a name="name"></a><span data-ttu-id="cf234-133">name</span><span class="sxs-lookup"><span data-stu-id="cf234-133">Name</span></span>  
 <span data-ttu-id="cf234-134">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="cf234-134">Data type: string</span></span>  
  
 <span data-ttu-id="cf234-135">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="cf234-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="cf234-136">Имя домена приложения.</span><span class="sxs-lookup"><span data-stu-id="cf234-136">The name of the appdomain.</span></span>  
  
### <a name="performancecounters"></a><span data-ttu-id="cf234-137">PerformanceCounters</span><span class="sxs-lookup"><span data-stu-id="cf234-137">PerformanceCounters</span></span>  
 <span data-ttu-id="cf234-138">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="cf234-138">Data type: string</span></span>  
  
 <span data-ttu-id="cf234-139">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="cf234-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="cf234-140">Область активных счетчиков производительности в домене приложения.</span><span class="sxs-lookup"><span data-stu-id="cf234-140">The scope of active performance counters in the appdomain.</span></span>  
  
### <a name="processid"></a><span data-ttu-id="cf234-141">ProcessId</span><span class="sxs-lookup"><span data-stu-id="cf234-141">ProcessId</span></span>  
 <span data-ttu-id="cf234-142">Тип данных: sint32</span><span class="sxs-lookup"><span data-stu-id="cf234-142">Data type: sint32</span></span>  
  
 <span data-ttu-id="cf234-143">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="cf234-143">Access type: Read-only</span></span>  
  
 <span data-ttu-id="cf234-144">Идентификатор процесса.</span><span class="sxs-lookup"><span data-stu-id="cf234-144">The process Id.</span></span>  
  
### <a name="serviceconfigpath"></a><span data-ttu-id="cf234-145">ServiceConfigPath</span><span class="sxs-lookup"><span data-stu-id="cf234-145">ServiceConfigPath</span></span>  
 <span data-ttu-id="cf234-146">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="cf234-146">Data type: string</span></span>  
  
 <span data-ttu-id="cf234-147">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="cf234-147">Access type: Read-only</span></span>  
  
 <span data-ttu-id="cf234-148">Путь к конфигурации службы.</span><span class="sxs-lookup"><span data-stu-id="cf234-148">The path to the configuration of the service.</span></span>  
  
### <a name="tracelevel"></a><span data-ttu-id="cf234-149">TraceLevel</span><span class="sxs-lookup"><span data-stu-id="cf234-149">TraceLevel</span></span>  
 <span data-ttu-id="cf234-150">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="cf234-150">Data type: string</span></span>  
  
 <span data-ttu-id="cf234-151">Тип доступа: чтение/запись</span><span class="sxs-lookup"><span data-stu-id="cf234-151">Access type: Read/Write</span></span>  
  
 <span data-ttu-id="cf234-152">Уровень трассировки источника трассировки System.Wmi.</span><span class="sxs-lookup"><span data-stu-id="cf234-152">The trace level of the System.Wmi trace source.</span></span>  
  
### <a name="servicemodeltracelisteners"></a><span data-ttu-id="cf234-153">ServiceModelTraceListeners</span><span class="sxs-lookup"><span data-stu-id="cf234-153">ServiceModelTraceListeners</span></span>  
 <span data-ttu-id="cf234-154">Тип данных: массив TraceListener</span><span class="sxs-lookup"><span data-stu-id="cf234-154">Data type: TraceListener array</span></span>  
  
 <span data-ttu-id="cf234-155">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="cf234-155">Access type: Read-only</span></span>  
  
 <span data-ttu-id="cf234-156">Коллекция прослушивателей, ожидающих передачи данных от источника трассировки System.ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="cf234-156">A collection of listeners from the System.ServiceModel trace source.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cf234-157">Требования</span><span class="sxs-lookup"><span data-stu-id="cf234-157">Requirements</span></span>  
  
|<span data-ttu-id="cf234-158">MOF</span><span class="sxs-lookup"><span data-stu-id="cf234-158">MOF</span></span>|<span data-ttu-id="cf234-159">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="cf234-159">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="cf234-160">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="cf234-160">Namespace</span></span>|<span data-ttu-id="cf234-161">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="cf234-161">Defined in root\ServiceModel</span></span>|

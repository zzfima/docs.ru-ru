---
title: AppDomainInfo
ms.date: 03/30/2017
ms.assetid: 6610b7d8-81eb-4bec-a543-9b72ad7b6f73
ms.openlocfilehash: 0b7f8aadbd9a9dfcdd33fc65be3a5a41ea95f5be
ms.sourcegitcommit: e42d09e5966dd9fd02847d3e7eeb4ec0877069f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2018
ms.locfileid: "49371580"
---
# <a name="appdomaininfo"></a><span data-ttu-id="c545b-102">AppDomainInfo</span><span class="sxs-lookup"><span data-stu-id="c545b-102">AppDomainInfo</span></span>
<span data-ttu-id="c545b-103">Сведения о домене приложения</span><span class="sxs-lookup"><span data-stu-id="c545b-103">Application domain information</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c545b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c545b-104">Syntax</span></span>  
  
```csharp
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
  
## <a name="methods"></a><span data-ttu-id="c545b-105">Методы</span><span class="sxs-lookup"><span data-stu-id="c545b-105">Methods</span></span>  
 <span data-ttu-id="c545b-106">Класс AppDomainInfo не определяет никакие методы.</span><span class="sxs-lookup"><span data-stu-id="c545b-106">The AppDomainInfo class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="c545b-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="c545b-107">Properties</span></span>  
 <span data-ttu-id="c545b-108">Класс AppDomainInfo имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="c545b-108">The AppDomainInfo class has the following properties:</span></span>  
  
### <a name="appdomainid"></a><span data-ttu-id="c545b-109">AppDomainId</span><span class="sxs-lookup"><span data-stu-id="c545b-109">AppDomainId</span></span>  
 <span data-ttu-id="c545b-110">Тип данных: sint32</span><span class="sxs-lookup"><span data-stu-id="c545b-110">Data type: sint32</span></span>  
  
 <span data-ttu-id="c545b-111">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="c545b-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c545b-112">Идентификатор домена приложения.</span><span class="sxs-lookup"><span data-stu-id="c545b-112">The Id of the appdomain.</span></span>  
  
### <a name="isdefault"></a><span data-ttu-id="c545b-113">IsDefault</span><span class="sxs-lookup"><span data-stu-id="c545b-113">IsDefault</span></span>  
 <span data-ttu-id="c545b-114">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="c545b-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="c545b-115">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="c545b-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c545b-116">Указывает, является ли домен приложения доменом приложения, используемым по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="c545b-116">Indicates whether the appdomain is the default appdomain.</span></span>  
  
### <a name="logmalformedmessages"></a><span data-ttu-id="c545b-117">LogMalformedMessages</span><span class="sxs-lookup"><span data-stu-id="c545b-117">LogMalformedMessages</span></span>  
 <span data-ttu-id="c545b-118">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="c545b-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="c545b-119">Тип доступа: чтение/запись</span><span class="sxs-lookup"><span data-stu-id="c545b-119">Access type: Read/Write</span></span>  
  
 <span data-ttu-id="c545b-120">Значение, указывающее, заносятся ли в журнал неправильные сообщения.</span><span class="sxs-lookup"><span data-stu-id="c545b-120">A value that specifies whether malformed messages are logged.</span></span>  
  
### <a name="logmessagesatservicelevel"></a><span data-ttu-id="c545b-121">LogMessagesAtServiceLevel</span><span class="sxs-lookup"><span data-stu-id="c545b-121">LogMessagesAtServiceLevel</span></span>  
 <span data-ttu-id="c545b-122">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="c545b-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="c545b-123">Тип доступа: чтение/запись</span><span class="sxs-lookup"><span data-stu-id="c545b-123">Access type: Read/Write</span></span>  
  
 <span data-ttu-id="c545b-124">Значение, указывающее, трассируются ли сообщения на уровне службы (перед шифрованием и преобразованиями, связанными с транспортом).</span><span class="sxs-lookup"><span data-stu-id="c545b-124">A value that specifies whether messages are traced at the service level (before encryption and transport-related transforms).</span></span>  
  
### <a name="logmessagesattransportlevel"></a><span data-ttu-id="c545b-125">LogMessagesAtTransportLevel</span><span class="sxs-lookup"><span data-stu-id="c545b-125">LogMessagesAtTransportLevel</span></span>  
 <span data-ttu-id="c545b-126">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="c545b-126">Data type: boolean</span></span>  
  
 <span data-ttu-id="c545b-127">Тип доступа: чтение/запись</span><span class="sxs-lookup"><span data-stu-id="c545b-127">Access type: Read/Write</span></span>  
  
 <span data-ttu-id="c545b-128">Значение, указывающее, трассируются ли сообщения на уровне транспорта.</span><span class="sxs-lookup"><span data-stu-id="c545b-128">A value that specifies whether messages are traced at the transport level.</span></span>  
  
### <a name="messageloggingtracelisteners"></a><span data-ttu-id="c545b-129">MessageLoggingTraceListeners</span><span class="sxs-lookup"><span data-stu-id="c545b-129">MessageLoggingTraceListeners</span></span>  
 <span data-ttu-id="c545b-130">Тип данных: массив TraceListener</span><span class="sxs-lookup"><span data-stu-id="c545b-130">Data type: TraceListener array</span></span>  
  
 <span data-ttu-id="c545b-131">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="c545b-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c545b-132">Коллекция прослушивателей трассировки, которые ожидают передачи данных источнику трассировки System.Wmi.MessageLogging.</span><span class="sxs-lookup"><span data-stu-id="c545b-132">The collection trace listeners that listen to the System.Wmi.MessageLogging trace source.</span></span>  
  
### <a name="name"></a><span data-ttu-id="c545b-133">name</span><span class="sxs-lookup"><span data-stu-id="c545b-133">Name</span></span>  
 <span data-ttu-id="c545b-134">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="c545b-134">Data type: string</span></span>  
  
 <span data-ttu-id="c545b-135">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="c545b-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c545b-136">Имя домена приложения.</span><span class="sxs-lookup"><span data-stu-id="c545b-136">The name of the appdomain.</span></span>  
  
### <a name="performancecounters"></a><span data-ttu-id="c545b-137">PerformanceCounters</span><span class="sxs-lookup"><span data-stu-id="c545b-137">PerformanceCounters</span></span>  
 <span data-ttu-id="c545b-138">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="c545b-138">Data type: string</span></span>  
  
 <span data-ttu-id="c545b-139">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="c545b-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c545b-140">Область активных счетчиков производительности в домене приложения.</span><span class="sxs-lookup"><span data-stu-id="c545b-140">The scope of active performance counters in the appdomain.</span></span>  
  
### <a name="processid"></a><span data-ttu-id="c545b-141">ProcessId</span><span class="sxs-lookup"><span data-stu-id="c545b-141">ProcessId</span></span>  
 <span data-ttu-id="c545b-142">Тип данных: sint32</span><span class="sxs-lookup"><span data-stu-id="c545b-142">Data type: sint32</span></span>  
  
 <span data-ttu-id="c545b-143">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="c545b-143">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c545b-144">Идентификатор процесса.</span><span class="sxs-lookup"><span data-stu-id="c545b-144">The process Id.</span></span>  
  
### <a name="serviceconfigpath"></a><span data-ttu-id="c545b-145">ServiceConfigPath</span><span class="sxs-lookup"><span data-stu-id="c545b-145">ServiceConfigPath</span></span>  
 <span data-ttu-id="c545b-146">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="c545b-146">Data type: string</span></span>  
  
 <span data-ttu-id="c545b-147">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="c545b-147">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c545b-148">Путь к конфигурации службы.</span><span class="sxs-lookup"><span data-stu-id="c545b-148">The path to the configuration of the service.</span></span>  
  
### <a name="tracelevel"></a><span data-ttu-id="c545b-149">TraceLevel</span><span class="sxs-lookup"><span data-stu-id="c545b-149">TraceLevel</span></span>  
 <span data-ttu-id="c545b-150">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="c545b-150">Data type: string</span></span>  
  
 <span data-ttu-id="c545b-151">Тип доступа: чтение/запись</span><span class="sxs-lookup"><span data-stu-id="c545b-151">Access type: Read/Write</span></span>  
  
 <span data-ttu-id="c545b-152">Уровень трассировки источника трассировки System.Wmi.</span><span class="sxs-lookup"><span data-stu-id="c545b-152">The trace level of the System.Wmi trace source.</span></span>  
  
### <a name="servicemodeltracelisteners"></a><span data-ttu-id="c545b-153">ServiceModelTraceListeners</span><span class="sxs-lookup"><span data-stu-id="c545b-153">ServiceModelTraceListeners</span></span>  
 <span data-ttu-id="c545b-154">Тип данных: массив TraceListener</span><span class="sxs-lookup"><span data-stu-id="c545b-154">Data type: TraceListener array</span></span>  
  
 <span data-ttu-id="c545b-155">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="c545b-155">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c545b-156">Коллекция прослушивателей, ожидающих передачи данных от источника трассировки System.ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="c545b-156">A collection of listeners from the System.ServiceModel trace source.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c545b-157">Требования</span><span class="sxs-lookup"><span data-stu-id="c545b-157">Requirements</span></span>  
  
|<span data-ttu-id="c545b-158">MOF</span><span class="sxs-lookup"><span data-stu-id="c545b-158">MOF</span></span>|<span data-ttu-id="c545b-159">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="c545b-159">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="c545b-160">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="c545b-160">Namespace</span></span>|<span data-ttu-id="c545b-161">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="c545b-161">Defined in root\ServiceModel</span></span>|

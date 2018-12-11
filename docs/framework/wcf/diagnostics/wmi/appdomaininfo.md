---
title: AppDomainInfo
ms.date: 03/30/2017
ms.assetid: 6610b7d8-81eb-4bec-a543-9b72ad7b6f73
ms.openlocfilehash: 0b7f8aadbd9a9dfcdd33fc65be3a5a41ea95f5be
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2018
ms.locfileid: "53127086"
---
# <a name="appdomaininfo"></a><span data-ttu-id="287cc-102">AppDomainInfo</span><span class="sxs-lookup"><span data-stu-id="287cc-102">AppDomainInfo</span></span>
<span data-ttu-id="287cc-103">Сведения о домене приложения</span><span class="sxs-lookup"><span data-stu-id="287cc-103">Application domain information</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="287cc-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="287cc-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="287cc-105">Методы</span><span class="sxs-lookup"><span data-stu-id="287cc-105">Methods</span></span>  
 <span data-ttu-id="287cc-106">Класс AppDomainInfo не определяет никакие методы.</span><span class="sxs-lookup"><span data-stu-id="287cc-106">The AppDomainInfo class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="287cc-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="287cc-107">Properties</span></span>  
 <span data-ttu-id="287cc-108">Класс AppDomainInfo имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="287cc-108">The AppDomainInfo class has the following properties:</span></span>  
  
### <a name="appdomainid"></a><span data-ttu-id="287cc-109">AppDomainId</span><span class="sxs-lookup"><span data-stu-id="287cc-109">AppDomainId</span></span>  
 <span data-ttu-id="287cc-110">Тип данных: sint32</span><span class="sxs-lookup"><span data-stu-id="287cc-110">Data type: sint32</span></span>  
  
 <span data-ttu-id="287cc-111">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="287cc-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="287cc-112">Идентификатор домена приложения.</span><span class="sxs-lookup"><span data-stu-id="287cc-112">The Id of the appdomain.</span></span>  
  
### <a name="isdefault"></a><span data-ttu-id="287cc-113">IsDefault</span><span class="sxs-lookup"><span data-stu-id="287cc-113">IsDefault</span></span>  
 <span data-ttu-id="287cc-114">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="287cc-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="287cc-115">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="287cc-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="287cc-116">Указывает, является ли домен приложения доменом приложения, используемым по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="287cc-116">Indicates whether the appdomain is the default appdomain.</span></span>  
  
### <a name="logmalformedmessages"></a><span data-ttu-id="287cc-117">LogMalformedMessages</span><span class="sxs-lookup"><span data-stu-id="287cc-117">LogMalformedMessages</span></span>  
 <span data-ttu-id="287cc-118">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="287cc-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="287cc-119">Тип доступа: Чтение и запись</span><span class="sxs-lookup"><span data-stu-id="287cc-119">Access type: Read/Write</span></span>  
  
 <span data-ttu-id="287cc-120">Значение, указывающее, заносятся ли в журнал неправильные сообщения.</span><span class="sxs-lookup"><span data-stu-id="287cc-120">A value that specifies whether malformed messages are logged.</span></span>  
  
### <a name="logmessagesatservicelevel"></a><span data-ttu-id="287cc-121">LogMessagesAtServiceLevel</span><span class="sxs-lookup"><span data-stu-id="287cc-121">LogMessagesAtServiceLevel</span></span>  
 <span data-ttu-id="287cc-122">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="287cc-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="287cc-123">Тип доступа: Чтение и запись</span><span class="sxs-lookup"><span data-stu-id="287cc-123">Access type: Read/Write</span></span>  
  
 <span data-ttu-id="287cc-124">Значение, указывающее, трассируются ли сообщения на уровне службы (перед шифрованием и преобразованиями, связанными с транспортом).</span><span class="sxs-lookup"><span data-stu-id="287cc-124">A value that specifies whether messages are traced at the service level (before encryption and transport-related transforms).</span></span>  
  
### <a name="logmessagesattransportlevel"></a><span data-ttu-id="287cc-125">LogMessagesAtTransportLevel</span><span class="sxs-lookup"><span data-stu-id="287cc-125">LogMessagesAtTransportLevel</span></span>  
 <span data-ttu-id="287cc-126">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="287cc-126">Data type: boolean</span></span>  
  
 <span data-ttu-id="287cc-127">Тип доступа: Чтение и запись</span><span class="sxs-lookup"><span data-stu-id="287cc-127">Access type: Read/Write</span></span>  
  
 <span data-ttu-id="287cc-128">Значение, указывающее, трассируются ли сообщения на уровне транспорта.</span><span class="sxs-lookup"><span data-stu-id="287cc-128">A value that specifies whether messages are traced at the transport level.</span></span>  
  
### <a name="messageloggingtracelisteners"></a><span data-ttu-id="287cc-129">MessageLoggingTraceListeners</span><span class="sxs-lookup"><span data-stu-id="287cc-129">MessageLoggingTraceListeners</span></span>  
 <span data-ttu-id="287cc-130">Тип данных: Массив TraceListener</span><span class="sxs-lookup"><span data-stu-id="287cc-130">Data type: TraceListener array</span></span>  
  
 <span data-ttu-id="287cc-131">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="287cc-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="287cc-132">Коллекция прослушивателей трассировки, которые ожидают передачи данных источнику трассировки System.Wmi.MessageLogging.</span><span class="sxs-lookup"><span data-stu-id="287cc-132">The collection trace listeners that listen to the System.Wmi.MessageLogging trace source.</span></span>  
  
### <a name="name"></a><span data-ttu-id="287cc-133">name</span><span class="sxs-lookup"><span data-stu-id="287cc-133">Name</span></span>  
 <span data-ttu-id="287cc-134">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="287cc-134">Data type: string</span></span>  
  
 <span data-ttu-id="287cc-135">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="287cc-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="287cc-136">Имя домена приложения.</span><span class="sxs-lookup"><span data-stu-id="287cc-136">The name of the appdomain.</span></span>  
  
### <a name="performancecounters"></a><span data-ttu-id="287cc-137">PerformanceCounters</span><span class="sxs-lookup"><span data-stu-id="287cc-137">PerformanceCounters</span></span>  
 <span data-ttu-id="287cc-138">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="287cc-138">Data type: string</span></span>  
  
 <span data-ttu-id="287cc-139">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="287cc-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="287cc-140">Область активных счетчиков производительности в домене приложения.</span><span class="sxs-lookup"><span data-stu-id="287cc-140">The scope of active performance counters in the appdomain.</span></span>  
  
### <a name="processid"></a><span data-ttu-id="287cc-141">ProcessId</span><span class="sxs-lookup"><span data-stu-id="287cc-141">ProcessId</span></span>  
 <span data-ttu-id="287cc-142">Тип данных: sint32</span><span class="sxs-lookup"><span data-stu-id="287cc-142">Data type: sint32</span></span>  
  
 <span data-ttu-id="287cc-143">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="287cc-143">Access type: Read-only</span></span>  
  
 <span data-ttu-id="287cc-144">Идентификатор процесса.</span><span class="sxs-lookup"><span data-stu-id="287cc-144">The process Id.</span></span>  
  
### <a name="serviceconfigpath"></a><span data-ttu-id="287cc-145">ServiceConfigPath</span><span class="sxs-lookup"><span data-stu-id="287cc-145">ServiceConfigPath</span></span>  
 <span data-ttu-id="287cc-146">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="287cc-146">Data type: string</span></span>  
  
 <span data-ttu-id="287cc-147">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="287cc-147">Access type: Read-only</span></span>  
  
 <span data-ttu-id="287cc-148">Путь к конфигурации службы.</span><span class="sxs-lookup"><span data-stu-id="287cc-148">The path to the configuration of the service.</span></span>  
  
### <a name="tracelevel"></a><span data-ttu-id="287cc-149">TraceLevel</span><span class="sxs-lookup"><span data-stu-id="287cc-149">TraceLevel</span></span>  
 <span data-ttu-id="287cc-150">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="287cc-150">Data type: string</span></span>  
  
 <span data-ttu-id="287cc-151">Тип доступа: Чтение и запись</span><span class="sxs-lookup"><span data-stu-id="287cc-151">Access type: Read/Write</span></span>  
  
 <span data-ttu-id="287cc-152">Уровень трассировки источника трассировки System.Wmi.</span><span class="sxs-lookup"><span data-stu-id="287cc-152">The trace level of the System.Wmi trace source.</span></span>  
  
### <a name="servicemodeltracelisteners"></a><span data-ttu-id="287cc-153">ServiceModelTraceListeners</span><span class="sxs-lookup"><span data-stu-id="287cc-153">ServiceModelTraceListeners</span></span>  
 <span data-ttu-id="287cc-154">Тип данных: Массив TraceListener</span><span class="sxs-lookup"><span data-stu-id="287cc-154">Data type: TraceListener array</span></span>  
  
 <span data-ttu-id="287cc-155">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="287cc-155">Access type: Read-only</span></span>  
  
 <span data-ttu-id="287cc-156">Коллекция прослушивателей, ожидающих передачи данных от источника трассировки System.ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="287cc-156">A collection of listeners from the System.ServiceModel trace source.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="287cc-157">Требования</span><span class="sxs-lookup"><span data-stu-id="287cc-157">Requirements</span></span>  
  
|<span data-ttu-id="287cc-158">MOF</span><span class="sxs-lookup"><span data-stu-id="287cc-158">MOF</span></span>|<span data-ttu-id="287cc-159">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="287cc-159">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="287cc-160">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="287cc-160">Namespace</span></span>|<span data-ttu-id="287cc-161">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="287cc-161">Defined in root\ServiceModel</span></span>|

---
title: LocalServiceSecuritySettings
ms.date: 03/30/2017
ms.assetid: 490aa0e5-5242-4f8d-b505-5ec6287633b4
ms.openlocfilehash: c1f3abe2d016ccab9b136752c4b2e6697ca59e66
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2018
ms.locfileid: "50188850"
---
# <a name="localservicesecuritysettings"></a><span data-ttu-id="f6f38-102">LocalServiceSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="f6f38-102">LocalServiceSecuritySettings</span></span>
<span data-ttu-id="f6f38-103">LocalServiceSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="f6f38-103">LocalServiceSecuritySettings</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f6f38-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f6f38-104">Syntax</span></span>  
  
```csharp
class LocalServiceSecuritySettings  
{  
  boolean DetectReplays;  
  datetime InactivityTimeout;  
  datetime IssuedCookieLifetime;  
  sint32 MaxCachedCookies;  
  datetime MaxClockSkew;  
  sint32 MaxPendingSessions;  
  sint32 MaxStatefulNegotiations;  
  datetime NegotiationTimeout;  
  boolean ReconnectTransportOnFailure;  
  sint32 ReplayCacheSize;  
  datetime ReplayWindow;  
  datetime SessionKeyRenewalInterval;  
  datetime SessionKeyRolloverInterval;  
  datetime TimestampValidityDuration;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="f6f38-105">Методы</span><span class="sxs-lookup"><span data-stu-id="f6f38-105">Methods</span></span>  
 <span data-ttu-id="f6f38-106">Класс LocalServiceSecuritySettings не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="f6f38-106">The LocalServiceSecuritySettings class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="f6f38-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="f6f38-107">Properties</span></span>  
 <span data-ttu-id="f6f38-108">Класс LocalServiceSecuritySettings имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="f6f38-108">The LocalServiceSecuritySettings class has the following properties:</span></span>  
  
### <a name="detectreplays"></a><span data-ttu-id="f6f38-109">DetectReplays</span><span class="sxs-lookup"><span data-stu-id="f6f38-109">DetectReplays</span></span>  
 <span data-ttu-id="f6f38-110">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="f6f38-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="f6f38-111">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="f6f38-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f6f38-112">Логическое значение, показывающее, будут ли атаки с повторением обнаружены и ликвидированы на канале автоматически.</span><span class="sxs-lookup"><span data-stu-id="f6f38-112">A Boolean value that specifies whether replay attacks against the channel are detected and dealt with automatically.</span></span>  
  
### <a name="inactivitytimeout"></a><span data-ttu-id="f6f38-113">InactivityTimeout</span><span class="sxs-lookup"><span data-stu-id="f6f38-113">InactivityTimeout</span></span>  
 <span data-ttu-id="f6f38-114">Тип данных: datetime</span><span class="sxs-lookup"><span data-stu-id="f6f38-114">Data type: datetime</span></span>  
  
 <span data-ttu-id="f6f38-115">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="f6f38-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f6f38-116">Максимальное количество ожидающих безопасных сеансов, поддерживаемое службой.</span><span class="sxs-lookup"><span data-stu-id="f6f38-116">The maximum number of pending security sessions that the service supports.</span></span>  
  
### <a name="issuedcookielifetime"></a><span data-ttu-id="f6f38-117">IssuedCookieLifetime</span><span class="sxs-lookup"><span data-stu-id="f6f38-117">IssuedCookieLifetime</span></span>  
 <span data-ttu-id="f6f38-118">Тип данных: datetime</span><span class="sxs-lookup"><span data-stu-id="f6f38-118">Data type: datetime</span></span>  
  
 <span data-ttu-id="f6f38-119">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="f6f38-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f6f38-120">Значение типа TimeSpan, которое задает время существования для всех новых файлов безопасности cookie.</span><span class="sxs-lookup"><span data-stu-id="f6f38-120">A TimeSpan that specifies the lifetime issued to all new security cookies.</span></span>  
  
### <a name="maxcachedcookies"></a><span data-ttu-id="f6f38-121">MaxCachedCookies</span><span class="sxs-lookup"><span data-stu-id="f6f38-121">MaxCachedCookies</span></span>  
 <span data-ttu-id="f6f38-122">Тип данных: sint32</span><span class="sxs-lookup"><span data-stu-id="f6f38-122">Data type: sint32</span></span>  
  
 <span data-ttu-id="f6f38-123">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="f6f38-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f6f38-124">Максимальное количество файлов cookie, которые могут быть кэшированы.</span><span class="sxs-lookup"><span data-stu-id="f6f38-124">The maximum number of cookies that can be cached.</span></span>  
  
### <a name="maxclockskew"></a><span data-ttu-id="f6f38-125">MaxClockSkew</span><span class="sxs-lookup"><span data-stu-id="f6f38-125">MaxClockSkew</span></span>  
 <span data-ttu-id="f6f38-126">Тип данных: datetime</span><span class="sxs-lookup"><span data-stu-id="f6f38-126">Data type: datetime</span></span>  
  
 <span data-ttu-id="f6f38-127">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="f6f38-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f6f38-128">Значение типа TimeSpan, указывающее максимальный разброс времени между системными часами взаимодействующих сторон.</span><span class="sxs-lookup"><span data-stu-id="f6f38-128">A TimeSpan that specifies the maximum time difference between the system clocks of the two communicating parties.</span></span>  
  
### <a name="maxpendingsessions"></a><span data-ttu-id="f6f38-129">MaxPendingSessions</span><span class="sxs-lookup"><span data-stu-id="f6f38-129">MaxPendingSessions</span></span>  
 <span data-ttu-id="f6f38-130">Тип данных: sint32</span><span class="sxs-lookup"><span data-stu-id="f6f38-130">Data type: sint32</span></span>  
  
 <span data-ttu-id="f6f38-131">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="f6f38-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f6f38-132">Максимальное количество ожидающих подключений к службе.</span><span class="sxs-lookup"><span data-stu-id="f6f38-132">The maximum number of pending connections on the service.</span></span>  
  
### <a name="maxstatefulnegotiations"></a><span data-ttu-id="f6f38-133">MaxStatefulNegotiations</span><span class="sxs-lookup"><span data-stu-id="f6f38-133">MaxStatefulNegotiations</span></span>  
 <span data-ttu-id="f6f38-134">Тип данных: sint32</span><span class="sxs-lookup"><span data-stu-id="f6f38-134">Data type: sint32</span></span>  
  
 <span data-ttu-id="f6f38-135">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="f6f38-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f6f38-136">Количество одновременно выполняемых согласований режима безопасности.</span><span class="sxs-lookup"><span data-stu-id="f6f38-136">The number of security negotiations that can be active concurrently.</span></span>  
  
### <a name="negotiationtimeout"></a><span data-ttu-id="f6f38-137">NegotiationTimeout</span><span class="sxs-lookup"><span data-stu-id="f6f38-137">NegotiationTimeout</span></span>  
 <span data-ttu-id="f6f38-138">Тип данных: datetime</span><span class="sxs-lookup"><span data-stu-id="f6f38-138">Data type: datetime</span></span>  
  
 <span data-ttu-id="f6f38-139">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="f6f38-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f6f38-140">Значение типа TimeSpan, указывающее максимальную длительность этапа согласования режима безопасности между сервером и клиентом.</span><span class="sxs-lookup"><span data-stu-id="f6f38-140">A TimeSpan that specifies the maximum duration for the security negotiation phase between server and client.</span></span>  
  
### <a name="reconnecttransportonfailure"></a><span data-ttu-id="f6f38-141">ReconnectTransportOnFailure</span><span class="sxs-lookup"><span data-stu-id="f6f38-141">ReconnectTransportOnFailure</span></span>  
 <span data-ttu-id="f6f38-142">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="f6f38-142">Data type: boolean</span></span>  
  
 <span data-ttu-id="f6f38-143">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="f6f38-143">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f6f38-144">Логическое значение, указывающее, будут ли подключения, использующие режим обмена сообщениями WS-Reliable, пытаться восстановиться после транспортных сбоев.</span><span class="sxs-lookup"><span data-stu-id="f6f38-144">A Boolean value that specifies whether connections using WS-Reliable messaging attempt to reconnect after transport failures.</span></span>  
  
### <a name="replaycachesize"></a><span data-ttu-id="f6f38-145">ReplayCacheSize</span><span class="sxs-lookup"><span data-stu-id="f6f38-145">ReplayCacheSize</span></span>  
 <span data-ttu-id="f6f38-146">Тип данных: sint32</span><span class="sxs-lookup"><span data-stu-id="f6f38-146">Data type: sint32</span></span>  
  
 <span data-ttu-id="f6f38-147">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="f6f38-147">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f6f38-148">Количество кэшированных параметров nonce, используемых для определения ответов.</span><span class="sxs-lookup"><span data-stu-id="f6f38-148">The number of cached nonces used for replay detection.</span></span>  
  
### <a name="replaywindow"></a><span data-ttu-id="f6f38-149">ReplayWindow</span><span class="sxs-lookup"><span data-stu-id="f6f38-149">ReplayWindow</span></span>  
 <span data-ttu-id="f6f38-150">Тип данных: datetime</span><span class="sxs-lookup"><span data-stu-id="f6f38-150">Data type: datetime</span></span>  
  
 <span data-ttu-id="f6f38-151">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="f6f38-151">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f6f38-152">Значение типа TimeSpan, которое указывает срок действия параметров nonce отдельного сообщения.</span><span class="sxs-lookup"><span data-stu-id="f6f38-152">A TimeSpan that specifies the duration in which individual message nonces are valid.</span></span>  
  
### <a name="sessionkeyrenewalinterval"></a><span data-ttu-id="f6f38-153">SessionKeyRenewalInterval</span><span class="sxs-lookup"><span data-stu-id="f6f38-153">SessionKeyRenewalInterval</span></span>  
 <span data-ttu-id="f6f38-154">Тип данных: datetime</span><span class="sxs-lookup"><span data-stu-id="f6f38-154">Data type: datetime</span></span>  
  
 <span data-ttu-id="f6f38-155">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="f6f38-155">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f6f38-156">Значение типа TimeSpan, которое задает интервал времени, по истечении которого инициатор обновляет ключ сеанса безопасности.</span><span class="sxs-lookup"><span data-stu-id="f6f38-156">A TimeSpan that specifies the duration after which the initiator renews the key for the security session.</span></span>  
  
### <a name="sessionkeyrolloverinterval"></a><span data-ttu-id="f6f38-157">SessionKeyRolloverInterval</span><span class="sxs-lookup"><span data-stu-id="f6f38-157">SessionKeyRolloverInterval</span></span>  
 <span data-ttu-id="f6f38-158">Тип данных: datetime</span><span class="sxs-lookup"><span data-stu-id="f6f38-158">Data type: datetime</span></span>  
  
 <span data-ttu-id="f6f38-159">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="f6f38-159">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f6f38-160">Значение типа TimeSpan, которое задает интервал времени, указывающий период, в течение которого предыдущий сеансовый ключ остается действительным для входящих сообщений, пока выполняется обновление ключа.</span><span class="sxs-lookup"><span data-stu-id="f6f38-160">A TimeSpan that specifies the time interval a previous session key is valid on incoming messages during a key renewal.</span></span>  
  
### <a name="timestampvalidityduration"></a><span data-ttu-id="f6f38-161">TimestampValidityDuration</span><span class="sxs-lookup"><span data-stu-id="f6f38-161">TimestampValidityDuration</span></span>  
 <span data-ttu-id="f6f38-162">Тип данных: datetime</span><span class="sxs-lookup"><span data-stu-id="f6f38-162">Data type: datetime</span></span>  
  
 <span data-ttu-id="f6f38-163">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="f6f38-163">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f6f38-164">Значение типа TimeSpan, которое определяет интервал времени, указывающий срок действия отметки времени.</span><span class="sxs-lookup"><span data-stu-id="f6f38-164">A TimeSpan that specifies the duration in which a time stamp is valid.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f6f38-165">Требования</span><span class="sxs-lookup"><span data-stu-id="f6f38-165">Requirements</span></span>  
  
|<span data-ttu-id="f6f38-166">MOF</span><span class="sxs-lookup"><span data-stu-id="f6f38-166">MOF</span></span>|<span data-ttu-id="f6f38-167">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="f6f38-167">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="f6f38-168">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="f6f38-168">Namespace</span></span>|<span data-ttu-id="f6f38-169">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="f6f38-169">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f6f38-170">См. также</span><span class="sxs-lookup"><span data-stu-id="f6f38-170">See Also</span></span>  
 <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings>

---
title: "Элемент &lt;localClientSettings&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4680ace5-f4e1-4fcb-b9d8-a4a4af5cd7ae
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: cabde7eb9dd122c2f7060b2f2e2c16f5949dc1f3
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="ltlocalclientsettingsgt-element"></a><span data-ttu-id="3d4da-102">Элемент &lt;localClientSettings&gt;</span><span class="sxs-lookup"><span data-stu-id="3d4da-102">&lt;localClientSettings&gt; element</span></span>
<span data-ttu-id="3d4da-103">Задает параметры безопасности локального клиента для этой привязки.</span><span class="sxs-lookup"><span data-stu-id="3d4da-103">Specifies the security settings of a local client for this binding.</span></span>  
  
 <span data-ttu-id="3d4da-104">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="3d4da-104">\<system.serviceModel></span></span>  
<span data-ttu-id="3d4da-105">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="3d4da-105">\<bindings></span></span>  
<span data-ttu-id="3d4da-106">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="3d4da-106">\<customBinding></span></span>  
<span data-ttu-id="3d4da-107">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="3d4da-107">\<binding></span></span>  
<span data-ttu-id="3d4da-108">\<Безопасность ></span><span class="sxs-lookup"><span data-stu-id="3d4da-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3d4da-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3d4da-109">Syntax</span></span>  
  
```xml  
<security>  
   <localClientSettings cacheCookies="Boolean"  
      cookieRenewalThresholdPercentage="Integer"  
      detectReplays="Boolean"  
      maxClockSkew="TimeSpan"  
      maxCookieCachingTime="TimeSpan"  
      reconnectTransportOnFailure="Boolean"  
      replayCacheSize="Integer"  
      replayWindow="TimeSpan"  
      sessionKeyRenewalInterval="TimeSpan"  
      sessionKeyRolloverInterval="TimeSpan"  
      timestampValidityDuration="TimeSpan" />  
</security>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3d4da-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="3d4da-110">Attributes and Elements</span></span>  
 <span data-ttu-id="3d4da-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="3d4da-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3d4da-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="3d4da-112">Attributes</span></span>  
  
|<span data-ttu-id="3d4da-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="3d4da-113">Attribute</span></span>|<span data-ttu-id="3d4da-114">Описание</span><span class="sxs-lookup"><span data-stu-id="3d4da-114">Description</span></span>|  
|---------------|-----------------|  
|`cacheCookies`|<span data-ttu-id="3d4da-115">Логическое значение, указывающее, включено ли кэширование файлов cookie.</span><span class="sxs-lookup"><span data-stu-id="3d4da-115">A Boolean value that specifies whether cookie caching is enabled.</span></span> <span data-ttu-id="3d4da-116">Значение по умолчанию — `false`.</span><span class="sxs-lookup"><span data-stu-id="3d4da-116">The default is `false`.</span></span>|  
|`cookieRenewalThresholdPercentage`|<span data-ttu-id="3d4da-117">Целое число, задающее максимальный процент файлов cookie, которые могут обновляться.</span><span class="sxs-lookup"><span data-stu-id="3d4da-117">An integer that specifies the maximum percentage of cookies that can be renewed.</span></span> <span data-ttu-id="3d4da-118">Это значение должно быть в диапазоне от 0 до 100 включительно.</span><span class="sxs-lookup"><span data-stu-id="3d4da-118">This value should be between 0 and 100 inclusively.</span></span> <span data-ttu-id="3d4da-119">Значение по умолчанию — 90.</span><span class="sxs-lookup"><span data-stu-id="3d4da-119">The default is 90.</span></span>|  
|`detectReplays`|<span data-ttu-id="3d4da-120">Логическое значение, показывающее, будут ли атаки с повторением обнаружены и ликвидированы на канале автоматически.</span><span class="sxs-lookup"><span data-stu-id="3d4da-120">A Boolean value that specifies whether replay attacks against the channel are detected and dealt with automatically.</span></span> <span data-ttu-id="3d4da-121">Значение по умолчанию — `false`.</span><span class="sxs-lookup"><span data-stu-id="3d4da-121">The default is `false`.</span></span>|  
|`maxClockSkew`|<span data-ttu-id="3d4da-122">Значение типа <xref:System.TimeSpan>, указывающее максимальный разброс времени между системными часами взаимодействующих сторон.</span><span class="sxs-lookup"><span data-stu-id="3d4da-122">A <xref:System.TimeSpan> that specifies the maximum time difference between the system clocks of the two communicating parties.</span></span> <span data-ttu-id="3d4da-123">Значение по умолчанию - 00:05:00.</span><span class="sxs-lookup"><span data-stu-id="3d4da-123">The default value is "00:05:00".</span></span><br /><br /> <span data-ttu-id="3d4da-124">Если задано значение по умолчанию, получатель принимает сообщения с отметками времени отправки, которое на пять минут раньше или позже времени получения сообщения.</span><span class="sxs-lookup"><span data-stu-id="3d4da-124">When this value is set to the default, the receiver accepts messages with send-time time stamps up to 5 minutes later or earlier than the time the message was received.</span></span> <span data-ttu-id="3d4da-125">Сообщения, которые не прошли проверку времени отправки, отклоняются.</span><span class="sxs-lookup"><span data-stu-id="3d4da-125">Messages that do not pass the send-time test are rejected.</span></span> <span data-ttu-id="3d4da-126">Данная настройка используется в сочетании с атрибутом `replayWindow`.</span><span class="sxs-lookup"><span data-stu-id="3d4da-126">This setting is used in conjunction with the `replayWindow` attribute.</span></span>|  
|`maxCookieCachingTime`|<span data-ttu-id="3d4da-127">Значение <xref:System.TimeSpan>, которое задает максимальное время существования файлов cookie.</span><span class="sxs-lookup"><span data-stu-id="3d4da-127">A <xref:System.TimeSpan> that specifies the maximum lifetime of cookies.</span></span> <span data-ttu-id="3d4da-128">Значение по умолчанию - 10675199.02:48:05.4775807.</span><span class="sxs-lookup"><span data-stu-id="3d4da-128">The default value is "10675199.02:48:05.4775807".</span></span>|  
|`reconnectTransportOnFailure`|<span data-ttu-id="3d4da-129">Логическое значение, указывающее, будет ли после транспортных сбоев выполняться попытка восстановления подключений, использующих режим обмена сообщениями WS-Reliable.</span><span class="sxs-lookup"><span data-stu-id="3d4da-129">A Boolean value that specifies whether connections using WS-Reliable messaging will attempt to reconnect after transport failures.</span></span> <span data-ttu-id="3d4da-130">По умолчанию используется значение `true`, что означает бесконечное число попыток повторного подключения.</span><span class="sxs-lookup"><span data-stu-id="3d4da-130">The default is `true`, which means that infinite attempts to reconnect are attempted.</span></span> <span data-ttu-id="3d4da-131">Цикл нарушается при возникновении тайм-аута бездействия, в результате чего канал вызывает исключение при невозможности повторного подключения.</span><span class="sxs-lookup"><span data-stu-id="3d4da-131">The cycle is broken by the inactivity time-out, which causes the channel to throw an exception when it cannot be reconnected.</span></span>|  
|`replayCacheSize`|<span data-ttu-id="3d4da-132">Положительное целое число, указывающее количество кэшированных параметров nonce, используемых для определения ответов.</span><span class="sxs-lookup"><span data-stu-id="3d4da-132">A positive integer that specifies the number of cached nonces used for replay detection.</span></span> <span data-ttu-id="3d4da-133">При превышении лимита самые старые параметры nonce удаляются, и создаются новые параметры nonce для новых сообщений.</span><span class="sxs-lookup"><span data-stu-id="3d4da-133">If this limit is exceeded, the oldest nonce is removed and a new nonce is created for the new message.</span></span> <span data-ttu-id="3d4da-134">Значение по умолчанию — 500000.</span><span class="sxs-lookup"><span data-stu-id="3d4da-134">The default value is 500000.</span></span>|  
|`replayWindow`|<span data-ttu-id="3d4da-135">Значение типа <xref:System.TimeSpan>, которое указывает срок действия параметров nonce отдельного сообщения.</span><span class="sxs-lookup"><span data-stu-id="3d4da-135">A <xref:System.TimeSpan> that specifies the duration in which individual message nonces are valid.</span></span><br /><br /> <span data-ttu-id="3d4da-136">По истечении данного срока сообщение с тем же параметром nonce, что и у сообщения, отправленного ранее, приниматься не будет.</span><span class="sxs-lookup"><span data-stu-id="3d4da-136">After this duration, a message sent with the same nonce as the one sent before will not be accepted.</span></span> <span data-ttu-id="3d4da-137">Данный атрибут используется вместе с атрибутом `maxClockSkew` в целях предотвращения атак с повторением передачи пакетов.</span><span class="sxs-lookup"><span data-stu-id="3d4da-137">This attribute is used in conjunction with the `maxClockSkew` attribute to prevent replay attacks.</span></span> <span data-ttu-id="3d4da-138">Злоумышленник может повторно отправить сообщение после закрытия окна повторной отправки сообщения.</span><span class="sxs-lookup"><span data-stu-id="3d4da-138">An attacker could replay a message after its replay window has expired.</span></span> <span data-ttu-id="3d4da-139">Данное сообщение, тем не менее, не пройдет проверку `maxClockSkew`, в результате которой отклоняются сообщения с отметками времени отправки, превышающими указанный период до или после времени получения сообщения.</span><span class="sxs-lookup"><span data-stu-id="3d4da-139">This message, however, would fail the `maxClockSkew` test which rejects messages with send-time timestamps up to a specified time later or earlier than the time the message was received.</span></span>|  
|`sessionKeyRenewalInterval`|<span data-ttu-id="3d4da-140">Значение <xref:System.TimeSpan>, которое задает интервал времени, по истечении которого инициатор будет обновлять ключ сеанса безопасности.</span><span class="sxs-lookup"><span data-stu-id="3d4da-140">A <xref:System.TimeSpan> that specifies the duration after which the initiator will renew the key for the security session.</span></span> <span data-ttu-id="3d4da-141">Значение по умолчанию - 10:00:00.</span><span class="sxs-lookup"><span data-stu-id="3d4da-141">The default is "10:00:00".</span></span>|  
|`sessionKeyRolloverInterval`|<span data-ttu-id="3d4da-142">Значение <xref:System.TimeSpan>, которое задает интервал времени, в течение которого предыдущий сеансовый ключ остается действительным для входящих сообщений, пока выполняется обновление ключа.</span><span class="sxs-lookup"><span data-stu-id="3d4da-142">A <xref:System.TimeSpan> that specifies the time interval a previous session key is valid on incoming messages during a key renewal.</span></span> <span data-ttu-id="3d4da-143">Значение по умолчанию - 00:05:00.</span><span class="sxs-lookup"><span data-stu-id="3d4da-143">The default is "00:05:00".</span></span><br /><br /> <span data-ttu-id="3d4da-144">Во время обновления ключа отправка сообщения клиентом и сервером всегда должна выполняться с помощью самого последнего доступного ключа.</span><span class="sxs-lookup"><span data-stu-id="3d4da-144">During key renewal, the client and server must always send messages using the most current available key.</span></span> <span data-ttu-id="3d4da-145">Обе стороны принимают входящие сообщения, защищенные с помощью предыдущего сеансового ключа, вплоть до истечения времени смены ключа.</span><span class="sxs-lookup"><span data-stu-id="3d4da-145">Both parties will accept incoming messages secured with the previous session key until the rollover time expires.</span></span>|  
|`timestampValidityDuration`|<span data-ttu-id="3d4da-146">Положительное значение типа <xref:System.TimeSpan>, указывающее срок действия отметки времени.</span><span class="sxs-lookup"><span data-stu-id="3d4da-146">A positive <xref:System.TimeSpan> that specifies the duration in which a time stamp is valid.</span></span> <span data-ttu-id="3d4da-147">Значение по умолчанию - 00:15:00.</span><span class="sxs-lookup"><span data-stu-id="3d4da-147">The default is "00:15:00".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3d4da-148">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="3d4da-148">Child Elements</span></span>  
 <span data-ttu-id="3d4da-149">Нет</span><span class="sxs-lookup"><span data-stu-id="3d4da-149">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3d4da-150">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="3d4da-150">Parent Elements</span></span>  
  
|<span data-ttu-id="3d4da-151">Элемент</span><span class="sxs-lookup"><span data-stu-id="3d4da-151">Element</span></span>|<span data-ttu-id="3d4da-152">Описание</span><span class="sxs-lookup"><span data-stu-id="3d4da-152">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3d4da-153">\<Безопасность ></span><span class="sxs-lookup"><span data-stu-id="3d4da-153">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md)|<span data-ttu-id="3d4da-154">Задает параметры безопасности для пользовательской привязки.</span><span class="sxs-lookup"><span data-stu-id="3d4da-154">Specifies the security options for a custom binding.</span></span>|  
|[<span data-ttu-id="3d4da-155">\<secureConversationBootstrap ></span><span class="sxs-lookup"><span data-stu-id="3d4da-155">\<secureConversationBootstrap></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md)|<span data-ttu-id="3d4da-156">Задает значения по умолчанию, используемые для инициализации службы безопасного обмена данными.</span><span class="sxs-lookup"><span data-stu-id="3d4da-156">Specifies the default values used for initiating a secure conversation service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3d4da-157">Примечания</span><span class="sxs-lookup"><span data-stu-id="3d4da-157">Remarks</span></span>  
 <span data-ttu-id="3d4da-158">Параметры являются локальными, в том смысле, что они не наследуются от политики безопасности службы.</span><span class="sxs-lookup"><span data-stu-id="3d4da-158">The settings are local in the sense that they are not settings derived from the security policy of the service.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d4da-159">См. также</span><span class="sxs-lookup"><span data-stu-id="3d4da-159">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.LocalClientSecuritySettingsElement>  
 <xref:System.ServiceModel.Configuration.SecurityElementBase.LocalClientSettings%2A>  
 <xref:System.ServiceModel.Channels.SecurityBindingElement.LocalClientSettings%2A>  
 <xref:System.ServiceModel.Channels.LocalClientSecuritySettings>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [<span data-ttu-id="3d4da-160">Привязки</span><span class="sxs-lookup"><span data-stu-id="3d4da-160">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="3d4da-161">Расширение привязок</span><span class="sxs-lookup"><span data-stu-id="3d4da-161">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="3d4da-162">Пользовательские привязки</span><span class="sxs-lookup"><span data-stu-id="3d4da-162">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="3d4da-163">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="3d4da-163">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)  
 [<span data-ttu-id="3d4da-164">Как: Создание пользовательской привязки, с использованием элемента SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="3d4da-164">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)  
 [<span data-ttu-id="3d4da-165">Безопасность пользовательской привязки</span><span class="sxs-lookup"><span data-stu-id="3d4da-165">Custom Binding Security</span></span>](../../../../../docs/framework/wcf/samples/custom-binding-security.md)

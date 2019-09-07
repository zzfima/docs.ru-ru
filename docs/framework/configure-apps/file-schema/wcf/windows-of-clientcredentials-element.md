---
title: <windows> элемента <clientCredentials>
ms.date: 03/30/2017
ms.assetid: 793e41c2-31ea-4159-abbc-2123bf097233
ms.openlocfilehash: 61ca99213f0b83a5af5df0184a8c1de405366288
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399117"
---
# <a name="windows-of-clientcredentials-element"></a><span data-ttu-id="840b6-102">\<> Windows > \<элемента ClientCredentials</span><span class="sxs-lookup"><span data-stu-id="840b6-102">\<windows> of \<clientCredentials> Element</span></span>
<span data-ttu-id="840b6-103">Определяет параметры учетных данных Windows, которые используются для представления клиента.</span><span class="sxs-lookup"><span data-stu-id="840b6-103">Specifies the settings for a Windows credential to be used to represent the client.</span></span>  
  
<span data-ttu-id="840b6-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="840b6-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="840b6-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="840b6-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="840b6-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> поведения**](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="840b6-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="840b6-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<endpointBehaviors >** ](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="840b6-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="840b6-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> поведения**](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="840b6-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="840b6-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> clientCredentials**](clientcredentials.md)</span><span class="sxs-lookup"><span data-stu-id="840b6-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)</span></span>\
<span data-ttu-id="840b6-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> Windows**</span><span class="sxs-lookup"><span data-stu-id="840b6-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<windows>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="840b6-111">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="840b6-111">Syntax</span></span>  
  
```xml  
<windows allowedImpersonationLevel="Identification/Impersonation/Delegation/Anonymous/None"
         allowNtlm="Boolean" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="840b6-112">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="840b6-112">Attributes and Elements</span></span>  
 <span data-ttu-id="840b6-113">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="840b6-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="840b6-114">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="840b6-114">Attributes</span></span>  
  
|<span data-ttu-id="840b6-115">Атрибут</span><span class="sxs-lookup"><span data-stu-id="840b6-115">Attribute</span></span>|<span data-ttu-id="840b6-116">Описание</span><span class="sxs-lookup"><span data-stu-id="840b6-116">Description</span></span>|  
|---------------|-----------------|  
|`allowedImpersonationLevel`|<span data-ttu-id="840b6-117">Задает параметры олицетворения, сообщаемые клиентом серверу.</span><span class="sxs-lookup"><span data-stu-id="840b6-117">Sets the impersonation preference that the client communicates to the server.</span></span> <span data-ttu-id="840b6-118">Режим олицетворения, выбираемый клиентом, не задается принудительно для сервера.</span><span class="sxs-lookup"><span data-stu-id="840b6-118">The impersonation mode that the client selects is not enforced on the server.</span></span> <span data-ttu-id="840b6-119">Допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="840b6-119">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="840b6-120">Идентификатор Сервер может получить удостоверение и привилегии клиента, но не может олицетворять клиента.</span><span class="sxs-lookup"><span data-stu-id="840b6-120">-   Identification: The server can get the identity and privileges of the client, but cannot impersonate the client.</span></span><br /><span data-ttu-id="840b6-121">Олицетворения Сервер может олицетворять контекст безопасности клиента в локальной системе.</span><span class="sxs-lookup"><span data-stu-id="840b6-121">-   Impersonation: The server can impersonate the client's security context on the local system.</span></span><br /><span data-ttu-id="840b6-122">Передачу Сервер может олицетворять контекст безопасности клиента в удаленных системах.</span><span class="sxs-lookup"><span data-stu-id="840b6-122">-   Delegation: The server can impersonate the client's security context on remote systems.</span></span><br /><span data-ttu-id="840b6-123">Подключившихся Серверу не удается олицетворить или опознать клиента.</span><span class="sxs-lookup"><span data-stu-id="840b6-123">-   Anonymous: The server cannot impersonate or identify the client.</span></span><br /><span data-ttu-id="840b6-124">None Уровень олицетворения не назначен.</span><span class="sxs-lookup"><span data-stu-id="840b6-124">-   None: An impersonation level is not assigned.</span></span><br /><br /> <span data-ttu-id="840b6-125">Значение по умолчанию - Identification.</span><span class="sxs-lookup"><span data-stu-id="840b6-125">The default is Identification.</span></span> <span data-ttu-id="840b6-126">Это атрибут типа <xref:System.Security.Principal.TokenImpersonationLevel>.</span><span class="sxs-lookup"><span data-stu-id="840b6-126">This attribute is of type <xref:System.Security.Principal.TokenImpersonationLevel>.</span></span>|  
|`allowNtlm`|<span data-ttu-id="840b6-127">Если установить для данного свойства значение `true`, то проверка подлинности может понижаться до NTLM в том случае, если проверка Kerberos недоступна.</span><span class="sxs-lookup"><span data-stu-id="840b6-127">Setting this property to `true` allows authentication to downgrade to NTLM if Kerberos is not available.</span></span><br /><br /> <span data-ttu-id="840b6-128">Если задать для `false` этого свойства значение Windows Communication Foundation (WCF), лучше будет создавать исключение, если используется NTLM.</span><span class="sxs-lookup"><span data-stu-id="840b6-128">Setting this property to `false` causes Windows Communication Foundation (WCF) to make a best-effort to throw an exception if NTLM is used.</span></span> <span data-ttu-id="840b6-129">Обратите внимание, что установка для данного свойства значения `false` не предотвращает отправки учетных данных NTLM по сети.</span><span class="sxs-lookup"><span data-stu-id="840b6-129">Note that setting this property to `false` may not prevent NTLM credentials from being sent over the wire.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="840b6-130">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="840b6-130">Child Elements</span></span>  
 <span data-ttu-id="840b6-131">Нет.</span><span class="sxs-lookup"><span data-stu-id="840b6-131">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="840b6-132">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="840b6-132">Parent Elements</span></span>  
  
|<span data-ttu-id="840b6-133">Элемент</span><span class="sxs-lookup"><span data-stu-id="840b6-133">Element</span></span>|<span data-ttu-id="840b6-134">Описание</span><span class="sxs-lookup"><span data-stu-id="840b6-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="840b6-135">\<> clientCredentials</span><span class="sxs-lookup"><span data-stu-id="840b6-135">\<clientCredentials></span></span>](clientcredentials.md)|<span data-ttu-id="840b6-136">Задает учетные данные, используемые для проверки подлинности клиента при подключении к службе.</span><span class="sxs-lookup"><span data-stu-id="840b6-136">Specifies the credentials used to authenticate the client to the service.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="840b6-137">См. также</span><span class="sxs-lookup"><span data-stu-id="840b6-137">See also</span></span>

- <xref:System.ServiceModel.Configuration.WindowsClientElement>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement.Windows%2A>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Description.ClientCredentials.Windows%2A>
- <xref:System.ServiceModel.Security.WindowsClientCredential>
- [<span data-ttu-id="840b6-138">Защита клиентов</span><span class="sxs-lookup"><span data-stu-id="840b6-138">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="840b6-139">Работа с сертификатами</span><span class="sxs-lookup"><span data-stu-id="840b6-139">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="840b6-140">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="840b6-140">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)

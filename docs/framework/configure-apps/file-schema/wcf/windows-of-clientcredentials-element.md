---
title: "&lt;windows&gt; элемента &lt;clientCredentials&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 793e41c2-31ea-4159-abbc-2123bf097233
caps.latest.revision: "13"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: bc98f45d197675f8cc9618f08447cc42acdd1872
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="ltwindowsgt-of-ltclientcredentialsgt-element"></a><span data-ttu-id="56e3b-102">&lt;windows&gt; элемента &lt;clientCredentials&gt;</span><span class="sxs-lookup"><span data-stu-id="56e3b-102">&lt;windows&gt; of &lt;clientCredentials&gt; Element</span></span>
<span data-ttu-id="56e3b-103">Определяет параметры учетных данных Windows, которые используются для представления клиента.</span><span class="sxs-lookup"><span data-stu-id="56e3b-103">Specifies the settings for a Windows credential to be used to represent the client.</span></span>  
  
 <span data-ttu-id="56e3b-104">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="56e3b-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="56e3b-105">\<поведения ></span><span class="sxs-lookup"><span data-stu-id="56e3b-105">\<behaviors></span></span>  
<span data-ttu-id="56e3b-106">\<endpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="56e3b-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="56e3b-107">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="56e3b-107">\<behavior></span></span>  
<span data-ttu-id="56e3b-108">\<clientCredentials ></span><span class="sxs-lookup"><span data-stu-id="56e3b-108">\<clientCredentials></span></span>  
<span data-ttu-id="56e3b-109">\<Windows ></span><span class="sxs-lookup"><span data-stu-id="56e3b-109">\<windows></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="56e3b-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="56e3b-110">Syntax</span></span>  
  
```xml  
<windows   
    allowedImpersonationLevel="Identification/Impersonation/Delegation/Anonymous/None"  
        allowNtlm="Boolean"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="56e3b-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="56e3b-111">Attributes and Elements</span></span>  
 <span data-ttu-id="56e3b-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="56e3b-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="56e3b-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="56e3b-113">Attributes</span></span>  
  
|<span data-ttu-id="56e3b-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="56e3b-114">Attribute</span></span>|<span data-ttu-id="56e3b-115">Описание</span><span class="sxs-lookup"><span data-stu-id="56e3b-115">Description</span></span>|  
|---------------|-----------------|  
|`allowedImpersonationLevel`|<span data-ttu-id="56e3b-116">Задает параметры олицетворения, сообщаемые клиентом серверу.</span><span class="sxs-lookup"><span data-stu-id="56e3b-116">Sets the impersonation preference that the client communicates to the server.</span></span> <span data-ttu-id="56e3b-117">Режим олицетворения, выбираемый клиентом, не задается принудительно для сервера.</span><span class="sxs-lookup"><span data-stu-id="56e3b-117">The impersonation mode that the client selects is not enforced on the server.</span></span> <span data-ttu-id="56e3b-118">Допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="56e3b-118">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="56e3b-119">-Identification: Сервер может получать удостоверение и привилегии клиента, но не может олицетворять клиента.</span><span class="sxs-lookup"><span data-stu-id="56e3b-119">-   Identification: The server can get the identity and privileges of the client, but cannot impersonate the client.</span></span><br /><span data-ttu-id="56e3b-120">-Олицетворения: Сервер может олицетворять контекст безопасности клиента в локальной системе.</span><span class="sxs-lookup"><span data-stu-id="56e3b-120">-   Impersonation: The server can impersonate the client's security context on the local system.</span></span><br /><span data-ttu-id="56e3b-121">-Делегирование: Сервер может олицетворять контекст безопасности клиента в удаленных системах.</span><span class="sxs-lookup"><span data-stu-id="56e3b-121">-   Delegation: The server can impersonate the client's security context on remote systems.</span></span><br /><span data-ttu-id="56e3b-122">-Anonymous: Сервер не может олицетворять или идентифицировать клиента.</span><span class="sxs-lookup"><span data-stu-id="56e3b-122">-   Anonymous: The server cannot impersonate or identify the client.</span></span><br /><span data-ttu-id="56e3b-123">— None: Уровень олицетворения не назначается.</span><span class="sxs-lookup"><span data-stu-id="56e3b-123">-   None: An impersonation level is not assigned.</span></span><br /><br /> <span data-ttu-id="56e3b-124">Значение по умолчанию - Identification.</span><span class="sxs-lookup"><span data-stu-id="56e3b-124">The default is Identification.</span></span> <span data-ttu-id="56e3b-125">Это атрибут типа <xref:System.Security.Principal.TokenImpersonationLevel>.</span><span class="sxs-lookup"><span data-stu-id="56e3b-125">This attribute is of type <xref:System.Security.Principal.TokenImpersonationLevel>.</span></span>|  
|`allowNtlm`|<span data-ttu-id="56e3b-126">Если установить для данного свойства значение `true`, то проверка подлинности может понижаться до NTLM в том случае, если проверка Kerberos недоступна.</span><span class="sxs-lookup"><span data-stu-id="56e3b-126">Setting this property to `true` allows authentication to downgrade to NTLM if Kerberos is not available.</span></span><br /><br /> <span data-ttu-id="56e3b-127">Если установить для данного свойства значение `false`, это приведет к тому, что [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] будет принимать все возможные усилия для вызова исключения в том случае, если используется NTLM.</span><span class="sxs-lookup"><span data-stu-id="56e3b-127">Setting this property to `false` causes [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] to make a best-effort to throw an exception if NTLM is used.</span></span> <span data-ttu-id="56e3b-128">Обратите внимание, что установка для данного свойства значения `false` не предотвращает отправки учетных данных NTLM по сети.</span><span class="sxs-lookup"><span data-stu-id="56e3b-128">Note that setting this property to `false` may not prevent NTLM credentials from being sent over the wire.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="56e3b-129">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="56e3b-129">Child Elements</span></span>  
 <span data-ttu-id="56e3b-130">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="56e3b-130">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="56e3b-131">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="56e3b-131">Parent Elements</span></span>  
  
|<span data-ttu-id="56e3b-132">Элемент</span><span class="sxs-lookup"><span data-stu-id="56e3b-132">Element</span></span>|<span data-ttu-id="56e3b-133">Описание</span><span class="sxs-lookup"><span data-stu-id="56e3b-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="56e3b-134">\<clientCredentials ></span><span class="sxs-lookup"><span data-stu-id="56e3b-134">\<clientCredentials></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md)|<span data-ttu-id="56e3b-135">Задает учетные данные, используемые для проверки подлинности клиента при подключении к службе.</span><span class="sxs-lookup"><span data-stu-id="56e3b-135">Specifies the credentials used to authenticate the client to the service.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="56e3b-136">См. также</span><span class="sxs-lookup"><span data-stu-id="56e3b-136">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.WindowsClientElement>  
 <xref:System.ServiceModel.Configuration.ClientCredentialsElement>  
 <xref:System.ServiceModel.Description.ClientCredentials>  
 <xref:System.ServiceModel.Configuration.ClientCredentialsElement.Windows%2A>  
 <xref:System.ServiceModel.Description.ClientCredentials>  
 <xref:System.ServiceModel.Description.ClientCredentials.Windows%2A>  
 <xref:System.ServiceModel.Security.WindowsClientCredential>  
 [<span data-ttu-id="56e3b-137">Защита клиентов</span><span class="sxs-lookup"><span data-stu-id="56e3b-137">Securing Clients</span></span>](../../../../../docs/framework/wcf/securing-clients.md)  
 [<span data-ttu-id="56e3b-138">Работа с сертификатами</span><span class="sxs-lookup"><span data-stu-id="56e3b-138">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [<span data-ttu-id="56e3b-139">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="56e3b-139">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)

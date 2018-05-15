---
title: '&lt;windows&gt; элемента &lt;clientCredentials&gt;'
ms.date: 03/30/2017
ms.assetid: 793e41c2-31ea-4159-abbc-2123bf097233
ms.openlocfilehash: 9badcfafff4bc09a16b0b9a565a9ea5c01e26bb5
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="ltwindowsgt-of-ltclientcredentialsgt-element"></a><span data-ttu-id="0a0f5-102">&lt;windows&gt; элемента &lt;clientCredentials&gt;</span><span class="sxs-lookup"><span data-stu-id="0a0f5-102">&lt;windows&gt; of &lt;clientCredentials&gt; Element</span></span>
<span data-ttu-id="0a0f5-103">Определяет параметры учетных данных Windows, которые используются для представления клиента.</span><span class="sxs-lookup"><span data-stu-id="0a0f5-103">Specifies the settings for a Windows credential to be used to represent the client.</span></span>  
  
 <span data-ttu-id="0a0f5-104">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="0a0f5-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="0a0f5-105">\<поведения ></span><span class="sxs-lookup"><span data-stu-id="0a0f5-105">\<behaviors></span></span>  
<span data-ttu-id="0a0f5-106">\<endpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="0a0f5-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="0a0f5-107">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="0a0f5-107">\<behavior></span></span>  
<span data-ttu-id="0a0f5-108">\<clientCredentials ></span><span class="sxs-lookup"><span data-stu-id="0a0f5-108">\<clientCredentials></span></span>  
<span data-ttu-id="0a0f5-109">\<Windows ></span><span class="sxs-lookup"><span data-stu-id="0a0f5-109">\<windows></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0a0f5-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0a0f5-110">Syntax</span></span>  
  
```xml  
<windows   
    allowedImpersonationLevel="Identification/Impersonation/Delegation/Anonymous/None"  
        allowNtlm="Boolean"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0a0f5-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="0a0f5-111">Attributes and Elements</span></span>  
 <span data-ttu-id="0a0f5-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="0a0f5-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0a0f5-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="0a0f5-113">Attributes</span></span>  
  
|<span data-ttu-id="0a0f5-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="0a0f5-114">Attribute</span></span>|<span data-ttu-id="0a0f5-115">Описание</span><span class="sxs-lookup"><span data-stu-id="0a0f5-115">Description</span></span>|  
|---------------|-----------------|  
|`allowedImpersonationLevel`|<span data-ttu-id="0a0f5-116">Задает параметры олицетворения, сообщаемые клиентом серверу.</span><span class="sxs-lookup"><span data-stu-id="0a0f5-116">Sets the impersonation preference that the client communicates to the server.</span></span> <span data-ttu-id="0a0f5-117">Режим олицетворения, выбираемый клиентом, не задается принудительно для сервера.</span><span class="sxs-lookup"><span data-stu-id="0a0f5-117">The impersonation mode that the client selects is not enforced on the server.</span></span> <span data-ttu-id="0a0f5-118">Допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="0a0f5-118">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="0a0f5-119">-Identification: Сервер может получать удостоверение и привилегии клиента, но не может олицетворять клиента.</span><span class="sxs-lookup"><span data-stu-id="0a0f5-119">-   Identification: The server can get the identity and privileges of the client, but cannot impersonate the client.</span></span><br /><span data-ttu-id="0a0f5-120">-Олицетворения: Сервер может олицетворять контекст безопасности клиента в локальной системе.</span><span class="sxs-lookup"><span data-stu-id="0a0f5-120">-   Impersonation: The server can impersonate the client's security context on the local system.</span></span><br /><span data-ttu-id="0a0f5-121">-Делегирование: Сервер может олицетворять контекст безопасности клиента в удаленных системах.</span><span class="sxs-lookup"><span data-stu-id="0a0f5-121">-   Delegation: The server can impersonate the client's security context on remote systems.</span></span><br /><span data-ttu-id="0a0f5-122">-Anonymous: Сервер не может олицетворять или идентифицировать клиента.</span><span class="sxs-lookup"><span data-stu-id="0a0f5-122">-   Anonymous: The server cannot impersonate or identify the client.</span></span><br /><span data-ttu-id="0a0f5-123">— None: Уровень олицетворения не назначается.</span><span class="sxs-lookup"><span data-stu-id="0a0f5-123">-   None: An impersonation level is not assigned.</span></span><br /><br /> <span data-ttu-id="0a0f5-124">Значение по умолчанию - Identification.</span><span class="sxs-lookup"><span data-stu-id="0a0f5-124">The default is Identification.</span></span> <span data-ttu-id="0a0f5-125">Это атрибут типа <xref:System.Security.Principal.TokenImpersonationLevel>.</span><span class="sxs-lookup"><span data-stu-id="0a0f5-125">This attribute is of type <xref:System.Security.Principal.TokenImpersonationLevel>.</span></span>|  
|`allowNtlm`|<span data-ttu-id="0a0f5-126">Если установить для данного свойства значение `true`, то проверка подлинности может понижаться до NTLM в том случае, если проверка Kerberos недоступна.</span><span class="sxs-lookup"><span data-stu-id="0a0f5-126">Setting this property to `true` allows authentication to downgrade to NTLM if Kerberos is not available.</span></span><br /><br /> <span data-ttu-id="0a0f5-127">Присвоение этому свойству `false` вызывает Windows Communication Foundation (WCF) вносить усилия для создания исключения, если используется NTLM.</span><span class="sxs-lookup"><span data-stu-id="0a0f5-127">Setting this property to `false` causes Windows Communication Foundation (WCF) to make a best-effort to throw an exception if NTLM is used.</span></span> <span data-ttu-id="0a0f5-128">Обратите внимание, что установка для данного свойства значения `false` не предотвращает отправки учетных данных NTLM по сети.</span><span class="sxs-lookup"><span data-stu-id="0a0f5-128">Note that setting this property to `false` may not prevent NTLM credentials from being sent over the wire.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0a0f5-129">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="0a0f5-129">Child Elements</span></span>  
 <span data-ttu-id="0a0f5-130">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="0a0f5-130">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0a0f5-131">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="0a0f5-131">Parent Elements</span></span>  
  
|<span data-ttu-id="0a0f5-132">Элемент</span><span class="sxs-lookup"><span data-stu-id="0a0f5-132">Element</span></span>|<span data-ttu-id="0a0f5-133">Описание</span><span class="sxs-lookup"><span data-stu-id="0a0f5-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0a0f5-134">\<clientCredentials ></span><span class="sxs-lookup"><span data-stu-id="0a0f5-134">\<clientCredentials></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md)|<span data-ttu-id="0a0f5-135">Задает учетные данные, используемые для проверки подлинности клиента при подключении к службе.</span><span class="sxs-lookup"><span data-stu-id="0a0f5-135">Specifies the credentials used to authenticate the client to the service.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0a0f5-136">См. также</span><span class="sxs-lookup"><span data-stu-id="0a0f5-136">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.WindowsClientElement>  
 <xref:System.ServiceModel.Configuration.ClientCredentialsElement>  
 <xref:System.ServiceModel.Description.ClientCredentials>  
 <xref:System.ServiceModel.Configuration.ClientCredentialsElement.Windows%2A>  
 <xref:System.ServiceModel.Description.ClientCredentials>  
 <xref:System.ServiceModel.Description.ClientCredentials.Windows%2A>  
 <xref:System.ServiceModel.Security.WindowsClientCredential>  
 [<span data-ttu-id="0a0f5-137">Защита клиентов</span><span class="sxs-lookup"><span data-stu-id="0a0f5-137">Securing Clients</span></span>](../../../../../docs/framework/wcf/securing-clients.md)  
 [<span data-ttu-id="0a0f5-138">Работа с сертификатами</span><span class="sxs-lookup"><span data-stu-id="0a0f5-138">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [<span data-ttu-id="0a0f5-139">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="0a0f5-139">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)

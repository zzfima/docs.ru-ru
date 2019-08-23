---
title: <windows> элемента <clientCredentials>
ms.date: 03/30/2017
ms.assetid: 793e41c2-31ea-4159-abbc-2123bf097233
ms.openlocfilehash: e9f0ed9879cc42ea25b83e6b626139a40a593112
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69940300"
---
# <a name="windows-of-clientcredentials-element"></a><span data-ttu-id="78b17-102">\<> Windows > \<элемента ClientCredentials</span><span class="sxs-lookup"><span data-stu-id="78b17-102">\<windows> of \<clientCredentials> Element</span></span>
<span data-ttu-id="78b17-103">Определяет параметры учетных данных Windows, которые используются для представления клиента.</span><span class="sxs-lookup"><span data-stu-id="78b17-103">Specifies the settings for a Windows credential to be used to represent the client.</span></span>  
  
 <span data-ttu-id="78b17-104">\<системой. > ServiceModel</span><span class="sxs-lookup"><span data-stu-id="78b17-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="78b17-105">\<> поведения</span><span class="sxs-lookup"><span data-stu-id="78b17-105">\<behaviors></span></span>  
<span data-ttu-id="78b17-106">\<endpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="78b17-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="78b17-107">\<> поведения</span><span class="sxs-lookup"><span data-stu-id="78b17-107">\<behavior></span></span>  
<span data-ttu-id="78b17-108">\<> clientCredentials</span><span class="sxs-lookup"><span data-stu-id="78b17-108">\<clientCredentials></span></span>  
<span data-ttu-id="78b17-109">\<> Windows</span><span class="sxs-lookup"><span data-stu-id="78b17-109">\<windows></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="78b17-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="78b17-110">Syntax</span></span>  
  
```xml  
<windows allowedImpersonationLevel="Identification/Impersonation/Delegation/Anonymous/None"
         allowNtlm="Boolean" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="78b17-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="78b17-111">Attributes and Elements</span></span>  
 <span data-ttu-id="78b17-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="78b17-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="78b17-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="78b17-113">Attributes</span></span>  
  
|<span data-ttu-id="78b17-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="78b17-114">Attribute</span></span>|<span data-ttu-id="78b17-115">Описание</span><span class="sxs-lookup"><span data-stu-id="78b17-115">Description</span></span>|  
|---------------|-----------------|  
|`allowedImpersonationLevel`|<span data-ttu-id="78b17-116">Задает параметры олицетворения, сообщаемые клиентом серверу.</span><span class="sxs-lookup"><span data-stu-id="78b17-116">Sets the impersonation preference that the client communicates to the server.</span></span> <span data-ttu-id="78b17-117">Режим олицетворения, выбираемый клиентом, не задается принудительно для сервера.</span><span class="sxs-lookup"><span data-stu-id="78b17-117">The impersonation mode that the client selects is not enforced on the server.</span></span> <span data-ttu-id="78b17-118">Допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="78b17-118">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="78b17-119">Идентификатор Сервер может получить удостоверение и привилегии клиента, но не может олицетворять клиента.</span><span class="sxs-lookup"><span data-stu-id="78b17-119">-   Identification: The server can get the identity and privileges of the client, but cannot impersonate the client.</span></span><br /><span data-ttu-id="78b17-120">Олицетворения Сервер может олицетворять контекст безопасности клиента в локальной системе.</span><span class="sxs-lookup"><span data-stu-id="78b17-120">-   Impersonation: The server can impersonate the client's security context on the local system.</span></span><br /><span data-ttu-id="78b17-121">Передачу Сервер может олицетворять контекст безопасности клиента в удаленных системах.</span><span class="sxs-lookup"><span data-stu-id="78b17-121">-   Delegation: The server can impersonate the client's security context on remote systems.</span></span><br /><span data-ttu-id="78b17-122">Подключившихся Серверу не удается олицетворить или опознать клиента.</span><span class="sxs-lookup"><span data-stu-id="78b17-122">-   Anonymous: The server cannot impersonate or identify the client.</span></span><br /><span data-ttu-id="78b17-123">None Уровень олицетворения не назначен.</span><span class="sxs-lookup"><span data-stu-id="78b17-123">-   None: An impersonation level is not assigned.</span></span><br /><br /> <span data-ttu-id="78b17-124">Значение по умолчанию - Identification.</span><span class="sxs-lookup"><span data-stu-id="78b17-124">The default is Identification.</span></span> <span data-ttu-id="78b17-125">Это атрибут типа <xref:System.Security.Principal.TokenImpersonationLevel>.</span><span class="sxs-lookup"><span data-stu-id="78b17-125">This attribute is of type <xref:System.Security.Principal.TokenImpersonationLevel>.</span></span>|  
|`allowNtlm`|<span data-ttu-id="78b17-126">Если установить для данного свойства значение `true`, то проверка подлинности может понижаться до NTLM в том случае, если проверка Kerberos недоступна.</span><span class="sxs-lookup"><span data-stu-id="78b17-126">Setting this property to `true` allows authentication to downgrade to NTLM if Kerberos is not available.</span></span><br /><br /> <span data-ttu-id="78b17-127">Если задать для `false` этого свойства значение Windows Communication Foundation (WCF), лучше будет создавать исключение, если используется NTLM.</span><span class="sxs-lookup"><span data-stu-id="78b17-127">Setting this property to `false` causes Windows Communication Foundation (WCF) to make a best-effort to throw an exception if NTLM is used.</span></span> <span data-ttu-id="78b17-128">Обратите внимание, что установка для данного свойства значения `false` не предотвращает отправки учетных данных NTLM по сети.</span><span class="sxs-lookup"><span data-stu-id="78b17-128">Note that setting this property to `false` may not prevent NTLM credentials from being sent over the wire.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="78b17-129">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="78b17-129">Child Elements</span></span>  
 <span data-ttu-id="78b17-130">Нет.</span><span class="sxs-lookup"><span data-stu-id="78b17-130">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="78b17-131">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="78b17-131">Parent Elements</span></span>  
  
|<span data-ttu-id="78b17-132">Элемент</span><span class="sxs-lookup"><span data-stu-id="78b17-132">Element</span></span>|<span data-ttu-id="78b17-133">Описание</span><span class="sxs-lookup"><span data-stu-id="78b17-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="78b17-134">\<> clientCredentials</span><span class="sxs-lookup"><span data-stu-id="78b17-134">\<clientCredentials></span></span>](clientcredentials.md)|<span data-ttu-id="78b17-135">Задает учетные данные, используемые для проверки подлинности клиента при подключении к службе.</span><span class="sxs-lookup"><span data-stu-id="78b17-135">Specifies the credentials used to authenticate the client to the service.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="78b17-136">См. также</span><span class="sxs-lookup"><span data-stu-id="78b17-136">See also</span></span>

- <xref:System.ServiceModel.Configuration.WindowsClientElement>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement.Windows%2A>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Description.ClientCredentials.Windows%2A>
- <xref:System.ServiceModel.Security.WindowsClientCredential>
- [<span data-ttu-id="78b17-137">Защита клиентов</span><span class="sxs-lookup"><span data-stu-id="78b17-137">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="78b17-138">Работа с сертификатами</span><span class="sxs-lookup"><span data-stu-id="78b17-138">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="78b17-139">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="78b17-139">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)

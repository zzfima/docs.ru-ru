---
title: Элемент <httpDigest>
ms.date: 03/30/2017
ms.assetid: 3da4f276-dfd9-4247-8c07-01d83618727c
ms.openlocfilehash: f392ebf4eeb6a008952fd4d5ef4e301e57f6eb31
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "70397993"
---
# <a name="httpdigest-element"></a><span data-ttu-id="5fcec-102">\<Элемент > Хттпдижест</span><span class="sxs-lookup"><span data-stu-id="5fcec-102">\<httpDigest> Element</span></span>
<span data-ttu-id="5fcec-103">Задает учетные данные, используемые для дайджест-проверки подлинности клиента при подключении к службе.</span><span class="sxs-lookup"><span data-stu-id="5fcec-103">Specifies a digest type credential used when authenticating the client to a service.</span></span>  
  
<span data-ttu-id="5fcec-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="5fcec-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="5fcec-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="5fcec-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="5fcec-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> поведения**](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="5fcec-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="5fcec-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<endpointBehaviors >** ](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="5fcec-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="5fcec-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> поведения**](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="5fcec-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="5fcec-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> clientCredentials**](clientcredentials.md)</span><span class="sxs-lookup"><span data-stu-id="5fcec-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)</span></span>\
<span data-ttu-id="5fcec-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Хттпдижест >**</span><span class="sxs-lookup"><span data-stu-id="5fcec-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<httpDigest>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5fcec-111">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5fcec-111">Syntax</span></span>  
  
```xml  
<digest impersonationLevel="Identification/Impersonation/Delegation/Anonymous/None" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5fcec-112">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="5fcec-112">Attributes and Elements</span></span>  
 <span data-ttu-id="5fcec-113">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="5fcec-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5fcec-114">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="5fcec-114">Attributes</span></span>  
  
|<span data-ttu-id="5fcec-115">Атрибут</span><span class="sxs-lookup"><span data-stu-id="5fcec-115">Attribute</span></span>|<span data-ttu-id="5fcec-116">Описание</span><span class="sxs-lookup"><span data-stu-id="5fcec-116">Description</span></span>|  
|---------------|-----------------|  
|`impersonationLevel`|<span data-ttu-id="5fcec-117">Задает параметры олицетворения, сообщаемые клиентом серверу.</span><span class="sxs-lookup"><span data-stu-id="5fcec-117">Sets the impersonation preference that the client communicates to the server.</span></span> <span data-ttu-id="5fcec-118">Режим олицетворения, выбираемый клиентом, не задается принудительно для сервера.</span><span class="sxs-lookup"><span data-stu-id="5fcec-118">The impersonation mode that the client selects is not enforced on the server.</span></span> <span data-ttu-id="5fcec-119">Допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="5fcec-119">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="5fcec-120">Идентификатор Сервер может получить удостоверение и привилегии клиента, но не может олицетворять клиента.</span><span class="sxs-lookup"><span data-stu-id="5fcec-120">-   Identification: The server can get the identity and privileges of the client, but cannot impersonate the client.</span></span><br /><span data-ttu-id="5fcec-121">Олицетворения Сервер может олицетворять контекст безопасности клиента в локальной системе.</span><span class="sxs-lookup"><span data-stu-id="5fcec-121">-   Impersonation: The server can impersonate the client's security context on the local system.</span></span><br /><span data-ttu-id="5fcec-122">Передачу Сервер может олицетворять контекст безопасности клиента в удаленных системах.</span><span class="sxs-lookup"><span data-stu-id="5fcec-122">-   Delegation: The server can impersonate the client's security context on remote systems.</span></span><br /><span data-ttu-id="5fcec-123">Подключившихся Серверу не удается олицетворить или опознать клиента.</span><span class="sxs-lookup"><span data-stu-id="5fcec-123">-   Anonymous: The server cannot impersonate or identify the client.</span></span><br /><span data-ttu-id="5fcec-124">None Уровень олицетворения не назначен.</span><span class="sxs-lookup"><span data-stu-id="5fcec-124">-   None: An impersonation level is not assigned.</span></span><br /><br /> <span data-ttu-id="5fcec-125">Значение по умолчанию - Identification.</span><span class="sxs-lookup"><span data-stu-id="5fcec-125">The default is Identification.</span></span> <span data-ttu-id="5fcec-126">Это атрибут типа <xref:System.Security.Principal.TokenImpersonationLevel>.</span><span class="sxs-lookup"><span data-stu-id="5fcec-126">This attribute is of type <xref:System.Security.Principal.TokenImpersonationLevel>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5fcec-127">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="5fcec-127">Child Elements</span></span>  
 <span data-ttu-id="5fcec-128">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="5fcec-128">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5fcec-129">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="5fcec-129">Parent Elements</span></span>  
  
|<span data-ttu-id="5fcec-130">Элемент</span><span class="sxs-lookup"><span data-stu-id="5fcec-130">Element</span></span>|<span data-ttu-id="5fcec-131">Описание</span><span class="sxs-lookup"><span data-stu-id="5fcec-131">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5fcec-132">\<> clientCredentials</span><span class="sxs-lookup"><span data-stu-id="5fcec-132">\<clientCredentials></span></span>](clientcredentials.md)|<span data-ttu-id="5fcec-133">Задает учетные данные, используемые для проверки подлинности клиента при подключении к службе.</span><span class="sxs-lookup"><span data-stu-id="5fcec-133">Specifies the credentials used to authenticate a client to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5fcec-134">Примечания</span><span class="sxs-lookup"><span data-stu-id="5fcec-134">Remarks</span></span>  
 <span data-ttu-id="5fcec-135">Хэш-кода — это хэш, определяемый с помощью алгоритма и набора входных данных.</span><span class="sxs-lookup"><span data-stu-id="5fcec-135">A digest is a hash determined by using an algorithm and a set of inputs.</span></span> <span data-ttu-id="5fcec-136">Структура проверки подлинности и проверяемый объект согласуют алгоритм и обмениваются данными, используемыми в качестве входных.</span><span class="sxs-lookup"><span data-stu-id="5fcec-136">The authenticator and the authenticated agree upon an algorithm and exchange the data used as inputs.</span></span> <span data-ttu-id="5fcec-137">Клиент может вычислить хэш и отправить его службе.</span><span class="sxs-lookup"><span data-stu-id="5fcec-137">The client can calculate the hash and send it to the service.</span></span> <span data-ttu-id="5fcec-138">Служба также вычисляет хэш и сравнивает значения.</span><span class="sxs-lookup"><span data-stu-id="5fcec-138">The service also calculates the hash and compares the values.</span></span> <span data-ttu-id="5fcec-139">Совпадение значений подтверждает подлинность клиента.</span><span class="sxs-lookup"><span data-stu-id="5fcec-139">A match validates the client.</span></span>  
  
 <span data-ttu-id="5fcec-140">Эта функция должна быть включена с помощью Active Directory в Windows и службах IIS.</span><span class="sxs-lookup"><span data-stu-id="5fcec-140">This feature must be enabled with Active Directory on Windows and Internet Information Services (IIS).</span></span> <span data-ttu-id="5fcec-141">Дополнительные сведения см. [в статье дайджест-проверка подлинности в IIS 6,0](https://go.microsoft.com/fwlink/?LinkId=88443).</span><span class="sxs-lookup"><span data-stu-id="5fcec-141">For more information, see [Digest Authentication in IIS 6.0](https://go.microsoft.com/fwlink/?LinkId=88443).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5fcec-142">См. также</span><span class="sxs-lookup"><span data-stu-id="5fcec-142">See also</span></span>

- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement.HttpDigest%2A>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Description.ClientCredentials.HttpDigest%2A>
- <xref:System.ServiceModel.Configuration.HttpDigestClientElement>
- <xref:System.ServiceModel.Security.HttpDigestClientCredential>
- [<span data-ttu-id="5fcec-143">Поведения безопасности</span><span class="sxs-lookup"><span data-stu-id="5fcec-143">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="5fcec-144">Защита клиентов</span><span class="sxs-lookup"><span data-stu-id="5fcec-144">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="5fcec-145">Работа с сертификатами</span><span class="sxs-lookup"><span data-stu-id="5fcec-145">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="5fcec-146">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="5fcec-146">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)

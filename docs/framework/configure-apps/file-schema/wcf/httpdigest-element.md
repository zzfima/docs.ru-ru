---
title: Элемент <httpDigest>
ms.date: 03/30/2017
ms.assetid: 3da4f276-dfd9-4247-8c07-01d83618727c
ms.openlocfilehash: c930efbc2cd7a6dc12795d5ac1c26ea92fc36599
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55259011"
---
# <a name="httpdigest-element"></a><span data-ttu-id="08314-102">\<httpDigest> Element</span><span class="sxs-lookup"><span data-stu-id="08314-102">\<httpDigest> Element</span></span>
<span data-ttu-id="08314-103">Задает учетные данные, используемые для дайджест-проверки подлинности клиента при подключении к службе.</span><span class="sxs-lookup"><span data-stu-id="08314-103">Specifies a digest type credential used when authenticating the client to a service.</span></span>  
  
 <span data-ttu-id="08314-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="08314-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="08314-105">\<варианты поведения ></span><span class="sxs-lookup"><span data-stu-id="08314-105">\<behaviors></span></span>  
<span data-ttu-id="08314-106">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="08314-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="08314-107">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="08314-107">\<behavior></span></span>  
<span data-ttu-id="08314-108">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="08314-108">\<clientCredentials></span></span>  
<span data-ttu-id="08314-109">\<httpDigest></span><span class="sxs-lookup"><span data-stu-id="08314-109">\<httpDigest></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="08314-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="08314-110">Syntax</span></span>  
  
```xml  
<digest impersonationLevel="Identification/Impersonation/Delegation/Anonymous/None" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="08314-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="08314-111">Attributes and Elements</span></span>  
 <span data-ttu-id="08314-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="08314-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="08314-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="08314-113">Attributes</span></span>  
  
|<span data-ttu-id="08314-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="08314-114">Attribute</span></span>|<span data-ttu-id="08314-115">Описание</span><span class="sxs-lookup"><span data-stu-id="08314-115">Description</span></span>|  
|---------------|-----------------|  
|`impersonationLevel`|<span data-ttu-id="08314-116">Задает параметры олицетворения, сообщаемые клиентом серверу.</span><span class="sxs-lookup"><span data-stu-id="08314-116">Sets the impersonation preference that the client communicates to the server.</span></span> <span data-ttu-id="08314-117">Режим олицетворения, выбираемый клиентом, не задается принудительно для сервера.</span><span class="sxs-lookup"><span data-stu-id="08314-117">The impersonation mode that the client selects is not enforced on the server.</span></span> <span data-ttu-id="08314-118">Допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="08314-118">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="08314-119">-Идентификация: Сервер может получать удостоверение и привилегии клиента, но не может олицетворять клиента.</span><span class="sxs-lookup"><span data-stu-id="08314-119">-   Identification: The server can get the identity and privileges of the client, but cannot impersonate the client.</span></span><br /><span data-ttu-id="08314-120">-Олицетворения: Сервер может олицетворять контекст безопасности клиента в локальной системе.</span><span class="sxs-lookup"><span data-stu-id="08314-120">-   Impersonation: The server can impersonate the client's security context on the local system.</span></span><br /><span data-ttu-id="08314-121">-Делегирование: Сервер может олицетворять контекст безопасности клиента в удаленных системах.</span><span class="sxs-lookup"><span data-stu-id="08314-121">-   Delegation: The server can impersonate the client's security context on remote systems.</span></span><br /><span data-ttu-id="08314-122">-Анонимный: Сервер не может олицетворять или идентифицировать клиента.</span><span class="sxs-lookup"><span data-stu-id="08314-122">-   Anonymous: The server cannot impersonate or identify the client.</span></span><br /><span data-ttu-id="08314-123">-None: Уровень олицетворения не назначается.</span><span class="sxs-lookup"><span data-stu-id="08314-123">-   None: An impersonation level is not assigned.</span></span><br /><br /> <span data-ttu-id="08314-124">Значение по умолчанию - Identification.</span><span class="sxs-lookup"><span data-stu-id="08314-124">The default is Identification.</span></span> <span data-ttu-id="08314-125">Это атрибут типа <xref:System.Security.Principal.TokenImpersonationLevel>.</span><span class="sxs-lookup"><span data-stu-id="08314-125">This attribute is of type <xref:System.Security.Principal.TokenImpersonationLevel>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="08314-126">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="08314-126">Child Elements</span></span>  
 <span data-ttu-id="08314-127">Нет</span><span class="sxs-lookup"><span data-stu-id="08314-127">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="08314-128">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="08314-128">Parent Elements</span></span>  
  
|<span data-ttu-id="08314-129">Элемент</span><span class="sxs-lookup"><span data-stu-id="08314-129">Element</span></span>|<span data-ttu-id="08314-130">Описание:</span><span class="sxs-lookup"><span data-stu-id="08314-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="08314-131">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="08314-131">\<clientCredentials></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md)|<span data-ttu-id="08314-132">Задает учетные данные, используемые для проверки подлинности клиента при подключении к службе.</span><span class="sxs-lookup"><span data-stu-id="08314-132">Specifies the credentials used to authenticate a client to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="08314-133">Примечания</span><span class="sxs-lookup"><span data-stu-id="08314-133">Remarks</span></span>  
 <span data-ttu-id="08314-134">Хэш-кода — это хэш, определяемый с помощью алгоритма и набора входных данных.</span><span class="sxs-lookup"><span data-stu-id="08314-134">A digest is a hash determined by using an algorithm and a set of inputs.</span></span> <span data-ttu-id="08314-135">Структура проверки подлинности и проверяемый объект согласуют алгоритм и обмениваются данными, используемыми в качестве входных.</span><span class="sxs-lookup"><span data-stu-id="08314-135">The authenticator and the authenticated agree upon an algorithm and exchange the data used as inputs.</span></span> <span data-ttu-id="08314-136">Клиент может вычислить хэш и отправить его службе.</span><span class="sxs-lookup"><span data-stu-id="08314-136">The client can calculate the hash and send it to the service.</span></span> <span data-ttu-id="08314-137">Служба также вычисляет хэш и сравнивает значения.</span><span class="sxs-lookup"><span data-stu-id="08314-137">The service also calculates the hash and compares the values.</span></span> <span data-ttu-id="08314-138">Совпадение значений подтверждает подлинность клиента.</span><span class="sxs-lookup"><span data-stu-id="08314-138">A match validates the client.</span></span>  
  
 <span data-ttu-id="08314-139">Эта возможность должна быть включена с помощью Active Directory в Windows и службах IIS.</span><span class="sxs-lookup"><span data-stu-id="08314-139">This feature must be enabled with Active Directory on Windows and Internet Information Services (IIS).</span></span> <span data-ttu-id="08314-140">Дополнительные сведения см. в разделе [дайджест-проверка подлинности в IIS 6.0](https://go.microsoft.com/fwlink/?LinkId=88443).</span><span class="sxs-lookup"><span data-stu-id="08314-140">For more information, see [Digest Authentication in IIS 6.0](https://go.microsoft.com/fwlink/?LinkId=88443).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08314-141">См. также</span><span class="sxs-lookup"><span data-stu-id="08314-141">See also</span></span>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement.HttpDigest%2A>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Description.ClientCredentials.HttpDigest%2A>
- <xref:System.ServiceModel.Configuration.HttpDigestClientElement>
- <xref:System.ServiceModel.Security.HttpDigestClientCredential>
- [<span data-ttu-id="08314-142">Поведения безопасности</span><span class="sxs-lookup"><span data-stu-id="08314-142">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="08314-143">Защита клиентов</span><span class="sxs-lookup"><span data-stu-id="08314-143">Securing Clients</span></span>](../../../../../docs/framework/wcf/securing-clients.md)
- [<span data-ttu-id="08314-144">Работа с сертификатами</span><span class="sxs-lookup"><span data-stu-id="08314-144">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="08314-145">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="08314-145">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)

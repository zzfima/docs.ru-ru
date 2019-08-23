---
title: Элемент <httpDigest>
ms.date: 03/30/2017
ms.assetid: 3da4f276-dfd9-4247-8c07-01d83618727c
ms.openlocfilehash: 2ceefdd7fab82025e89ad08d8423d57524c2e4d8
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69925562"
---
# <a name="httpdigest-element"></a><span data-ttu-id="1b662-102">\<Элемент > Хттпдижест</span><span class="sxs-lookup"><span data-stu-id="1b662-102">\<httpDigest> Element</span></span>
<span data-ttu-id="1b662-103">Задает учетные данные, используемые для дайджест-проверки подлинности клиента при подключении к службе.</span><span class="sxs-lookup"><span data-stu-id="1b662-103">Specifies a digest type credential used when authenticating the client to a service.</span></span>  
  
 <span data-ttu-id="1b662-104">\<системой. > ServiceModel</span><span class="sxs-lookup"><span data-stu-id="1b662-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="1b662-105">\<> поведения</span><span class="sxs-lookup"><span data-stu-id="1b662-105">\<behaviors></span></span>  
<span data-ttu-id="1b662-106">\<endpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="1b662-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="1b662-107">\<> поведения</span><span class="sxs-lookup"><span data-stu-id="1b662-107">\<behavior></span></span>  
<span data-ttu-id="1b662-108">\<> clientCredentials</span><span class="sxs-lookup"><span data-stu-id="1b662-108">\<clientCredentials></span></span>  
<span data-ttu-id="1b662-109">\<Хттпдижест ></span><span class="sxs-lookup"><span data-stu-id="1b662-109">\<httpDigest></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1b662-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1b662-110">Syntax</span></span>  
  
```xml  
<digest impersonationLevel="Identification/Impersonation/Delegation/Anonymous/None" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1b662-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="1b662-111">Attributes and Elements</span></span>  
 <span data-ttu-id="1b662-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="1b662-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1b662-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="1b662-113">Attributes</span></span>  
  
|<span data-ttu-id="1b662-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="1b662-114">Attribute</span></span>|<span data-ttu-id="1b662-115">Описание</span><span class="sxs-lookup"><span data-stu-id="1b662-115">Description</span></span>|  
|---------------|-----------------|  
|`impersonationLevel`|<span data-ttu-id="1b662-116">Задает параметры олицетворения, сообщаемые клиентом серверу.</span><span class="sxs-lookup"><span data-stu-id="1b662-116">Sets the impersonation preference that the client communicates to the server.</span></span> <span data-ttu-id="1b662-117">Режим олицетворения, выбираемый клиентом, не задается принудительно для сервера.</span><span class="sxs-lookup"><span data-stu-id="1b662-117">The impersonation mode that the client selects is not enforced on the server.</span></span> <span data-ttu-id="1b662-118">Допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="1b662-118">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="1b662-119">Идентификатор Сервер может получить удостоверение и привилегии клиента, но не может олицетворять клиента.</span><span class="sxs-lookup"><span data-stu-id="1b662-119">-   Identification: The server can get the identity and privileges of the client, but cannot impersonate the client.</span></span><br /><span data-ttu-id="1b662-120">Олицетворения Сервер может олицетворять контекст безопасности клиента в локальной системе.</span><span class="sxs-lookup"><span data-stu-id="1b662-120">-   Impersonation: The server can impersonate the client's security context on the local system.</span></span><br /><span data-ttu-id="1b662-121">Передачу Сервер может олицетворять контекст безопасности клиента в удаленных системах.</span><span class="sxs-lookup"><span data-stu-id="1b662-121">-   Delegation: The server can impersonate the client's security context on remote systems.</span></span><br /><span data-ttu-id="1b662-122">Подключившихся Серверу не удается олицетворить или опознать клиента.</span><span class="sxs-lookup"><span data-stu-id="1b662-122">-   Anonymous: The server cannot impersonate or identify the client.</span></span><br /><span data-ttu-id="1b662-123">None Уровень олицетворения не назначен.</span><span class="sxs-lookup"><span data-stu-id="1b662-123">-   None: An impersonation level is not assigned.</span></span><br /><br /> <span data-ttu-id="1b662-124">Значение по умолчанию - Identification.</span><span class="sxs-lookup"><span data-stu-id="1b662-124">The default is Identification.</span></span> <span data-ttu-id="1b662-125">Это атрибут типа <xref:System.Security.Principal.TokenImpersonationLevel>.</span><span class="sxs-lookup"><span data-stu-id="1b662-125">This attribute is of type <xref:System.Security.Principal.TokenImpersonationLevel>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1b662-126">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="1b662-126">Child Elements</span></span>  
 <span data-ttu-id="1b662-127">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="1b662-127">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1b662-128">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="1b662-128">Parent Elements</span></span>  
  
|<span data-ttu-id="1b662-129">Элемент</span><span class="sxs-lookup"><span data-stu-id="1b662-129">Element</span></span>|<span data-ttu-id="1b662-130">Описание</span><span class="sxs-lookup"><span data-stu-id="1b662-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1b662-131">\<> clientCredentials</span><span class="sxs-lookup"><span data-stu-id="1b662-131">\<clientCredentials></span></span>](clientcredentials.md)|<span data-ttu-id="1b662-132">Задает учетные данные, используемые для проверки подлинности клиента при подключении к службе.</span><span class="sxs-lookup"><span data-stu-id="1b662-132">Specifies the credentials used to authenticate a client to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1b662-133">Примечания</span><span class="sxs-lookup"><span data-stu-id="1b662-133">Remarks</span></span>  
 <span data-ttu-id="1b662-134">Хэш-кода — это хэш, определяемый с помощью алгоритма и набора входных данных.</span><span class="sxs-lookup"><span data-stu-id="1b662-134">A digest is a hash determined by using an algorithm and a set of inputs.</span></span> <span data-ttu-id="1b662-135">Структура проверки подлинности и проверяемый объект согласуют алгоритм и обмениваются данными, используемыми в качестве входных.</span><span class="sxs-lookup"><span data-stu-id="1b662-135">The authenticator and the authenticated agree upon an algorithm and exchange the data used as inputs.</span></span> <span data-ttu-id="1b662-136">Клиент может вычислить хэш и отправить его службе.</span><span class="sxs-lookup"><span data-stu-id="1b662-136">The client can calculate the hash and send it to the service.</span></span> <span data-ttu-id="1b662-137">Служба также вычисляет хэш и сравнивает значения.</span><span class="sxs-lookup"><span data-stu-id="1b662-137">The service also calculates the hash and compares the values.</span></span> <span data-ttu-id="1b662-138">Совпадение значений подтверждает подлинность клиента.</span><span class="sxs-lookup"><span data-stu-id="1b662-138">A match validates the client.</span></span>  
  
 <span data-ttu-id="1b662-139">Эта функция должна быть включена с помощью Active Directory в Windows и службах IIS.</span><span class="sxs-lookup"><span data-stu-id="1b662-139">This feature must be enabled with Active Directory on Windows and Internet Information Services (IIS).</span></span> <span data-ttu-id="1b662-140">Дополнительные сведения см. [в статье дайджест-проверка подлинности в IIS 6,0](https://go.microsoft.com/fwlink/?LinkId=88443).</span><span class="sxs-lookup"><span data-stu-id="1b662-140">For more information, see [Digest Authentication in IIS 6.0](https://go.microsoft.com/fwlink/?LinkId=88443).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b662-141">См. также</span><span class="sxs-lookup"><span data-stu-id="1b662-141">See also</span></span>

- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement.HttpDigest%2A>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Description.ClientCredentials.HttpDigest%2A>
- <xref:System.ServiceModel.Configuration.HttpDigestClientElement>
- <xref:System.ServiceModel.Security.HttpDigestClientCredential>
- [<span data-ttu-id="1b662-142">Поведения безопасности</span><span class="sxs-lookup"><span data-stu-id="1b662-142">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="1b662-143">Защита клиентов</span><span class="sxs-lookup"><span data-stu-id="1b662-143">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="1b662-144">Работа с сертификатами</span><span class="sxs-lookup"><span data-stu-id="1b662-144">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="1b662-145">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="1b662-145">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)

---
title: <servicePointManager> (Сетевые параметры)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#servicePointManager
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/servicePointManager
helpviewer_keywords:
- servicePointManager element
- <servicePointManager> element
ms.assetid: 6e5def51-3646-4ef6-a7bd-c69151321bec
ms.openlocfilehash: 407ed85de109a671030eccff8ddd92af91628014
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59202213"
---
# <a name="servicepointmanager-element-network-settings"></a><span data-ttu-id="fd881-102">\<servicePointManager > (сетевые параметры)</span><span class="sxs-lookup"><span data-stu-id="fd881-102">\<servicePointManager> Element (Network Settings)</span></span>
<span data-ttu-id="fd881-103">Настраивает подключения к сетевым ресурсам.</span><span class="sxs-lookup"><span data-stu-id="fd881-103">Configures connections to network resources.</span></span>  
  
 <span data-ttu-id="fd881-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="fd881-104">\<configuration></span></span>  
<span data-ttu-id="fd881-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="fd881-105">\<system.net></span></span>  
<span data-ttu-id="fd881-106">\<Параметры ></span><span class="sxs-lookup"><span data-stu-id="fd881-106">\<settings></span></span>  
<span data-ttu-id="fd881-107">\<servicePointManager ></span><span class="sxs-lookup"><span data-stu-id="fd881-107">\<servicePointManager></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fd881-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fd881-108">Syntax</span></span>  
  
```xml  
<servicePointManager  
  checkCertificateName="true|false"  
  checkCertificateRevocationList="true|false"  
  encryptionPolicy="AllowNoEncryption|NoEncryption|RequireEncryption"  
  expect100Continue="true|false"  
  useNagleAlgorithm="true|false"  
  enableDnsRoundRobin="true|false"  
  dnsRefreshTimeout="time"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fd881-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="fd881-109">Attributes and Elements</span></span>  
 <span data-ttu-id="fd881-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="fd881-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fd881-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="fd881-111">Attributes</span></span>  
  
|**<span data-ttu-id="fd881-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="fd881-112">Attribute</span></span>**|**<span data-ttu-id="fd881-113">Описание</span><span class="sxs-lookup"><span data-stu-id="fd881-113">Description</span></span>**|  
|-------------------|---------------------|  
|`checkCertificateName`|<span data-ttu-id="fd881-114">Указывает, должен ли система проверить соответствие имени узла сервера имен на сертификат перед использованием сертификата.</span><span class="sxs-lookup"><span data-stu-id="fd881-114">Specifies whether the system should verify that the name on the certificate matches the server host name before using the certificate.</span></span> <span data-ttu-id="fd881-115">Значение по умолчанию — `true`.</span><span class="sxs-lookup"><span data-stu-id="fd881-115">The default value is `true`.</span></span>|  
|`checkCertificateRevocationList`|<span data-ttu-id="fd881-116">Указывает, должна ли система проверять был отозван ли сертификат, прежде чем использовать сертификат.</span><span class="sxs-lookup"><span data-stu-id="fd881-116">Specifies whether the system should check whether the certificate has been revoked before using the certificate.</span></span> <span data-ttu-id="fd881-117">Значение по умолчанию — `false`.</span><span class="sxs-lookup"><span data-stu-id="fd881-117">The default value is `false`.</span></span>|  
|`dnsRefreshTimeout`|<span data-ttu-id="fd881-118">Указывает продолжительность службы доменных имен (DNS) разрешений кэшируются в сочетании с параметром циклического перебора DNS, в миллисекундах.</span><span class="sxs-lookup"><span data-stu-id="fd881-118">Specifies how long Domain Name Service (DNS) resolutions are cached in conjunction with the DNS Round Robin option, in milliseconds.</span></span> <span data-ttu-id="fd881-119">По умолчанию установлено значение 120 000 миллисекунд (2 минуты).</span><span class="sxs-lookup"><span data-stu-id="fd881-119">The default value is 120,000 milliseconds (two minutes).</span></span>|  
|`enableDnsRoundRobin`|<span data-ttu-id="fd881-120">Указывает имя ли разрешение DNS узла с несколькими адресами протокола Интернета (IP) возвращаемое все адреса или только первый из них.</span><span class="sxs-lookup"><span data-stu-id="fd881-120">Specifies whether DNS resolutions of host names with multiple Internet Protocol (IP) addresses return all the addresses, or just the first one.</span></span> <span data-ttu-id="fd881-121">Значение по умолчанию — `false`.</span><span class="sxs-lookup"><span data-stu-id="fd881-121">The default value is `false`.</span></span>|  
|`encryptionPolicy`|<span data-ttu-id="fd881-122">Указывает политики шифрования, примененный к сеанс SSL/TLS на <xref:System.Net.ServicePointManager> экземпляра.</span><span class="sxs-lookup"><span data-stu-id="fd881-122">Specifies the encryption policy applied to an SSL/TLS session on a <xref:System.Net.ServicePointManager> instance.</span></span> <span data-ttu-id="fd881-123">Возможные значения эквивалентны значениям <xref:System.Net.Security.EncryptionPolicy> перечисления.</span><span class="sxs-lookup"><span data-stu-id="fd881-123">The possible values are equivalent to the values for the <xref:System.Net.Security.EncryptionPolicy> enumeration.</span></span> <span data-ttu-id="fd881-124">Использование <xref:System.Security.Authentication.CipherAlgorithmType.Null> является обязательным, если настроена политика шифрования `NoEncryption`.</span><span class="sxs-lookup"><span data-stu-id="fd881-124">The use of <xref:System.Security.Authentication.CipherAlgorithmType.Null> is required when the encryption policy is set to `NoEncryption`.</span></span> <span data-ttu-id="fd881-125">Значение по умолчанию — `RequireEncryption`.</span><span class="sxs-lookup"><span data-stu-id="fd881-125">The default value is `RequireEncryption`.</span></span>|  
|`expect100Continue`|<span data-ttu-id="fd881-126">Указывает ли методы POST следует ожидать появления `100-continue` ответа от сервера.</span><span class="sxs-lookup"><span data-stu-id="fd881-126">Specifies whether POST methods should expect to receive a `100-continue` response from the server.</span></span> <span data-ttu-id="fd881-127">Значение по умолчанию — `true`.</span><span class="sxs-lookup"><span data-stu-id="fd881-127">The default value is `true`.</span></span>|  
|`useNagleAlgorithm`|<span data-ttu-id="fd881-128">Указывает, использовать ли подключениям, управляемым диспетчером точки службы алгоритм Nagle.</span><span class="sxs-lookup"><span data-stu-id="fd881-128">Specifies whether connections controlled by the service point manager use the Nagle algorithm.</span></span> <span data-ttu-id="fd881-129">Значение по умолчанию — `true`.</span><span class="sxs-lookup"><span data-stu-id="fd881-129">The default value is `true`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fd881-130">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="fd881-130">Child Elements</span></span>  
 <span data-ttu-id="fd881-131">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="fd881-131">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="fd881-132">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="fd881-132">Parent Elements</span></span>  
  
|**<span data-ttu-id="fd881-133">Элемент</span><span class="sxs-lookup"><span data-stu-id="fd881-133">Element</span></span>**|**<span data-ttu-id="fd881-134">Описание</span><span class="sxs-lookup"><span data-stu-id="fd881-134">Description</span></span>**|  
|-----------------|---------------------|  
|[<span data-ttu-id="fd881-135">Параметры</span><span class="sxs-lookup"><span data-stu-id="fd881-135">Settings</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/settings-element-network-settings.md)|<span data-ttu-id="fd881-136">Настраивает основные параметры сети для пространства имен <xref:System.Net>.</span><span class="sxs-lookup"><span data-stu-id="fd881-136">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fd881-137">Примечания</span><span class="sxs-lookup"><span data-stu-id="fd881-137">Remarks</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="fd881-138">Файлы конфигурации</span><span class="sxs-lookup"><span data-stu-id="fd881-138">Configuration Files</span></span>  
 <span data-ttu-id="fd881-139">Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="fd881-139">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd881-140">См. также</span><span class="sxs-lookup"><span data-stu-id="fd881-140">See also</span></span>

- <xref:System.Net.ServicePointManager>
- <xref:System.Net.Security.EncryptionPolicy>
- [<span data-ttu-id="fd881-141">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="fd881-141">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)

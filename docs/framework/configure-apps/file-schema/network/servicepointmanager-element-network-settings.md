---
title: Элемент <servicePointManager> (параметры сети)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#servicePointManager
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/servicePointManager
helpviewer_keywords:
- servicePointManager element
- <servicePointManager> element
ms.assetid: 6e5def51-3646-4ef6-a7bd-c69151321bec
ms.openlocfilehash: b7333016fea2d46285d3c98181c0ca4904c376f8
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/14/2019
ms.locfileid: "74089128"
---
# <a name="servicepointmanager-element-network-settings"></a><span data-ttu-id="211e5-102">Элемент \<servicePointManager > (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="211e5-102">\<servicePointManager> Element (Network Settings)</span></span>
<span data-ttu-id="211e5-103">Настраивает подключения к сетевым ресурсам.</span><span class="sxs-lookup"><span data-stu-id="211e5-103">Configures connections to network resources.</span></span>  

<span data-ttu-id="211e5-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="211e5-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="211e5-105">&nbsp;&nbsp;[ **\<System. net >** ](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="211e5-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>\
<span data-ttu-id="211e5-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<** ](settings-element-network-settings.md) ></span><span class="sxs-lookup"><span data-stu-id="211e5-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<settings>**](settings-element-network-settings.md)</span></span>\
<span data-ttu-id="211e5-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<servicePointManager >**</span><span class="sxs-lookup"><span data-stu-id="211e5-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<servicePointManager>**</span></span>

## <a name="syntax"></a><span data-ttu-id="211e5-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="211e5-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="211e5-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="211e5-109">Attributes and Elements</span></span>  
 <span data-ttu-id="211e5-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="211e5-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="211e5-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="211e5-111">Attributes</span></span>  
  
|<span data-ttu-id="211e5-112">**Attribute (XElement Dynamic Property)** (Attribute (динамическое свойство XElement))</span><span class="sxs-lookup"><span data-stu-id="211e5-112">**Attribute**</span></span>|<span data-ttu-id="211e5-113">**Описание**</span><span class="sxs-lookup"><span data-stu-id="211e5-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`checkCertificateName`|<span data-ttu-id="211e5-114">Указывает, должна ли система проверять имя сертификата на соответствие имени узла сервера перед использованием сертификата.</span><span class="sxs-lookup"><span data-stu-id="211e5-114">Specifies whether the system should verify that the name on the certificate matches the server host name before using the certificate.</span></span> <span data-ttu-id="211e5-115">Значение по умолчанию — `true`.</span><span class="sxs-lookup"><span data-stu-id="211e5-115">The default value is `true`.</span></span>|  
|`checkCertificateRevocationList`|<span data-ttu-id="211e5-116">Указывает, должна ли система проверять, отозван ли сертификат перед использованием сертификата.</span><span class="sxs-lookup"><span data-stu-id="211e5-116">Specifies whether the system should check whether the certificate has been revoked before using the certificate.</span></span> <span data-ttu-id="211e5-117">Значение по умолчанию — `false`.</span><span class="sxs-lookup"><span data-stu-id="211e5-117">The default value is `false`.</span></span>|  
|`dnsRefreshTimeout`|<span data-ttu-id="211e5-118">Указывает, как долго кэшируются разрешения службы доменных имен (DNS) в сочетании с параметром циклического перебора DNS в миллисекундах.</span><span class="sxs-lookup"><span data-stu-id="211e5-118">Specifies how long Domain Name Service (DNS) resolutions are cached in conjunction with the DNS Round Robin option, in milliseconds.</span></span> <span data-ttu-id="211e5-119">По умолчанию установлено значение 120 000 миллисекунд (2 минуты).</span><span class="sxs-lookup"><span data-stu-id="211e5-119">The default value is 120,000 milliseconds (two minutes).</span></span>|  
|`enableDnsRoundRobin`|<span data-ttu-id="211e5-120">Указывает, должны ли разрешения DNS имен узлов с несколькими IP-адресами возвращать все адреса или только первый из них.</span><span class="sxs-lookup"><span data-stu-id="211e5-120">Specifies whether DNS resolutions of host names with multiple Internet Protocol (IP) addresses return all the addresses, or just the first one.</span></span> <span data-ttu-id="211e5-121">Значение по умолчанию — `false`.</span><span class="sxs-lookup"><span data-stu-id="211e5-121">The default value is `false`.</span></span>|  
|`encryptionPolicy`|<span data-ttu-id="211e5-122">Указывает политику шифрования, применяемую к сеансу SSL/TLS на <xref:System.Net.ServicePointManager> экземпляре.</span><span class="sxs-lookup"><span data-stu-id="211e5-122">Specifies the encryption policy applied to an SSL/TLS session on a <xref:System.Net.ServicePointManager> instance.</span></span> <span data-ttu-id="211e5-123">Возможные значения эквивалентны значениям перечисления <xref:System.Net.Security.EncryptionPolicy>.</span><span class="sxs-lookup"><span data-stu-id="211e5-123">The possible values are equivalent to the values for the <xref:System.Net.Security.EncryptionPolicy> enumeration.</span></span> <span data-ttu-id="211e5-124">Использование <xref:System.Security.Authentication.CipherAlgorithmType.Null> требуется, если для политики шифрования задано значение `NoEncryption`.</span><span class="sxs-lookup"><span data-stu-id="211e5-124">The use of <xref:System.Security.Authentication.CipherAlgorithmType.Null> is required when the encryption policy is set to `NoEncryption`.</span></span> <span data-ttu-id="211e5-125">Значение по умолчанию — `RequireEncryption`.</span><span class="sxs-lookup"><span data-stu-id="211e5-125">The default value is `RequireEncryption`.</span></span>|  
|`expect100Continue`|<span data-ttu-id="211e5-126">Указывает, должны ли методы POST рассчитывать на получение `100-continue` ответа от сервера.</span><span class="sxs-lookup"><span data-stu-id="211e5-126">Specifies whether POST methods should expect to receive a `100-continue` response from the server.</span></span> <span data-ttu-id="211e5-127">Значение по умолчанию — `true`.</span><span class="sxs-lookup"><span data-stu-id="211e5-127">The default value is `true`.</span></span>|  
|`useNagleAlgorithm`|<span data-ttu-id="211e5-128">Указывает, используют ли подключения, управляемые диспетчером точек обслуживания, алгоритм Nagle.</span><span class="sxs-lookup"><span data-stu-id="211e5-128">Specifies whether connections controlled by the service point manager use the Nagle algorithm.</span></span> <span data-ttu-id="211e5-129">Значение по умолчанию — `true`.</span><span class="sxs-lookup"><span data-stu-id="211e5-129">The default value is `true`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="211e5-130">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="211e5-130">Child Elements</span></span>  
 <span data-ttu-id="211e5-131">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="211e5-131">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="211e5-132">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="211e5-132">Parent Elements</span></span>  
  
|<span data-ttu-id="211e5-133">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="211e5-133">**Element**</span></span>|<span data-ttu-id="211e5-134">**Описание**</span><span class="sxs-lookup"><span data-stu-id="211e5-134">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="211e5-135">Параметры</span><span class="sxs-lookup"><span data-stu-id="211e5-135">Settings</span></span>](settings-element-network-settings.md)|<span data-ttu-id="211e5-136">Настраивает основные параметры сети для пространства имен <xref:System.Net>.</span><span class="sxs-lookup"><span data-stu-id="211e5-136">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="211e5-137">Заметки</span><span class="sxs-lookup"><span data-stu-id="211e5-137">Remarks</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="211e5-138">Файлы конфигурации</span><span class="sxs-lookup"><span data-stu-id="211e5-138">Configuration Files</span></span>  
 <span data-ttu-id="211e5-139">Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="211e5-139">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="211e5-140">См. также</span><span class="sxs-lookup"><span data-stu-id="211e5-140">See also</span></span>

- <xref:System.Net.ServicePointManager>
- <xref:System.Net.Security.EncryptionPolicy>
- [<span data-ttu-id="211e5-141">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="211e5-141">Network Settings Schema</span></span>](index.md)

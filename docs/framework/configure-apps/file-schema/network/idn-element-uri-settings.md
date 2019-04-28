---
title: Элемент <idn> (параметры URI)
ms.date: 03/30/2017
ms.assetid: 16c8e869-1791-4cf5-9244-3d3c738f60ec
ms.openlocfilehash: 2d2729f9120d6b6fe673904ad2bf6d005ddf5469
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61705120"
---
# <a name="idn-element-uri-settings"></a><span data-ttu-id="e1e4d-102">\<IDN > (параметры Uri)</span><span class="sxs-lookup"><span data-stu-id="e1e4d-102">\<idn> Element (Uri Settings)</span></span>
<span data-ttu-id="e1e4d-103">Указывает, применяется ли синтаксический анализ международных доменных имен (IDN) к имени домена.</span><span class="sxs-lookup"><span data-stu-id="e1e4d-103">Specifies if Internationalized Domain Name (IDN) parsing is applied to a domain name.</span></span>  
  
## <a name="schema-hierarchy"></a><span data-ttu-id="e1e4d-104">Схема иерархии</span><span class="sxs-lookup"><span data-stu-id="e1e4d-104">Schema Hierarchy</span></span>  
 [<span data-ttu-id="e1e4d-105">Элемент \<configuration></span><span class="sxs-lookup"><span data-stu-id="e1e4d-105">\<configuration> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)  
  
 [<span data-ttu-id="e1e4d-106">\<URI > (параметры Uri)</span><span class="sxs-lookup"><span data-stu-id="e1e4d-106">\<Uri> Element (Uri Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/uri-element-uri-settings.md)  
  
 [<span data-ttu-id="e1e4d-107">\<IDN ></span><span class="sxs-lookup"><span data-stu-id="e1e4d-107">\<idn></span></span>](../../../../../docs/framework/configure-apps/file-schema/network/idn-element-uri-settings.md)  
  
## <a name="syntax"></a><span data-ttu-id="e1e4d-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e1e4d-108">Syntax</span></span>  
  
```xml  
<idn  
  enabled="All|AllExceptIntranet|None"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e1e4d-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="e1e4d-109">Attributes and Elements</span></span>  
 <span data-ttu-id="e1e4d-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="e1e4d-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e1e4d-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="e1e4d-111">Attributes</span></span>  
  
|<span data-ttu-id="e1e4d-112">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="e1e4d-112">**Element**</span></span>|<span data-ttu-id="e1e4d-113">**Описание**</span><span class="sxs-lookup"><span data-stu-id="e1e4d-113">**Description**</span></span>|  
|-----------------|---------------------|  
|`enabled`|<span data-ttu-id="e1e4d-114">Указывает, что синтаксический анализ международных доменных имен (IDN), применяемые к имени домена, значение по умолчанию — none.</span><span class="sxs-lookup"><span data-stu-id="e1e4d-114">Specifies if Internationalized Domain Name (IDN) parsing is applied to a domain name The default value is none.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e1e4d-115">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="e1e4d-115">Child Elements</span></span>  
 <span data-ttu-id="e1e4d-116">Нет</span><span class="sxs-lookup"><span data-stu-id="e1e4d-116">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e1e4d-117">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="e1e4d-117">Parent Elements</span></span>  
  
|<span data-ttu-id="e1e4d-118">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="e1e4d-118">**Element**</span></span>|<span data-ttu-id="e1e4d-119">**Описание**</span><span class="sxs-lookup"><span data-stu-id="e1e4d-119">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="e1e4d-120">URI</span><span class="sxs-lookup"><span data-stu-id="e1e4d-120">uri</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/uri-element-uri-settings.md)|<span data-ttu-id="e1e4d-121">Содержит параметры, определяющие, каким образом платформа .NET Framework обрабатывает веб-адреса, выраженные с использованием универсальных кодов ресурсов (URI).</span><span class="sxs-lookup"><span data-stu-id="e1e4d-121">Contains settings that specify how the .NET Framework handles web addresses expressed using uniform resource identifiers (URIs).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e1e4d-122">Примечания</span><span class="sxs-lookup"><span data-stu-id="e1e4d-122">Remarks</span></span>  
 <span data-ttu-id="e1e4d-123">Существующий <xref:System.Uri> класс был расширен в .NET Framework 3.5.</span><span class="sxs-lookup"><span data-stu-id="e1e4d-123">The existing <xref:System.Uri> class has been extended in .NET Framework 3.5.</span></span> <span data-ttu-id="e1e4d-124">3.0 с пакетом обновления 1 и 2.0 с пакетом обновления 1 с поддержкой международных идентификаторов ресурсов (IRI) и международных доменных имен (IDN).</span><span class="sxs-lookup"><span data-stu-id="e1e4d-124">3.0 SP1, and 2.0 SP1 with support for International Resource Identifiers (IRI) and Internationalized Domain Names (IDN).</span></span> <span data-ttu-id="e1e4d-125">Текущие пользователи не увидят любое изменение в .NET Framework 2.0, пока они не запустят IRI и IDN поддержки.</span><span class="sxs-lookup"><span data-stu-id="e1e4d-125">Current users will not see any change from the .NET Framework 2.0 behavior unless they specifically enable IRI and IDN support.</span></span> <span data-ttu-id="e1e4d-126">Это обеспечивает совместимость приложений с предыдущими версиями платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e1e4d-126">This ensures application compatibility with prior versions of the .NET Framework.</span></span>  
  
 <span data-ttu-id="e1e4d-127">Чтобы включить поддержку IRI, необходимы следующие два изменения:</span><span class="sxs-lookup"><span data-stu-id="e1e4d-127">To enable support for IRI, the following two changes are required:</span></span>  
  
1. <span data-ttu-id="e1e4d-128">Добавьте следующую строку в файл machine.config в каталоге .NET Framework 2.0</span><span class="sxs-lookup"><span data-stu-id="e1e4d-128">Add the following line to the machine.config file under the .NET Framework 2.0 directory</span></span>  
  
    ```xml  
    <section name="uri" type="System.Configuration.UriSection, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
    ```  
  
2. <span data-ttu-id="e1e4d-129">Укажите, нужно ли синтаксический анализ международных доменных имен (IDN), применяемый к имени домена и должны ли применяться правила синтаксического анализа IRI.</span><span class="sxs-lookup"><span data-stu-id="e1e4d-129">Specify whether you want Internationalized Domain Name (IDN) parsing applied to the domain name and whether IRI parsing rules should be applied.</span></span> <span data-ttu-id="e1e4d-130">Это можно сделать в файле machine.config или в файле app.config.</span><span class="sxs-lookup"><span data-stu-id="e1e4d-130">This can be done in the machine.config or in the app.config file.</span></span>  
  
 <span data-ttu-id="e1e4d-131">Существует три возможных значения для IDN в зависимости от DNS-серверы, которые используются:</span><span class="sxs-lookup"><span data-stu-id="e1e4d-131">There are three possible values for IDN depending on the DNS servers that are used:</span></span>  
  
- <span data-ttu-id="e1e4d-132">IDN включена = All</span><span class="sxs-lookup"><span data-stu-id="e1e4d-132">idn enabled = All</span></span>  
  
     <span data-ttu-id="e1e4d-133">Это значение преобразует имена доменов из Юникода в их эквиваленты в Punycode (IDN-имена).</span><span class="sxs-lookup"><span data-stu-id="e1e4d-133">This value will convert any Unicode domain names to their Punycode equivalents (IDN names).</span></span>  
  
- <span data-ttu-id="e1e4d-134">idn enabled = AllExceptIntranet</span><span class="sxs-lookup"><span data-stu-id="e1e4d-134">idn enabled = AllExceptIntranet</span></span>  
  
     <span data-ttu-id="e1e4d-135">Это значение будет преобразовать все имена доменов из Юникода не в локальной интрасети эквиваленты в Punycode (IDN-имена).</span><span class="sxs-lookup"><span data-stu-id="e1e4d-135">This value will convert all Unicode domain names not on the local Intranet to use the Punycode equivalents (IDN names).</span></span> <span data-ttu-id="e1e4d-136">В этом случае чтобы обрабатывать международные имена в локальной интрасети, DNS-серверы, которые используются для интрасети должны поддерживать разрешение имен в Юникоде.</span><span class="sxs-lookup"><span data-stu-id="e1e4d-136">In this case to handle international names on the local Intranet, the DNS servers that are used for the Intranet should support Unicode name resolution.</span></span>  
  
- <span data-ttu-id="e1e4d-137">IDN включена = нет</span><span class="sxs-lookup"><span data-stu-id="e1e4d-137">idn enabled = None</span></span>  
  
     <span data-ttu-id="e1e4d-138">Это значение не будет преобразовать имена доменов из Юникода в Punycode.</span><span class="sxs-lookup"><span data-stu-id="e1e4d-138">This value will not convert any Unicode domain names to use Punycode.</span></span> <span data-ttu-id="e1e4d-139">Это значение по умолчанию, которое совместимо с поведением .NET Framework 2.0.</span><span class="sxs-lookup"><span data-stu-id="e1e4d-139">This is the default value which is consistent with the .NET Framework 2.0 behaviour.</span></span>  
  
 <span data-ttu-id="e1e4d-140">При включенном IDN метки в Юникоде в доменном имени будут преобразованы в аналоги в кодировке Punicode.</span><span class="sxs-lookup"><span data-stu-id="e1e4d-140">Enabling IDN will convert all Unicode labels in a domain name to their Punycode equivalents.</span></span> <span data-ttu-id="e1e4d-141">Имена Punicode содержат только символы ASCII и всегда начинаются с префикса "xn--".</span><span class="sxs-lookup"><span data-stu-id="e1e4d-141">Punycode names contain only ASCII characters and always start with the xn-- prefix.</span></span> <span data-ttu-id="e1e4d-142">Это сделано для того, чтобы поддерживать существующие DNS-серверы в интрасети, так как большинство DNS-серверов поддерживает только символы ASCII (см. RFC 3940).</span><span class="sxs-lookup"><span data-stu-id="e1e4d-142">The reason for this is to support existing DNS servers on the Internet, since most DNS servers only support ASCII characters (see RFC 3940).</span></span>  
  
### <a name="configuration-files"></a><span data-ttu-id="e1e4d-143">Файлы конфигурации</span><span class="sxs-lookup"><span data-stu-id="e1e4d-143">Configuration Files</span></span>  
 <span data-ttu-id="e1e4d-144">Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="e1e4d-144">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e1e4d-145">Пример</span><span class="sxs-lookup"><span data-stu-id="e1e4d-145">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="e1e4d-146">Описание</span><span class="sxs-lookup"><span data-stu-id="e1e4d-146">Description</span></span>  
 <span data-ttu-id="e1e4d-147">В следующем примере показано конфигурацию, используемую <xref:System.Uri> класс для поддержки синтаксического анализа IRI и IDN-имена.</span><span class="sxs-lookup"><span data-stu-id="e1e4d-147">The following example shows a configuration used by the <xref:System.Uri> class to support IRI parsing and IDN names.</span></span>  
  
### <a name="code"></a><span data-ttu-id="e1e4d-148">Код</span><span class="sxs-lookup"><span data-stu-id="e1e4d-148">Code</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <idn enabled="All" />  
    <iriParsing enabled="true" />  
  </uri>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="e1e4d-149">См. также</span><span class="sxs-lookup"><span data-stu-id="e1e4d-149">See also</span></span>

- <xref:System.Configuration.IdnElement?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection?displayProperty=nameWithType>
- [<span data-ttu-id="e1e4d-150">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="e1e4d-150">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)

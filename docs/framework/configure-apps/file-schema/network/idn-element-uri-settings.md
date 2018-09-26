---
title: '&lt;IDN&gt; (параметры Uri)'
ms.date: 03/30/2017
ms.assetid: 16c8e869-1791-4cf5-9244-3d3c738f60ec
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 1537c17cb3c16beeb41cfaa4103e0664e93facc7
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/25/2018
ms.locfileid: "47170604"
---
# <a name="ltidngt-element-uri-settings"></a><span data-ttu-id="add19-102">&lt;IDN&gt; (параметры Uri)</span><span class="sxs-lookup"><span data-stu-id="add19-102">&lt;idn&gt; Element (Uri Settings)</span></span>
<span data-ttu-id="add19-103">Указывает, применяется ли синтаксический анализ международных доменных имен (IDN) к имени домена.</span><span class="sxs-lookup"><span data-stu-id="add19-103">Specifies if Internationalized Domain Name (IDN) parsing is applied to a domain name.</span></span>  
  
## <a name="schema-hierarchy"></a><span data-ttu-id="add19-104">Схема иерархии</span><span class="sxs-lookup"><span data-stu-id="add19-104">Schema Hierarchy</span></span>  
 [<span data-ttu-id="add19-105">Элемент \<configuration></span><span class="sxs-lookup"><span data-stu-id="add19-105">\<configuration> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)  
  
 [<span data-ttu-id="add19-106">\<URI > (параметры Uri)</span><span class="sxs-lookup"><span data-stu-id="add19-106">\<Uri> Element (Uri Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/uri-element-uri-settings.md)  
  
 [<span data-ttu-id="add19-107">\<IDN ></span><span class="sxs-lookup"><span data-stu-id="add19-107">\<idn></span></span>](../../../../../docs/framework/configure-apps/file-schema/network/idn-element-uri-settings.md)  
  
## <a name="syntax"></a><span data-ttu-id="add19-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="add19-108">Syntax</span></span>  
  
```xml  
<idn  
  enabled="All|AllExceptIntranet|None"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="add19-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="add19-109">Attributes and Elements</span></span>  
 <span data-ttu-id="add19-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="add19-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="add19-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="add19-111">Attributes</span></span>  
  
|<span data-ttu-id="add19-112">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="add19-112">**Element**</span></span>|<span data-ttu-id="add19-113">**Описание**</span><span class="sxs-lookup"><span data-stu-id="add19-113">**Description**</span></span>|  
|-----------------|---------------------|  
|`enabled`|<span data-ttu-id="add19-114">Указывает, что синтаксический анализ международных доменных имен (IDN), применяемые к имени домена, значение по умолчанию — none.</span><span class="sxs-lookup"><span data-stu-id="add19-114">Specifies if Internationalized Domain Name (IDN) parsing is applied to a domain name The default value is none.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="add19-115">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="add19-115">Child Elements</span></span>  
 <span data-ttu-id="add19-116">Нет</span><span class="sxs-lookup"><span data-stu-id="add19-116">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="add19-117">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="add19-117">Parent Elements</span></span>  
  
|<span data-ttu-id="add19-118">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="add19-118">**Element**</span></span>|<span data-ttu-id="add19-119">**Описание**</span><span class="sxs-lookup"><span data-stu-id="add19-119">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="add19-120">URI</span><span class="sxs-lookup"><span data-stu-id="add19-120">uri</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/uri-element-uri-settings.md)|<span data-ttu-id="add19-121">Содержит параметры, определяющие, каким образом платформа .NET Framework обрабатывает веб-адреса, выраженные с использованием универсальных кодов ресурсов (URI).</span><span class="sxs-lookup"><span data-stu-id="add19-121">Contains settings that specify how the .NET Framework handles web addresses expressed using uniform resource identifiers (URIs).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="add19-122">Примечания</span><span class="sxs-lookup"><span data-stu-id="add19-122">Remarks</span></span>  
 <span data-ttu-id="add19-123">Существующий <xref:System.Uri> класс был расширен в .NET Framework 3.5.</span><span class="sxs-lookup"><span data-stu-id="add19-123">The existing <xref:System.Uri> class has been extended in .NET Framework 3.5.</span></span> <span data-ttu-id="add19-124">3.0 с пакетом обновления 1 и 2.0 с пакетом обновления 1 с поддержкой международных идентификаторов ресурсов (IRI) и международных доменных имен (IDN).</span><span class="sxs-lookup"><span data-stu-id="add19-124">3.0 SP1, and 2.0 SP1 with support for International Resource Identifiers (IRI) and Internationalized Domain Names (IDN).</span></span> <span data-ttu-id="add19-125">Текущие пользователи не увидят любое изменение в .NET Framework 2.0, пока они не запустят IRI и IDN поддержки.</span><span class="sxs-lookup"><span data-stu-id="add19-125">Current users will not see any change from the .NET Framework 2.0 behavior unless they specifically enable IRI and IDN support.</span></span> <span data-ttu-id="add19-126">Это обеспечивает совместимость приложений с предыдущими версиями платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="add19-126">This ensures application compatibility with prior versions of the .NET Framework.</span></span>  
  
 <span data-ttu-id="add19-127">Чтобы включить поддержку IRI, необходимы следующие два изменения:</span><span class="sxs-lookup"><span data-stu-id="add19-127">To enable support for IRI, the following two changes are required:</span></span>  
  
1.  <span data-ttu-id="add19-128">Добавьте следующую строку в файл machine.config в каталоге .NET Framework 2.0</span><span class="sxs-lookup"><span data-stu-id="add19-128">Add the following line to the machine.config file under the .NET Framework 2.0 directory</span></span>  
  
    ```xml  
    <section name="uri" type="System.Configuration.UriSection, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
    ```  
  
2.  <span data-ttu-id="add19-129">Укажите, нужно ли синтаксический анализ международных доменных имен (IDN), применяемый к имени домена и должны ли применяться правила синтаксического анализа IRI.</span><span class="sxs-lookup"><span data-stu-id="add19-129">Specify whether you want Internationalized Domain Name (IDN) parsing applied to the domain name and whether IRI parsing rules should be applied.</span></span> <span data-ttu-id="add19-130">Это можно сделать в файле machine.config или в файле app.config.</span><span class="sxs-lookup"><span data-stu-id="add19-130">This can be done in the machine.config or in the app.config file.</span></span>  
  
 <span data-ttu-id="add19-131">Существует три возможных значения для IDN в зависимости от DNS-серверы, которые используются:</span><span class="sxs-lookup"><span data-stu-id="add19-131">There are three possible values for IDN depending on the DNS servers that are used:</span></span>  
  
-   <span data-ttu-id="add19-132">IDN включена = All</span><span class="sxs-lookup"><span data-stu-id="add19-132">idn enabled = All</span></span>  
  
     <span data-ttu-id="add19-133">Это значение преобразует имена доменов из Юникода в их эквиваленты в Punycode (IDN-имена).</span><span class="sxs-lookup"><span data-stu-id="add19-133">This value will convert any Unicode domain names to their Punycode equivalents (IDN names).</span></span>  
  
-   <span data-ttu-id="add19-134">IDN включена = AllExceptIntranet</span><span class="sxs-lookup"><span data-stu-id="add19-134">idn enabled = AllExceptIntranet</span></span>  
  
     <span data-ttu-id="add19-135">Это значение будет преобразовать все имена доменов из Юникода не в локальной интрасети эквиваленты в Punycode (IDN-имена).</span><span class="sxs-lookup"><span data-stu-id="add19-135">This value will convert all Unicode domain names not on the local Intranet to use the Punycode equivalents (IDN names).</span></span> <span data-ttu-id="add19-136">В этом случае чтобы обрабатывать международные имена в локальной интрасети, DNS-серверы, которые используются для интрасети должны поддерживать разрешение имен в Юникоде.</span><span class="sxs-lookup"><span data-stu-id="add19-136">In this case to handle international names on the local Intranet, the DNS servers that are used for the Intranet should support Unicode name resolution.</span></span>  
  
-   <span data-ttu-id="add19-137">IDN включена = нет</span><span class="sxs-lookup"><span data-stu-id="add19-137">idn enabled = None</span></span>  
  
     <span data-ttu-id="add19-138">Это значение не будет преобразовать имена доменов из Юникода в Punycode.</span><span class="sxs-lookup"><span data-stu-id="add19-138">This value will not convert any Unicode domain names to use Punycode.</span></span> <span data-ttu-id="add19-139">Это значение по умолчанию, которое совместимо с поведением .NET Framework 2.0.</span><span class="sxs-lookup"><span data-stu-id="add19-139">This is the default value which is consistent with the .NET Framework 2.0 behaviour.</span></span>  
  
 <span data-ttu-id="add19-140">При включенном IDN метки в Юникоде в доменном имени будут преобразованы в аналоги в кодировке Punicode.</span><span class="sxs-lookup"><span data-stu-id="add19-140">Enabling IDN will convert all Unicode labels in a domain name to their Punycode equivalents.</span></span> <span data-ttu-id="add19-141">Имена Punicode содержат только символы ASCII и всегда начинаются с префикса "xn--".</span><span class="sxs-lookup"><span data-stu-id="add19-141">Punycode names contain only ASCII characters and always start with the xn-- prefix.</span></span> <span data-ttu-id="add19-142">Это сделано для того, чтобы поддерживать существующие DNS-серверы в интрасети, так как большинство DNS-серверов поддерживает только символы ASCII (см. RFC 3940).</span><span class="sxs-lookup"><span data-stu-id="add19-142">The reason for this is to support existing DNS servers on the Internet, since most DNS servers only support ASCII characters (see RFC 3940).</span></span>  
  
### <a name="configuration-files"></a><span data-ttu-id="add19-143">Файлы конфигурации</span><span class="sxs-lookup"><span data-stu-id="add19-143">Configuration Files</span></span>  
 <span data-ttu-id="add19-144">Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="add19-144">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="add19-145">Пример</span><span class="sxs-lookup"><span data-stu-id="add19-145">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="add19-146">Описание</span><span class="sxs-lookup"><span data-stu-id="add19-146">Description</span></span>  
 <span data-ttu-id="add19-147">В следующем примере показано конфигурацию, используемую <xref:System.Uri> класс для поддержки синтаксического анализа IRI и IDN-имена.</span><span class="sxs-lookup"><span data-stu-id="add19-147">The following example shows a configuration used by the <xref:System.Uri> class to support IRI parsing and IDN names.</span></span>  
  
### <a name="code"></a><span data-ttu-id="add19-148">Код</span><span class="sxs-lookup"><span data-stu-id="add19-148">Code</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <idn enabled="All" />  
    <iriParsing enabled="true" />  
  </uri>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="add19-149">См. также</span><span class="sxs-lookup"><span data-stu-id="add19-149">See Also</span></span>  
 <xref:System.Configuration.IdnElement?displayProperty=nameWithType>  
 <xref:System.Configuration.UriSection?displayProperty=nameWithType>  
 [<span data-ttu-id="add19-150">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="add19-150">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)

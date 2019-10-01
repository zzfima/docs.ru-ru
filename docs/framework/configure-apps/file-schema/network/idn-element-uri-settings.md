---
title: Элемент <idn> (параметры URI)
ms.date: 03/30/2017
ms.assetid: 16c8e869-1791-4cf5-9244-3d3c738f60ec
ms.openlocfilehash: 533b2562f6e5c8d6c2bf452e56dff9a8bf8ab376
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/01/2019
ms.locfileid: "71698164"
---
# <a name="idn-element-uri-settings"></a><span data-ttu-id="f51c8-102">Элемент > @no__t 0idn (Параметры URI)</span><span class="sxs-lookup"><span data-stu-id="f51c8-102">\<idn> Element (Uri Settings)</span></span>

<span data-ttu-id="f51c8-103">Указывает, применяется ли синтаксический анализ международного доменного имени (IDN) к доменному имени.</span><span class="sxs-lookup"><span data-stu-id="f51c8-103">Specifies if Internationalized Domain Name (IDN) parsing is applied to a domain name.</span></span>
  
[<span data-ttu-id="f51c8-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="f51c8-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="f51c8-105">&nbsp; @ no__t-1[ **\<uri >** ](uri-element-uri-settings.md)</span><span class="sxs-lookup"><span data-stu-id="f51c8-105">&nbsp;&nbsp;[**\<uri>**](uri-element-uri-settings.md)</span></span>  
<span data-ttu-id="f51c8-106">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 **\<idn >**</span><span class="sxs-lookup"><span data-stu-id="f51c8-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<idn>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f51c8-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f51c8-107">Syntax</span></span>  
  
```xml
<idn
  enabled="All|AllExceptIntranet|None"
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f51c8-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="f51c8-108">Attributes and Elements</span></span>  
 <span data-ttu-id="f51c8-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="f51c8-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f51c8-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="f51c8-110">Attributes</span></span>  

|<span data-ttu-id="f51c8-111">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="f51c8-111">**Element**</span></span>|<span data-ttu-id="f51c8-112">**Описание**</span><span class="sxs-lookup"><span data-stu-id="f51c8-112">**Description**</span></span>|  
|-----------------|---------------------|  
|`enabled`|<span data-ttu-id="f51c8-113">Указывает, применяется ли синтаксический анализ международного доменного имени (IDN) к доменному имени. значение по умолчанию — None.</span><span class="sxs-lookup"><span data-stu-id="f51c8-113">Specifies if Internationalized Domain Name (IDN) parsing is applied to a domain name The default value is none.</span></span>|  

### <a name="child-elements"></a><span data-ttu-id="f51c8-114">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="f51c8-114">Child elements</span></span>

<span data-ttu-id="f51c8-115">None</span><span class="sxs-lookup"><span data-stu-id="f51c8-115">None</span></span>
  
### <a name="parent-elements"></a><span data-ttu-id="f51c8-116">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="f51c8-116">Parent elements</span></span>

|<span data-ttu-id="f51c8-117">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="f51c8-117">**Element**</span></span>|<span data-ttu-id="f51c8-118">**Описание**</span><span class="sxs-lookup"><span data-stu-id="f51c8-118">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="f51c8-119">URI</span><span class="sxs-lookup"><span data-stu-id="f51c8-119">uri</span></span>](uri-element-uri-settings.md)|<span data-ttu-id="f51c8-120">Содержит параметры, определяющие, как .NET Framework обрабатывает веб-адреса, выраженные с помощью универсальных идентификаторов ресурсов (URI).</span><span class="sxs-lookup"><span data-stu-id="f51c8-120">Contains settings that specify how the .NET Framework handles web addresses expressed using uniform resource identifiers (URIs).</span></span>|  

## <a name="remarks"></a><span data-ttu-id="f51c8-121">Примечания</span><span class="sxs-lookup"><span data-stu-id="f51c8-121">Remarks</span></span>

<span data-ttu-id="f51c8-122">Существующий класс <xref:System.Uri> был расширен в .NET Framework 3,5.</span><span class="sxs-lookup"><span data-stu-id="f51c8-122">The existing <xref:System.Uri> class has been extended in .NET Framework 3.5.</span></span> <span data-ttu-id="f51c8-123">3,0 с пакетом обновления 1 (SP1) и 2,0 с пакетом обновления 1 (SP1) с поддержкой международных идентификаторов ресурсов (IRI) и международных доменных имен (IDN).</span><span class="sxs-lookup"><span data-stu-id="f51c8-123">3.0 SP1, and 2.0 SP1 with support for International Resource Identifiers (IRI) and Internationalized Domain Names (IDN).</span></span> <span data-ttu-id="f51c8-124">Текущие пользователи не увидят каких бы то ни было изменений в работе .NET Framework 2,0, если они специально не включают поддержку IRI и IDN.</span><span class="sxs-lookup"><span data-stu-id="f51c8-124">Current users will not see any change from the .NET Framework 2.0 behavior unless they specifically enable IRI and IDN support.</span></span> <span data-ttu-id="f51c8-125">Это обеспечивает совместимость приложений с предыдущими версиями платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f51c8-125">This ensures application compatibility with prior versions of the .NET Framework.</span></span>

<span data-ttu-id="f51c8-126">Чтобы включить поддержку IRI, требуются следующие два изменения:</span><span class="sxs-lookup"><span data-stu-id="f51c8-126">To enable support for IRI, the following two changes are required:</span></span>

1. <span data-ttu-id="f51c8-127">Добавьте следующую строку в файл Machine. config в каталоге .NET Framework 2,0:</span><span class="sxs-lookup"><span data-stu-id="f51c8-127">Add the following line to the machine.config file under the .NET Framework 2.0 directory:</span></span>
  
    ```xml  
    <section name="uri" type="System.Configuration.UriSection, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
    ```  
  
2. <span data-ttu-id="f51c8-128">Укажите, следует ли применять синтаксический анализ международного доменного имени (IDN) к доменному имени и следует ли применять правила синтаксического анализа IRI.</span><span class="sxs-lookup"><span data-stu-id="f51c8-128">Specify whether you want Internationalized Domain Name (IDN) parsing applied to the domain name and whether IRI parsing rules should be applied.</span></span> <span data-ttu-id="f51c8-129">Это можно сделать в файле machine.config или в файле app.config.</span><span class="sxs-lookup"><span data-stu-id="f51c8-129">This can be done in the machine.config or in the app.config file.</span></span>

 <span data-ttu-id="f51c8-130">Существует три возможных значения для IDN в зависимости от используемых DNS-серверов.</span><span class="sxs-lookup"><span data-stu-id="f51c8-130">There are three possible values for IDN depending on the DNS servers that are used:</span></span>

- <span data-ttu-id="f51c8-131">IDN включен = ALL</span><span class="sxs-lookup"><span data-stu-id="f51c8-131">idn enabled = All</span></span>  

     <span data-ttu-id="f51c8-132">Это значение преобразует любые доменные имена Юникода в их эквиваленты в Punycode (имена IDN).</span><span class="sxs-lookup"><span data-stu-id="f51c8-132">This value will convert any Unicode domain names to their Punycode equivalents (IDN names).</span></span>

- <span data-ttu-id="f51c8-133">IDN включен = Аллексцептинтранет</span><span class="sxs-lookup"><span data-stu-id="f51c8-133">idn enabled = AllExceptIntranet</span></span>

     <span data-ttu-id="f51c8-134">Это значение преобразует все доменные имена Юникода, которые не находятся в локальной интрасети, для использования эквивалентов в Punycode (IDN-имен).</span><span class="sxs-lookup"><span data-stu-id="f51c8-134">This value will convert all Unicode domain names not on the local Intranet to use the Punycode equivalents (IDN names).</span></span> <span data-ttu-id="f51c8-135">В этом случае для обработки международных имен в локальной интрасети DNS-серверы, используемые для интрасети, должны поддерживать разрешение имен Юникода.</span><span class="sxs-lookup"><span data-stu-id="f51c8-135">In this case to handle international names on the local Intranet, the DNS servers that are used for the Intranet should support Unicode name resolution.</span></span>

- <span data-ttu-id="f51c8-136">IDN включен = None</span><span class="sxs-lookup"><span data-stu-id="f51c8-136">idn enabled = None</span></span>

     <span data-ttu-id="f51c8-137">Это значение не приводит к преобразованию любых доменных имен Юникода для использования Punycode.</span><span class="sxs-lookup"><span data-stu-id="f51c8-137">This value will not convert any Unicode domain names to use Punycode.</span></span> <span data-ttu-id="f51c8-138">Это значение по умолчанию, которое согласуется с поведением .NET Framework 2,0.</span><span class="sxs-lookup"><span data-stu-id="f51c8-138">This is the default value which is consistent with the .NET Framework 2.0 behavior.</span></span>

 <span data-ttu-id="f51c8-139">При включенном IDN метки в Юникоде в доменном имени будут преобразованы в аналоги в кодировке Punicode.</span><span class="sxs-lookup"><span data-stu-id="f51c8-139">Enabling IDN will convert all Unicode labels in a domain name to their Punycode equivalents.</span></span> <span data-ttu-id="f51c8-140">Имена Punicode содержат только символы ASCII и всегда начинаются с префикса "xn--".</span><span class="sxs-lookup"><span data-stu-id="f51c8-140">Punycode names contain only ASCII characters and always start with the xn-- prefix.</span></span> <span data-ttu-id="f51c8-141">Это сделано для того, чтобы поддерживать существующие DNS-серверы в интрасети, так как большинство DNS-серверов поддерживает только символы ASCII (см. RFC 3940).</span><span class="sxs-lookup"><span data-stu-id="f51c8-141">The reason for this is to support existing DNS servers on the Internet, since most DNS servers only support ASCII characters (see RFC 3940).</span></span>

### <a name="configuration-files"></a><span data-ttu-id="f51c8-142">Файлы конфигурации.</span><span class="sxs-lookup"><span data-stu-id="f51c8-142">Configuration files</span></span>

<span data-ttu-id="f51c8-143">Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="f51c8-143">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>

## <a name="example"></a><span data-ttu-id="f51c8-144">Пример</span><span class="sxs-lookup"><span data-stu-id="f51c8-144">Example</span></span>

<span data-ttu-id="f51c8-145">В следующем примере показана конфигурация, используемая классом <xref:System.Uri> для поддержки синтаксического анализа IRI и имен IDN:</span><span class="sxs-lookup"><span data-stu-id="f51c8-145">The following example shows a configuration used by the <xref:System.Uri> class to support IRI parsing and IDN names:</span></span>

```xml
<configuration>
  <uri>
    <idn enabled="All" />
    <iriParsing enabled="true" />
  </uri>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="f51c8-146">См. также</span><span class="sxs-lookup"><span data-stu-id="f51c8-146">See also</span></span>

- <xref:System.Configuration.IdnElement?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection?displayProperty=nameWithType>
- [<span data-ttu-id="f51c8-147">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="f51c8-147">Network Settings Schema</span></span>](index.md)

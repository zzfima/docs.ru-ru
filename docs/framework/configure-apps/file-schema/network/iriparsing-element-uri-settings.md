---
title: <iriParsing> (Параметры Uri)
ms.date: 03/30/2017
ms.assetid: 953d0b53-445e-41f9-b302-77c4030852ce
ms.openlocfilehash: 7033f4dcda7d2fe73310ae0d36d9b05c090d13d4
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/09/2019
ms.locfileid: "59299674"
---
# <a name="iriparsing-element-uri-settings"></a><span data-ttu-id="cf870-102">\<iriParsing > (параметры Uri)</span><span class="sxs-lookup"><span data-stu-id="cf870-102">\<iriParsing> Element (Uri Settings)</span></span>
<span data-ttu-id="cf870-103">Определяет, применяется ли к <xref:System.Uri> анализ международных идентификаторов ресурсов (IRI) и применяются ли правила анализа IRI.</span><span class="sxs-lookup"><span data-stu-id="cf870-103">Specifies if International Resource Identifier (IRI) parsing is applied to a <xref:System.Uri> and whether IRI parsing rules should be applied.</span></span>  
  
## <a name="schema-hierarchy"></a><span data-ttu-id="cf870-104">Схема иерархии</span><span class="sxs-lookup"><span data-stu-id="cf870-104">Schema Hierarchy</span></span>  
 [<span data-ttu-id="cf870-105">\<Конфигурация > элемент</span><span class="sxs-lookup"><span data-stu-id="cf870-105">\<configuration> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)  
  
 [<span data-ttu-id="cf870-106">\<URI > (параметры Uri)</span><span class="sxs-lookup"><span data-stu-id="cf870-106">\<Uri> Element (Uri Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/uri-element-uri-settings.md)  
  
 [<span data-ttu-id="cf870-107">\<iriParsing ></span><span class="sxs-lookup"><span data-stu-id="cf870-107">\<iriParsing></span></span>](../../../../../docs/framework/configure-apps/file-schema/network/iriparsing-element-uri-settings.md)  
  
## <a name="syntax"></a><span data-ttu-id="cf870-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cf870-108">Syntax</span></span>  
  
```xml  
<iriParsing  
  enabled="true|false"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cf870-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="cf870-109">Attributes and Elements</span></span>  
 <span data-ttu-id="cf870-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="cf870-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cf870-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="cf870-111">Attributes</span></span>  
  
|**<span data-ttu-id="cf870-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="cf870-112">Element</span></span>**|**<span data-ttu-id="cf870-113">Описание</span><span class="sxs-lookup"><span data-stu-id="cf870-113">Description</span></span>**|  
|-----------------|---------------------|  
|`enabled`|<span data-ttu-id="cf870-114">Указывает, включена ли синтаксического анализа IRI.</span><span class="sxs-lookup"><span data-stu-id="cf870-114">Specifies whether IRI parsing is enabled.</span></span> <span data-ttu-id="cf870-115">Значение по умолчанию — `false`.</span><span class="sxs-lookup"><span data-stu-id="cf870-115">The default value is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="cf870-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="cf870-116">Child Elements</span></span>  
 <span data-ttu-id="cf870-117">Нет</span><span class="sxs-lookup"><span data-stu-id="cf870-117">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="cf870-118">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="cf870-118">Parent Elements</span></span>  
  
|**<span data-ttu-id="cf870-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="cf870-119">Element</span></span>**|**<span data-ttu-id="cf870-120">Описание</span><span class="sxs-lookup"><span data-stu-id="cf870-120">Description</span></span>**|  
|-----------------|---------------------|  
|[<span data-ttu-id="cf870-121">uri</span><span class="sxs-lookup"><span data-stu-id="cf870-121">uri</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/uri-element-uri-settings.md)|<span data-ttu-id="cf870-122">Содержит параметры, определяющие, каким образом платформа .NET Framework обрабатывает веб-адреса, выраженные с использованием универсальных кодов ресурсов (URI).</span><span class="sxs-lookup"><span data-stu-id="cf870-122">Contains settings that specify how the .NET Framework handles web addresses expressed using uniform resource identifiers (URIs).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cf870-123">Примечания</span><span class="sxs-lookup"><span data-stu-id="cf870-123">Remarks</span></span>  
 <span data-ttu-id="cf870-124">Существующий <xref:System.Uri> класс был расширен в .NET Framework 3.5.</span><span class="sxs-lookup"><span data-stu-id="cf870-124">The existing <xref:System.Uri> class has been extended in .NET Framework 3.5.</span></span> <span data-ttu-id="cf870-125">3.0 с пакетом обновления 1 и 2.0 с пакетом обновления 1 для предоставления поддержки для международных идентификаторов ресурсов (IRI) и международных доменных имен (IDN).</span><span class="sxs-lookup"><span data-stu-id="cf870-125">3.0 SP1, and 2.0 SP1 to provide support for International Resource Identifiers (IRI) and Internationalized Domain Names (IDN).</span></span> <span data-ttu-id="cf870-126">Текущие пользователи не увидят любое изменение в .NET Framework 2.0, пока они не запустят IRI и IDN поддержки.</span><span class="sxs-lookup"><span data-stu-id="cf870-126">Current users will not see any change from the .NET Framework 2.0 behavior unless they specifically enable IRI and IDN support.</span></span> <span data-ttu-id="cf870-127">Это обеспечивает совместимость приложений с предыдущими версиями платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="cf870-127">This ensures application compatibility with prior versions of the .NET Framework.</span></span>  
  
 <span data-ttu-id="cf870-128">Чтобы включить поддержку IRI, необходимы следующие два изменения:</span><span class="sxs-lookup"><span data-stu-id="cf870-128">To enable support for IRI, the following two changes are required:</span></span>  
  
1. <span data-ttu-id="cf870-129">Добавьте следующую строку в файл machine.config в каталоге .NET Framework 2.0</span><span class="sxs-lookup"><span data-stu-id="cf870-129">Add the following line to the machine.config file under the .NET Framework 2.0 directory</span></span>  
  
    ```xml  
    <section name="uri" type="System.Configuration.UriSection, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
    ```  
  
2. <span data-ttu-id="cf870-130">Укажите, должна ли применяться правила синтаксического анализа IRI.</span><span class="sxs-lookup"><span data-stu-id="cf870-130">Specify whether IRI parsing rules should be applied.</span></span> <span data-ttu-id="cf870-131">Это можно сделать в файле machine.config или в файле app.config.</span><span class="sxs-lookup"><span data-stu-id="cf870-131">This can be done in the machine.config or in the app.config file.</span></span>  
  
 <span data-ttu-id="cf870-132">Включение синтаксического анализа IRI (iriParsing включена = `true`) нормализация и проверка символов в соответствии с последней IRI правилами в RFC 3987.</span><span class="sxs-lookup"><span data-stu-id="cf870-132">Enabling IRI parsing (iriParsing enabled = `true`) will do normalization and character checking according to the latest IRI rules in RFC 3987.</span></span> <span data-ttu-id="cf870-133">Значение по умолчанию — `false` и нормализации и символов проверку в соответствии с RFC 2396 и RFC 3986 (для литералов IPv6).</span><span class="sxs-lookup"><span data-stu-id="cf870-133">The default value is `false` and will do normalization and character checking according to RFC 2396 and RFC 3986 (for IPv6 literals).</span></span>  
  
### <a name="configuration-files"></a><span data-ttu-id="cf870-134">Файлы конфигурации</span><span class="sxs-lookup"><span data-stu-id="cf870-134">Configuration Files</span></span>  
 <span data-ttu-id="cf870-135">Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="cf870-135">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="cf870-136">Пример</span><span class="sxs-lookup"><span data-stu-id="cf870-136">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="cf870-137">Описание</span><span class="sxs-lookup"><span data-stu-id="cf870-137">Description</span></span>  
 <span data-ttu-id="cf870-138">В следующем примере показано конфигурацию, используемую <xref:System.Uri> класс для поддержки синтаксического анализа IRI и IDN-имена.</span><span class="sxs-lookup"><span data-stu-id="cf870-138">The following example shows a configuration used by the <xref:System.Uri> class to support IRI parsing and IDN names.</span></span>  
  
### <a name="code"></a><span data-ttu-id="cf870-139">Код</span><span class="sxs-lookup"><span data-stu-id="cf870-139">Code</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <idn enabled="All" />  
    <iriParsing enabled="true" />  
  </uri>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="cf870-140">См. также</span><span class="sxs-lookup"><span data-stu-id="cf870-140">See also</span></span>

- <xref:System.Configuration.IriParsingElement?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection?displayProperty=nameWithType>
- [<span data-ttu-id="cf870-141">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="cf870-141">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)

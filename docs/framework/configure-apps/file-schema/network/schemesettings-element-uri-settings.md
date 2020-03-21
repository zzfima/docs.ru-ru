---
title: Элемент <schemeSettings> (параметры URI)
ms.date: 03/30/2017
ms.assetid: 0ae45c6e-8c4c-4c0d-8b9f-a93824648890
ms.openlocfilehash: c745c90bb61b9ee393687d7f6db4fd11565c7dc7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154651"
---
# <a name="schemesettings-element-uri-settings"></a><span data-ttu-id="dec38-102">\<Элемент schemeSettings> (параметры URI)</span><span class="sxs-lookup"><span data-stu-id="dec38-102">\<schemeSettings> Element (Uri Settings)</span></span>
<span data-ttu-id="dec38-103">Определяет, как <xref:System.Uri> анализируется для определенных схем.</span><span class="sxs-lookup"><span data-stu-id="dec38-103">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>  
  
[<span data-ttu-id="dec38-104">**\<конфигурация>**</span><span class="sxs-lookup"><span data-stu-id="dec38-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="dec38-105">&nbsp;&nbsp;[**\<uri>**](uri-element-uri-settings.md)</span><span class="sxs-lookup"><span data-stu-id="dec38-105">&nbsp;&nbsp;[**\<uri>**](uri-element-uri-settings.md)</span></span>  
<span data-ttu-id="dec38-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<schemeSettings>**</span><span class="sxs-lookup"><span data-stu-id="dec38-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<schemeSettings>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dec38-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="dec38-107">Syntax</span></span>  
  
```xml  
<schemeSettings>
</schemeSettings>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="dec38-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="dec38-108">Attributes and Elements</span></span>  
 <span data-ttu-id="dec38-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="dec38-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="dec38-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="dec38-110">Attributes</span></span>  
 <span data-ttu-id="dec38-111">None</span><span class="sxs-lookup"><span data-stu-id="dec38-111">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="dec38-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="dec38-112">Child Elements</span></span>  
  
|<span data-ttu-id="dec38-113">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="dec38-113">**Element**</span></span>|<span data-ttu-id="dec38-114">**Описание**</span><span class="sxs-lookup"><span data-stu-id="dec38-114">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="dec38-115">добавление</span><span class="sxs-lookup"><span data-stu-id="dec38-115">add</span></span>](add-element-for-schemesettings-uri-settings.md)|<span data-ttu-id="dec38-116">Добавляет настройку схемы для имени схемы.</span><span class="sxs-lookup"><span data-stu-id="dec38-116">Adds a scheme setting for a scheme name.</span></span>|  
|[<span data-ttu-id="dec38-117">Ясно</span><span class="sxs-lookup"><span data-stu-id="dec38-117">clear</span></span>](clear-element-for-schemesettings-uri-settings.md)|<span data-ttu-id="dec38-118">Очищает все существующие настройки схемы.</span><span class="sxs-lookup"><span data-stu-id="dec38-118">Clears all existing scheme settings.</span></span>|  
|[<span data-ttu-id="dec38-119">удаление</span><span class="sxs-lookup"><span data-stu-id="dec38-119">remove</span></span>](remove-element-for-schemesettings-uri-settings.md)|<span data-ttu-id="dec38-120">Удаляет настройку схемы для имени схемы.</span><span class="sxs-lookup"><span data-stu-id="dec38-120">Removes a scheme setting for a scheme name.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="dec38-121">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="dec38-121">Parent Elements</span></span>  
  
|<span data-ttu-id="dec38-122">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="dec38-122">**Element**</span></span>|<span data-ttu-id="dec38-123">**Описание**</span><span class="sxs-lookup"><span data-stu-id="dec38-123">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="dec38-124">Uri</span><span class="sxs-lookup"><span data-stu-id="dec38-124">uri</span></span>](uri-element-uri-settings.md)|<span data-ttu-id="dec38-125">Содержит настройки, определяющие, как система .NET обрабатывает веб-адреса, выраженные с помощью единых идентификаторов ресурсов (URIs).</span><span class="sxs-lookup"><span data-stu-id="dec38-125">Contains settings that specify how the .NET Framework handles web addresses expressed using uniform resource identifiers (URIs).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dec38-126">Remarks</span><span class="sxs-lookup"><span data-stu-id="dec38-126">Remarks</span></span>  
 <span data-ttu-id="dec38-127">По умолчанию <xref:System.Uri?displayProperty=nameWithType> класс оон избегает процентов закодированных делимитеров пути перед выполнением сжатия пути.</span><span class="sxs-lookup"><span data-stu-id="dec38-127">By default, the <xref:System.Uri?displayProperty=nameWithType> class un-escapes percent encoded path delimiters before executing path compression.</span></span> <span data-ttu-id="dec38-128">Это было реализовано в качестве механизма безопасности от атак, как следующее:</span><span class="sxs-lookup"><span data-stu-id="dec38-128">This was implemented as a security mechanism against attacks like the following:</span></span>  
  
 `http://www.contoso.com/..%2F..%2F/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="dec38-129">Если этот URI передается модулям, не обрабатываемым закодированными символами процентов правильно, это может привести к тому, что следующая команда будет выполнена сервером:</span><span class="sxs-lookup"><span data-stu-id="dec38-129">If this URI gets passed down to modules not handling percent encoded characters correctly, it could result in the following command being executed by the server:</span></span>  
  
 `c:\Windows\System32\cmd.exe /c dir c:\`  
  
 <span data-ttu-id="dec38-130">По этой <xref:System.Uri?displayProperty=nameWithType> причине, класс сначала ООН-побегов путь разграничения, а затем применяется путь сжатия.</span><span class="sxs-lookup"><span data-stu-id="dec38-130">For this reason, <xref:System.Uri?displayProperty=nameWithType> class first un-escapes path delimiters and then applies path compression.</span></span> <span data-ttu-id="dec38-131">Результат передачи вредоносного URL <xref:System.Uri?displayProperty=nameWithType> выше к классу конструктора приводит к следующему URI:</span><span class="sxs-lookup"><span data-stu-id="dec38-131">The result of passing the malicious URL above to <xref:System.Uri?displayProperty=nameWithType> class constructor results in the following URI:</span></span>  
  
 `http://www.microsoft.com/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="dec38-132">Это поведение по умолчанию может быть изменено, чтобы не выходить из неизменяемых процентов закодированных делимитеров пути, используя опцию конфигурации schemeSettings для определенной схемы.</span><span class="sxs-lookup"><span data-stu-id="dec38-132">This default behavior can be modified to not un-escape percent encoded path delimiters using the schemeSettings configuration option for a specific scheme.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="dec38-133">Файлы конфигурации</span><span class="sxs-lookup"><span data-stu-id="dec38-133">Configuration Files</span></span>  
 <span data-ttu-id="dec38-134">Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="dec38-134">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="dec38-135">Пример</span><span class="sxs-lookup"><span data-stu-id="dec38-135">Example</span></span>  
 <span data-ttu-id="dec38-136">В следующем примере показана <xref:System.Uri> конфигурация, используемая классом для поддержки не исследует делимитеров пути, закодированных процентом, для схемы http.</span><span class="sxs-lookup"><span data-stu-id="dec38-136">The following example shows a configuration used by the <xref:System.Uri> class to support not escaping percent-encoded path delimiters for the http scheme.</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <schemeSettings>  
      <add name="http" genericUriParserOptions="DontUnescapePathDotsAndSlashes"/>  
    </schemeSettings>  
  </uri>  
</configuration>  
```  
  
## <a name="element-information"></a><span data-ttu-id="dec38-137">Сведения об элементе</span><span class="sxs-lookup"><span data-stu-id="dec38-137">Element Information</span></span>  
  
|||
|-|-|  
|<span data-ttu-id="dec38-138">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="dec38-138">Namespace</span></span>|<span data-ttu-id="dec38-139">Система</span><span class="sxs-lookup"><span data-stu-id="dec38-139">System</span></span>|  
|<span data-ttu-id="dec38-140">Имя схемы</span><span class="sxs-lookup"><span data-stu-id="dec38-140">Schema Name</span></span>||  
|<span data-ttu-id="dec38-141">Файл проверки</span><span class="sxs-lookup"><span data-stu-id="dec38-141">Validation File</span></span>||  
|<span data-ttu-id="dec38-142">Может быть пустым</span><span class="sxs-lookup"><span data-stu-id="dec38-142">Can be Empty</span></span>||  
  
## <a name="see-also"></a><span data-ttu-id="dec38-143">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="dec38-143">See also</span></span>

- <xref:System.Configuration.SchemeSettingElement?displayProperty=nameWithType>
- <xref:System.Configuration.SchemeSettingElementCollection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection.SchemeSettings%2A?displayProperty=nameWithType>
- <xref:System.GenericUriParserOptions?displayProperty=nameWithType>
- <xref:System.Uri?displayProperty=nameWithType>
- [<span data-ttu-id="dec38-144">Схема настройки сети</span><span class="sxs-lookup"><span data-stu-id="dec38-144">Network Settings Schema</span></span>](index.md)

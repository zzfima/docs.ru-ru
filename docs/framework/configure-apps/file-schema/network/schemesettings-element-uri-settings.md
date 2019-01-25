---
title: '&lt;schemeSettings&gt; (параметры Uri)'
ms.date: 03/30/2017
ms.assetid: 0ae45c6e-8c4c-4c0d-8b9f-a93824648890
ms.openlocfilehash: 3320fde81df3ec31bd52e3194a84686acc5d9216
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54628894"
---
# <a name="ltschemesettingsgt-element-uri-settings"></a><span data-ttu-id="82229-102">&lt;schemeSettings&gt; (параметры Uri)</span><span class="sxs-lookup"><span data-stu-id="82229-102">&lt;schemeSettings&gt; Element (Uri Settings)</span></span>
<span data-ttu-id="82229-103">Определяет, как <xref:System.Uri> анализируется для определенных схем.</span><span class="sxs-lookup"><span data-stu-id="82229-103">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>  
  
 <span data-ttu-id="82229-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="82229-104">\<configuration></span></span>  
<span data-ttu-id="82229-105">\<URI ></span><span class="sxs-lookup"><span data-stu-id="82229-105">\<uri></span></span>  
<span data-ttu-id="82229-106">\<schemeSettings ></span><span class="sxs-lookup"><span data-stu-id="82229-106">\<schemeSettings></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="82229-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="82229-107">Syntax</span></span>  
  
```xml  
<schemeSettings>   
</schemeSettings>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="82229-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="82229-108">Attributes and Elements</span></span>  
 <span data-ttu-id="82229-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="82229-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="82229-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="82229-110">Attributes</span></span>  
 <span data-ttu-id="82229-111">Нет</span><span class="sxs-lookup"><span data-stu-id="82229-111">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="82229-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="82229-112">Child Elements</span></span>  
  
|<span data-ttu-id="82229-113">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="82229-113">**Element**</span></span>|<span data-ttu-id="82229-114">**Описание**</span><span class="sxs-lookup"><span data-stu-id="82229-114">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="82229-115">add</span><span class="sxs-lookup"><span data-stu-id="82229-115">add</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/add-element-for-schemesettings-uri-settings.md)|<span data-ttu-id="82229-116">Добавляет параметр схемы для имени схемы.</span><span class="sxs-lookup"><span data-stu-id="82229-116">Adds a scheme setting for a scheme name.</span></span>|  
|[<span data-ttu-id="82229-117">clear</span><span class="sxs-lookup"><span data-stu-id="82229-117">clear</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/clear-element-for-schemesettings-uri-settings.md)|<span data-ttu-id="82229-118">Удаляет все существующие параметры схемы.</span><span class="sxs-lookup"><span data-stu-id="82229-118">Clears all existing scheme settings.</span></span>|  
|[<span data-ttu-id="82229-119">remove</span><span class="sxs-lookup"><span data-stu-id="82229-119">remove</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/remove-element-for-schemesettings-uri-settings.md)|<span data-ttu-id="82229-120">Удаляет параметр схемы для имени схемы.</span><span class="sxs-lookup"><span data-stu-id="82229-120">Removes a scheme setting for a scheme name.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="82229-121">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="82229-121">Parent Elements</span></span>  
  
|<span data-ttu-id="82229-122">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="82229-122">**Element**</span></span>|<span data-ttu-id="82229-123">**Описание**</span><span class="sxs-lookup"><span data-stu-id="82229-123">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="82229-124">URI</span><span class="sxs-lookup"><span data-stu-id="82229-124">uri</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/uri-element-uri-settings.md)|<span data-ttu-id="82229-125">Содержит параметры, определяющие, каким образом платформа .NET Framework обрабатывает веб-адреса, выраженные с использованием универсальных кодов ресурсов (URI).</span><span class="sxs-lookup"><span data-stu-id="82229-125">Contains settings that specify how the .NET Framework handles web addresses expressed using uniform resource identifiers (URIs).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="82229-126">Примечания</span><span class="sxs-lookup"><span data-stu-id="82229-126">Remarks</span></span>  
 <span data-ttu-id="82229-127">По умолчанию <xref:System.Uri?displayProperty=nameWithType> знаком процента Отмена переходов класс разделители пути до выполнения сжатия пути.</span><span class="sxs-lookup"><span data-stu-id="82229-127">By default, the <xref:System.Uri?displayProperty=nameWithType> class un-escapes percent encoded path delimiters before executing path compression.</span></span> <span data-ttu-id="82229-128">Это было реализовано в качестве механизма защиты от атак, следующим образом:</span><span class="sxs-lookup"><span data-stu-id="82229-128">This was implemented as a security mechanism against attacks like the following:</span></span>  
  
 `http://www.contoso.com/..%2F..%2F/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="82229-129">Если этот URI передается вниз, чтобы модули не обрабатывает процентов символы в кодировке неправильно, это может привести в следующей команде, выполняемой на сервере:</span><span class="sxs-lookup"><span data-stu-id="82229-129">If this URI gets passed down to modules not handling percent encoded characters correctly, it could result in the following command being executed by the server:</span></span>  
  
 `c:\Windows\System32\cmd.exe /c dir c:\`  
  
 <span data-ttu-id="82229-130">По этой причине <xref:System.Uri?displayProperty=nameWithType> класса первый разделители пути Отмена переходов, а затем применяет сжатие пути.</span><span class="sxs-lookup"><span data-stu-id="82229-130">For this reason, <xref:System.Uri?displayProperty=nameWithType> class first un-escapes path delimiters and then applies path compression.</span></span> <span data-ttu-id="82229-131">Результат передачи вредоносных URL-адрес выше <xref:System.Uri?displayProperty=nameWithType> класса конструктор результаты в следующий URI:</span><span class="sxs-lookup"><span data-stu-id="82229-131">The result of passing the malicious URL above to <xref:System.Uri?displayProperty=nameWithType> class constructor results in the following URI:</span></span>  
  
 `http://www.microsoft.com/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="82229-132">Можно изменить это поведение по умолчанию для не разделители отмены escape процента закодированный путь, с помощью параметра конфигурации schemeSettings для определенной схемы.</span><span class="sxs-lookup"><span data-stu-id="82229-132">This default behavior can be modified to not un-escape percent encoded path delimiters using the schemeSettings configuration option for a specific scheme.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="82229-133">Файлы конфигурации</span><span class="sxs-lookup"><span data-stu-id="82229-133">Configuration Files</span></span>  
 <span data-ttu-id="82229-134">Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="82229-134">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="82229-135">Пример</span><span class="sxs-lookup"><span data-stu-id="82229-135">Example</span></span>  
 <span data-ttu-id="82229-136">В следующем примере показано конфигурацию, используемую <xref:System.Uri> класс для поддержки не экранирования разделителей закодированные пути для схемы http.</span><span class="sxs-lookup"><span data-stu-id="82229-136">The following example shows a configuration used by the <xref:System.Uri> class to support not escaping percent-encoded path delimiters for the http scheme.</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <schemeSettings>  
      <add name="http" genericUriParserOptions="DontUnescapePathDotsAndSlashes"/>  
    </schemeSettings>  
  </uri>  
</configuration>  
```  
  
## <a name="element-information"></a><span data-ttu-id="82229-137">Сведения об элементе</span><span class="sxs-lookup"><span data-stu-id="82229-137">Element Information</span></span>  
  
|||
|-|-|  
|<span data-ttu-id="82229-138">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="82229-138">Namespace</span></span>|<span data-ttu-id="82229-139">Система</span><span class="sxs-lookup"><span data-stu-id="82229-139">System</span></span>|  
|<span data-ttu-id="82229-140">Имя схемы</span><span class="sxs-lookup"><span data-stu-id="82229-140">Schema Name</span></span>||  
|<span data-ttu-id="82229-141">Файл проверки</span><span class="sxs-lookup"><span data-stu-id="82229-141">Validation File</span></span>||  
|<span data-ttu-id="82229-142">Может быть пустым</span><span class="sxs-lookup"><span data-stu-id="82229-142">Can be Empty</span></span>||  
  
## <a name="see-also"></a><span data-ttu-id="82229-143">См. также</span><span class="sxs-lookup"><span data-stu-id="82229-143">See also</span></span>
- <xref:System.Configuration.SchemeSettingElement?displayProperty=nameWithType>
- <xref:System.Configuration.SchemeSettingElementCollection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection.SchemeSettings%2A?displayProperty=nameWithType>
- <xref:System.GenericUriParserOptions?displayProperty=nameWithType>
- <xref:System.Uri?displayProperty=nameWithType>
- [<span data-ttu-id="82229-144">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="82229-144">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)

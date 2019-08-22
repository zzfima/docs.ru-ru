---
title: Элемент <clear> для schemeSettings (параметры URI)
ms.date: 03/30/2017
ms.assetid: 65098332-ce61-4542-ab8d-e7dc0257d31f
ms.openlocfilehash: 51c669aff767948523172aa075677ad3fb6478a2
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/21/2019
ms.locfileid: "69664178"
---
# <a name="clear-element-for-schemesettings-uri-settings"></a><span data-ttu-id="091f8-102">\<Очистка элемента > для schemeSettings (Параметры URI)</span><span class="sxs-lookup"><span data-stu-id="091f8-102">\<clear> Element for schemeSettings (Uri Settings)</span></span>
<span data-ttu-id="091f8-103">Удаляет все существующие параметры схемы.</span><span class="sxs-lookup"><span data-stu-id="091f8-103">Clears all existing scheme settings.</span></span>  
  
 <span data-ttu-id="091f8-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="091f8-104">\<configuration></span></span>  
<span data-ttu-id="091f8-105">\<> URI</span><span class="sxs-lookup"><span data-stu-id="091f8-105">\<uri></span></span>  
<span data-ttu-id="091f8-106">\<schemeSettings ></span><span class="sxs-lookup"><span data-stu-id="091f8-106">\<schemeSettings></span></span>  
<span data-ttu-id="091f8-107">\<очистить ></span><span class="sxs-lookup"><span data-stu-id="091f8-107">\<clear></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="091f8-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="091f8-108">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="091f8-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="091f8-109">Attributes and Elements</span></span>  
 <span data-ttu-id="091f8-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="091f8-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="091f8-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="091f8-111">Attributes</span></span>  
 <span data-ttu-id="091f8-112">Нет.</span><span class="sxs-lookup"><span data-stu-id="091f8-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="091f8-113">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="091f8-113">Child Elements</span></span>  
 <span data-ttu-id="091f8-114">Нет.</span><span class="sxs-lookup"><span data-stu-id="091f8-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="091f8-115">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="091f8-115">Parent Elements</span></span>  
  
|<span data-ttu-id="091f8-116">Элемент</span><span class="sxs-lookup"><span data-stu-id="091f8-116">Element</span></span>|<span data-ttu-id="091f8-117">Описание</span><span class="sxs-lookup"><span data-stu-id="091f8-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="091f8-118">Элемент \<schemeSettings> (параметры URI)</span><span class="sxs-lookup"><span data-stu-id="091f8-118">\<schemeSettings> Element (Uri Settings)</span></span>](schemesettings-element-uri-settings.md)|<span data-ttu-id="091f8-119">Определяет, как <xref:System.Uri> анализируется для определенных схем.</span><span class="sxs-lookup"><span data-stu-id="091f8-119">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="091f8-120">Примечания</span><span class="sxs-lookup"><span data-stu-id="091f8-120">Remarks</span></span>  
 <span data-ttu-id="091f8-121">По умолчанию класс <xref:System.Uri?displayProperty=nameWithType> отменяет escape-символы в процентах, закодированные разделителями, перед выполнением сжатия пути.</span><span class="sxs-lookup"><span data-stu-id="091f8-121">By default, the <xref:System.Uri?displayProperty=nameWithType> class un-escapes percent encoded path delimiters before executing path compression.</span></span> <span data-ttu-id="091f8-122">Это было реализовано в качестве механизма безопасности для атак, подобных следующим:</span><span class="sxs-lookup"><span data-stu-id="091f8-122">This was implemented as a security mechanism against attacks like the following:</span></span>  
  
 `http://www.contoso.com/..%2F..%2F/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="091f8-123">Если этот URI передается в модули, которые неправильно обрабатывают закодированные символы процента, это может привести к выполнению следующей команды на сервере:</span><span class="sxs-lookup"><span data-stu-id="091f8-123">If this URI gets passed down to modules not handling percent encoded characters correctly, it could result in the following command being executed by the server:</span></span>  
  
 `c:\Windows\System32\cmd.exe /c dir c:\`  
  
 <span data-ttu-id="091f8-124">По этой причине <xref:System.Uri?displayProperty=nameWithType> класс сначала отменяет escape-разделители путей, а затем применяет сжатие пути.</span><span class="sxs-lookup"><span data-stu-id="091f8-124">For this reason, <xref:System.Uri?displayProperty=nameWithType> class first un-escapes path delimiters and then applies path compression.</span></span> <span data-ttu-id="091f8-125">Результат передачи вредоносного URL-адреса выше в <xref:System.Uri?displayProperty=nameWithType> конструктор класса приводит к следующему URI:</span><span class="sxs-lookup"><span data-stu-id="091f8-125">The result of passing the malicious URL above to <xref:System.Uri?displayProperty=nameWithType> class constructor results in the following URI:</span></span>  
  
 `http://www.microsoft.com/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="091f8-126">Это поведение по умолчанию можно изменить, чтобы не отменять escape-символы в процентах с помощью параметра конфигурации schemeSettings для определенной схемы.</span><span class="sxs-lookup"><span data-stu-id="091f8-126">This default behavior can be modified to not un-escape percent encoded path delimiters using the schemeSettings configuration option for a specific scheme.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="091f8-127">Файлы конфигурации</span><span class="sxs-lookup"><span data-stu-id="091f8-127">Configuration Files</span></span>  
 <span data-ttu-id="091f8-128">Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="091f8-128">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="091f8-129">Пример</span><span class="sxs-lookup"><span data-stu-id="091f8-129">Example</span></span>  
 <span data-ttu-id="091f8-130">В следующем примере показана конфигурация, используемая <xref:System.Uri> классом, который очищает все параметры схемы и добавляет поддержку для разделителей пути, не экранированных в процентах, для схемы HTTP.</span><span class="sxs-lookup"><span data-stu-id="091f8-130">The following example shows a configuration used by the <xref:System.Uri> class that clears all scheme settings and then adds support for not escaping percent-encoded path delimiters for the http scheme.</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <schemeSettings>  
      <clear/>  
      <add name="http" genericUriParserOptions="DontUnescapePathDotsAndSlashes"/>  
    </schemeSettings>  
  </uri>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="091f8-131">См. также</span><span class="sxs-lookup"><span data-stu-id="091f8-131">See also</span></span>

- <xref:System.Configuration.SchemeSettingElement?displayProperty=nameWithType>
- <xref:System.Configuration.SchemeSettingElementCollection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection.SchemeSettings%2A?displayProperty=nameWithType>
- <xref:System.GenericUriParserOptions?displayProperty=nameWithType>
- <xref:System.Uri?displayProperty=nameWithType>
- [<span data-ttu-id="091f8-132">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="091f8-132">Network Settings Schema</span></span>](index.md)

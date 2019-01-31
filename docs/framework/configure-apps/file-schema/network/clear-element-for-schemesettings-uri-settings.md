---
title: Элемент <clear> для schemeSettings (Параметры URI)
ms.date: 03/30/2017
ms.assetid: 65098332-ce61-4542-ab8d-e7dc0257d31f
ms.openlocfilehash: 5bb97fbe04cbd3bba85113200abe6495639bab87
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55287109"
---
# <a name="clear-element-for-schemesettings-uri-settings"></a><span data-ttu-id="6cbcc-102">\<Очистить > элемент для schemeSettings (параметры Uri)</span><span class="sxs-lookup"><span data-stu-id="6cbcc-102">\<clear> Element for schemeSettings (Uri Settings)</span></span>
<span data-ttu-id="6cbcc-103">Удаляет все существующие параметры схемы.</span><span class="sxs-lookup"><span data-stu-id="6cbcc-103">Clears all existing scheme settings.</span></span>  
  
 <span data-ttu-id="6cbcc-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="6cbcc-104">\<configuration></span></span>  
<span data-ttu-id="6cbcc-105">\<URI ></span><span class="sxs-lookup"><span data-stu-id="6cbcc-105">\<uri></span></span>  
<span data-ttu-id="6cbcc-106">\<schemeSettings ></span><span class="sxs-lookup"><span data-stu-id="6cbcc-106">\<schemeSettings></span></span>  
<span data-ttu-id="6cbcc-107">\<Очистить ></span><span class="sxs-lookup"><span data-stu-id="6cbcc-107">\<clear></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6cbcc-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6cbcc-108">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6cbcc-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="6cbcc-109">Attributes and Elements</span></span>  
 <span data-ttu-id="6cbcc-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="6cbcc-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6cbcc-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="6cbcc-111">Attributes</span></span>  
 <span data-ttu-id="6cbcc-112">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="6cbcc-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="6cbcc-113">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="6cbcc-113">Child Elements</span></span>  
 <span data-ttu-id="6cbcc-114">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="6cbcc-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6cbcc-115">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="6cbcc-115">Parent Elements</span></span>  
  
|<span data-ttu-id="6cbcc-116">Элемент</span><span class="sxs-lookup"><span data-stu-id="6cbcc-116">Element</span></span>|<span data-ttu-id="6cbcc-117">Описание</span><span class="sxs-lookup"><span data-stu-id="6cbcc-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6cbcc-118">Элемент \<schemeSettings> (параметры URI)</span><span class="sxs-lookup"><span data-stu-id="6cbcc-118">\<schemeSettings> Element (Uri Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/schemesettings-element-uri-settings.md)|<span data-ttu-id="6cbcc-119">Определяет, как <xref:System.Uri> анализируется для определенных схем.</span><span class="sxs-lookup"><span data-stu-id="6cbcc-119">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6cbcc-120">Примечания</span><span class="sxs-lookup"><span data-stu-id="6cbcc-120">Remarks</span></span>  
 <span data-ttu-id="6cbcc-121">По умолчанию <xref:System.Uri?displayProperty=nameWithType> знаком процента Отмена переходов класс разделители пути до выполнения сжатия пути.</span><span class="sxs-lookup"><span data-stu-id="6cbcc-121">By default, the <xref:System.Uri?displayProperty=nameWithType> class un-escapes percent encoded path delimiters before executing path compression.</span></span> <span data-ttu-id="6cbcc-122">Это было реализовано в качестве механизма защиты от атак, следующим образом:</span><span class="sxs-lookup"><span data-stu-id="6cbcc-122">This was implemented as a security mechanism against attacks like the following:</span></span>  
  
 `http://www.contoso.com/..%2F..%2F/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="6cbcc-123">Если этот URI передается вниз, чтобы модули не обрабатывает процентов символы в кодировке неправильно, это может привести в следующей команде, выполняемой на сервере:</span><span class="sxs-lookup"><span data-stu-id="6cbcc-123">If this URI gets passed down to modules not handling percent encoded characters correctly, it could result in the following command being executed by the server:</span></span>  
  
 `c:\Windows\System32\cmd.exe /c dir c:\`  
  
 <span data-ttu-id="6cbcc-124">По этой причине <xref:System.Uri?displayProperty=nameWithType> класса первый разделители пути Отмена переходов, а затем применяет сжатие пути.</span><span class="sxs-lookup"><span data-stu-id="6cbcc-124">For this reason, <xref:System.Uri?displayProperty=nameWithType> class first un-escapes path delimiters and then applies path compression.</span></span> <span data-ttu-id="6cbcc-125">Результат передачи вредоносных URL-адрес выше <xref:System.Uri?displayProperty=nameWithType> класса конструктор результаты в следующий URI:</span><span class="sxs-lookup"><span data-stu-id="6cbcc-125">The result of passing the malicious URL above to <xref:System.Uri?displayProperty=nameWithType> class constructor results in the following URI:</span></span>  
  
 `http://www.microsoft.com/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="6cbcc-126">Можно изменить это поведение по умолчанию для не разделители отмены escape процента закодированный путь, с помощью параметра конфигурации schemeSettings для определенной схемы.</span><span class="sxs-lookup"><span data-stu-id="6cbcc-126">This default behavior can be modified to not un-escape percent encoded path delimiters using the schemeSettings configuration option for a specific scheme.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="6cbcc-127">Файлы конфигурации</span><span class="sxs-lookup"><span data-stu-id="6cbcc-127">Configuration Files</span></span>  
 <span data-ttu-id="6cbcc-128">Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="6cbcc-128">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="6cbcc-129">Пример</span><span class="sxs-lookup"><span data-stu-id="6cbcc-129">Example</span></span>  
 <span data-ttu-id="6cbcc-130">В следующем примере показано конфигурацию, используемую <xref:System.Uri> класс, который удаляет все параметры схемы, а затем добавляет поддержку не экранирования разделителей закодированные пути для схемы http.</span><span class="sxs-lookup"><span data-stu-id="6cbcc-130">The following example shows a configuration used by the <xref:System.Uri> class that clears all scheme settings and then adds support for not escaping percent-encoded path delimiters for the http scheme.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="6cbcc-131">См. также</span><span class="sxs-lookup"><span data-stu-id="6cbcc-131">See also</span></span>
- <xref:System.Configuration.SchemeSettingElement?displayProperty=nameWithType>
- <xref:System.Configuration.SchemeSettingElementCollection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection.SchemeSettings%2A?displayProperty=nameWithType>
- <xref:System.GenericUriParserOptions?displayProperty=nameWithType>
- <xref:System.Uri?displayProperty=nameWithType>
- [<span data-ttu-id="6cbcc-132">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="6cbcc-132">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)

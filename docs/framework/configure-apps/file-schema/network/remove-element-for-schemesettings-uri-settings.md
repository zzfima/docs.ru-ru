---
title: Элемент <remove> для schemeSettings (параметры URI)
ms.date: 03/30/2017
ms.assetid: 4095ba51-de20-4f87-b562-018abe422c91
ms.openlocfilehash: f29ee86deaa150324b40f4fac12ead152553e50d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61674445"
---
# <a name="remove-element-for-schemesettings-uri-settings"></a><span data-ttu-id="2ac16-102">\<Удалить > элемент для schemeSettings (параметры Uri)</span><span class="sxs-lookup"><span data-stu-id="2ac16-102">\<remove> Element for schemeSettings (Uri Settings)</span></span>
<span data-ttu-id="2ac16-103">Удаляет параметр схемы для имени схемы.</span><span class="sxs-lookup"><span data-stu-id="2ac16-103">Removes a scheme setting for a scheme name.</span></span>  
  
 <span data-ttu-id="2ac16-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="2ac16-104">\<configuration></span></span>  
<span data-ttu-id="2ac16-105">\<URI ></span><span class="sxs-lookup"><span data-stu-id="2ac16-105">\<uri></span></span>  
<span data-ttu-id="2ac16-106">\<schemeSettings ></span><span class="sxs-lookup"><span data-stu-id="2ac16-106">\<schemeSettings></span></span>  
<span data-ttu-id="2ac16-107">\<Удалить ></span><span class="sxs-lookup"><span data-stu-id="2ac16-107">\<remove></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2ac16-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2ac16-108">Syntax</span></span>  
  
```xml  
<remove
  name="http|https"
/>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2ac16-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="2ac16-109">Attributes and Elements</span></span>  
 <span data-ttu-id="2ac16-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="2ac16-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2ac16-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="2ac16-111">Attributes</span></span>  
  
|<span data-ttu-id="2ac16-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="2ac16-112">Attribute</span></span>|<span data-ttu-id="2ac16-113">Описание</span><span class="sxs-lookup"><span data-stu-id="2ac16-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2ac16-114">имя</span><span class="sxs-lookup"><span data-stu-id="2ac16-114">name</span></span>|<span data-ttu-id="2ac16-115">Имя схемы, к которому применяется этот параметр.</span><span class="sxs-lookup"><span data-stu-id="2ac16-115">The scheme name for which this setting applies.</span></span> <span data-ttu-id="2ac16-116">Только поддерживаемые значения: имя = «http» и имя = «https».</span><span class="sxs-lookup"><span data-stu-id="2ac16-116">The only supported values are name="http" and name="https".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2ac16-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="2ac16-117">Child Elements</span></span>  
 <span data-ttu-id="2ac16-118">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="2ac16-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2ac16-119">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="2ac16-119">Parent Elements</span></span>  
  
|<span data-ttu-id="2ac16-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="2ac16-120">Element</span></span>|<span data-ttu-id="2ac16-121">Описание</span><span class="sxs-lookup"><span data-stu-id="2ac16-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2ac16-122">Элемент \<schemeSettings> (параметры URI)</span><span class="sxs-lookup"><span data-stu-id="2ac16-122">\<schemeSettings> Element (Uri Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/schemesettings-element-uri-settings.md)|<span data-ttu-id="2ac16-123">Определяет, как <xref:System.Uri> анализируется для определенных схем.</span><span class="sxs-lookup"><span data-stu-id="2ac16-123">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2ac16-124">Примечания</span><span class="sxs-lookup"><span data-stu-id="2ac16-124">Remarks</span></span>  
 <span data-ttu-id="2ac16-125">По умолчанию <xref:System.Uri?displayProperty=nameWithType> знаком процента Отмена переходов класс разделители пути до выполнения сжатия пути.</span><span class="sxs-lookup"><span data-stu-id="2ac16-125">By default, the <xref:System.Uri?displayProperty=nameWithType> class un-escapes percent encoded path delimiters before executing path compression.</span></span> <span data-ttu-id="2ac16-126">Это было реализовано в качестве механизма защиты от атак, следующим образом:</span><span class="sxs-lookup"><span data-stu-id="2ac16-126">This was implemented as a security mechanism against attacks like the following:</span></span>  
  
 `http://www.contoso.com/..%2F..%2F/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="2ac16-127">Если этот URI передается вниз, чтобы модули не обрабатывает процентов символы в кодировке неправильно, это может привести в следующей команде, выполняемой на сервере:</span><span class="sxs-lookup"><span data-stu-id="2ac16-127">If this URI gets passed down to modules not handling percent encoded characters correctly, it could result in the following command being executed by the server:</span></span>  
  
 `c:\Windows\System32\cmd.exe /c dir c:\`  
  
 <span data-ttu-id="2ac16-128">По этой причине <xref:System.Uri?displayProperty=nameWithType> класса первый разделители пути Отмена переходов, а затем применяет сжатие пути.</span><span class="sxs-lookup"><span data-stu-id="2ac16-128">For this reason, <xref:System.Uri?displayProperty=nameWithType> class first un-escapes path delimiters and then applies path compression.</span></span> <span data-ttu-id="2ac16-129">Результат передачи вредоносных URL-адрес выше <xref:System.Uri?displayProperty=nameWithType> класса конструктор результаты в следующий URI:</span><span class="sxs-lookup"><span data-stu-id="2ac16-129">The result of passing the malicious URL above to <xref:System.Uri?displayProperty=nameWithType> class constructor results in the following URI:</span></span>  
  
 `http://www.microsoft.com/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="2ac16-130">Можно изменить это поведение по умолчанию для не разделители отмены escape процента закодированный путь, с помощью параметра конфигурации schemeSettings для определенной схемы.</span><span class="sxs-lookup"><span data-stu-id="2ac16-130">This default behavior can be modified to not un-escape percent encoded path delimiters using the schemeSettings configuration option for a specific scheme.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="2ac16-131">Файлы конфигурации</span><span class="sxs-lookup"><span data-stu-id="2ac16-131">Configuration Files</span></span>  
 <span data-ttu-id="2ac16-132">Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="2ac16-132">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="2ac16-133">Пример</span><span class="sxs-lookup"><span data-stu-id="2ac16-133">Example</span></span>  
 <span data-ttu-id="2ac16-134">В следующем примере показано конфигурацию, используемую <xref:System.Uri> класс, который удаляет все параметры схемы для схемы http.</span><span class="sxs-lookup"><span data-stu-id="2ac16-134">The following example shows a configuration used by the <xref:System.Uri> class that removes any scheme settings for the http scheme.</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <schemeSettings>  
      <remove name="http"/>  
    </schemeSettings>  
  </uri>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="2ac16-135">См. также</span><span class="sxs-lookup"><span data-stu-id="2ac16-135">See also</span></span>

- <xref:System.Configuration.SchemeSettingElement?displayProperty=nameWithType>
- <xref:System.Configuration.SchemeSettingElementCollection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection.SchemeSettings%2A?displayProperty=nameWithType>
- <xref:System.GenericUriParserOptions?displayProperty=nameWithType>
- <xref:System.Uri?displayProperty=nameWithType>
- [<span data-ttu-id="2ac16-136">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="2ac16-136">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)

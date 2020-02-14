---
title: элемент <clear> для NameValueSectionHandler и DictionarySectionHandler
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName/clear
helpviewer_keywords:
- clear Element
- <clear> Element
ms.assetid: ff2294ec-fb82-4b0c-933e-ae185433fc7b
ms.openlocfilehash: f6d860f35d22002030ffa3d09dd0d8a96116bf5e
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2020
ms.locfileid: "77214743"
---
# <a name="clear-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a><span data-ttu-id="30fc2-102">\<Clear > элемента для NameValueSectionHandler и DictionarySectionHandler</span><span class="sxs-lookup"><span data-stu-id="30fc2-102">\<clear> element for NameValueSectionHandler and DictionarySectionHandler</span></span>

<span data-ttu-id="30fc2-103">Удаляет все ранее определенные параметры в разделе.</span><span class="sxs-lookup"><span data-stu-id="30fc2-103">Clears all previously defined settings in a section.</span></span>

<span data-ttu-id="30fc2-104">[ **\<configuration>** ](configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="30fc2-104">[**\<configuration>**](configuration-element.md)</span></span>\
<span data-ttu-id="30fc2-105">&nbsp;&nbsp;[ **\<sectionName >** ](custom-element-2.md)</span><span class="sxs-lookup"><span data-stu-id="30fc2-105">&nbsp;&nbsp;[**\<sectionName>**](custom-element-2.md)</span></span>\
<span data-ttu-id="30fc2-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<clear >**</span><span class="sxs-lookup"><span data-stu-id="30fc2-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>

## <a name="syntax"></a><span data-ttu-id="30fc2-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="30fc2-107">Syntax</span></span>

```xml
<clear />
```

## <a name="attributes"></a><span data-ttu-id="30fc2-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="30fc2-108">Attributes</span></span>

<span data-ttu-id="30fc2-109">Нет</span><span class="sxs-lookup"><span data-stu-id="30fc2-109">None</span></span>

## <a name="parent-element"></a><span data-ttu-id="30fc2-110">Родительский элемент</span><span class="sxs-lookup"><span data-stu-id="30fc2-110">Parent element</span></span>

|     | <span data-ttu-id="30fc2-111">Описание</span><span class="sxs-lookup"><span data-stu-id="30fc2-111">Description</span></span> |
| --- | ------------|
| [<span data-ttu-id="30fc2-112"> **\<sectionName >** Дерев</span><span class="sxs-lookup"><span data-stu-id="30fc2-112">**\<sectionName>** Element</span></span>](custom-element-2.md) | <span data-ttu-id="30fc2-113">Определяет параметры для пользовательских разделов конфигурации, использующих классы <xref:System.Configuration.NameValueSectionHandler> и <xref:System.Configuration.DictionarySectionHandler>.</span><span class="sxs-lookup"><span data-stu-id="30fc2-113">Defines settings for custom configuration sections that use the <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler> classes.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="30fc2-114">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="30fc2-114">Child elements</span></span>

<span data-ttu-id="30fc2-115">Нет</span><span class="sxs-lookup"><span data-stu-id="30fc2-115">None</span></span>

## <a name="remarks"></a><span data-ttu-id="30fc2-116">Примечания</span><span class="sxs-lookup"><span data-stu-id="30fc2-116">Remarks</span></span>

<span data-ttu-id="30fc2-117">Можно использовать элемент **\<clear >** , чтобы удалить из приложения все параметры, которые были определены на более высоком уровне в иерархии файлов конфигурации.</span><span class="sxs-lookup"><span data-stu-id="30fc2-117">You can use the **\<clear>** element to remove all settings from your application that were defined at a higher level in the configuration file hierarchy.</span></span>

## <a name="example"></a><span data-ttu-id="30fc2-118">Пример</span><span class="sxs-lookup"><span data-stu-id="30fc2-118">Example</span></span>

<span data-ttu-id="30fc2-119">В этом примере определяется файл конфигурации компьютера и файл конфигурации приложения, а также демонстрируется использование элемента **\<clear >** в файле конфигурации приложения для очистки разделов, ранее определенных в файле конфигурации компьютера.</span><span class="sxs-lookup"><span data-stu-id="30fc2-119">This example defines a machine configuration file and an application configuration file and shows how to use the **\<clear>** element in an application configuration file to clear sections previously defined in the machine configuration file.</span></span>

<span data-ttu-id="30fc2-120">В следующем коде файла конфигурации компьютера объявляется раздел **\<мисектион >** :</span><span class="sxs-lookup"><span data-stu-id="30fc2-120">The following machine configuration file code declares the section **\<mySection>**:</span></span>

```xml
<!-- Machine.config file -->
<configuration>
  <configSections>
    <section name="mySection" type="System.Configuration.NameValueSectionHandler,System" />
  </configSections>
  <mySection>
    <add key="key1" value="value1" />
    <add key="key2" value="value2" />
  </mySection>
</configuration>
```

<span data-ttu-id="30fc2-121">Следующий код файла конфигурации приложения удаляет все параметры из **\<мисектион >** .</span><span class="sxs-lookup"><span data-stu-id="30fc2-121">The following application configuration file code removes all settings from **\<mySection>**.</span></span> <span data-ttu-id="30fc2-122">Приложение не может получить параметры, которые были объявлены в, в разделе **\<мисектион >** файла конфигурации компьютера.</span><span class="sxs-lookup"><span data-stu-id="30fc2-122">The application cannot retrieve any of the settings that were declared in the in the **\<mySection>** section of the machine configuration file.</span></span>

```xml
<!-- Application configuration file -->
<configuration>
  <mySection>
    <clear/>
  </mySection>
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="30fc2-123">Файл конфигурации</span><span class="sxs-lookup"><span data-stu-id="30fc2-123">Configuration file</span></span>

<span data-ttu-id="30fc2-124">Этот элемент можно использовать в файле конфигурации приложения, файле конфигурации компьютера (*Machine. config*) и файлах *Web. config* , которые не находятся на уровне каталога приложений.</span><span class="sxs-lookup"><span data-stu-id="30fc2-124">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="30fc2-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="30fc2-125">See also</span></span>

- [<span data-ttu-id="30fc2-126">Схема файла конфигурации для .NET Framework</span><span class="sxs-lookup"><span data-stu-id="30fc2-126">Configuration file schema for the .NET Framework</span></span>](index.md)

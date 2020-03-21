---
title: Элемент <remove> для <configSections>
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/remove
helpviewer_keywords:
- remove Element
- <remove> Element
ms.assetid: ae4d82e0-e8fe-468c-81ab-46d63c4d66a8
ms.openlocfilehash: 6991e3f73ac180fc690ec48e1a0d15f40c915733
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154534"
---
# <a name="remove-element-for-configsections"></a><span data-ttu-id="8b0b4-102">\<удалить элемент \<> для> конфигураций</span><span class="sxs-lookup"><span data-stu-id="8b0b4-102">\<remove> element for \<configSections></span></span>

<span data-ttu-id="8b0b4-103">Удаляет заранее определенный раздел или группу раздела.</span><span class="sxs-lookup"><span data-stu-id="8b0b4-103">Removes a predefined section or section group.</span></span>

<span data-ttu-id="8b0b4-104">[**\<конфигурация>**](configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="8b0b4-104">[**\<configuration>**](configuration-element.md)</span></span>\
<span data-ttu-id="8b0b4-105">&nbsp;&nbsp;[**\<конфигурации>**](configsections-element-for-configuration.md)</span><span class="sxs-lookup"><span data-stu-id="8b0b4-105">&nbsp;&nbsp;[**\<configSections>**](configsections-element-for-configuration.md)</span></span>\
<span data-ttu-id="8b0b4-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<удалить>**</span><span class="sxs-lookup"><span data-stu-id="8b0b4-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**</span></span>

## <a name="syntax"></a><span data-ttu-id="8b0b4-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8b0b4-107">Syntax</span></span>

```xml
<remove name="section name or section group name" />
```

## <a name="attribute"></a><span data-ttu-id="8b0b4-108">attribute</span><span class="sxs-lookup"><span data-stu-id="8b0b4-108">Attribute</span></span>

|           | <span data-ttu-id="8b0b4-109">Описание</span><span class="sxs-lookup"><span data-stu-id="8b0b4-109">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="8b0b4-110">**name**</span><span class="sxs-lookup"><span data-stu-id="8b0b4-110">**name**</span></span>  | <span data-ttu-id="8b0b4-111">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="8b0b4-111">Required attribute.</span></span><br><br><span data-ttu-id="8b0b4-112">Уотек названия группы раздела или раздела для удаления.</span><span class="sxs-lookup"><span data-stu-id="8b0b4-112">Specifies the name of the section or section group to remove.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="8b0b4-113">Родительский элемент</span><span class="sxs-lookup"><span data-stu-id="8b0b4-113">Parent element</span></span>

|     | <span data-ttu-id="8b0b4-114">Описание</span><span class="sxs-lookup"><span data-stu-id="8b0b4-114">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="8b0b4-115">\*\* \<конфигурации>\*\* Элемент</span><span class="sxs-lookup"><span data-stu-id="8b0b4-115">**\<configSections>** Element</span></span>](configsections-element-for-configuration.md) | <span data-ttu-id="8b0b4-116">Содержит раздел конфигурации и декларации пространства имен.</span><span class="sxs-lookup"><span data-stu-id="8b0b4-116">Contains configuration section and namespace declarations.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="8b0b4-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="8b0b4-117">Child elements</span></span>

<span data-ttu-id="8b0b4-118">None</span><span class="sxs-lookup"><span data-stu-id="8b0b4-118">None</span></span>

## <a name="remarks"></a><span data-ttu-id="8b0b4-119">Remarks</span><span class="sxs-lookup"><span data-stu-id="8b0b4-119">Remarks</span></span>

<span data-ttu-id="8b0b4-120">Элемент \*\* \<удаления>\*\* можно удалить разделы и группы разделов из приложения, которые были определены на более высоком уровне в иерархии файлов конфигурации.</span><span class="sxs-lookup"><span data-stu-id="8b0b4-120">You can use the **\<remove>** element to remove sections and section groups from your application that were defined at a higher level in the configuration file hierarchy.</span></span>

## <a name="example"></a><span data-ttu-id="8b0b4-121">Пример</span><span class="sxs-lookup"><span data-stu-id="8b0b4-121">Example</span></span>

<span data-ttu-id="8b0b4-122">В следующем примере показано, как использовать \*\* \<элемент удаления>\*\* в файле конфигурации приложения для удаления раздела, ранее определенного в файле конфигурации машины.</span><span class="sxs-lookup"><span data-stu-id="8b0b4-122">The following example shows how to use the **\<remove>** element in an application configuration file to remove a section previously defined in the machine configuration file.</span></span>

<span data-ttu-id="8b0b4-123">Следующий файл овый код конфигурации машины объявляет \*\* \<образец разделаРаздел>: \*\*</span><span class="sxs-lookup"><span data-stu-id="8b0b4-123">The following machine configuration file code declares the section **\<sampleSection>**:</span></span>

```xml
<!-- Machine.config file -->
<configuration>
  <configSections>
    <section name="sampleSection"
             type="System.Configuration.SingleTagSectionHandler" />
  </configSections>
  <sampleSection setting1="Value1"
                 setting2="value two"
                 setting3="third value" />
</configuration>
```

<span data-ttu-id="8b0b4-124">Следующий файл конфигурации приложения код удаляет \*\* \<образецРаздел>\*\* раздел.</span><span class="sxs-lookup"><span data-stu-id="8b0b4-124">The following application configuration file code removes the **\<sampleSection>** section.</span></span> <span data-ttu-id="8b0b4-125">После удаления приложение не может получить настройки в \*\* \<>sampleSection. \*\*</span><span class="sxs-lookup"><span data-stu-id="8b0b4-125">After removal, the application cannot retrieve the settings in **\<sampleSection>**.</span></span>

```xml
<!-- Application configuration file -->
<configuration>
  <configSections>
    <remove name="sampleSection"/>
  </configSections>
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="8b0b4-126">Файл конфигурации</span><span class="sxs-lookup"><span data-stu-id="8b0b4-126">Configuration file</span></span>

<span data-ttu-id="8b0b4-127">Этот элемент может быть использован в файле конфигурации приложения, файле конфигурации машины *(Machine.config)* и файлах *Web.config,* которые не находятся на уровне каталога приложений.</span><span class="sxs-lookup"><span data-stu-id="8b0b4-127">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="8b0b4-128">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="8b0b4-128">See also</span></span>

- [<span data-ttu-id="8b0b4-129">Схема конфигурации файла для рамочного соглашения .NET</span><span class="sxs-lookup"><span data-stu-id="8b0b4-129">Configuration file schema for the .NET Framework</span></span>](index.md)

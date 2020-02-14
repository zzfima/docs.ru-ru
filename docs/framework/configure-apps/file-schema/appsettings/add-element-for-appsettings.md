---
title: Элемент <add> для <appSettings>
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/appSettings/add
helpviewer_keywords:
- add Element
- <add> Element
ms.assetid: 8734efdc-00f6-4a65-bba6-084c5bc65246
ms.openlocfilehash: 5c7de79ec626966e71d461dd3865b294a8979db2
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2020
ms.locfileid: "77214812"
---
# <a name="add-element-for-appsettings"></a><span data-ttu-id="b4d8b-102">\<добавить элемент > для \<appSettings ></span><span class="sxs-lookup"><span data-stu-id="b4d8b-102">\<add> element for \<appSettings></span></span>

<span data-ttu-id="b4d8b-103">Добавляет пользовательский параметр приложения.</span><span class="sxs-lookup"><span data-stu-id="b4d8b-103">Adds a custom application setting.</span></span>

<span data-ttu-id="b4d8b-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="b4d8b-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="b4d8b-105">&nbsp;&nbsp;[ **\<appSettings>** ](appsettings-element-for-configuration.md)</span><span class="sxs-lookup"><span data-stu-id="b4d8b-105">&nbsp;&nbsp;[**\<appSettings>**](appsettings-element-for-configuration.md)</span></span>\
<span data-ttu-id="b4d8b-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<добавить >**</span><span class="sxs-lookup"><span data-stu-id="b4d8b-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>

## <a name="syntax"></a><span data-ttu-id="b4d8b-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b4d8b-107">Syntax</span></span>

```xml
<appSettings>
  <add key="Key of custom setting" value="Value of custom setting" />
</appSettings>
```

## <a name="attributes"></a><span data-ttu-id="b4d8b-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="b4d8b-108">Attributes</span></span>

|           | <span data-ttu-id="b4d8b-109">Описание</span><span class="sxs-lookup"><span data-stu-id="b4d8b-109">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="b4d8b-110">**key**</span><span class="sxs-lookup"><span data-stu-id="b4d8b-110">**key**</span></span>   | <span data-ttu-id="b4d8b-111">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="b4d8b-111">Required attribute.</span></span><br><br><span data-ttu-id="b4d8b-112">Указывает имя добавляемого ключа.</span><span class="sxs-lookup"><span data-stu-id="b4d8b-112">Specifies the name of the key to add.</span></span> |
| <span data-ttu-id="b4d8b-113">**value**</span><span class="sxs-lookup"><span data-stu-id="b4d8b-113">**value**</span></span> | <span data-ttu-id="b4d8b-114">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="b4d8b-114">Required attribute.</span></span><br><br><span data-ttu-id="b4d8b-115">Указывает значение добавляемого ключа.</span><span class="sxs-lookup"><span data-stu-id="b4d8b-115">Specifies the value of the key to add.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="b4d8b-116">Родительский элемент</span><span class="sxs-lookup"><span data-stu-id="b4d8b-116">Parent element</span></span>

|     | <span data-ttu-id="b4d8b-117">Описание</span><span class="sxs-lookup"><span data-stu-id="b4d8b-117">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="b4d8b-118"> **\<appSettings>** </span><span class="sxs-lookup"><span data-stu-id="b4d8b-118">**\<appSettings>**</span></span>](appsettings-element-for-configuration.md) | <span data-ttu-id="b4d8b-119">Содержит пользовательские параметры приложения, такие как пути к файлам, URL-адреса XML-веб-служб и другие сведения о пользовательской конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="b4d8b-119">Contains custom application settings, such as file paths, XML Web service URLs, or any other custom configuration information for an application.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="b4d8b-120">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="b4d8b-120">Child elements</span></span>

<span data-ttu-id="b4d8b-121">Нет</span><span class="sxs-lookup"><span data-stu-id="b4d8b-121">None</span></span>

## <a name="example"></a><span data-ttu-id="b4d8b-122">Пример</span><span class="sxs-lookup"><span data-stu-id="b4d8b-122">Example</span></span>

<span data-ttu-id="b4d8b-123">В следующем примере показано, как добавить настраиваемый параметр конфигурации для имени приложения:</span><span class="sxs-lookup"><span data-stu-id="b4d8b-123">The following example shows how to add a custom configuration setting for the application's name:</span></span>

```xml
<appSettings>
  <add key="ApplicationName" value="MyApplication" />
</appSettings>
```

<span data-ttu-id="b4d8b-124">В следующем примере элемент `<add>` используется для определения двух параметров совместимости в приложении ASP.NET:</span><span class="sxs-lookup"><span data-stu-id="b4d8b-124">The following example uses the `<add>` element to define two compatibility settings in an ASP.NET application:</span></span>

```xml
<appSettings>
  <add key="AppContext.SetSwitch:Switch.System.Globalization.NoAsyncCurrentCulture" value="true" />
  <add key="AppContext.SetSwitch:Switch.System.Uri.DontEnableStrictRFC3986ReservedCharacterSets" value="true" />
</appSettings>
```

## <a name="see-also"></a><span data-ttu-id="b4d8b-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="b4d8b-125">See also</span></span>

- [<span data-ttu-id="b4d8b-126">Схема файла конфигурации для .NET Framework</span><span class="sxs-lookup"><span data-stu-id="b4d8b-126">Configuration file schema for the .NET Framework</span></span>](../index.md)

---
title: Схема параметров приложения
ms.date: 03/30/2017
helpviewer_keywords:
- schema application settings
- application settings, schema [Windows Forms]
- Windows Forms, application settings schema
- configuration schema [.NET Framework], application settings
ms.assetid: 5797fcff-6081-4e8c-bebf-63d9c70cf14b
author: mcleblanc
ms.author: markl
ms.openlocfilehash: f11be59941759687806591feb1edcce28b2119e6
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/25/2018
ms.locfileid: "47073440"
---
# <a name="application-settings-schema"></a><span data-ttu-id="f1a56-102">Схема параметров приложения</span><span class="sxs-lookup"><span data-stu-id="f1a56-102">Application Settings schema</span></span>

<span data-ttu-id="f1a56-103">Параметры приложений позволяют приложению Windows Forms или ASP.NET сохранять и извлекать параметры области приложения и уровня пользователя.</span><span class="sxs-lookup"><span data-stu-id="f1a56-103">Application settings allow a Windows Forms or ASP.NET application to store and retrieve application-scoped and user-scoped settings.</span></span> <span data-ttu-id="f1a56-104">В этом контексте *параметр* является любая информация, не относящиеся к приложению или к текущему пользователю — от строку подключения базы данных для пользователя предпочтительный размер окна по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="f1a56-104">In this context, a *setting* is any piece of information that may be specific to the application or specific to the current user — anything from a database connection string to the user's preferred default window size.</span></span>

<span data-ttu-id="f1a56-105">По умолчанию использует параметры приложения в приложении Windows Forms <xref:System.Configuration.LocalFileSettingsProvider> класс, который использует систему конфигурации .NET для хранения параметров в файле конфигурации XML.</span><span class="sxs-lookup"><span data-stu-id="f1a56-105">By default, application settings in a Windows Forms application uses the <xref:System.Configuration.LocalFileSettingsProvider> class, which uses the .NET configuration system to store settings in an XML configuration file.</span></span> <span data-ttu-id="f1a56-106">Дополнительные сведения о файлах, используемых параметрами приложения, см. в разделе [архитектура параметров приложения](~/docs/framework/winforms/advanced/application-settings-architecture.md).</span><span class="sxs-lookup"><span data-stu-id="f1a56-106">For more information about the files used by application settings, see [Application Settings Architecture](~/docs/framework/winforms/advanced/application-settings-architecture.md).</span></span>

<span data-ttu-id="f1a56-107">Параметры приложения определяет следующие элементы как часть файлов конфигурации, используемые в нем.</span><span class="sxs-lookup"><span data-stu-id="f1a56-107">Application settings defines the following elements as part of the configuration files it uses.</span></span>

| <span data-ttu-id="f1a56-108">Элемент</span><span class="sxs-lookup"><span data-stu-id="f1a56-108">Element</span></span>                    | <span data-ttu-id="f1a56-109">Описание</span><span class="sxs-lookup"><span data-stu-id="f1a56-109">Description</span></span>                                                                           |
| -------------------------- | ------------------------------------------------------------------------------------- |
| <span data-ttu-id="f1a56-110">**\<applicationSettings >**</span><span class="sxs-lookup"><span data-stu-id="f1a56-110">**\<applicationSettings>**</span></span> | <span data-ttu-id="f1a56-111">Содержит все  **\<параметр >** теги, относящиеся к приложению.</span><span class="sxs-lookup"><span data-stu-id="f1a56-111">Contains all **\<setting>** tags specific to the application.</span></span>                         |
| <span data-ttu-id="f1a56-112">**\<userSettings >**</span><span class="sxs-lookup"><span data-stu-id="f1a56-112">**\<userSettings>**</span></span>        | <span data-ttu-id="f1a56-113">Содержит все  **\<параметр >** теги, относящиеся к текущему пользователю.</span><span class="sxs-lookup"><span data-stu-id="f1a56-113">Contains all **\<setting>** tags specific to the current user.</span></span>                        |
| <span data-ttu-id="f1a56-114">**\<параметр >**</span><span class="sxs-lookup"><span data-stu-id="f1a56-114">**\<setting>**</span></span>             | <span data-ttu-id="f1a56-115">Определяет параметр.</span><span class="sxs-lookup"><span data-stu-id="f1a56-115">Defines a setting.</span></span> <span data-ttu-id="f1a56-116">Дочерним для элемента  **\<applicationSettings >** или  **\<userSettings >**.</span><span class="sxs-lookup"><span data-stu-id="f1a56-116">Child of either **\<applicationSettings>** or **\<userSettings>**.</span></span> |
| <span data-ttu-id="f1a56-117">**\<value>**</span><span class="sxs-lookup"><span data-stu-id="f1a56-117">**\<value>**</span></span>               | <span data-ttu-id="f1a56-118">Определяет значение параметра.</span><span class="sxs-lookup"><span data-stu-id="f1a56-118">Defines a setting's value.</span></span> <span data-ttu-id="f1a56-119">Потомком  **\<параметр >**.</span><span class="sxs-lookup"><span data-stu-id="f1a56-119">Child of **\<setting>**.</span></span>                                   |

## <a name="applicationsettings-element"></a><span data-ttu-id="f1a56-120">\<applicationSettings > элемент</span><span class="sxs-lookup"><span data-stu-id="f1a56-120">\<applicationSettings> element</span></span>

<span data-ttu-id="f1a56-121">Этот элемент содержит все  **\<параметр >** теги, относящиеся к экземпляру приложения на клиентском компьютере.</span><span class="sxs-lookup"><span data-stu-id="f1a56-121">This element contains all **\<setting>** tags that are specific to an instance of the application on a client computer.</span></span> <span data-ttu-id="f1a56-122">Атрибуты не определяются.</span><span class="sxs-lookup"><span data-stu-id="f1a56-122">It defines no attributes.</span></span>

## <a name="usersettings-element"></a><span data-ttu-id="f1a56-123">\<userSettings > элемент</span><span class="sxs-lookup"><span data-stu-id="f1a56-123">\<userSettings> element</span></span>

<span data-ttu-id="f1a56-124">Этот элемент содержит все  **\<параметр >** теги, характерные для пользователя, который в настоящее время использует приложение.</span><span class="sxs-lookup"><span data-stu-id="f1a56-124">This element contains all **\<setting>** tags that are specific to the user who is currently using the application.</span></span> <span data-ttu-id="f1a56-125">Атрибуты не определяются.</span><span class="sxs-lookup"><span data-stu-id="f1a56-125">It defines no attributes.</span></span>

## <a name="setting-element"></a><span data-ttu-id="f1a56-126">\<Установка > элемент</span><span class="sxs-lookup"><span data-stu-id="f1a56-126">\<setting> element</span></span>

<span data-ttu-id="f1a56-127">Этот элемент определяет параметр.</span><span class="sxs-lookup"><span data-stu-id="f1a56-127">This element defines a setting.</span></span> <span data-ttu-id="f1a56-128">Он имеет следующие атрибуты.</span><span class="sxs-lookup"><span data-stu-id="f1a56-128">It has the following attributes.</span></span>

| <span data-ttu-id="f1a56-129">Атрибут</span><span class="sxs-lookup"><span data-stu-id="f1a56-129">Attribute</span></span>        | <span data-ttu-id="f1a56-130">Описание</span><span class="sxs-lookup"><span data-stu-id="f1a56-130">Description</span></span> |
| ---------------- | ----------- |
| <span data-ttu-id="f1a56-131">**name**</span><span class="sxs-lookup"><span data-stu-id="f1a56-131">**name**</span></span>         | <span data-ttu-id="f1a56-132">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="f1a56-132">Required.</span></span> <span data-ttu-id="f1a56-133">Уникальный идентификатор параметра.</span><span class="sxs-lookup"><span data-stu-id="f1a56-133">The unique ID of the setting.</span></span> <span data-ttu-id="f1a56-134">Параметры, созданные с помощью Visual Studio сохраняются с именем `ProjectName.Properties.Settings`.</span><span class="sxs-lookup"><span data-stu-id="f1a56-134">Settings created through Visual Studio are saved with the name `ProjectName.Properties.Settings`.</span></span> |
| <span data-ttu-id="f1a56-135">**serializedAs**</span><span class="sxs-lookup"><span data-stu-id="f1a56-135">**serializedAs**</span></span> | <span data-ttu-id="f1a56-136">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="f1a56-136">Required.</span></span> <span data-ttu-id="f1a56-137">Формат, используемый для сериализации значение к тексту.</span><span class="sxs-lookup"><span data-stu-id="f1a56-137">The format to use for serializing the value to text.</span></span> <span data-ttu-id="f1a56-138">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="f1a56-138">Valid values are:</span></span><br><br><span data-ttu-id="f1a56-139">- `string`.</span><span class="sxs-lookup"><span data-stu-id="f1a56-139">- `string`.</span></span> <span data-ttu-id="f1a56-140">Значение сериализуется как строки с помощью <xref:System.ComponentModel.TypeConverter>.</span><span class="sxs-lookup"><span data-stu-id="f1a56-140">The value is serialized as a string using a <xref:System.ComponentModel.TypeConverter>.</span></span><br><span data-ttu-id="f1a56-141">- `xml`.</span><span class="sxs-lookup"><span data-stu-id="f1a56-141">- `xml`.</span></span> <span data-ttu-id="f1a56-142">Значение сериализуется с помощью XML-сериализации.</span><span class="sxs-lookup"><span data-stu-id="f1a56-142">The value is serialized using XML serialization.</span></span><br><span data-ttu-id="f1a56-143">- `binary`.</span><span class="sxs-lookup"><span data-stu-id="f1a56-143">- `binary`.</span></span> <span data-ttu-id="f1a56-144">Значение сериализуется как двоичные кодировке текста, с использованием двоичной сериализации.</span><span class="sxs-lookup"><span data-stu-id="f1a56-144">The value is serialized as text-encoded binary using binary serialization.</span></span><br /><span data-ttu-id="f1a56-145">- `custom`.</span><span class="sxs-lookup"><span data-stu-id="f1a56-145">- `custom`.</span></span> <span data-ttu-id="f1a56-146">Поставщик параметров имеет распознает этот параметр и сериализует и десериализует его.</span><span class="sxs-lookup"><span data-stu-id="f1a56-146">The settings provider has inherent knowledge of this setting and serializes and de-serializes it.</span></span> |

## <a name="value-element"></a><span data-ttu-id="f1a56-147">\<Значение > элемент</span><span class="sxs-lookup"><span data-stu-id="f1a56-147">\<value> element</span></span>

<span data-ttu-id="f1a56-148">Этот элемент содержит значение параметра.</span><span class="sxs-lookup"><span data-stu-id="f1a56-148">This element contains the value of a setting.</span></span>

## <a name="example"></a><span data-ttu-id="f1a56-149">Пример</span><span class="sxs-lookup"><span data-stu-id="f1a56-149">Example</span></span>

<span data-ttu-id="f1a56-150">В примере показан файл параметров приложения, который определяет два параметры приложения и двух параметров пользователя:</span><span class="sxs-lookup"><span data-stu-id="f1a56-150">The following example shows an application settings file that defines two application-scoped settings and two user-scoped settings:</span></span>

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
  <configSections>
    <sectionGroup name="applicationSettings" type="System.Configuration.ApplicationSettingsGroup, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">
      <section name="WindowsApplication1.Properties.Settings" type="System.Configuration.ClientSettingsSection, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />
    </sectionGroup>
    <sectionGroup name="userSettings" type="System.Configuration.UserSettingsGroup, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">
      <section name="WindowsApplication1.Properties.Settings" type="System.Configuration.ClientSettingsSection, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" allowExeDefinition="MachineToLocalUser" />
    </sectionGroup>
  </configSections>
  <applicationSettings>
    <WindowsApplication1.Properties.Settings>
      <setting name="Cursor" serializeAs="String">
        <value>Default</value>
      </setting>
      <setting name="DoubleBuffering" serializeAs="String">
        <value>False</value>
      </setting>
    </WindowsApplication1.Properties.Settings>
  </applicationSettings>
  <userSettings>
    <WindowsApplication1.Properties.Settings>
      <setting name="FormTitle" serializeAs="String">
        <value>Form1</value>
      </setting>
      <setting name="FormSize" serializeAs="String">
        <value>595, 536</value>
      </setting>
    </WindowsApplication1.Properties.Settings>
  </userSettings>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="f1a56-151">См. также</span><span class="sxs-lookup"><span data-stu-id="f1a56-151">See also</span></span>

<span data-ttu-id="f1a56-152">[Общие сведения о параметрах приложений](~/docs/framework/winforms/advanced/application-settings-overview.md) </span><span class="sxs-lookup"><span data-stu-id="f1a56-152">[Application Settings Overview](~/docs/framework/winforms/advanced/application-settings-overview.md) </span></span>  
[<span data-ttu-id="f1a56-153">Архитектура параметров приложения</span><span class="sxs-lookup"><span data-stu-id="f1a56-153">Application Settings Architecture</span></span>](~/docs/framework/winforms/advanced/application-settings-architecture.md)

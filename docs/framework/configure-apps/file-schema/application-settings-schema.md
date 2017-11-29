---
title: "Схема параметров приложения"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- schema application settings
- application settings, schema [Windows Forms]
- Windows Forms, application settings schema
- configuration schema [.NET Framework], application settings
ms.assetid: 5797fcff-6081-4e8c-bebf-63d9c70cf14b
caps.latest.revision: "3"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: d93a18b17e0d6b8e413903fb84dc6b427d94f6af
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="application-settings-schema"></a><span data-ttu-id="4072b-102">Схема параметров приложения</span><span class="sxs-lookup"><span data-stu-id="4072b-102">Application Settings schema</span></span>

<span data-ttu-id="4072b-103">Параметры приложений позволяют приложению Windows Forms или ASP.NET сохранять и извлекать параметры области приложения и пользователя.</span><span class="sxs-lookup"><span data-stu-id="4072b-103">Application settings allow a Windows Forms or ASP.NET application to store and retrieve application-scoped and user-scoped settings.</span></span> <span data-ttu-id="4072b-104">В этом контексте *параметр* является любая информация, которая конкретного приложения или только к текущему пользователю, что-либо из строки подключения к базе данных пользователю предпочитаемые размер окна по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="4072b-104">In this context, a *setting* is any piece of information that may be specific to the application or specific to the current user — anything from a database connection string to the user's preferred default window size.</span></span>

<span data-ttu-id="4072b-105">По умолчанию параметры приложения в приложении Windows Forms использует <xref:System.Configuration.LocalFileSettingsProvider> класс, который использует систему конфигурации .NET для хранения параметров в файл конфигурации XML.</span><span class="sxs-lookup"><span data-stu-id="4072b-105">By default, application settings in a Windows Forms application uses the <xref:System.Configuration.LocalFileSettingsProvider> class, which uses the .NET configuration system to store settings in an XML configuration file.</span></span> <span data-ttu-id="4072b-106">Дополнительные сведения о файлах, используемых параметрами приложения см. в разделе [архитектура параметров приложения](~/docs/framework/winforms/advanced/application-settings-architecture.md).</span><span class="sxs-lookup"><span data-stu-id="4072b-106">For more information about the files used by application settings, see [Application Settings Architecture](~/docs/framework/winforms/advanced/application-settings-architecture.md).</span></span>

<span data-ttu-id="4072b-107">Параметры приложения определяют следующие элементы как часть файлов конфигурации, используемые в нем.</span><span class="sxs-lookup"><span data-stu-id="4072b-107">Application settings defines the following elements as part of the configuration files it uses.</span></span>

| <span data-ttu-id="4072b-108">Элемент</span><span class="sxs-lookup"><span data-stu-id="4072b-108">Element</span></span>                    | <span data-ttu-id="4072b-109">Описание</span><span class="sxs-lookup"><span data-stu-id="4072b-109">Description</span></span>                                                                           |
| -------------------------- | ------------------------------------------------------------------------------------- |
| <span data-ttu-id="4072b-110">**\<applicationSettings >**</span><span class="sxs-lookup"><span data-stu-id="4072b-110">**\<applicationSettings>**</span></span> | <span data-ttu-id="4072b-111">Содержит все  **\<параметр >** теги, относящиеся к приложению.</span><span class="sxs-lookup"><span data-stu-id="4072b-111">Contains all **\<setting>** tags specific to the application.</span></span>                         |
| <span data-ttu-id="4072b-112">**\<userSettings >**</span><span class="sxs-lookup"><span data-stu-id="4072b-112">**\<userSettings>**</span></span>        | <span data-ttu-id="4072b-113">Содержит все  **\<параметр >** теги, относящиеся к текущему пользователю.</span><span class="sxs-lookup"><span data-stu-id="4072b-113">Contains all **\<setting>** tags specific to the current user.</span></span>                        |
| <span data-ttu-id="4072b-114">**\<параметр >**</span><span class="sxs-lookup"><span data-stu-id="4072b-114">**\<setting>**</span></span>             | <span data-ttu-id="4072b-115">Определяет параметр.</span><span class="sxs-lookup"><span data-stu-id="4072b-115">Defines a setting.</span></span> <span data-ttu-id="4072b-116">Дочерним для элемента  **\<applicationSettings >** или  **\<userSettings >**.</span><span class="sxs-lookup"><span data-stu-id="4072b-116">Child of either **\<applicationSettings>** or **\<userSettings>**.</span></span> |
| <span data-ttu-id="4072b-117">**\<value>**</span><span class="sxs-lookup"><span data-stu-id="4072b-117">**\<value>**</span></span>               | <span data-ttu-id="4072b-118">Определяет значение параметра.</span><span class="sxs-lookup"><span data-stu-id="4072b-118">Defines a setting's value.</span></span> <span data-ttu-id="4072b-119">Дочерний  **\<параметр >**.</span><span class="sxs-lookup"><span data-stu-id="4072b-119">Child of **\<setting>**.</span></span>                                   |

## <a name="applicationsettings-element"></a><span data-ttu-id="4072b-120">\<applicationSettings > элемент</span><span class="sxs-lookup"><span data-stu-id="4072b-120">\<applicationSettings> element</span></span>

<span data-ttu-id="4072b-121">Этот элемент содержит все  **\<параметр >** теги, относящиеся к экземпляру приложения на клиентском компьютере.</span><span class="sxs-lookup"><span data-stu-id="4072b-121">This element contains all **\<setting>** tags that are specific to an instance of the application on a client computer.</span></span> <span data-ttu-id="4072b-122">Атрибуты не определяются.</span><span class="sxs-lookup"><span data-stu-id="4072b-122">It defines no attributes.</span></span>

## <a name="usersettings-element"></a><span data-ttu-id="4072b-123">\<userSettings > элемент</span><span class="sxs-lookup"><span data-stu-id="4072b-123">\<userSettings> element</span></span>

<span data-ttu-id="4072b-124">Этот элемент содержит все  **\<параметр >** теги, относящиеся к пользователю, работающему с приложением.</span><span class="sxs-lookup"><span data-stu-id="4072b-124">This element contains all **\<setting>** tags that are specific to the user who is currently using the application.</span></span> <span data-ttu-id="4072b-125">Атрибуты не определяются.</span><span class="sxs-lookup"><span data-stu-id="4072b-125">It defines no attributes.</span></span>

## <a name="setting-element"></a><span data-ttu-id="4072b-126">\<Настройка > элемент</span><span class="sxs-lookup"><span data-stu-id="4072b-126">\<setting> element</span></span>

<span data-ttu-id="4072b-127">Этот элемент определяет параметр.</span><span class="sxs-lookup"><span data-stu-id="4072b-127">This element defines a setting.</span></span> <span data-ttu-id="4072b-128">Он имеет следующие атрибуты.</span><span class="sxs-lookup"><span data-stu-id="4072b-128">It has the following attributes.</span></span>

| <span data-ttu-id="4072b-129">Атрибут</span><span class="sxs-lookup"><span data-stu-id="4072b-129">Attribute</span></span>        | <span data-ttu-id="4072b-130">Описание</span><span class="sxs-lookup"><span data-stu-id="4072b-130">Description</span></span> |
| ---------------- | ----------- |
| <span data-ttu-id="4072b-131">**name**</span><span class="sxs-lookup"><span data-stu-id="4072b-131">**name**</span></span>         | <span data-ttu-id="4072b-132">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="4072b-132">Required.</span></span> <span data-ttu-id="4072b-133">Уникальный идентификатор параметра.</span><span class="sxs-lookup"><span data-stu-id="4072b-133">The unique ID of the setting.</span></span> <span data-ttu-id="4072b-134">Параметры, созданные с помощью Visual Studio сохраняются с именем `ProjectName.Properties.Settings`.</span><span class="sxs-lookup"><span data-stu-id="4072b-134">Settings created through Visual Studio are saved with the name `ProjectName.Properties.Settings`.</span></span> |
| <span data-ttu-id="4072b-135">**serializedAs**</span><span class="sxs-lookup"><span data-stu-id="4072b-135">**serializedAs**</span></span> | <span data-ttu-id="4072b-136">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="4072b-136">Required.</span></span> <span data-ttu-id="4072b-137">Формат, используемый для сериализации значения в текст.</span><span class="sxs-lookup"><span data-stu-id="4072b-137">The format to use for serializing the value to text.</span></span> <span data-ttu-id="4072b-138">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="4072b-138">Valid values are:</span></span><br><br><span data-ttu-id="4072b-139">- `string`.</span><span class="sxs-lookup"><span data-stu-id="4072b-139">- `string`.</span></span> <span data-ttu-id="4072b-140">Значение сериализуется как строки с помощью <xref:System.ComponentModel.TypeConverter>.</span><span class="sxs-lookup"><span data-stu-id="4072b-140">The value is serialized as a string using a <xref:System.ComponentModel.TypeConverter>.</span></span><br><span data-ttu-id="4072b-141">- `xml`.</span><span class="sxs-lookup"><span data-stu-id="4072b-141">- `xml`.</span></span> <span data-ttu-id="4072b-142">Значение сериализуется с использованием XML-сериализации.</span><span class="sxs-lookup"><span data-stu-id="4072b-142">The value is serialized using XML serialization.</span></span><br><span data-ttu-id="4072b-143">- `binary`.</span><span class="sxs-lookup"><span data-stu-id="4072b-143">- `binary`.</span></span> <span data-ttu-id="4072b-144">Значение сериализуется как текст в кодировке двоичного файла с использованием двоичной сериализации.</span><span class="sxs-lookup"><span data-stu-id="4072b-144">The value is serialized as text-encoded binary using binary serialization.</span></span><br /><span data-ttu-id="4072b-145">- `custom`.</span><span class="sxs-lookup"><span data-stu-id="4072b-145">- `custom`.</span></span> <span data-ttu-id="4072b-146">Поставщик параметров имеет встроенные сведения об этот параметр и сериализует и десериализует его.</span><span class="sxs-lookup"><span data-stu-id="4072b-146">The settings provider has inherent knowledge of this setting and serializes and de-serializes it.</span></span> |

## <a name="value-element"></a><span data-ttu-id="4072b-147">\<Значение > элемент</span><span class="sxs-lookup"><span data-stu-id="4072b-147">\<value> element</span></span>

<span data-ttu-id="4072b-148">Этот элемент содержит значение параметра.</span><span class="sxs-lookup"><span data-stu-id="4072b-148">This element contains the value of a setting.</span></span>

## <a name="example"></a><span data-ttu-id="4072b-149">Пример</span><span class="sxs-lookup"><span data-stu-id="4072b-149">Example</span></span>

<span data-ttu-id="4072b-150">Следующий пример показывает файл параметров приложения, который определяет два параметры приложения и двух параметров пользователя:</span><span class="sxs-lookup"><span data-stu-id="4072b-150">The following example shows an application settings file that defines two application-scoped settings and two user-scoped settings:</span></span>

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

## <a name="see-also"></a><span data-ttu-id="4072b-151">См. также</span><span class="sxs-lookup"><span data-stu-id="4072b-151">See also</span></span>

<span data-ttu-id="4072b-152">[Общие сведения о параметрах приложений](~/docs/framework/winforms/advanced/application-settings-overview.md) </span><span class="sxs-lookup"><span data-stu-id="4072b-152">[Application Settings Overview](~/docs/framework/winforms/advanced/application-settings-overview.md) </span></span>  
[<span data-ttu-id="4072b-153">Архитектура параметров приложения</span><span class="sxs-lookup"><span data-stu-id="4072b-153">Application Settings Architecture</span></span>](~/docs/framework/winforms/advanced/application-settings-architecture.md)

---
title: Упаковка и развертывание пользовательских расширений My
ms.date: 08/14/2018
helpviewer_keywords:
- My namespace [Visual Basic], customizing
- My namespace
- My namespace [Visual Basic], extending
ms.assetid: fd89c54b-0290-4c50-95a3-ff17d4487a21
ms.openlocfilehash: a2e2a6705fb3d8d4424d46d96bbf49b41e1414af
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74330263"
---
# <a name="package-and-deploy-custom-my-extensions-visual-basic"></a>Упаковка и развертывание пользовательских расширений My (Visual Basic)

Visual Basic предоставляет простой способ развертывания расширений пользовательского пространства имен `My` с помощью шаблонов Visual Studio. При создании шаблона проекта, для которого расширения `My` являются неотъемлемой частью нового типа проекта, при экспорте шаблона можно просто включить пользовательский код расширения `My` в проект. Дополнительные сведения об экспорте шаблонов проектов см. [в разделе инструкции. Создание шаблонов проектов](/visualstudio/ide/how-to-create-project-templates).

Если расширение Custom `My` находится в одном файле кода, можно экспортировать файл как шаблон элемента, который пользователи могут добавлять в любой тип Visual Basic проекта. Затем можно настроить шаблон элемента, чтобы включить дополнительные возможности и поведение для пользовательского расширения `My` в проекте Visual Basic. К этим возможностям относятся следующие.

- Предоставление пользователям возможности управлять пользовательским расширением `My` на странице " **Мои расширения** " в конструкторе проектов Visual Basic.

- Автоматическое добавление пользовательского расширения `My` при добавлении ссылки на указанную сборку в проект.

- Скрытие шаблона элемента расширения `My` в диалоговом окне **Добавление элемента** , чтобы он не включался в список элементов проекта.

В этом разделе описывается упаковка пользовательского расширения `My` в качестве скрытого шаблона элемента, который можно управлять со страницы **Мои расширения** в конструкторе проектов Visual Basic. Расширение настраиваемого `My` также может быть добавлено автоматически при добавлении ссылки на указанную сборку в проект.

## <a name="create-a-my-namespace-extension"></a>Создание расширения пространства имен My

Первым шагом в создании пакета развертывания для пользовательского расширения `My` является создание расширения в виде одного файла кода. Дополнительные сведения и рекомендации по созданию пользовательского расширения `My` см. [в разделе расширение пространства имен My в Visual Basic](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-my-namespace.md).

## <a name="export-a-my-namespace-extension-as-an-item-template"></a>Экспорт расширения пространства имен My в качестве шаблона элемента

После создания файла кода, содержащего расширение пространства имен `My`, можно экспортировать файл кода в качестве шаблона элемента Visual Studio. Инструкции по экспорту файла в качестве шаблона элемента Visual Studio см. [в разделе инструкции. Создание шаблонов элементов](/visualstudio/ide/how-to-create-item-templates).

> [!NOTE]
> Если расширение пространства имен `My` зависит от конкретной сборки, можно настроить шаблон элемента для автоматической установки расширения пространства имен `My` при добавлении ссылки на эту сборку. В результате вы хотите исключить эту ссылку на сборку при экспорте файла кода в качестве шаблона элемента Visual Studio.

## <a name="customize-the-item-template"></a>Настройка шаблона элемента

Вы можете включить управление шаблоном элемента со страницы **My Extensions (Мои расширения** ) в конструкторе проектов Visual Basic. Можно также включить автоматическое добавление шаблона элемента при добавлении в проект ссылки на указанную сборку. Чтобы включить эти настройки, добавьте в шаблон новый файл, который называется файлом CustomData, а затем добавьте новый элемент в XML-файл в файле VSTEMPLATE.

### <a name="add-the-customdata-file"></a>Добавление файла CustomData

Файл CustomData — это текстовый файл с расширением имени файла. CustomData (для имени файла можно задать любое значение, значимое для шаблона) и содержащее XML. XML-код в файле CustomData указывает Visual Basic включить расширение `My`, когда пользователи используют страницу **Мои расширения** конструктора проектов Visual Basic. При необходимости можно добавить атрибут <`AssemblyFullName>` в XML-файл CustomData. Это указывает Visual Basic автоматически установить расширение пользовательского `My` при добавлении в проект ссылки на определенную сборку. Для создания файла CustomData можно использовать любой текстовый редактор или редактор XML, а затем добавить его в сжатую папку (ZIP-файл) шаблона элемента.

Например, в следующем XML-коде показано содержимое файла CustomData, который добавит элемент шаблона в папку My Extensions проекта Visual Basic, когда в проект будет добавлена ссылка на сборку Microsoft. VisualBasic. PowerPacks. vs. dll.

```xml
<VBMyExtensionTemplate
    ID="Microsoft.VisualBasic.Samples.MyExtensions.MyPrinterInfo"
    Version="1.0.0.0"
    AssemblyFullName="Microsoft.VisualBasic.PowerPacks.vs"
/>
```

Файл CustomData содержит элемент <`VBMyExtensionTemplate>`, имеющий атрибуты, перечисленные в следующей таблице.

|Атрибут|Описание|
|---|---|
|`ID`|Обязательно. Уникальный идентификатор для расширения. Если расширение с таким ИДЕНТИФИКАТОРом уже было добавлено в проект, пользователю не будет предложено добавить его снова.|
|`Version`|Обязательно. Номер версии для шаблона элемента.|
|`AssemblyFullName`|Необязательный элемент. Имя сборки. При добавлении ссылки на эту сборку в проект пользователю будет предложено добавить расширение `My` из этого шаблона элемента.|

### <a name="add-the-customdatasignature-element-to-the-vstemplate-file"></a>Добавление элемента \<Кустомдатасигнатуре > в файл VSTEMPLATE

Чтобы найти шаблон элемента Visual Studio в качестве расширения пространства имен `My`, необходимо также изменить VSTEMPLATE-файл для шаблона элемента. Необходимо добавить элемент `<CustomDataSignature>` в элемент `<TemplateData>`. Элемент `<CustomDataSignature>` должен содержать текст `Microsoft.VisualBasic.MyExtension`, как показано в следующем примере.

```xml
<CustomDataSignature>Microsoft.VisualBasic.MyExtension</CustomDataSignature>
```

Нельзя изменять файлы в сжатой папке (ZIP-файле) напрямую. Необходимо скопировать VSTEMPLATE файл из сжатой папки, изменить его, а затем заменить файл VSTEMPLATE в сжатой папке обновленной копией.

В следующем примере показано содержимое VSTEMPLATE-файла, в котором добавлен элемент `<CustomDataSignature>`.

```xml
<VSTemplate Version="2.0.0" xmlns="http://schemas.microsoft.com/developer/vstemplate/2005" Type="Item">
  <TemplateData>
    <DefaultName>MyCustomExtensionModule.vb</DefaultName>
    <Name>MyPrinterInfo</Name>
    <Description>Custom My Extensions Item Template</Description>
    <ProjectType>VisualBasic</ProjectType>
    <SortOrder>10</SortOrder>
    <Icon>__TemplateIcon.ico</Icon>
    <CustomDataSignature      >Microsoft.VisualBasic.MyExtension</CustomDataSignature>
  </TemplateData>
  <TemplateContent>
    <References />
    <ProjectItem SubType="Code"
                 TargetFileName="$fileinputname$.vb"
                 ReplaceParameters="true"
     >MyCustomExtensionModule.vb</ProjectItem>
  </TemplateContent>
</VSTemplate>
```

## <a name="install-the-template"></a>Установка шаблона

Чтобы установить шаблон, можно скопировать сжатую папку (*ZIP* -файл) в папку шаблонов элементов Visual Basic. По умолчанию шаблоны элементов пользователей находятся в *%UserProfile%\Documents\Visual Studio \<версии\>\Темплатес\итемтемплатес\висуал Basic*. Кроме того, шаблон можно опубликовать в виде файла Visual Studio Installer (*VSI*).

## <a name="see-also"></a>См. также

- [Расширение пространства имен My в Visual Basic](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-my-namespace.md)
- [Расширение модели приложения Visual Basic](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-visual-basic-application-model.md)
- [Настройка доступа к объектам через My](../../../visual-basic/developing-apps/customizing-extending-my/customizing-which-objects-are-available-in-my.md)
- [Страница "Мои расширения", конструктор проектов](/visualstudio/ide/reference/my-extensions-page-project-designer-visual-basic)

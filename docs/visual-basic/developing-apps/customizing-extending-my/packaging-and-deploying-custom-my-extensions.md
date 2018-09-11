---
title: Упаковка и развертывание пользовательских расширений пространства имен My (Visual Basic)
ms.date: 08/14/2018
helpviewer_keywords:
- My namespace [Visual Basic], customizing
- My namespace
- My namespace [Visual Basic], extending
ms.assetid: fd89c54b-0290-4c50-95a3-ff17d4487a21
ms.openlocfilehash: 4212f58c39f63be6ba20c3b79e5d9c98d0615c5e
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2018
ms.locfileid: "44271131"
---
# <a name="package-and-deploy-custom-my-extensions-visual-basic"></a>Упаковка и развертывание пользовательских расширений пространства имен My (Visual Basic)

Visual Basic предоставляет простой способ развертывания пользовательских `My` расширения пространства имен с помощью шаблонов Visual Studio. Если вы создаете шаблон проекта, для которого ваши `My` расширения являются неотъемлемой частью нового типа проекта, можно просто включить пользовательский `My` код расширения в проект при экспорте шаблона. Дополнительные сведения об экспорте шаблонов проектов см. в разделе [как: создание шаблонов проектов](/visualstudio/ide/how-to-create-project-templates).

Если пользовательский `My` расширения в одном файле кода, можно экспортировать файл в качестве шаблона элемента, который пользователи могут добавлять в любой тип проекта Visual Basic. Затем можно настроить шаблон элемента для включения дополнительных возможностей и поведения пользовательского `My` расширения в проекте Visual Basic. Эти возможности включают следующее:

- Возможность управления пользовательским `My` расширения из **Мои расширения** страницы в конструкторе проектов Visual Basic.

- Автоматического добавления пользовательского `My` в проект добавляется расширение при ссылку к указанной сборке.

- Скрытие `My` шаблона элемента расширения в **Добавление элемента** диалоговое окно, чтобы он не включен в список элементов проекта.

В этом разделе рассматривается упаковка пользовательского `My` расширения в качестве шаблона скрытый элемент, которыми можно управлять из **Мои расширения** страницы в конструкторе проектов Visual Basic. Пользовательский `My` расширения можно также добавлять автоматически при добавлении в проект ссылку на указанную сборку.

## <a name="create-a-my-namespace-extension"></a>Создание расширения пространства имен My

Первым шагом создания пакета развертывания для настраиваемого `My` расширения заключается в создании расширения в виде одного файла кода. Дополнительные сведения и рекомендации о том, как создавать пользовательские `My` расширения, см. в разделе [расширение пространства имен My в Visual Basic](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-my-namespace.md).

## <a name="export-a-my-namespace-extension-as-an-item-template"></a>Экспорт расширение My namespace как шаблон элемента

После того как файл кода, который содержит ваши `My` расширение пространства имен, можно экспортировать в файл кода как шаблона элемента Visual Studio. Инструкции по экспорту файла в качестве шаблона элемента Visual Studio, см. в разделе [как: создание шаблонов элементов](/visualstudio/ide/how-to-create-item-templates).

> [!NOTE]
> Если ваш `My` расширение пространства имен имеет зависимость от определенной сборки, можно настроить шаблон элемента для автоматической установки вашего `My` расширение пространства имен при добавлении ссылки на эту сборку. Таким образом вы хотите исключить ссылку на данную сборку при экспорте в файл кода в виде шаблона элемента Visual Studio.

## <a name="customize-the-item-template"></a>Настроить шаблон элемента

Вы можете включить шаблон элемента осуществляется из **Мои расширения** страницы в конструкторе проектов Visual Basic. Кроме того, вы можете включить шаблона элемента для добавляться автоматически при добавлении в проект ссылку на указанную сборку. Чтобы включить эти настройки, будет добавьте новый файл с именем CustomData, к шаблону и затем добавьте новый элемент в XML-документ в файле .vstemplate.

### <a name="add-the-customdata-file"></a>Добавьте файл CustomData

Файл CustomData — это текстовый файл, имеющий расширение имени файла. CustomData (имя файла может быть присвоено любое значение значимые в шаблон), которая содержит XML. XML в файле CustomData сообщает Visual Basic для включения в `My` расширение, когда пользователи применяют **Мои расширения** страницы в конструкторе проектов Visual Basic. При необходимости можно добавить <`AssemblyFullName>` атрибута в файл CustomData XML. Это указывает, что Visual Basic для автоматической установки пользовательских `My` расширение, когда ссылка на определенную сборку добавляется в проект. Можно использовать любой текстовый редактор или редактор XML для создания файла CustomData и затем добавить его в шаблон элемента сжатую папку (ZIP-файл).

Например следующий код XML показано содержимое файла CustomData, добавляющий элемент шаблона в папку My Extensions проекта Visual Basic, когда ссылка на сборку Microsoft.VisualBasic.PowerPacks.Vs.dll добавляется в проект.

```xml
<VBMyExtensionTemplate
    ID="Microsoft.VisualBasic.Samples.MyExtensions.MyPrinterInfo"
    Version="1.0.0.0"
    AssemblyFullName="Microsoft.VisualBasic.PowerPacks.vs"
/>
```

Файл CustomData содержит <`VBMyExtensionTemplate>` элемент, имеющий атрибуты, перечисленные в следующей таблице.

|Атрибут|Описание|
|---|---|
|`ID`|Обязательно. Уникальный идентификатор для расширения. Если расширение, которое имеет этот идентификатор уже был добавлен в проект, он будет не предложено добавить его снова.|
|`Version`|Обязательно. Номер версии для шаблона элемента.|
|`AssemblyFullName`|Необязательный. Имя сборки. При добавлении в проект ссылку на эту сборку, пользователю будет предложено добавить `My` расширения на основе этого шаблона элемента.|

### <a name="add-the-customdatasignature-element-to-the-vstemplate-file"></a>Добавить \<CustomDataSignature > элемент VSTEMPLATE-файл

Для идентификации элемента шаблона Visual Studio как `My` расширение пространства имен, необходимо также изменить файл VSTEMPLATE для шаблона элемента. Необходимо добавить `<CustomDataSignature>` элемент `<TemplateData>` элемент. `<CustomDataSignature>` Элемент должен содержать текст `Microsoft.VisualBasic.MyExtension`, как показано в следующем примере.

```xml
<CustomDataSignature>Microsoft.VisualBasic.MyExtension</CustomDataSignature>
```

Нельзя напрямую изменять файлы в сжатую папку (ZIP-файл). Необходимо скопировать файл VSTEMPLATE из сжатой папки, измените его и затем заменить файл VSTEMPLATE в сжатой папке обновленной версией.

В следующем примере показано содержимое VSTEMPLATE-файл, имеющий `<CustomDataSignature>` добавлен указанный элемент.

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

Чтобы установить шаблон, можно скопировать сжатую папку (*ZIP-файл* файл) в папку Шаблоны элементов Visual Basic. По умолчанию, пользовательских шаблонов элементов находятся в *%USERPROFILE%\Documents\Visual Studio \<версии\>\Templates\ItemTemplates\Visual Basic*. Кроме того, можно опубликовать шаблон, как Visual Studio Installer (*.vsi*) файла.

## <a name="see-also"></a>См. также

- [Расширение пространства имен My в Visual Basic](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-my-namespace.md)
- [Расширение модели приложения Visual Basic](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-visual-basic-application-model.md)
- [Настройка доступа к объектам через My](../../../visual-basic/developing-apps/customizing-extending-my/customizing-which-objects-are-available-in-my.md)
- [Страница "Мои расширения", конструктор проектов](/visualstudio/ide/reference/my-extensions-page-project-designer-visual-basic)

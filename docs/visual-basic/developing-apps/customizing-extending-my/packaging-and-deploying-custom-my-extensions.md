---
title: "Упаковка и развертывание пользовательских расширений пространства имен My (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- My namespace [Visual Basic], customizing
- My namespace
- My namespace [Visual Basic], extending
ms.assetid: fd89c54b-0290-4c50-95a3-ff17d4487a21
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 94a9ea977d0add14ae9f0c9a889b008b94610ee0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="packaging-and-deploying-custom-my-extensions-visual-basic"></a>Упаковка и развертывание пользовательских расширений пространства имен My (Visual Basic)
Visual Basic предоставляет удобный способ развертывания пользовательских `My` расширений пространства имен с помощью шаблонов Visual Studio. Если вы создаете шаблон проекта, для которого вашей `My` расширения являются неотъемлемой частью, можно просто включить пользовательский `My` расширение кода в проект при экспорте шаблона. Дополнительные сведения об экспорте шаблонов проекта см. в разделе [как: создание шаблонов проектов](/visualstudio/ide/how-to-create-project-templates).  
  
 Если пользовательский `My` расширения в одном файле кода, можно экспортировать файл в качестве шаблона элемента, который пользователи могут добавлять в любой тип проекта Visual Basic. Затем можно настроить шаблон элемента для включения дополнительных возможностей и поведения пользовательского `My` расширения в проекте Visual Basic. Эти возможности включают следующее:  
  
-   Возможность управления пользовательским `My` расширения из **Мои расширения** страницы конструктора проектов Visual Basic.  
  
-   Автоматического добавления пользовательского `My` в проект добавляется расширение при передаче ссылки на указанную сборку.  
  
-   Скрытие `My` шаблона элемента расширения в **добавить элемент** диалоговое окно, чтобы он не включен в список элементов проекта.  
  
 В этом разделе описывается, как упаковка пользовательского `My` расширения в качестве скрытого шаблона элемента, можно управлять из **Мои расширения** страницы конструктора проектов Visual Basic. Пользовательский `My` расширения можно также добавлять автоматически при добавлении ссылки на указанную сборку в проект.  
  
## <a name="create-a-my-namespace-extension"></a>Создайте расширение My namespace  
 Первым шагом при создании пакета развертывания для пользовательского `My` расширения является создание расширения в виде одного файла кода. Дополнительные сведения и рекомендации о том, как создать настраиваемый `My` расширения, в разделе [расширение My Namespace в Visual Basic](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-my-namespace.md).  
  
## <a name="export-a-my-namespace-extension-as-an-item-template"></a>Экспорт расширения пространства имен My в качестве шаблона элемента  
 После того как файл кода, который содержит ваш `My` расширение пространства имен, можно экспортировать в файл кода в качестве шаблона элемента Visual Studio. Инструкции по экспорту файла в качестве шаблона элемента Visual Studio см. в разделе [как: создание шаблонов элементов](/visualstudio/ide/how-to-create-item-templates).  
  
> [!NOTE]
>  Если ваш `My` расширение пространства имен имеет зависимость от определенной сборки, можно настроить шаблон элемента на автоматическую установку вашей `My` расширение пространства имен при добавлении ссылки на эту сборку. В результате может потребоваться исключить ссылку на данную сборку при экспорте в файл кода в виде шаблона элемента Visual Studio.  
  
## <a name="customize-the-item-template"></a>Настроить шаблон элемента  
 Можно включить шаблоном элемента осуществляется из **Мои расширения** страницы конструктора проектов Visual Basic. Можно также включить шаблона элемента для добавления автоматически при добавлении ссылки на указанную сборку в проект. Чтобы включить эти настройки, будет добавьте новый файл с именем CustomData, к шаблону и затем добавьте новый элемент в XML-документ в файле .vstemplate.  
  
### <a name="add-the-customdata-file"></a>Добавьте файл CustomData  
 CustomData файла является текстовый файл, который имеет расширение имени файла. CustomData (имя файла может быть присвоено любое значение может применяться в шаблоне), которая содержит XML. XML в файле CustomData сообщает Visual Basic для включения вашей `My` расширение, если пользователи используют **Мои расширения** страницы конструктора проектов Visual Basic. При необходимости можно добавлять <`AssemblyFullName>` в файл CustomData XML. Это указывает, что Visual Basic, чтобы автоматически установить пользовательскую `My` расширение, когда ссылка на определенную сборку добавляется в проект. Можно использовать любой текстовый редактор или редактор XML для создания файла CustomData и затем добавить его в шаблон элемента сжатую папку (ZIP-файл).  
  
 Например следующий XML показано содержимое файла CustomData, будет добавлен элемент шаблона в папку "Мои расширения" проекта Visual Basic, когда ссылка на сборку Microsoft.VisualBasic.PowerPacks.Vs.dll добавляется в проект.  
  
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
|`ID`|Обязательный. Уникальный идентификатор расширения. Если расширение, имеющее этот идентификатор уже был добавлен в проект, пользователь будет приглашение не добавить его еще раз.|  
|`Version`|Обязательный. Номер версии для шаблона элемента.|  
|`AssemblyFullName`|Необязательно. Имя сборки. При добавлении в проект ссылку на эту сборку пользователю будет предложено добавить `My` расширения на основе этого шаблона элемента.|  
  
### <a name="add-the-customdatasignature-element-to-the-vstemplate-file"></a>Добавить \<CustomDataSignature > элемент VSTEMPLATE-файлу  
 Для идентификации элемента шаблона Visual Studio как `My` расширение пространства имен, необходимо также изменить файл VSTEMPLATE для шаблона элемента. Необходимо добавить `<CustomDataSignature>` элемента `<TemplateData>` элемент. `<CustomDataSignature>` Элемент должен содержать текст `Microsoft.VisualBasic.MyExtension`, как показано в следующем примере.  
  
```xml  
<CustomDataSignature>Microsoft.VisualBasic.MyExtension</CustomDataSignature>  
```  
  
 Нельзя непосредственно изменять файлы в сжатую папку (ZIP-файл). Необходимо скопировать файл VSTEMPLATE из сжатой папки, изменить его и затем заменить файл VSTEMPLATE в сжатой папке обновленной версией.  
  
 В следующем примере показано содержимое VSTEMPLATE-файл, который имеет `<CustomDataSignature>` добавлен элемент.  
  
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
 Для установки шаблона, шаблоны элементов Visual Basic папку (например, Мои документы\Visual Studio 2008\Templates\Item Templates\Visual Basic) можно скопировать сжатой папки (ZIP-файл). Кроме того можно опубликовать шаблон в файл установщика Visual Studio (VSI).  
  
## <a name="see-also"></a>См. также  
 [Расширение пространства имен My в Visual Basic](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-my-namespace.md)  
 [Расширение модели приложения Visual Basic](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-visual-basic-application-model.md)  
 [Настройка доступа к объектам через My](../../../visual-basic/developing-apps/customizing-extending-my/customizing-which-objects-are-available-in-my.md)  
 [Страница "Мои расширения" Конструктор проектов](/visualstudio/ide/reference/my-extensions-page-project-designer-visual-basic)

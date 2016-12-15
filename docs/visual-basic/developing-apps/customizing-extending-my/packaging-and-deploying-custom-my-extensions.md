---
title: "Упаковка и развертывание пользовательских расширений пространства имен My (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "My - пространство имен"
  - "My - пространство имен, настройка"
  - "My - пространство имен, расширение"
ms.assetid: fd89c54b-0290-4c50-95a3-ff17d4487a21
caps.latest.revision: 10
caps.handback.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Упаковка и развертывание пользовательских расширений пространства имен My (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Visual Basic предоставляет удобный способ развертывания пользовательских расширений пространства имен `My` с помощью шаблонов Visual Studio.  Если вы создаете шаблон проекта, составной частью которого являются расширения пространства имен `My`, достаточно включить пользовательский код расширения `My` в проект при экспорте шаблона.  Дополнительные сведения об экспорте шаблонов проекта см. в разделе [Практическое руководство. Создание шаблонов проектов](../Topic/How%20to:%20Create%20Project%20Templates.md).  
  
 Если пользовательское расширение `My` находится в одном файле кода, можно экспортировать этот файл как шаблон элемента, который пользователи затем смогут добавлять в любой тип проектов Visual Basic.  Затем можно настроить шаблон элемента для включения дополнительных возможностей и поведения пользовательского расширения `My` в проекте Visual Basic.  Эти возможности включают следующее:  
  
-   Возможность управления пользовательским расширением `My` со страницы **Мои расширения** в конструкторе проектов Visual Basic.  
  
-   Возможность автоматического добавления пользовательского расширения `My` при добавлении в проект ссылки на указанную сборку.  
  
-   Возможность скрытия шаблона элемента расширения `My` в диалоговом окне **Добавление элемента**, чтобы он не включался в список элементов проекта.  
  
 В этом разделе рассматривается упаковка пользовательского расширения `My` в качестве скрытого шаблона элемента, которым можно управлять со страницы **Мои расширения** в конструкторе проектов Visual Basic.  Пользовательское расширение `My` можно также добавлять автоматически при добавлении в проект ссылки на указанную сборку.  
  
## Создание расширения пространства имен My  
 Первый шаг в создании пакета развертывания для пользовательского расширения пространства имен `My` — создание расширения в виде одного файла кода.  Подробные сведения и руководство по созданию пользовательского расширения пространства имен `My` см. в разделе [Расширение пространства имен My в Visual Basic](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-my-namespace.md).  
  
## Экспорт расширения пространства имен My в качестве шаблона элемента  
 После получения файла с кодом, содержащего расширение пространства имен `My`, можно экспортировать файл с кодом в качестве шаблона элемента Visual Studio.  Инструкции по экспорту файла в качестве шаблона элемента Visual Studio см. в разделе [Практическое руководство. Создание шаблонов элементов](../Topic/How%20to:%20Create%20Item%20Templates.md).  
  
> [!NOTE]
>  Если расширение пространства имен `My` имеет зависимость от определенной сборки, можно настроить шаблон элемента на автоматическую установку расширения пространства имен `My` при добавлении ссылки на эту сборку.  В результате можно будет исключить ссылку на данную сборку при экспорте файла с кодом в качестве шаблона элемента Visual Studio.  
  
## Настройка шаблона элемента  
 Можно включить возможность управления шаблоном элемента на странице **Мои расширения** в конструкторе проектов Visual Basic.  Можно также включить автоматическое добавление шаблона элемента при добавлении в проект ссылки на указанную сборку.  Чтобы включить эти настройки, нужно добавить к шаблону новый файл с именем CustomData, а затем добавить новый элемент в XML\-код в файле с расширением VSTEMPLATE.  
  
### Добавление файла CustomData  
 Файл CustomData — это текстовый с расширением CUSTOMDATA \(имя файла может быть любое по смыслу шаблона\), содержащий XML.  XML в файле CustomData сообщает Visual Basic о необходимости включить пользовательское расширение `My` при использовании страницы **Мои расширения** страницы в конструкторе проектов Visual Basic.  При необходимости в XML\-код в файле CustomData можно добавить атрибут `AssemblyFullName>`.  Тем Visual Basic дается команда на автоматическую установку пользовательского расширения `My` при добавлении в проект ссылки на определенную сборку.  Можно использовать любой текстовый редактор или XML\-редактор для создания файла CustomData, а затем добавить его в сжатую папку \(ZIP\-файл\) элемента шаблона.  
  
 Например, следующий XML\-код представляет собой содержимое файла CustomData, добавляющего шаблон элемента в папку My Extensions проекта Visual Basic при добавлении в проект ссылки на сборку Microsoft.VisualBasic.PowerPacks.VS.dll.  
  
```  
<VBMyExtensionTemplate   
    ID="Microsoft.VisualBasic.Samples.MyExtensions.MyPrinterInfo"   
    Version="1.0.0.0"  
    AssemblyFullName="Microsoft.VisualBasic.PowerPacks.vs"  
/>  
```  
  
 Файл CustomData содержит элемент `VBMyExtensionTemplate>`, имеющий атрибуты, перечисленные в следующей таблице.  
  
|||  
|-|-|  
|Атрибут|Описание|  
|`ID`|Обязательный.  Уникальный идентификатор расширения.  Если расширение, имеющее этот идентификатор, уже было добавлено в проект, то пользователю не будет предложено добавить его снова.|  
|`Version`|Обязательный.  Номер версии для шаблона элемента.|  
|`AssemblyFullName`|Необязательный.  Имя сборки.  При добавлении в проект ссылки на эту сборку пользователю будет предложено добавить расширение `My` из данного шаблона элемента.|  
  
### Добавление элемента \<CustomDataSignature\> в файл VSTEMPLATE  
 Для идентификации элемента шаблона Visual Studio как расширения пространства имен `My` необходимо также изменить файл VSTEMPLATE для шаблона элемента.  Необходимо добавить элемент `<CustomDataSignature>` в элемент `<TemplateData>`.  Элемент `<CustomDataSignature>` должен содержать текст `Microsoft.VisualBasic.MyExtension`, как показано в следующем примере.  
  
```  
<CustomDataSignature>Microsoft.VisualBasic.MyExtension</CustomDataSignature>  
```  
  
 Нельзя изменять файлы в сжатой папке \(ZIP\-файл\) непосредственно.  Необходимо скопировать файл VSTEMPLATE из сжатой папки, изменить его и затем заменить файл VSTEMPLATE в сжатой папке обновленной версией.  
  
 В следующем примере показано содержимое файла VSTEMPLATE, в который был добавлен элемент `<CustomDataSignature>`.  
  
```  
<VSTemplate Version="2.0.0" xmlns="http://schemas.microsoft.com/developer/vstemplate/2005" Type="Item">  
  <TemplateData>  
    <DefaultName>MyCustomExtensionModule.vb</DefaultName>  
    <Name>MyPrinterInfo</Name>  
    <Description>Custom My Extensions Item Template</Description>  
    <ProjectType>VisualBasic</ProjectType>  
    <SortOrder>10</SortOrder>  
    <Icon>__TemplateIcon.ico</Icon>  
    <CustomDataSignature       >Microsoft.VisualBasic.MyExtension</CustomDataSignature>  
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
  
## Установка шаблона  
 Чтобы установить шаблон, можно скопировать сжатую папку \(ZIP\-файл\) в папку с элементами шаблона Visual Basic \(например, My Documents\\Visual Studio 2008\\Templates\\Item Templates\\Visual Basic\).  Вместо этого, можно опубликовать шаблон в виде файла установщика Visual Studio \(расширение VSI\).  Сведения о публикации шаблонов в виде файла установщика Visual Studio см. в разделе [NIB: How to: Publish Project Templates](http://msdn.microsoft.com/ru-ru/b9087f58-64e9-4767-bf54-e3bf40d63b20).  
  
## См. также  
 [Расширение пространства имен My в Visual Basic](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-my-namespace.md)   
 [Расширение модели приложения Visual Basic](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-visual-basic-application-model.md)   
 [Настройка доступа к объектам через My](../../../visual-basic/developing-apps/customizing-extending-my/customizing-which-objects-are-available-in-my.md)   
 [Страница "Мои расширения", конструктор проектов](/visual-studio/ide/reference/my-extensions-page-project-designer-visual-basic)
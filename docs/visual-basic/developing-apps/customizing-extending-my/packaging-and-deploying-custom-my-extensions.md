---
title: "Упаковка и развертывание пользовательских расширений пространства имен My (Visual Basic) | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- My namespace, customizing
- My namespace
- My namespace, extending
ms.assetid: fd89c54b-0290-4c50-95a3-ff17d4487a21
caps.latest.revision: 10
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 950592c0fb197959ce1c3cf6128093846a022709
ms.lasthandoff: 03/13/2017

---
# <a name="packaging-and-deploying-custom-my-extensions-visual-basic"></a>Упаковка и развертывание пользовательских расширений пространства имен My (Visual Basic)
Visual Basic предоставляет удобный способ развертывания пользовательских `My` расширения пространства имен с помощью шаблонов Visual Studio. Если вы создаете шаблон проекта, для которого вашей `My` расширения являются неотъемлемой частью, достаточно включить пользовательский `My` расширение кода в проект при экспорте шаблона. Дополнительные сведения об экспорте шаблонов проекта см. в разделе [Практическое руководство: создание шаблонов проекта](http://msdn.microsoft.com/library/a1a6999d-a34c-48a8-b1cf-027eb5c76398).  
  
 Если пользовательский `My` расширения в одном файле кода, можно экспортировать файл как шаблон элемента, который пользователи могут добавлять в любой тип проектов Visual Basic. Затем можно настроить шаблон элемента для включения дополнительных возможностей и поведения пользовательского `My` расширения в проекте Visual Basic. Эти возможности включают следующее:  
  
-   Возможность управления пользовательским `My` расширения из **Мои расширения** страницы в конструкторе проектов Visual Basic.  
  
-   Автоматическое добавление пользовательских `My` в проект добавляется расширение, когда ссылка на указанную сборку.  
  
-   Скрытие `My` шаблона элемента расширения в **добавить элемент** диалоговое окно, чтобы он не включен в список элементов проекта.  
  
 В этом разделе рассматривается упаковка пользовательского `My` расширения в качестве скрытого шаблона элемента, можно управлять из **Мои расширения** страницы в конструкторе проектов Visual Basic. Пользовательская `My` расширения можно также добавлять автоматически при добавлении в проект ссылки на указанную сборку.  
  
## <a name="create-a-my-namespace-extension"></a>Создание расширения пространства имен My  
 Первым шагом в создании пакета развертывания для пользовательского `My` расширения является создание расширения в виде одного файла кода. Дополнительные сведения и инструкции о том, как создать настраиваемый `My` расширения, в разделе [расширение пространства имен My в Visual Basic](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-my-namespace.md).  
  
## <a name="export-a-my-namespace-extension-as-an-item-template"></a>Экспорт расширения пространства имен My в качестве шаблона элемента  
 После добавления в файл кода, содержащий ваш `My` расширение пространства имен, можно экспортировать файл с кодом в качестве шаблона элемента Visual Studio. Инструкции по экспорту файла в качестве шаблона элемента Visual Studio см. в разделе [Практическое руководство: создание шаблонов элементов](http://msdn.microsoft.com/library/77bc53d4-d607-4820-a032-7e3b365891b5).  
  
> [!NOTE]
>  Если ваш `My` расширение пространства имен имеет зависимость от определенной сборки, можно настроить шаблон элемента на автоматическую установку вашего `My` расширение пространства имен при добавлении ссылки на эту сборку. В результате вы хотите исключить ссылку на данную сборку при экспорте в файл кода в виде шаблона элемента Visual Studio.  
  
## <a name="customize-the-item-template"></a>Настройка шаблона элемента  
 Можно включить шаблоном элемента управления из **Мои расширения** страницы в конструкторе проектов Visual Basic. Можно также включить шаблон элемента добавляется автоматически при добавлении в проект ссылки на указанную сборку. Чтобы включить эти настройки, будут добавьте новый файл с именем CustomData, к шаблону и затем добавьте новый элемент в XML-код в файле .vstemplate.  
  
### <a name="add-the-customdata-file"></a>Добавьте файл CustomData  
 Файл CustomData — текстовый файл, который имеет расширение имени файла. CustomData (имя файла может быть присвоено любое значение может применяться в шаблоне), которая содержит XML. XML в файле CustomData сообщает Visual Basic для включения вашего `My` расширение при использовании **Мои расширения** страницы в конструкторе проектов Visual Basic. При необходимости можно добавить `AssemblyFullName>` в файл CustomData XML. Это указывает, что Visual Basic на автоматическую установку пользовательского `My` при получении ссылки на определенную сборку расширения добавляется в проект. Можно использовать любой текстовый редактор или редактор XML для создания файла CustomData и затем добавить в шаблон элемента сжатую папку (ZIP-файл).  
  
 Например следующий код XML показывает содержимое файла CustomData, который добавляет элемент шаблона в папку Мои расширения проекта Visual Basic, когда ссылка на сборку Microsoft.VisualBasic.PowerPacks.Vs.dll добавляется в проект.  
  
```  
<VBMyExtensionTemplate   
    ID="Microsoft.VisualBasic.Samples.MyExtensions.MyPrinterInfo"   
    Version="1.0.0.0"  
    AssemblyFullName="Microsoft.VisualBasic.PowerPacks.vs"  
/>  
```  
  
 Файл CustomData содержит `VBMyExtensionTemplate>` элемент, имеющий атрибуты, перечисленные в следующей таблице.  
  
|Атрибут|Описание|  
|---|---|  
|`ID`|Обязательный. Уникальный идентификатор расширения. Если расширение, имеющее этот идентификатор уже были добавлены в проект, пользователь не потребует добавлять его снова.|  
|`Version`|Обязательный. Номер версии для шаблона элемента.|  
|`AssemblyFullName`|Необязательный. Имя сборки. Когда в проект добавляется ссылка на эту сборку, пользователю будет предложено добавить `My` расширения на основе этого шаблона элемента.|  
  
### <a name="add-the-customdatasignature-element-to-the-vstemplate-file"></a>Добавить \<CustomDataSignature настроек элемент VSTEMPLATE-файлу  
 Для идентификации элемента шаблона Visual Studio как `My` расширение пространства имен, необходимо также изменить файл VSTEMPLATE для шаблона элемента. Необходимо добавить `<CustomDataSignature>` элемента `<TemplateData>` элемент. `<CustomDataSignature>` Элемент должен содержать текст `Microsoft.VisualBasic.MyExtension`, как показано в следующем примере.  
  
```  
<CustomDataSignature>Microsoft.VisualBasic.MyExtension</CustomDataSignature>  
```  
  
 Нельзя непосредственно изменять файлы в сжатой папке (ZIP-файл). Необходимо скопировать файл VSTEMPLATE из сжатой папки, изменить его и затем заменить файл VSTEMPLATE в сжатой папке обновленной версией.  
  
 В следующем примере показано содержимое VSTEMPLATE-файл, который имеет `<CustomDataSignature>` добавлен элемент.  
  
```  
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
 Установка шаблона, можно скопировать сжатую папку (ZIP-файл) в Visual Basic элемент папку шаблонов (например, Мои документы\Visual Studio 2008\Templates\Item Templates\Visual базового). Кроме того можно опубликовать шаблон в виде файла установщика Visual Studio (VSI).  
  
## <a name="see-also"></a>См. также  
 [Расширение пространства имен My в Visual Basic](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-my-namespace.md)   
 [Расширение модели приложения Visual Basic](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-visual-basic-application-model.md)   
 [Настройка доступа к объектам, доступные в моей](../../../visual-basic/developing-apps/customizing-extending-my/customizing-which-objects-are-available-in-my.md)   
 [Страница "Мои расширения" Конструктор проектов](https://docs.microsoft.com/visualstudio/ide/reference/my-extensions-page-project-designer-visual-basic)

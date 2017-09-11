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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 81483722227873d1b145219ae5c4326d841ff876
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="packaging-and-deploying-custom-my-extensions-visual-basic"></a><span data-ttu-id="34a35-102">Упаковка и развертывание пользовательских расширений пространства имен My (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="34a35-102">Packaging and deploying custom My extensions (Visual Basic)</span></span>
<span data-ttu-id="34a35-103">Visual Basic предоставляет удобный способ развертывания пользовательских `My` расширения пространства имен с помощью шаблонов Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="34a35-103">Visual Basic provides an easy way for you to deploy your custom `My` namespace extensions by using Visual Studio templates.</span></span> <span data-ttu-id="34a35-104">Если вы создаете шаблон проекта, для которого вашей `My` расширения являются неотъемлемой частью, достаточно включить пользовательский `My` расширение кода в проект при экспорте шаблона.</span><span class="sxs-lookup"><span data-stu-id="34a35-104">If you are creating a project template for which your `My` extensions are an integral part of the new project type, you can just include your custom `My` extension code with the project when you export the template.</span></span> <span data-ttu-id="34a35-105">Дополнительные сведения об экспорте шаблонов проекта см. в разделе [Практическое руководство: создание шаблонов проекта](http://msdn.microsoft.com/library/a1a6999d-a34c-48a8-b1cf-027eb5c76398).</span><span class="sxs-lookup"><span data-stu-id="34a35-105">For more information about exporting project templates, see [How to: Create Project Templates](http://msdn.microsoft.com/library/a1a6999d-a34c-48a8-b1cf-027eb5c76398).</span></span>  
  
 <span data-ttu-id="34a35-106">Если пользовательский `My` расширения в одном файле кода, можно экспортировать файл как шаблон элемента, который пользователи могут добавлять в любой тип проектов Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="34a35-106">If your custom `My` extension is in a single code file, you can export the file as an item template that users can add to any type of Visual Basic project.</span></span> <span data-ttu-id="34a35-107">Затем можно настроить шаблон элемента для включения дополнительных возможностей и поведения пользовательского `My` расширения в проекте Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="34a35-107">You can then customize the item template to enable additional capabilities and behavior for your custom `My` extension in a Visual Basic project.</span></span> <span data-ttu-id="34a35-108">Эти возможности включают следующее:</span><span class="sxs-lookup"><span data-stu-id="34a35-108">Those capabilities include the following:</span></span>  
  
-   <span data-ttu-id="34a35-109">Возможность управления пользовательским `My` расширения из **Мои расширения** страницы в конструкторе проектов Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="34a35-109">Allowing users to manage your custom `My` extension from the **My Extensions** page of the Visual Basic Project Designer.</span></span>  
  
-   <span data-ttu-id="34a35-110">Автоматическое добавление пользовательских `My` в проект добавляется расширение, когда ссылка на указанную сборку.</span><span class="sxs-lookup"><span data-stu-id="34a35-110">Automatically adding your custom `My` extension when a reference to a specified assembly is added to a project.</span></span>  
  
-   <span data-ttu-id="34a35-111">Скрытие `My` шаблона элемента расширения в **добавить элемент** диалоговое окно, чтобы он не включен в список элементов проекта.</span><span class="sxs-lookup"><span data-stu-id="34a35-111">Hiding the `My` extension item template in the **Add Item** dialog box so that it is not included in the list of project items.</span></span>  
  
 <span data-ttu-id="34a35-112">В этом разделе рассматривается упаковка пользовательского `My` расширения в качестве скрытого шаблона элемента, можно управлять из **Мои расширения** страницы в конструкторе проектов Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="34a35-112">This topic discusses how to package a custom `My` extension as a hidden item template that can be managed from the **My Extensions** page of the Visual Basic Project Designer.</span></span> <span data-ttu-id="34a35-113">Пользовательская `My` расширения можно также добавлять автоматически при добавлении в проект ссылки на указанную сборку.</span><span class="sxs-lookup"><span data-stu-id="34a35-113">The custom `My` extension can also be added automatically when a reference to a specified assembly is added to a project.</span></span>  
  
## <a name="create-a-my-namespace-extension"></a><span data-ttu-id="34a35-114">Создание расширения пространства имен My</span><span class="sxs-lookup"><span data-stu-id="34a35-114">Create a My namespace extension</span></span>  
 <span data-ttu-id="34a35-115">Первым шагом в создании пакета развертывания для пользовательского `My` расширения является создание расширения в виде одного файла кода.</span><span class="sxs-lookup"><span data-stu-id="34a35-115">The first step in creating a deployment package for a custom `My` extension is to create the extension as a single code file.</span></span> <span data-ttu-id="34a35-116">Дополнительные сведения и инструкции о том, как создать настраиваемый `My` расширения, в разделе [расширение пространства имен My в Visual Basic](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-my-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="34a35-116">For details and guidance about how to create a custom `My` extension, see [Extending the My Namespace in Visual Basic](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-my-namespace.md).</span></span>  
  
## <a name="export-a-my-namespace-extension-as-an-item-template"></a><span data-ttu-id="34a35-117">Экспорт расширения пространства имен My в качестве шаблона элемента</span><span class="sxs-lookup"><span data-stu-id="34a35-117">Export a My namespace extension as an item template</span></span>  
 <span data-ttu-id="34a35-118">После добавления в файл кода, содержащий ваш `My` расширение пространства имен, можно экспортировать файл с кодом в качестве шаблона элемента Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="34a35-118">After you have a code file that includes your `My` namespace extension, you can export the code file as a Visual Studio item template.</span></span> <span data-ttu-id="34a35-119">Инструкции по экспорту файла в качестве шаблона элемента Visual Studio см. в разделе [Практическое руководство: создание шаблонов элементов](http://msdn.microsoft.com/library/77bc53d4-d607-4820-a032-7e3b365891b5).</span><span class="sxs-lookup"><span data-stu-id="34a35-119">For instructions on how to export a file as a Visual Studio item template, see [How to: Create Item Templates](http://msdn.microsoft.com/library/77bc53d4-d607-4820-a032-7e3b365891b5).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="34a35-120">Если ваш `My` расширение пространства имен имеет зависимость от определенной сборки, можно настроить шаблон элемента на автоматическую установку вашего `My` расширение пространства имен при добавлении ссылки на эту сборку.</span><span class="sxs-lookup"><span data-stu-id="34a35-120">If your `My` namespace extension has a dependency on a particular assembly, you can customize your item template to automatically install your `My` namespace extension when a reference to that assembly is added.</span></span> <span data-ttu-id="34a35-121">В результате вы хотите исключить ссылку на данную сборку при экспорте в файл кода в виде шаблона элемента Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="34a35-121">As a result, you will want to exclude that assembly reference when you export the code file as a Visual Studio item template.</span></span>  
  
## <a name="customize-the-item-template"></a><span data-ttu-id="34a35-122">Настройка шаблона элемента</span><span class="sxs-lookup"><span data-stu-id="34a35-122">Customize the item template</span></span>  
 <span data-ttu-id="34a35-123">Можно включить шаблоном элемента управления из **Мои расширения** страницы в конструкторе проектов Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="34a35-123">You can enable your item template to be managed from the **My Extensions** page of the Visual Basic Project Designer.</span></span> <span data-ttu-id="34a35-124">Можно также включить шаблон элемента добавляется автоматически при добавлении в проект ссылки на указанную сборку.</span><span class="sxs-lookup"><span data-stu-id="34a35-124">You can also enable the item template to be added automatically when a reference to a specified assembly is added to a project.</span></span> <span data-ttu-id="34a35-125">Чтобы включить эти настройки, будут добавьте новый файл с именем CustomData, к шаблону и затем добавьте новый элемент в XML-код в файле .vstemplate.</span><span class="sxs-lookup"><span data-stu-id="34a35-125">To enable these customizations, you will add a new file, called the CustomData file, to your template, and then add a new element to the XML in your .vstemplate file.</span></span>  
  
### <a name="add-the-customdata-file"></a><span data-ttu-id="34a35-126">Добавьте файл CustomData</span><span class="sxs-lookup"><span data-stu-id="34a35-126">Add the CustomData file</span></span>  
 <span data-ttu-id="34a35-127">Файл CustomData — текстовый файл, который имеет расширение имени файла. CustomData (имя файла может быть присвоено любое значение может применяться в шаблоне), которая содержит XML.</span><span class="sxs-lookup"><span data-stu-id="34a35-127">The CustomData file is a text file that has a file name extension of .CustomData (the file name can be set to any value meaningful to your template) and that contains XML.</span></span> <span data-ttu-id="34a35-128">XML в файле CustomData сообщает Visual Basic для включения вашего `My` расширение при использовании **Мои расширения** страницы в конструкторе проектов Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="34a35-128">The XML in the CustomData file instructs Visual Basic to include your `My` extension when users use the **My Extensions** page of the Visual Basic Project Designer.</span></span> <span data-ttu-id="34a35-129">При необходимости можно добавить `AssemblyFullName>` в файл CustomData XML.</span><span class="sxs-lookup"><span data-stu-id="34a35-129">You can optionally add the <`AssemblyFullName>` attribute to your CustomData file XML.</span></span> <span data-ttu-id="34a35-130">Это указывает, что Visual Basic на автоматическую установку пользовательского `My` при получении ссылки на определенную сборку расширения добавляется в проект.</span><span class="sxs-lookup"><span data-stu-id="34a35-130">This instructs Visual Basic to automatically install your custom `My` extension when a reference to a particular assembly is added to the project.</span></span> <span data-ttu-id="34a35-131">Можно использовать любой текстовый редактор или редактор XML для создания файла CustomData и затем добавить в шаблон элемента сжатую папку (ZIP-файл).</span><span class="sxs-lookup"><span data-stu-id="34a35-131">You can use any text editor or XML editor to create the CustomData file, and then add it to your item template's compressed folder (.zip file).</span></span>  
  
 <span data-ttu-id="34a35-132">Например следующий код XML показывает содержимое файла CustomData, который добавляет элемент шаблона в папку Мои расширения проекта Visual Basic, когда ссылка на сборку Microsoft.VisualBasic.PowerPacks.Vs.dll добавляется в проект.</span><span class="sxs-lookup"><span data-stu-id="34a35-132">For example, the following XML shows the contents of a CustomData file that will add the template item to the My Extensions folder of a Visual Basic project when a reference to the Microsoft.VisualBasic.PowerPacks.Vs.dll assembly is added to the project.</span></span>  
  
```  
<VBMyExtensionTemplate   
    ID="Microsoft.VisualBasic.Samples.MyExtensions.MyPrinterInfo"   
    Version="1.0.0.0"  
    AssemblyFullName="Microsoft.VisualBasic.PowerPacks.vs"  
/>  
```  
  
 <span data-ttu-id="34a35-133">Файл CustomData содержит `VBMyExtensionTemplate>` элемент, имеющий атрибуты, перечисленные в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="34a35-133">The CustomData file contains a <`VBMyExtensionTemplate>` element that has attributes as listed in the following table.</span></span>  
  
|<span data-ttu-id="34a35-134">Атрибут</span><span class="sxs-lookup"><span data-stu-id="34a35-134">Attribute</span></span>|<span data-ttu-id="34a35-135">Описание</span><span class="sxs-lookup"><span data-stu-id="34a35-135">Description</span></span>|  
|---|---|  
|`ID`|<span data-ttu-id="34a35-136">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="34a35-136">Required.</span></span> <span data-ttu-id="34a35-137">Уникальный идентификатор расширения.</span><span class="sxs-lookup"><span data-stu-id="34a35-137">A unique identifier for the extension.</span></span> <span data-ttu-id="34a35-138">Если расширение, имеющее этот идентификатор уже были добавлены в проект, пользователь не потребует добавлять его снова.</span><span class="sxs-lookup"><span data-stu-id="34a35-138">If the extension that has this ID has already been added to the project, the user will not be prompted to add it again.</span></span>|  
|`Version`|<span data-ttu-id="34a35-139">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="34a35-139">Required.</span></span> <span data-ttu-id="34a35-140">Номер версии для шаблона элемента.</span><span class="sxs-lookup"><span data-stu-id="34a35-140">A version number for the item template.</span></span>|  
|`AssemblyFullName`|<span data-ttu-id="34a35-141">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="34a35-141">Optional.</span></span> <span data-ttu-id="34a35-142">Имя сборки.</span><span class="sxs-lookup"><span data-stu-id="34a35-142">An assembly name.</span></span> <span data-ttu-id="34a35-143">Когда в проект добавляется ссылка на эту сборку, пользователю будет предложено добавить `My` расширения на основе этого шаблона элемента.</span><span class="sxs-lookup"><span data-stu-id="34a35-143">When a reference to this assembly is added to the project, the user will be prompted to add the `My` extension from this item template.</span></span>|  
  
### <a name="add-the-customdatasignature-element-to-the-vstemplate-file"></a><span data-ttu-id="34a35-144">Добавить \<CustomDataSignature настроек элемент VSTEMPLATE-файлу</span><span class="sxs-lookup"><span data-stu-id="34a35-144">Add the \<CustomDataSignature> element to the .vstemplate file</span></span>  
 <span data-ttu-id="34a35-145">Для идентификации элемента шаблона Visual Studio как `My` расширение пространства имен, необходимо также изменить файл VSTEMPLATE для шаблона элемента.</span><span class="sxs-lookup"><span data-stu-id="34a35-145">To identify your Visual Studio item template as a `My` namespace extension, you must also modify the .vstemplate file for your item template.</span></span> <span data-ttu-id="34a35-146">Необходимо добавить `<CustomDataSignature>` элемента `<TemplateData>` элемент.</span><span class="sxs-lookup"><span data-stu-id="34a35-146">You must add a `<CustomDataSignature>` element to the `<TemplateData>` element.</span></span> <span data-ttu-id="34a35-147">`<CustomDataSignature>` Элемент должен содержать текст `Microsoft.VisualBasic.MyExtension`, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="34a35-147">The `<CustomDataSignature>` element must contain the text `Microsoft.VisualBasic.MyExtension`, as shown in the following example.</span></span>  
  
```  
<CustomDataSignature>Microsoft.VisualBasic.MyExtension</CustomDataSignature>  
```  
  
 <span data-ttu-id="34a35-148">Нельзя непосредственно изменять файлы в сжатой папке (ZIP-файл).</span><span class="sxs-lookup"><span data-stu-id="34a35-148">You cannot modify files in a compressed folder (.zip file) directly.</span></span> <span data-ttu-id="34a35-149">Необходимо скопировать файл VSTEMPLATE из сжатой папки, изменить его и затем заменить файл VSTEMPLATE в сжатой папке обновленной версией.</span><span class="sxs-lookup"><span data-stu-id="34a35-149">You must copy the .vstemplate file from the compressed folder, modify it, and then replace the .vstemplate file in the compressed folder with your updated copy.</span></span>  
  
 <span data-ttu-id="34a35-150">В следующем примере показано содержимое VSTEMPLATE-файл, который имеет `<CustomDataSignature>` добавлен элемент.</span><span class="sxs-lookup"><span data-stu-id="34a35-150">The following example shows the contents of a .vstemplate file that has the `<CustomDataSignature>` element added.</span></span>  
  
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
  
## <a name="install-the-template"></a><span data-ttu-id="34a35-151">Установка шаблона</span><span class="sxs-lookup"><span data-stu-id="34a35-151">Install the template</span></span>  
 <span data-ttu-id="34a35-152">Установка шаблона, можно скопировать сжатую папку (ZIP-файл) в Visual Basic элемент папку шаблонов (например, Мои документы\Visual Studio 2008\Templates\Item Templates\Visual базового).</span><span class="sxs-lookup"><span data-stu-id="34a35-152">To install the template, you can copy the compressed folder (.zip file) to the Visual Basic item templates folder (for example, My Documents\Visual Studio 2008\Templates\Item Templates\Visual Basic).</span></span> <span data-ttu-id="34a35-153">Кроме того можно опубликовать шаблон в виде файла установщика Visual Studio (VSI).</span><span class="sxs-lookup"><span data-stu-id="34a35-153">Alternatively, you can publish the template as a Visual Studio Installer (.vsi) file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34a35-154">См. также</span><span class="sxs-lookup"><span data-stu-id="34a35-154">See also</span></span>  
 <span data-ttu-id="34a35-155">[Расширение пространства имен My в Visual Basic](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-my-namespace.md) </span><span class="sxs-lookup"><span data-stu-id="34a35-155">[Extending the My Namespace in Visual Basic](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-my-namespace.md) </span></span>  
<span data-ttu-id="34a35-156"> [Расширение модели приложения Visual Basic](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-visual-basic-application-model.md) </span><span class="sxs-lookup"><span data-stu-id="34a35-156"> [Extending the Visual Basic Application Model](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-visual-basic-application-model.md) </span></span>  
<span data-ttu-id="34a35-157"> [Настройка доступа к объектам, доступные в моей](../../../visual-basic/developing-apps/customizing-extending-my/customizing-which-objects-are-available-in-my.md) </span><span class="sxs-lookup"><span data-stu-id="34a35-157"> [Customizing Which Objects are Available in My](../../../visual-basic/developing-apps/customizing-extending-my/customizing-which-objects-are-available-in-my.md) </span></span>  
<span data-ttu-id="34a35-158"> [Страница "Мои расширения" Конструктор проектов](https://docs.microsoft.com/visualstudio/ide/reference/my-extensions-page-project-designer-visual-basic)</span><span class="sxs-lookup"><span data-stu-id="34a35-158"> [My Extensions Page, Project Designer](https://docs.microsoft.com/visualstudio/ide/reference/my-extensions-page-project-designer-visual-basic)</span></span>

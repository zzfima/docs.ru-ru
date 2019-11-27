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
# <a name="package-and-deploy-custom-my-extensions-visual-basic"></a><span data-ttu-id="c9a89-102">Упаковка и развертывание пользовательских расширений My (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c9a89-102">Package and deploy custom My extensions (Visual Basic)</span></span>

<span data-ttu-id="c9a89-103">Visual Basic предоставляет простой способ развертывания расширений пользовательского пространства имен `My` с помощью шаблонов Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="c9a89-103">Visual Basic provides an easy way for you to deploy your custom `My` namespace extensions by using Visual Studio templates.</span></span> <span data-ttu-id="c9a89-104">При создании шаблона проекта, для которого расширения `My` являются неотъемлемой частью нового типа проекта, при экспорте шаблона можно просто включить пользовательский код расширения `My` в проект.</span><span class="sxs-lookup"><span data-stu-id="c9a89-104">If you are creating a project template for which your `My` extensions are an integral part of the new project type, you can just include your custom `My` extension code with the project when you export the template.</span></span> <span data-ttu-id="c9a89-105">Дополнительные сведения об экспорте шаблонов проектов см. [в разделе инструкции. Создание шаблонов проектов](/visualstudio/ide/how-to-create-project-templates).</span><span class="sxs-lookup"><span data-stu-id="c9a89-105">For more information about exporting project templates, see [How to: Create Project Templates](/visualstudio/ide/how-to-create-project-templates).</span></span>

<span data-ttu-id="c9a89-106">Если расширение Custom `My` находится в одном файле кода, можно экспортировать файл как шаблон элемента, который пользователи могут добавлять в любой тип Visual Basic проекта.</span><span class="sxs-lookup"><span data-stu-id="c9a89-106">If your custom `My` extension is in a single code file, you can export the file as an item template that users can add to any type of Visual Basic project.</span></span> <span data-ttu-id="c9a89-107">Затем можно настроить шаблон элемента, чтобы включить дополнительные возможности и поведение для пользовательского расширения `My` в проекте Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="c9a89-107">You can then customize the item template to enable additional capabilities and behavior for your custom `My` extension in a Visual Basic project.</span></span> <span data-ttu-id="c9a89-108">К этим возможностям относятся следующие.</span><span class="sxs-lookup"><span data-stu-id="c9a89-108">Those capabilities include the following:</span></span>

- <span data-ttu-id="c9a89-109">Предоставление пользователям возможности управлять пользовательским расширением `My` на странице " **Мои расширения** " в конструкторе проектов Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="c9a89-109">Allowing users to manage your custom `My` extension from the **My Extensions** page of the Visual Basic Project Designer.</span></span>

- <span data-ttu-id="c9a89-110">Автоматическое добавление пользовательского расширения `My` при добавлении ссылки на указанную сборку в проект.</span><span class="sxs-lookup"><span data-stu-id="c9a89-110">Automatically adding your custom `My` extension when a reference to a specified assembly is added to a project.</span></span>

- <span data-ttu-id="c9a89-111">Скрытие шаблона элемента расширения `My` в диалоговом окне **Добавление элемента** , чтобы он не включался в список элементов проекта.</span><span class="sxs-lookup"><span data-stu-id="c9a89-111">Hiding the `My` extension item template in the **Add Item** dialog box so that it is not included in the list of project items.</span></span>

<span data-ttu-id="c9a89-112">В этом разделе описывается упаковка пользовательского расширения `My` в качестве скрытого шаблона элемента, который можно управлять со страницы **Мои расширения** в конструкторе проектов Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="c9a89-112">This topic discusses how to package a custom `My` extension as a hidden item template that can be managed from the **My Extensions** page of the Visual Basic Project Designer.</span></span> <span data-ttu-id="c9a89-113">Расширение настраиваемого `My` также может быть добавлено автоматически при добавлении ссылки на указанную сборку в проект.</span><span class="sxs-lookup"><span data-stu-id="c9a89-113">The custom `My` extension can also be added automatically when a reference to a specified assembly is added to a project.</span></span>

## <a name="create-a-my-namespace-extension"></a><span data-ttu-id="c9a89-114">Создание расширения пространства имен My</span><span class="sxs-lookup"><span data-stu-id="c9a89-114">Create a My namespace extension</span></span>

<span data-ttu-id="c9a89-115">Первым шагом в создании пакета развертывания для пользовательского расширения `My` является создание расширения в виде одного файла кода.</span><span class="sxs-lookup"><span data-stu-id="c9a89-115">The first step in creating a deployment package for a custom `My` extension is to create the extension as a single code file.</span></span> <span data-ttu-id="c9a89-116">Дополнительные сведения и рекомендации по созданию пользовательского расширения `My` см. [в разделе расширение пространства имен My в Visual Basic](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-my-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="c9a89-116">For details and guidance about how to create a custom `My` extension, see [Extending the My Namespace in Visual Basic](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-my-namespace.md).</span></span>

## <a name="export-a-my-namespace-extension-as-an-item-template"></a><span data-ttu-id="c9a89-117">Экспорт расширения пространства имен My в качестве шаблона элемента</span><span class="sxs-lookup"><span data-stu-id="c9a89-117">Export a My namespace extension as an item template</span></span>

<span data-ttu-id="c9a89-118">После создания файла кода, содержащего расширение пространства имен `My`, можно экспортировать файл кода в качестве шаблона элемента Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="c9a89-118">After you have a code file that includes your `My` namespace extension, you can export the code file as a Visual Studio item template.</span></span> <span data-ttu-id="c9a89-119">Инструкции по экспорту файла в качестве шаблона элемента Visual Studio см. [в разделе инструкции. Создание шаблонов элементов](/visualstudio/ide/how-to-create-item-templates).</span><span class="sxs-lookup"><span data-stu-id="c9a89-119">For instructions on how to export a file as a Visual Studio item template, see [How to: Create Item Templates](/visualstudio/ide/how-to-create-item-templates).</span></span>

> [!NOTE]
> <span data-ttu-id="c9a89-120">Если расширение пространства имен `My` зависит от конкретной сборки, можно настроить шаблон элемента для автоматической установки расширения пространства имен `My` при добавлении ссылки на эту сборку.</span><span class="sxs-lookup"><span data-stu-id="c9a89-120">If your `My` namespace extension has a dependency on a particular assembly, you can customize your item template to automatically install your `My` namespace extension when a reference to that assembly is added.</span></span> <span data-ttu-id="c9a89-121">В результате вы хотите исключить эту ссылку на сборку при экспорте файла кода в качестве шаблона элемента Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="c9a89-121">As a result, you will want to exclude that assembly reference when you export the code file as a Visual Studio item template.</span></span>

## <a name="customize-the-item-template"></a><span data-ttu-id="c9a89-122">Настройка шаблона элемента</span><span class="sxs-lookup"><span data-stu-id="c9a89-122">Customize the item template</span></span>

<span data-ttu-id="c9a89-123">Вы можете включить управление шаблоном элемента со страницы **My Extensions (Мои расширения** ) в конструкторе проектов Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="c9a89-123">You can enable your item template to be managed from the **My Extensions** page of the Visual Basic Project Designer.</span></span> <span data-ttu-id="c9a89-124">Можно также включить автоматическое добавление шаблона элемента при добавлении в проект ссылки на указанную сборку.</span><span class="sxs-lookup"><span data-stu-id="c9a89-124">You can also enable the item template to be added automatically when a reference to a specified assembly is added to a project.</span></span> <span data-ttu-id="c9a89-125">Чтобы включить эти настройки, добавьте в шаблон новый файл, который называется файлом CustomData, а затем добавьте новый элемент в XML-файл в файле VSTEMPLATE.</span><span class="sxs-lookup"><span data-stu-id="c9a89-125">To enable these customizations, you will add a new file, called the CustomData file, to your template, and then add a new element to the XML in your .vstemplate file.</span></span>

### <a name="add-the-customdata-file"></a><span data-ttu-id="c9a89-126">Добавление файла CustomData</span><span class="sxs-lookup"><span data-stu-id="c9a89-126">Add the CustomData file</span></span>

<span data-ttu-id="c9a89-127">Файл CustomData — это текстовый файл с расширением имени файла. CustomData (для имени файла можно задать любое значение, значимое для шаблона) и содержащее XML.</span><span class="sxs-lookup"><span data-stu-id="c9a89-127">The CustomData file is a text file that has a file name extension of .CustomData (the file name can be set to any value meaningful to your template) and that contains XML.</span></span> <span data-ttu-id="c9a89-128">XML-код в файле CustomData указывает Visual Basic включить расширение `My`, когда пользователи используют страницу **Мои расширения** конструктора проектов Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="c9a89-128">The XML in the CustomData file instructs Visual Basic to include your `My` extension when users use the **My Extensions** page of the Visual Basic Project Designer.</span></span> <span data-ttu-id="c9a89-129">При необходимости можно добавить атрибут <`AssemblyFullName>` в XML-файл CustomData.</span><span class="sxs-lookup"><span data-stu-id="c9a89-129">You can optionally add the <`AssemblyFullName>` attribute to your CustomData file XML.</span></span> <span data-ttu-id="c9a89-130">Это указывает Visual Basic автоматически установить расширение пользовательского `My` при добавлении в проект ссылки на определенную сборку.</span><span class="sxs-lookup"><span data-stu-id="c9a89-130">This instructs Visual Basic to automatically install your custom `My` extension when a reference to a particular assembly is added to the project.</span></span> <span data-ttu-id="c9a89-131">Для создания файла CustomData можно использовать любой текстовый редактор или редактор XML, а затем добавить его в сжатую папку (ZIP-файл) шаблона элемента.</span><span class="sxs-lookup"><span data-stu-id="c9a89-131">You can use any text editor or XML editor to create the CustomData file, and then add it to your item template's compressed folder (.zip file).</span></span>

<span data-ttu-id="c9a89-132">Например, в следующем XML-коде показано содержимое файла CustomData, который добавит элемент шаблона в папку My Extensions проекта Visual Basic, когда в проект будет добавлена ссылка на сборку Microsoft. VisualBasic. PowerPacks. vs. dll.</span><span class="sxs-lookup"><span data-stu-id="c9a89-132">For example, the following XML shows the contents of a CustomData file that will add the template item to the My Extensions folder of a Visual Basic project when a reference to the Microsoft.VisualBasic.PowerPacks.Vs.dll assembly is added to the project.</span></span>

```xml
<VBMyExtensionTemplate
    ID="Microsoft.VisualBasic.Samples.MyExtensions.MyPrinterInfo"
    Version="1.0.0.0"
    AssemblyFullName="Microsoft.VisualBasic.PowerPacks.vs"
/>
```

<span data-ttu-id="c9a89-133">Файл CustomData содержит элемент <`VBMyExtensionTemplate>`, имеющий атрибуты, перечисленные в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="c9a89-133">The CustomData file contains a <`VBMyExtensionTemplate>` element that has attributes as listed in the following table.</span></span>

|<span data-ttu-id="c9a89-134">Атрибут</span><span class="sxs-lookup"><span data-stu-id="c9a89-134">Attribute</span></span>|<span data-ttu-id="c9a89-135">Описание</span><span class="sxs-lookup"><span data-stu-id="c9a89-135">Description</span></span>|
|---|---|
|`ID`|<span data-ttu-id="c9a89-136">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="c9a89-136">Required.</span></span> <span data-ttu-id="c9a89-137">Уникальный идентификатор для расширения.</span><span class="sxs-lookup"><span data-stu-id="c9a89-137">A unique identifier for the extension.</span></span> <span data-ttu-id="c9a89-138">Если расширение с таким ИДЕНТИФИКАТОРом уже было добавлено в проект, пользователю не будет предложено добавить его снова.</span><span class="sxs-lookup"><span data-stu-id="c9a89-138">If the extension that has this ID has already been added to the project, the user will not be prompted to add it again.</span></span>|
|`Version`|<span data-ttu-id="c9a89-139">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="c9a89-139">Required.</span></span> <span data-ttu-id="c9a89-140">Номер версии для шаблона элемента.</span><span class="sxs-lookup"><span data-stu-id="c9a89-140">A version number for the item template.</span></span>|
|`AssemblyFullName`|<span data-ttu-id="c9a89-141">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="c9a89-141">Optional.</span></span> <span data-ttu-id="c9a89-142">Имя сборки.</span><span class="sxs-lookup"><span data-stu-id="c9a89-142">An assembly name.</span></span> <span data-ttu-id="c9a89-143">При добавлении ссылки на эту сборку в проект пользователю будет предложено добавить расширение `My` из этого шаблона элемента.</span><span class="sxs-lookup"><span data-stu-id="c9a89-143">When a reference to this assembly is added to the project, the user will be prompted to add the `My` extension from this item template.</span></span>|

### <a name="add-the-customdatasignature-element-to-the-vstemplate-file"></a><span data-ttu-id="c9a89-144">Добавление элемента \<Кустомдатасигнатуре > в файл VSTEMPLATE</span><span class="sxs-lookup"><span data-stu-id="c9a89-144">Add the \<CustomDataSignature> element to the .vstemplate file</span></span>

<span data-ttu-id="c9a89-145">Чтобы найти шаблон элемента Visual Studio в качестве расширения пространства имен `My`, необходимо также изменить VSTEMPLATE-файл для шаблона элемента.</span><span class="sxs-lookup"><span data-stu-id="c9a89-145">To identify your Visual Studio item template as a `My` namespace extension, you must also modify the .vstemplate file for your item template.</span></span> <span data-ttu-id="c9a89-146">Необходимо добавить элемент `<CustomDataSignature>` в элемент `<TemplateData>`.</span><span class="sxs-lookup"><span data-stu-id="c9a89-146">You must add a `<CustomDataSignature>` element to the `<TemplateData>` element.</span></span> <span data-ttu-id="c9a89-147">Элемент `<CustomDataSignature>` должен содержать текст `Microsoft.VisualBasic.MyExtension`, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="c9a89-147">The `<CustomDataSignature>` element must contain the text `Microsoft.VisualBasic.MyExtension`, as shown in the following example.</span></span>

```xml
<CustomDataSignature>Microsoft.VisualBasic.MyExtension</CustomDataSignature>
```

<span data-ttu-id="c9a89-148">Нельзя изменять файлы в сжатой папке (ZIP-файле) напрямую.</span><span class="sxs-lookup"><span data-stu-id="c9a89-148">You cannot modify files in a compressed folder (.zip file) directly.</span></span> <span data-ttu-id="c9a89-149">Необходимо скопировать VSTEMPLATE файл из сжатой папки, изменить его, а затем заменить файл VSTEMPLATE в сжатой папке обновленной копией.</span><span class="sxs-lookup"><span data-stu-id="c9a89-149">You must copy the .vstemplate file from the compressed folder, modify it, and then replace the .vstemplate file in the compressed folder with your updated copy.</span></span>

<span data-ttu-id="c9a89-150">В следующем примере показано содержимое VSTEMPLATE-файла, в котором добавлен элемент `<CustomDataSignature>`.</span><span class="sxs-lookup"><span data-stu-id="c9a89-150">The following example shows the contents of a .vstemplate file that has the `<CustomDataSignature>` element added.</span></span>

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

## <a name="install-the-template"></a><span data-ttu-id="c9a89-151">Установка шаблона</span><span class="sxs-lookup"><span data-stu-id="c9a89-151">Install the template</span></span>

<span data-ttu-id="c9a89-152">Чтобы установить шаблон, можно скопировать сжатую папку (*ZIP* -файл) в папку шаблонов элементов Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="c9a89-152">To install the template, you can copy the compressed folder (*.zip* file) to the Visual Basic item templates folder.</span></span> <span data-ttu-id="c9a89-153">По умолчанию шаблоны элементов пользователей находятся в *%UserProfile%\Documents\Visual Studio \<версии\>\Темплатес\итемтемплатес\висуал Basic*.</span><span class="sxs-lookup"><span data-stu-id="c9a89-153">By default, user item templates are located in *%USERPROFILE%\Documents\Visual Studio \<Version\>\Templates\ItemTemplates\Visual Basic*.</span></span> <span data-ttu-id="c9a89-154">Кроме того, шаблон можно опубликовать в виде файла Visual Studio Installer (*VSI*).</span><span class="sxs-lookup"><span data-stu-id="c9a89-154">Alternatively, you can publish the template as a Visual Studio Installer (*.vsi*) file.</span></span>

## <a name="see-also"></a><span data-ttu-id="c9a89-155">См. также</span><span class="sxs-lookup"><span data-stu-id="c9a89-155">See also</span></span>

- [<span data-ttu-id="c9a89-156">Расширение пространства имен My в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c9a89-156">Extending the My Namespace in Visual Basic</span></span>](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-my-namespace.md)
- [<span data-ttu-id="c9a89-157">Расширение модели приложения Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c9a89-157">Extending the Visual Basic Application Model</span></span>](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-visual-basic-application-model.md)
- [<span data-ttu-id="c9a89-158">Настройка доступа к объектам через My</span><span class="sxs-lookup"><span data-stu-id="c9a89-158">Customizing Which Objects are Available in My</span></span>](../../../visual-basic/developing-apps/customizing-extending-my/customizing-which-objects-are-available-in-my.md)
- [<span data-ttu-id="c9a89-159">Страница "Мои расширения", конструктор проектов</span><span class="sxs-lookup"><span data-stu-id="c9a89-159">My Extensions Page, Project Designer</span></span>](/visualstudio/ide/reference/my-extensions-page-project-designer-visual-basic)

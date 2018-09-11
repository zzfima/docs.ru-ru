---
title: Упаковка и развертывание пользовательских расширений пространства имен My (Visual Basic)
ms.date: 08/14/2018
helpviewer_keywords:
- My namespace [Visual Basic], customizing
- My namespace
- My namespace [Visual Basic], extending
ms.assetid: fd89c54b-0290-4c50-95a3-ff17d4487a21
ms.openlocfilehash: 4212f58c39f63be6ba20c3b79e5d9c98d0615c5e
ms.sourcegitcommit: 67de6cb5dd66a19f2180ba7e4d7aecc697f8a963
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2018
ms.locfileid: "44342674"
---
# <a name="package-and-deploy-custom-my-extensions-visual-basic"></a><span data-ttu-id="5f7b3-102">Упаковка и развертывание пользовательских расширений пространства имен My (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5f7b3-102">Package and deploy custom My extensions (Visual Basic)</span></span>

<span data-ttu-id="5f7b3-103">Visual Basic предоставляет простой способ развертывания пользовательских `My` расширения пространства имен с помощью шаблонов Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="5f7b3-103">Visual Basic provides an easy way for you to deploy your custom `My` namespace extensions by using Visual Studio templates.</span></span> <span data-ttu-id="5f7b3-104">Если вы создаете шаблон проекта, для которого ваши `My` расширения являются неотъемлемой частью нового типа проекта, можно просто включить пользовательский `My` код расширения в проект при экспорте шаблона.</span><span class="sxs-lookup"><span data-stu-id="5f7b3-104">If you are creating a project template for which your `My` extensions are an integral part of the new project type, you can just include your custom `My` extension code with the project when you export the template.</span></span> <span data-ttu-id="5f7b3-105">Дополнительные сведения об экспорте шаблонов проектов см. в разделе [как: создание шаблонов проектов](/visualstudio/ide/how-to-create-project-templates).</span><span class="sxs-lookup"><span data-stu-id="5f7b3-105">For more information about exporting project templates, see [How to: Create Project Templates](/visualstudio/ide/how-to-create-project-templates).</span></span>

<span data-ttu-id="5f7b3-106">Если пользовательский `My` расширения в одном файле кода, можно экспортировать файл в качестве шаблона элемента, который пользователи могут добавлять в любой тип проекта Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="5f7b3-106">If your custom `My` extension is in a single code file, you can export the file as an item template that users can add to any type of Visual Basic project.</span></span> <span data-ttu-id="5f7b3-107">Затем можно настроить шаблон элемента для включения дополнительных возможностей и поведения пользовательского `My` расширения в проекте Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="5f7b3-107">You can then customize the item template to enable additional capabilities and behavior for your custom `My` extension in a Visual Basic project.</span></span> <span data-ttu-id="5f7b3-108">Эти возможности включают следующее:</span><span class="sxs-lookup"><span data-stu-id="5f7b3-108">Those capabilities include the following:</span></span>

- <span data-ttu-id="5f7b3-109">Возможность управления пользовательским `My` расширения из **Мои расширения** страницы в конструкторе проектов Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="5f7b3-109">Allowing users to manage your custom `My` extension from the **My Extensions** page of the Visual Basic Project Designer.</span></span>

- <span data-ttu-id="5f7b3-110">Автоматического добавления пользовательского `My` в проект добавляется расширение при ссылку к указанной сборке.</span><span class="sxs-lookup"><span data-stu-id="5f7b3-110">Automatically adding your custom `My` extension when a reference to a specified assembly is added to a project.</span></span>

- <span data-ttu-id="5f7b3-111">Скрытие `My` шаблона элемента расширения в **Добавление элемента** диалоговое окно, чтобы он не включен в список элементов проекта.</span><span class="sxs-lookup"><span data-stu-id="5f7b3-111">Hiding the `My` extension item template in the **Add Item** dialog box so that it is not included in the list of project items.</span></span>

<span data-ttu-id="5f7b3-112">В этом разделе рассматривается упаковка пользовательского `My` расширения в качестве шаблона скрытый элемент, которыми можно управлять из **Мои расширения** страницы в конструкторе проектов Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="5f7b3-112">This topic discusses how to package a custom `My` extension as a hidden item template that can be managed from the **My Extensions** page of the Visual Basic Project Designer.</span></span> <span data-ttu-id="5f7b3-113">Пользовательский `My` расширения можно также добавлять автоматически при добавлении в проект ссылку на указанную сборку.</span><span class="sxs-lookup"><span data-stu-id="5f7b3-113">The custom `My` extension can also be added automatically when a reference to a specified assembly is added to a project.</span></span>

## <a name="create-a-my-namespace-extension"></a><span data-ttu-id="5f7b3-114">Создание расширения пространства имен My</span><span class="sxs-lookup"><span data-stu-id="5f7b3-114">Create a My namespace extension</span></span>

<span data-ttu-id="5f7b3-115">Первым шагом создания пакета развертывания для настраиваемого `My` расширения заключается в создании расширения в виде одного файла кода.</span><span class="sxs-lookup"><span data-stu-id="5f7b3-115">The first step in creating a deployment package for a custom `My` extension is to create the extension as a single code file.</span></span> <span data-ttu-id="5f7b3-116">Дополнительные сведения и рекомендации о том, как создавать пользовательские `My` расширения, см. в разделе [расширение пространства имен My в Visual Basic](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-my-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="5f7b3-116">For details and guidance about how to create a custom `My` extension, see [Extending the My Namespace in Visual Basic](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-my-namespace.md).</span></span>

## <a name="export-a-my-namespace-extension-as-an-item-template"></a><span data-ttu-id="5f7b3-117">Экспорт расширение My namespace как шаблон элемента</span><span class="sxs-lookup"><span data-stu-id="5f7b3-117">Export a My namespace extension as an item template</span></span>

<span data-ttu-id="5f7b3-118">После того как файл кода, который содержит ваши `My` расширение пространства имен, можно экспортировать в файл кода как шаблона элемента Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="5f7b3-118">After you have a code file that includes your `My` namespace extension, you can export the code file as a Visual Studio item template.</span></span> <span data-ttu-id="5f7b3-119">Инструкции по экспорту файла в качестве шаблона элемента Visual Studio, см. в разделе [как: создание шаблонов элементов](/visualstudio/ide/how-to-create-item-templates).</span><span class="sxs-lookup"><span data-stu-id="5f7b3-119">For instructions on how to export a file as a Visual Studio item template, see [How to: Create Item Templates](/visualstudio/ide/how-to-create-item-templates).</span></span>

> [!NOTE]
> <span data-ttu-id="5f7b3-120">Если ваш `My` расширение пространства имен имеет зависимость от определенной сборки, можно настроить шаблон элемента для автоматической установки вашего `My` расширение пространства имен при добавлении ссылки на эту сборку.</span><span class="sxs-lookup"><span data-stu-id="5f7b3-120">If your `My` namespace extension has a dependency on a particular assembly, you can customize your item template to automatically install your `My` namespace extension when a reference to that assembly is added.</span></span> <span data-ttu-id="5f7b3-121">Таким образом вы хотите исключить ссылку на данную сборку при экспорте в файл кода в виде шаблона элемента Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="5f7b3-121">As a result, you will want to exclude that assembly reference when you export the code file as a Visual Studio item template.</span></span>

## <a name="customize-the-item-template"></a><span data-ttu-id="5f7b3-122">Настроить шаблон элемента</span><span class="sxs-lookup"><span data-stu-id="5f7b3-122">Customize the item template</span></span>

<span data-ttu-id="5f7b3-123">Вы можете включить шаблон элемента осуществляется из **Мои расширения** страницы в конструкторе проектов Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="5f7b3-123">You can enable your item template to be managed from the **My Extensions** page of the Visual Basic Project Designer.</span></span> <span data-ttu-id="5f7b3-124">Кроме того, вы можете включить шаблона элемента для добавляться автоматически при добавлении в проект ссылку на указанную сборку.</span><span class="sxs-lookup"><span data-stu-id="5f7b3-124">You can also enable the item template to be added automatically when a reference to a specified assembly is added to a project.</span></span> <span data-ttu-id="5f7b3-125">Чтобы включить эти настройки, будет добавьте новый файл с именем CustomData, к шаблону и затем добавьте новый элемент в XML-документ в файле .vstemplate.</span><span class="sxs-lookup"><span data-stu-id="5f7b3-125">To enable these customizations, you will add a new file, called the CustomData file, to your template, and then add a new element to the XML in your .vstemplate file.</span></span>

### <a name="add-the-customdata-file"></a><span data-ttu-id="5f7b3-126">Добавьте файл CustomData</span><span class="sxs-lookup"><span data-stu-id="5f7b3-126">Add the CustomData file</span></span>

<span data-ttu-id="5f7b3-127">Файл CustomData — это текстовый файл, имеющий расширение имени файла. CustomData (имя файла может быть присвоено любое значение значимые в шаблон), которая содержит XML.</span><span class="sxs-lookup"><span data-stu-id="5f7b3-127">The CustomData file is a text file that has a file name extension of .CustomData (the file name can be set to any value meaningful to your template) and that contains XML.</span></span> <span data-ttu-id="5f7b3-128">XML в файле CustomData сообщает Visual Basic для включения в `My` расширение, когда пользователи применяют **Мои расширения** страницы в конструкторе проектов Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="5f7b3-128">The XML in the CustomData file instructs Visual Basic to include your `My` extension when users use the **My Extensions** page of the Visual Basic Project Designer.</span></span> <span data-ttu-id="5f7b3-129">При необходимости можно добавить <`AssemblyFullName>` атрибута в файл CustomData XML.</span><span class="sxs-lookup"><span data-stu-id="5f7b3-129">You can optionally add the <`AssemblyFullName>` attribute to your CustomData file XML.</span></span> <span data-ttu-id="5f7b3-130">Это указывает, что Visual Basic для автоматической установки пользовательских `My` расширение, когда ссылка на определенную сборку добавляется в проект.</span><span class="sxs-lookup"><span data-stu-id="5f7b3-130">This instructs Visual Basic to automatically install your custom `My` extension when a reference to a particular assembly is added to the project.</span></span> <span data-ttu-id="5f7b3-131">Можно использовать любой текстовый редактор или редактор XML для создания файла CustomData и затем добавить его в шаблон элемента сжатую папку (ZIP-файл).</span><span class="sxs-lookup"><span data-stu-id="5f7b3-131">You can use any text editor or XML editor to create the CustomData file, and then add it to your item template's compressed folder (.zip file).</span></span>

<span data-ttu-id="5f7b3-132">Например следующий код XML показано содержимое файла CustomData, добавляющий элемент шаблона в папку My Extensions проекта Visual Basic, когда ссылка на сборку Microsoft.VisualBasic.PowerPacks.Vs.dll добавляется в проект.</span><span class="sxs-lookup"><span data-stu-id="5f7b3-132">For example, the following XML shows the contents of a CustomData file that will add the template item to the My Extensions folder of a Visual Basic project when a reference to the Microsoft.VisualBasic.PowerPacks.Vs.dll assembly is added to the project.</span></span>

```xml
<VBMyExtensionTemplate
    ID="Microsoft.VisualBasic.Samples.MyExtensions.MyPrinterInfo"
    Version="1.0.0.0"
    AssemblyFullName="Microsoft.VisualBasic.PowerPacks.vs"
/>
```

<span data-ttu-id="5f7b3-133">Файл CustomData содержит <`VBMyExtensionTemplate>` элемент, имеющий атрибуты, перечисленные в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="5f7b3-133">The CustomData file contains a <`VBMyExtensionTemplate>` element that has attributes as listed in the following table.</span></span>

|<span data-ttu-id="5f7b3-134">Атрибут</span><span class="sxs-lookup"><span data-stu-id="5f7b3-134">Attribute</span></span>|<span data-ttu-id="5f7b3-135">Описание</span><span class="sxs-lookup"><span data-stu-id="5f7b3-135">Description</span></span>|
|---|---|
|`ID`|<span data-ttu-id="5f7b3-136">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="5f7b3-136">Required.</span></span> <span data-ttu-id="5f7b3-137">Уникальный идентификатор для расширения.</span><span class="sxs-lookup"><span data-stu-id="5f7b3-137">A unique identifier for the extension.</span></span> <span data-ttu-id="5f7b3-138">Если расширение, которое имеет этот идентификатор уже был добавлен в проект, он будет не предложено добавить его снова.</span><span class="sxs-lookup"><span data-stu-id="5f7b3-138">If the extension that has this ID has already been added to the project, the user will not be prompted to add it again.</span></span>|
|`Version`|<span data-ttu-id="5f7b3-139">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="5f7b3-139">Required.</span></span> <span data-ttu-id="5f7b3-140">Номер версии для шаблона элемента.</span><span class="sxs-lookup"><span data-stu-id="5f7b3-140">A version number for the item template.</span></span>|
|`AssemblyFullName`|<span data-ttu-id="5f7b3-141">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="5f7b3-141">Optional.</span></span> <span data-ttu-id="5f7b3-142">Имя сборки.</span><span class="sxs-lookup"><span data-stu-id="5f7b3-142">An assembly name.</span></span> <span data-ttu-id="5f7b3-143">При добавлении в проект ссылку на эту сборку, пользователю будет предложено добавить `My` расширения на основе этого шаблона элемента.</span><span class="sxs-lookup"><span data-stu-id="5f7b3-143">When a reference to this assembly is added to the project, the user will be prompted to add the `My` extension from this item template.</span></span>|

### <a name="add-the-customdatasignature-element-to-the-vstemplate-file"></a><span data-ttu-id="5f7b3-144">Добавить \<CustomDataSignature > элемент VSTEMPLATE-файл</span><span class="sxs-lookup"><span data-stu-id="5f7b3-144">Add the \<CustomDataSignature> element to the .vstemplate file</span></span>

<span data-ttu-id="5f7b3-145">Для идентификации элемента шаблона Visual Studio как `My` расширение пространства имен, необходимо также изменить файл VSTEMPLATE для шаблона элемента.</span><span class="sxs-lookup"><span data-stu-id="5f7b3-145">To identify your Visual Studio item template as a `My` namespace extension, you must also modify the .vstemplate file for your item template.</span></span> <span data-ttu-id="5f7b3-146">Необходимо добавить `<CustomDataSignature>` элемент `<TemplateData>` элемент.</span><span class="sxs-lookup"><span data-stu-id="5f7b3-146">You must add a `<CustomDataSignature>` element to the `<TemplateData>` element.</span></span> <span data-ttu-id="5f7b3-147">`<CustomDataSignature>` Элемент должен содержать текст `Microsoft.VisualBasic.MyExtension`, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="5f7b3-147">The `<CustomDataSignature>` element must contain the text `Microsoft.VisualBasic.MyExtension`, as shown in the following example.</span></span>

```xml
<CustomDataSignature>Microsoft.VisualBasic.MyExtension</CustomDataSignature>
```

<span data-ttu-id="5f7b3-148">Нельзя напрямую изменять файлы в сжатую папку (ZIP-файл).</span><span class="sxs-lookup"><span data-stu-id="5f7b3-148">You cannot modify files in a compressed folder (.zip file) directly.</span></span> <span data-ttu-id="5f7b3-149">Необходимо скопировать файл VSTEMPLATE из сжатой папки, измените его и затем заменить файл VSTEMPLATE в сжатой папке обновленной версией.</span><span class="sxs-lookup"><span data-stu-id="5f7b3-149">You must copy the .vstemplate file from the compressed folder, modify it, and then replace the .vstemplate file in the compressed folder with your updated copy.</span></span>

<span data-ttu-id="5f7b3-150">В следующем примере показано содержимое VSTEMPLATE-файл, имеющий `<CustomDataSignature>` добавлен указанный элемент.</span><span class="sxs-lookup"><span data-stu-id="5f7b3-150">The following example shows the contents of a .vstemplate file that has the `<CustomDataSignature>` element added.</span></span>

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

## <a name="install-the-template"></a><span data-ttu-id="5f7b3-151">Установка шаблона</span><span class="sxs-lookup"><span data-stu-id="5f7b3-151">Install the template</span></span>

<span data-ttu-id="5f7b3-152">Чтобы установить шаблон, можно скопировать сжатую папку (*ZIP-файл* файл) в папку Шаблоны элементов Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="5f7b3-152">To install the template, you can copy the compressed folder (*.zip* file) to the Visual Basic item templates folder.</span></span> <span data-ttu-id="5f7b3-153">По умолчанию, пользовательских шаблонов элементов находятся в *%USERPROFILE%\Documents\Visual Studio \<версии\>\Templates\ItemTemplates\Visual Basic*.</span><span class="sxs-lookup"><span data-stu-id="5f7b3-153">By default, user item templates are located in *%USERPROFILE%\Documents\Visual Studio \<Version\>\Templates\ItemTemplates\Visual Basic*.</span></span> <span data-ttu-id="5f7b3-154">Кроме того, можно опубликовать шаблон, как Visual Studio Installer (*.vsi*) файла.</span><span class="sxs-lookup"><span data-stu-id="5f7b3-154">Alternatively, you can publish the template as a Visual Studio Installer (*.vsi*) file.</span></span>

## <a name="see-also"></a><span data-ttu-id="5f7b3-155">См. также</span><span class="sxs-lookup"><span data-stu-id="5f7b3-155">See also</span></span>

- [<span data-ttu-id="5f7b3-156">Расширение пространства имен My в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="5f7b3-156">Extending the My Namespace in Visual Basic</span></span>](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-my-namespace.md)
- [<span data-ttu-id="5f7b3-157">Расширение модели приложения Visual Basic</span><span class="sxs-lookup"><span data-stu-id="5f7b3-157">Extending the Visual Basic Application Model</span></span>](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-visual-basic-application-model.md)
- [<span data-ttu-id="5f7b3-158">Настройка доступа к объектам через My</span><span class="sxs-lookup"><span data-stu-id="5f7b3-158">Customizing Which Objects are Available in My</span></span>](../../../visual-basic/developing-apps/customizing-extending-my/customizing-which-objects-are-available-in-my.md)
- [<span data-ttu-id="5f7b3-159">Страница "Мои расширения", конструктор проектов</span><span class="sxs-lookup"><span data-stu-id="5f7b3-159">My Extensions Page, Project Designer</span></span>](/visualstudio/ide/reference/my-extensions-page-project-designer-visual-basic)

---
title: "Практическое руководство: Включение XML IntelliSense в Visual Basic | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- XML IntelliSense [Visual Basic]
- XML [Visual Basic], IntelliSense
- IntelliSense [Visual Basic], XML
ms.assetid: af67d0ee-a4a6-4abf-9c07-5a8cfe80d111
caps.latest.revision: 25
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
ms.sourcegitcommit: 31905a37f09db5f5192123f0118252fbe8b02eff
ms.openlocfilehash: e367016c93586ad34492628b6a4384a5ef1b6acd
ms.contentlocale: ru-ru
ms.lasthandoff: 05/26/2017

---
# <a name="how-to-enable-xml-intellisense-in-visual-basic"></a><span data-ttu-id="5f89a-102">Практическое руководство. Включение XML IntelliSense в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="5f89a-102">How to: Enable XML IntelliSense in Visual Basic</span></span>
<span data-ttu-id="5f89a-103">XML IntelliSense в Visual Basic предоставляет завершение слов для элементов, определенных в схеме XML.</span><span class="sxs-lookup"><span data-stu-id="5f89a-103">XML IntelliSense in Visual Basic provides word completion for elements that are defined in an XML schema.</span></span> <span data-ttu-id="5f89a-104">Включение XML IntelliSense в Visual Basic, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="5f89a-104">To enable XML IntelliSense in Visual Basic, you must do the following:</span></span>  
  
1.  <span data-ttu-id="5f89a-105">Получите файл XML-схемы (XSD) или файлы для файлов XML, которые приложение будет считывать или записи.</span><span class="sxs-lookup"><span data-stu-id="5f89a-105">Obtain the XML schema (XSD) file or files for the XML files that your application will read from or write to.</span></span>  
  
2.  <span data-ttu-id="5f89a-106">Включите файлы схемы XML в проект.</span><span class="sxs-lookup"><span data-stu-id="5f89a-106">Include the XML schema files in your project.</span></span>  
  
3.  <span data-ttu-id="5f89a-107">Импортируйте целевое пространство имен или пространства имен в файл кода или проект.</span><span class="sxs-lookup"><span data-stu-id="5f89a-107">Import the target namespace or namespaces into your code file or project.</span></span> <span data-ttu-id="5f89a-108">Целевое пространство имен определяется `targetNamespace` или `tns` атрибут XSD-схемы.</span><span class="sxs-lookup"><span data-stu-id="5f89a-108">A target namespace is identified by the `targetNamespace` or `tns` attribute of your XSD schema.</span></span>  
  
     <span data-ttu-id="5f89a-109">Чтобы импортировать целевое пространство имен, используйте `Imports` оператор, или добавьте пространство имен для всех файлов кода в проекте с помощью **ссылки** страницы в конструкторе проектов.</span><span class="sxs-lookup"><span data-stu-id="5f89a-109">To import a target namespace, use the `Imports` statement, or add a namespace for all code files in a project by using the **References** page of the Project Designer.</span></span>  
  
 <span data-ttu-id="5f89a-110">Дополнительные сведения о возможностях XML IntelliSense в Visual Basic см. в разделе [XML IntelliSense в Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/xml-intellisense.md).</span><span class="sxs-lookup"><span data-stu-id="5f89a-110">For more information on the capabilities of XML IntelliSense in Visual Basic, see [XML IntelliSense in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/xml-intellisense.md).</span></span> <span data-ttu-id="5f89a-111">Дополнительные сведения об импорте пространства имен XML см. в разделе [оператор Imports (пространство имен XML)](../../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md) или [страница "ссылки" в конструкторе проектов (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/references-page-project-designer-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="5f89a-111">For more information on importing XML namespaces, see [Imports Statement (XML Namespace)](../../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md) or [References Page, Project Designer (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/references-page-project-designer-visual-basic).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
 <span data-ttu-id="5f89a-112">![ссылка на видео](../../../../visual-basic/programming-guide/language-features/xml/media/playvideo.gif "PlayVideo") для просмотра видеоверсии этого раздела, в разделе [видео: Включение XML IntelliSense в Visual Basic](http://go.microsoft.com/fwlink/?LinkId=102466).</span><span class="sxs-lookup"><span data-stu-id="5f89a-112">![link to video](../../../../visual-basic/programming-guide/language-features/xml/media/playvideo.gif "PlayVideo") For a video version of this topic, see [Video How to: Enable XML IntelliSense in Visual Basic](http://go.microsoft.com/fwlink/?LinkId=102466).</span></span> <span data-ttu-id="5f89a-113">Связанные демонстрационные видеоролики см. в разделе [как мне Включение XML IntelliSense и пространства имен XML используйте?](http://go.microsoft.com/fwlink/?LinkId=143035).</span><span class="sxs-lookup"><span data-stu-id="5f89a-113">For a related video demonstration, see [How Do I Enable XML IntelliSense and Use XML Namespaces?](http://go.microsoft.com/fwlink/?LinkId=143035).</span></span>  
  
## <a name="enable-xml-intellisense-in-visual-basic"></a><span data-ttu-id="5f89a-114">Включение XML IntelliSense в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="5f89a-114">Enable XML IntelliSense in Visual Basic</span></span>  
 <span data-ttu-id="5f89a-115">Если имеется файл XML, но нет файла XSD-схемы для него, в пакете обновления&1; можно создать файл схемы XSD с помощью XML для мастера схем.</span><span class="sxs-lookup"><span data-stu-id="5f89a-115">If you have an XML file but you do not have an XSD schema file for it, in SP1 you can create an XSD schema file by using the XML to Schema Wizard.</span></span> <span data-ttu-id="5f89a-116">Можно также использовать вывода схемы в XML-редакторе Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="5f89a-116">You can also use schema inference in the Visual Studio XML Editor.</span></span>  
  
#### <a name="to-create-an-xsd-schema-file-for-an-xml-file-by-using-the-xml-to-schema-wizard-requires-sp1"></a><span data-ttu-id="5f89a-117">Создание файла схемы XSD для XML-файла с помощью XML для мастера схем (требуется пакет обновлений&1;)</span><span class="sxs-lookup"><span data-stu-id="5f89a-117">To create an XSD schema file for an XML file by using the XML to Schema Wizard (requires SP1)</span></span>  
  
1.  <span data-ttu-id="5f89a-118">В проекте, щелкните **Добавление нового элемента** на **проекта** меню.</span><span class="sxs-lookup"><span data-stu-id="5f89a-118">In your project, click **Add New Item** on the **Project** menu.</span></span>  
  
2.  <span data-ttu-id="5f89a-119">Выберите **Xml to Schema** шаблона элемента, либо от **данные** или **Общие элементы** категорий шаблонов.</span><span class="sxs-lookup"><span data-stu-id="5f89a-119">Select the **Xml to Schema** item template from either the **Data** or **Common Items** template categories.</span></span>  
  
3.  <span data-ttu-id="5f89a-120">Укажите имя файла для XSD-файла или файлов, которые будут храниться в производного набора схем и нажмите кнопку **добавить**.</span><span class="sxs-lookup"><span data-stu-id="5f89a-120">Provide a file name for the XSD file or files that the inferred schema set will be stored in, and then click **Add**.</span></span>  
  
4.  <span data-ttu-id="5f89a-121">В **определение XML набора схем из XML-документов** окна, добавьте один или несколько XML-документов для определения набора схем XML.</span><span class="sxs-lookup"><span data-stu-id="5f89a-121">In the **Infer XML Schema set from XML documents** window, add one or more XML documents to infer the XML schema set from.</span></span>  
  
    -   <span data-ttu-id="5f89a-122">Чтобы добавить текстовые файлы, содержащие XML-документов с помощью проводника, щелкните **добавить из файла**.</span><span class="sxs-lookup"><span data-stu-id="5f89a-122">To add text files that contain XML documents by using File Explorer, click **Add from File**.</span></span>  
  
    -   <span data-ttu-id="5f89a-123">Чтобы добавить XML-документ из HTTP-адреса, щелкните **добавить из Интернета**.</span><span class="sxs-lookup"><span data-stu-id="5f89a-123">To add an XML document from an HTTP address, click **Add from Web**.</span></span>  
  
    -   <span data-ttu-id="5f89a-124">Чтобы скопировать или напечатать содержимое XML-документа в мастере, щелкните **ввод или вставка XML**.</span><span class="sxs-lookup"><span data-stu-id="5f89a-124">To copy or type the contents of an XML document into the wizard, click **Type or paste XML**.</span></span>  
  
5.  <span data-ttu-id="5f89a-125">После указания всех источников XML-документов из которых нужно получить набор схем XML, нажмите кнопку **ОК** для определения схем XML значение.</span><span class="sxs-lookup"><span data-stu-id="5f89a-125">When you have specified all the XML document sources from which you want to infer the XML schema set, click **OK** to infer the XML schema set.</span></span> <span data-ttu-id="5f89a-126">Набор схем сохраняется в папку проекта в один или несколько файлов XSD.</span><span class="sxs-lookup"><span data-stu-id="5f89a-126">The schema set is saved in your project folder in one or more XSD files.</span></span> <span data-ttu-id="5f89a-127">(Для каждого пространства имен XML в схеме создается файл.)</span><span class="sxs-lookup"><span data-stu-id="5f89a-127">(For each XML namespace in the schema, a file is created.)</span></span>  
  
#### <a name="to-create-an-xsd-schema-file-for-an-xml-file-by-using-schema-inference-in-the-visual-studio-xml-editor"></a><span data-ttu-id="5f89a-128">Создание файла схемы XSD для XML-файла с помощью вывода схемы в XML-редакторе Visual Studio</span><span class="sxs-lookup"><span data-stu-id="5f89a-128">To create an XSD schema file for an XML file by using schema inference in the Visual Studio XML Editor</span></span>  
  
1.  <span data-ttu-id="5f89a-129">Изменение XML-файла в конструкторе Visual Studio XML.</span><span class="sxs-lookup"><span data-stu-id="5f89a-129">Edit the XML file in the Visual Studio XML Designer.</span></span>  
  
2.  <span data-ttu-id="5f89a-130">Когда курсор находится где-нибудь в XML-файле **XML** появится меню.</span><span class="sxs-lookup"><span data-stu-id="5f89a-130">When the cursor is somewhere in the XML file, the **XML** menu appears.</span></span> <span data-ttu-id="5f89a-131">Щелкните **Create Schema** на **XML** меню.</span><span class="sxs-lookup"><span data-stu-id="5f89a-131">Click **Create Schema** on the **XML** menu.</span></span> <span data-ttu-id="5f89a-132">XSD-файл создается из XSD-схемы из XML-файла.</span><span class="sxs-lookup"><span data-stu-id="5f89a-132">An XSD file is created from XSD schema inferred from the XML file.</span></span>  
  
3.  <span data-ttu-id="5f89a-133">Сохраните файл схемы XSD.</span><span class="sxs-lookup"><span data-stu-id="5f89a-133">Save the XSD schema file.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="5f89a-134">Разные XSD-схемы могут быть получены из нескольких XML-документов, которые предназначены для одной и той же схемы.</span><span class="sxs-lookup"><span data-stu-id="5f89a-134">Different XSD schemas might be inferred from multiple XML documents that are intended to have the same schema.</span></span> <span data-ttu-id="5f89a-135">Это может произойти, когда определенные элементы и атрибуты находятся в одном XML-файле, а не в другом, или элементы включены в другом порядке.</span><span class="sxs-lookup"><span data-stu-id="5f89a-135">This can occur when particular elements and attributes are found in one XML file and not in another, or when elements are included in different order, for example.</span></span> <span data-ttu-id="5f89a-136">Если вы изучите XSD-схемы для полноты и точности.</span><span class="sxs-lookup"><span data-stu-id="5f89a-136">You should review inferred XSD schemas for completeness and accuracy when you use XSD schema inference.</span></span>  
  
#### <a name="to-include-an-xsd-schema-file"></a><span data-ttu-id="5f89a-137">Для включения файла схемы XSD</span><span class="sxs-lookup"><span data-stu-id="5f89a-137">To include an XSD schema file</span></span>  
  
-   <span data-ttu-id="5f89a-138">По умолчанию не отображается XSD-файлов в проектах Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="5f89a-138">By default, you cannot see XSD files in Visual Basic projects.</span></span> <span data-ttu-id="5f89a-139">Если XSD-файл уже имеется в папках для проекта, нажмите кнопку **Показать все файлы** кнопки в **обозревателе решений**.</span><span class="sxs-lookup"><span data-stu-id="5f89a-139">If your XSD file is already included in the folders for your project, click the **Show All Files** button in **Solution Explorer**.</span></span> <span data-ttu-id="5f89a-140">Найдите XSD-файл в **обозревателе решений**, щелкните правой кнопкой мыши файл и нажмите кнопку **включить файл в проект**.</span><span class="sxs-lookup"><span data-stu-id="5f89a-140">Locate the XSD file in **Solution Explorer**, right-click the file, and click **Include File in Project**.</span></span>  
  
-   <span data-ttu-id="5f89a-141">Если XSD-файл еще не входит в проект, в **обозревателе решений**, щелкните правой кнопкой мыши папку, в которой требуется сохранить XSD-файл, выберите пункт **добавить**и нажмите кнопку **существующий элемент**.</span><span class="sxs-lookup"><span data-stu-id="5f89a-141">If your XSD file is not already part of your project, in **Solution Explorer**, right-click the folder in which you want to store the XSD file, point to **Add**, and then click **Existing Item**.</span></span> <span data-ttu-id="5f89a-142">Найдите XSD-файл и нажмите кнопку **добавить**.</span><span class="sxs-lookup"><span data-stu-id="5f89a-142">Locate your XSD file and then click **Add**.</span></span>  
  
#### <a name="to-import-an-xml-namespace-in-a-code-file"></a><span data-ttu-id="5f89a-143">Чтобы импортировать пространство имен XML в файле кода</span><span class="sxs-lookup"><span data-stu-id="5f89a-143">To import an XML namespace in a code file</span></span>  
  
1.  <span data-ttu-id="5f89a-144">Определение целевого пространства имен из XSD-схемы.</span><span class="sxs-lookup"><span data-stu-id="5f89a-144">Identify the target namespace from your XSD schema.</span></span>  
  
2.  <span data-ttu-id="5f89a-145">Добавьте в начало файла с кодом `Imports` инструкции для целевого пространства имен XML, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="5f89a-145">At the beginning of the code file, add an `Imports` statement for the target XML namespace, as shown in the following example.</span></span>  
  
     <span data-ttu-id="5f89a-146">[!code-vb[VbXMLSamples&#1;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-enable-xml-intellisense_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="5f89a-146">[!code-vb[VbXMLSamples#1](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-enable-xml-intellisense_1.vb)]</span></span>  
  
     <span data-ttu-id="5f89a-147">Чтобы импортировать пространство имен XML как пространство имен по умолчанию, то есть, пространство имен, которое применяется к XML-элементов и атрибутов, которые не имеют префикса пространства имен, добавьте `Imports` инструкции для конечного пространства имен XML по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="5f89a-147">To import an XML namespace as the default namespace, that is, the namespace that is applied to XML elements and attributes that do not have a namespace prefix, add an `Imports` statement for the target default XML namespace.</span></span> <span data-ttu-id="5f89a-148">Не указывайте префикс пространства имен.</span><span class="sxs-lookup"><span data-stu-id="5f89a-148">Do not specify a namespace prefix.</span></span> <span data-ttu-id="5f89a-149">Ниже приведен пример `Imports` инструкции.</span><span class="sxs-lookup"><span data-stu-id="5f89a-149">Following is an example of an `Imports` statement.</span></span>  
  
     <span data-ttu-id="5f89a-150">[!code-vb[VbXmlSamples&#50;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-enable-xml-intellisense_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="5f89a-150">[!code-vb[VbXmlSamples#50](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-enable-xml-intellisense_2.vb)]</span></span>  
  
#### <a name="to-import-an-xml-namespace-for-all-files-in-a-project"></a><span data-ttu-id="5f89a-151">Чтобы импортировать пространство имен XML для всех файлов в проекте</span><span class="sxs-lookup"><span data-stu-id="5f89a-151">To import an XML namespace for all files in a project</span></span>  
  
1.  <span data-ttu-id="5f89a-152">Пространство имен XML, импортированные в файле кода применяется к только что файл кода.</span><span class="sxs-lookup"><span data-stu-id="5f89a-152">An XML namespace imported in a code file applies to that code file only.</span></span> <span data-ttu-id="5f89a-153">Чтобы импортировать пространство имен XML, который применяется ко всем файлам кода в проекте, откройте конструктор проектов, дважды щелкнув **Мой проект** в **обозревателе решений**.</span><span class="sxs-lookup"><span data-stu-id="5f89a-153">To import an XML namespace that applies to all code files in a project, open the Project Designer by double-clicking **My Project** in **Solution Explorer**.</span></span>  
  
2.  <span data-ttu-id="5f89a-154">На **ссылки** вкладке **импортированные пространства имен** введите конечное пространство имен XML в виде полного объявления пространства имен XML (например, `<xmlns: ns="http://sampleNamespace">`).</span><span class="sxs-lookup"><span data-stu-id="5f89a-154">On the **References** tab, in the **Imported namespaces** box, type the target XML namespace in the form of a full XML namespace declaration (for example, `<xmlns: ns="http://sampleNamespace">`).</span></span> <span data-ttu-id="5f89a-155">Если целевое пространство имен XML не указывает префикс пространства имен, пространство имен будет пространство имен XML по умолчанию для проекта.</span><span class="sxs-lookup"><span data-stu-id="5f89a-155">If the target XML namespace does not specify a namespace prefix, the namespace will be the default XML namespace for the project.</span></span>  
  
3.  <span data-ttu-id="5f89a-156">Щелкните **добавить пользовательский импорт**.</span><span class="sxs-lookup"><span data-stu-id="5f89a-156">Click **Add User Import**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f89a-157">См. также</span><span class="sxs-lookup"><span data-stu-id="5f89a-157">See Also</span></span>  
 <span data-ttu-id="5f89a-158">[Оператор Imports (пространство имен XML)](../../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md) </span><span class="sxs-lookup"><span data-stu-id="5f89a-158">[Imports Statement (XML Namespace)](../../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md) </span></span>  
<span data-ttu-id="5f89a-159"> [Страница "Ссылки" в конструкторе проектов (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/references-page-project-designer-visual-basic) </span><span class="sxs-lookup"><span data-stu-id="5f89a-159"> [References Page, Project Designer (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/references-page-project-designer-visual-basic) </span></span>  
<span data-ttu-id="5f89a-160"> [XML IntelliSense в Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/xml-intellisense.md)</span><span class="sxs-lookup"><span data-stu-id="5f89a-160"> [XML IntelliSense in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/xml-intellisense.md)</span></span>


---
title: "Пошаговое руководство: Внедрение сведений о типах из сборок Microsoft Office в Visual Studio (Visual Basic) | Документы Microsoft"
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
ms.assetid: 26b44286-5066-4ad4-8e6a-c24902be347c
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 31905a37f09db5f5192123f0118252fbe8b02eff
ms.openlocfilehash: c527941d6eae56d66cbede92ced3f66d24937354
ms.contentlocale: ru-ru
ms.lasthandoff: 05/26/2017

---
# <a name="walkthrough-embedding-type-information-from-microsoft-office-assemblies-in-visual-studio-visual-basic"></a><span data-ttu-id="1351a-102">Пошаговое руководство: Внедрение сведений о типах из сборок Microsoft Office в Visual Studio (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1351a-102">Walkthrough: Embedding Type Information from Microsoft Office Assemblies in Visual Studio (Visual Basic)</span></span>
<span data-ttu-id="1351a-103">Если внедрить сведения о типах в приложении, которое ссылается на COM-объекты, можно исключить потребность в основной сборки взаимодействия (PIA).</span><span class="sxs-lookup"><span data-stu-id="1351a-103">If you embed type information in an application that references COM objects, you can eliminate the need for a primary interop assembly (PIA).</span></span> <span data-ttu-id="1351a-104">Кроме того внедренные сведения о типах позволяет обеспечить независимость от версии приложения.</span><span class="sxs-lookup"><span data-stu-id="1351a-104">Additionally, the embedded type information enables you to achieve version independence for your application.</span></span> <span data-ttu-id="1351a-105">То есть программы могут записываться использовать типы из нескольких версий библиотеки COM без конкретной основной сборки ВЗАИМОДЕЙСТВИЯ для каждой версии.</span><span class="sxs-lookup"><span data-stu-id="1351a-105">That is, your program can be written to use types from multiple versions of a COM library without requiring a specific PIA for each version.</span></span> <span data-ttu-id="1351a-106">Это типично для приложений, использующих объекты из библиотек Microsoft Office.</span><span class="sxs-lookup"><span data-stu-id="1351a-106">This is a common scenario for applications that use objects from Microsoft Office libraries.</span></span> <span data-ttu-id="1351a-107">Внедрение данных о типе позволяет одному построению программы работать с различными версиями Microsoft Office на разных компьютерах без необходимости повторного развертывания программы или основной сборки ВЗАИМОДЕЙСТВИЯ для каждой версии Microsoft Office.</span><span class="sxs-lookup"><span data-stu-id="1351a-107">Embedding type information enables the same build of a program to work with different versions of Microsoft Office on different computers without the need to redeploy either the program or the PIA for each version of Microsoft Office.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="prerequisites"></a><span data-ttu-id="1351a-108">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="1351a-108">Prerequisites</span></span>  
 <span data-ttu-id="1351a-109">Необходимо выполнить следующие требования.</span><span class="sxs-lookup"><span data-stu-id="1351a-109">This walkthrough requires the following:</span></span>  
  
-   <span data-ttu-id="1351a-110">Компьютер, на котором установлена Visual Studio и Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="1351a-110">A computer on which Visual Studio and Microsoft Excel are installed.</span></span>  
  
-   <span data-ttu-id="1351a-111">Второй компьютер, на котором установлена .NET Framework 4 или более поздней версии и разными версиями Excel.</span><span class="sxs-lookup"><span data-stu-id="1351a-111">A second computer on which the .NET Framework 4 or higher and a different version of Excel are installed.</span></span>  
  
##  <span data-ttu-id="1351a-112"><a name="BKMK_createapp"></a>Чтобы создать приложение, которое работает с различными версиями Microsoft Office</span><span class="sxs-lookup"><span data-stu-id="1351a-112"><a name="BKMK_createapp"></a> To create an application that works with multiple versions of Microsoft Office</span></span>  
  
1.  <span data-ttu-id="1351a-113">Запустите Visual Studio на компьютере, на котором установлен Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="1351a-113">Start Visual Studio on a computer on which Excel is installed.</span></span>  
  
2.  <span data-ttu-id="1351a-114">В меню **Файл** последовательно выберите пункты **Создать**и **Проект**.</span><span class="sxs-lookup"><span data-stu-id="1351a-114">On the **File** menu, choose **New**, **Project**.</span></span>  
  
3.  <span data-ttu-id="1351a-115">В **новый проект** в диалоговом **типы проектов** область, убедитесь, что **Windows** выбран.</span><span class="sxs-lookup"><span data-stu-id="1351a-115">In the **New Project** dialog box, in the **Project Types** pane, make sure that **Windows** is selected.</span></span> <span data-ttu-id="1351a-116">Выберите **консольное приложение** в **шаблоны** области.</span><span class="sxs-lookup"><span data-stu-id="1351a-116">Select **Console Application** in the **Templates** pane.</span></span> <span data-ttu-id="1351a-117">В **имя** введите `CreateExcelWorkbook`, а затем выберите **ОК** кнопки.</span><span class="sxs-lookup"><span data-stu-id="1351a-117">In the **Name** box, enter `CreateExcelWorkbook`, and then choose the **OK** button.</span></span> <span data-ttu-id="1351a-118">Создан новый проект.</span><span class="sxs-lookup"><span data-stu-id="1351a-118">The new project is created.</span></span>  
  
4.  <span data-ttu-id="1351a-119">Откройте контекстное меню для проекта CreateExcelWorkbook, а затем выберите **свойства**.</span><span class="sxs-lookup"><span data-stu-id="1351a-119">Open the shortcut menu for the CreateExcelWorkbook project and then choose **Properties**.</span></span> <span data-ttu-id="1351a-120">Выберите **ссылки** вкладки.</span><span class="sxs-lookup"><span data-stu-id="1351a-120">Choose the **References** tab.</span></span> <span data-ttu-id="1351a-121">Нажмите кнопку **Добавить** .</span><span class="sxs-lookup"><span data-stu-id="1351a-121">Choose the **Add** button.</span></span>  
  
5.  <span data-ttu-id="1351a-122">На **.NET** выберите последнюю версию `Microsoft.Office.Interop.Excel`.</span><span class="sxs-lookup"><span data-stu-id="1351a-122">On the **.NET** tab, choose the most recent version of `Microsoft.Office.Interop.Excel`.</span></span> <span data-ttu-id="1351a-123">Например **Microsoft.Office.Interop.Excel 14.0.0.0**.</span><span class="sxs-lookup"><span data-stu-id="1351a-123">For example, **Microsoft.Office.Interop.Excel 14.0.0.0**.</span></span> <span data-ttu-id="1351a-124">Нажмите кнопку **ОК** .</span><span class="sxs-lookup"><span data-stu-id="1351a-124">Choose the **OK** button.</span></span>  
  
6.  <span data-ttu-id="1351a-125">В списке ссылок для **CreateExcelWorkbook** проекта, выберите ссылку для `Microsoft.Office.Interop.Excel` , добавленного на предыдущем шаге.</span><span class="sxs-lookup"><span data-stu-id="1351a-125">In the list of references for the **CreateExcelWorkbook** project, select the reference for `Microsoft.Office.Interop.Excel` that you added in the previous step.</span></span> <span data-ttu-id="1351a-126">В **свойства** окна, убедитесь, что `Embed Interop Types` свойству `True`.</span><span class="sxs-lookup"><span data-stu-id="1351a-126">In the **Properties** window, make sure that the `Embed Interop Types` property is set to `True`.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="1351a-127">Приложения, созданного в этом пошаговом руководстве выполняется с различными версиями Microsoft Office благодаря сведениям о внедренного типа взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="1351a-127">The application created in this walkthrough runs with different versions of Microsoft Office because of the embedded interop type information.</span></span> <span data-ttu-id="1351a-128">Если `Embed Interop Types` свойству `False`, должен включать основные сборки ВЗАИМОДЕЙСТВИЯ для каждой версии Microsoft Office, приложение будет работать с.</span><span class="sxs-lookup"><span data-stu-id="1351a-128">If the `Embed Interop Types` property is set to `False`, you must include a PIA for each version of Microsoft Office that the application will run with.</span></span>  
  
7.  <span data-ttu-id="1351a-129">Откройте файл Module1.vb.</span><span class="sxs-lookup"><span data-stu-id="1351a-129">Open the Module1.vb file.</span></span> <span data-ttu-id="1351a-130">Замените код в файле следующим кодом:</span><span class="sxs-lookup"><span data-stu-id="1351a-130">Replace the code in the file with the following code:</span></span>  
  
    ```vb  
    Imports Excel = Microsoft.Office.Interop.Excel  
  
    Module Module1  
  
        Sub Main()  
            Dim values = {4, 6, 18, 2, 1, 76, 0, 3, 11}  
  
            CreateWorkbook(values, "C:\SampleFolder\SampleWorkbook.xls")  
        End Sub  
  
        Sub CreateWorkbook(ByVal values As Integer(), ByVal filePath As String)  
            Dim excelApp As Excel.Application = Nothing  
            Dim wkbk As Excel.Workbook  
            Dim sheet As Excel.Worksheet  
  
            Try  
                ' Start Excel and create a workbook and worksheet.  
                excelApp = New Excel.Application  
                wkbk = excelApp.Workbooks.Add()  
                sheet = CType(wkbk.Sheets.Add(), Excel.Worksheet)  
                sheet.Name = "Sample Worksheet"  
  
                ' Write a column of values.  
                ' In the For loop, both the row index and array index start at 1.  
                ' Therefore the value of 4 at array index 0 is not included.  
                For i = 1 To values.Length - 1  
                    sheet.Cells(i, 1) = values(i)  
                Next  
  
                ' Suppress any alerts and save the file. Create the directory   
                ' if it does not exist. Overwrite the file if it exists.  
                excelApp.DisplayAlerts = False  
                Dim folderPath = My.Computer.FileSystem.GetParentPath(filePath)  
                If Not My.Computer.FileSystem.DirectoryExists(folderPath) Then  
                    My.Computer.FileSystem.CreateDirectory(folderPath)  
                End If  
                wkbk.SaveAs(filePath)  
        Catch  
  
            Finally  
                sheet = Nothing  
                wkbk = Nothing  
  
                ' Close Excel.  
                excelApp.Quit()  
                excelApp = Nothing  
            End Try  
  
        End Sub  
    End Module  
    ```  
  
8.  <span data-ttu-id="1351a-131">Сохраните проект.</span><span class="sxs-lookup"><span data-stu-id="1351a-131">Save the project.</span></span>  
  
9. <span data-ttu-id="1351a-132">Нажмите CTRL + F5, чтобы построить и запустить проект.</span><span class="sxs-lookup"><span data-stu-id="1351a-132">Press CTRL+F5 to build and run the project.</span></span> <span data-ttu-id="1351a-133">Убедитесь, что книга Excel был создан в расположении, указанном в примере кода: C:\SampleFolder\SampleWorkbook.xls.</span><span class="sxs-lookup"><span data-stu-id="1351a-133">Verify that an Excel workbook has been created at the location specified in the example code: C:\SampleFolder\SampleWorkbook.xls.</span></span>  
  
##  <span data-ttu-id="1351a-134"><a name="BKMK_publishapp"></a>Для публикации приложения на компьютере, на котором установлен другой версии Microsoft Office</span><span class="sxs-lookup"><span data-stu-id="1351a-134"><a name="BKMK_publishapp"></a> To publish the application to a computer on which a different version of Microsoft Office is installed</span></span>  
  
1.  <span data-ttu-id="1351a-135">Откройте проект, созданный в ходе этого пошагового руководства в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="1351a-135">Open the project created by this walkthrough in Visual Studio.</span></span>  
  
2.  <span data-ttu-id="1351a-136">На **построения** меню, выберите **CreateExcelWorkbook публикации**.</span><span class="sxs-lookup"><span data-stu-id="1351a-136">On the **Build** menu, choose **Publish CreateExcelWorkbook**.</span></span> <span data-ttu-id="1351a-137">Следуйте указаниям мастера публикации, чтобы создать устанавливаемую версию приложения.</span><span class="sxs-lookup"><span data-stu-id="1351a-137">Follow the steps of the Publish Wizard to create an installable version of the application.</span></span> <span data-ttu-id="1351a-138">Дополнительные сведения см. в разделе [мастер публикации (Разработка решений Office в Visual Studio)](https://msdn.microsoft.com/library/bb625071).</span><span class="sxs-lookup"><span data-stu-id="1351a-138">For more information, see [Publish Wizard (Office Development in Visual Studio)](https://msdn.microsoft.com/library/bb625071).</span></span>  
  
3.  <span data-ttu-id="1351a-139">Установите приложение на компьютере, на котором установлена .NET Framework 4 или более поздней версии и разными версиями Excel.</span><span class="sxs-lookup"><span data-stu-id="1351a-139">Install the application on a computer on which the .NET Framework 4 or higher and a different version of Excel are installed.</span></span>  
  
4.  <span data-ttu-id="1351a-140">После завершения установки запустите установленную программу.</span><span class="sxs-lookup"><span data-stu-id="1351a-140">When the installation is finished, run the installed program.</span></span>  
  
5.  <span data-ttu-id="1351a-141">Убедитесь, что книга Excel был создан в расположении, указанном в образце кода: C:\SampleFolder\SampleWorkbook.xls.</span><span class="sxs-lookup"><span data-stu-id="1351a-141">Verify that an Excel workbook has been created at the location specified in the sample code: C:\SampleFolder\SampleWorkbook.xls.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1351a-142">См. также</span><span class="sxs-lookup"><span data-stu-id="1351a-142">See Also</span></span>  
 <span data-ttu-id="1351a-143">[Пошаговое руководство: Внедрение типов из управляемых сборок в Visual Studio (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/walkthrough-embedding-types-from-managed-assemblies-in-vs.md) </span><span class="sxs-lookup"><span data-stu-id="1351a-143">[Walkthrough: Embedding Types from Managed Assemblies in Visual Studio (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/walkthrough-embedding-types-from-managed-assemblies-in-vs.md) </span></span>  
<span data-ttu-id="1351a-144"> [/ LINK (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/link.md)</span><span class="sxs-lookup"><span data-stu-id="1351a-144"> [/link (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/link.md)</span></span>


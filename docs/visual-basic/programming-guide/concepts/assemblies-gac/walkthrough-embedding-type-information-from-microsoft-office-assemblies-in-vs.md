---
title: 'Пошаговое руководство: Внедрение сведений о типах из сборок Microsoft Office в Visual Studio (Visual Basic)'
ms.date: 07/20/2015
ms.assetid: 26b44286-5066-4ad4-8e6a-c24902be347c
ms.openlocfilehash: 6a28e95f9c3cfcc2481c8f4f9f83303648df43cd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33643826"
---
# <a name="walkthrough-embedding-type-information-from-microsoft-office-assemblies-in-visual-studio-visual-basic"></a><span data-ttu-id="30b0a-102">Пошаговое руководство: Внедрение сведений о типах из сборок Microsoft Office в Visual Studio (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="30b0a-102">Walkthrough: Embedding Type Information from Microsoft Office Assemblies in Visual Studio (Visual Basic)</span></span>
<span data-ttu-id="30b0a-103">Если в приложение, имеющее ссылки на COM-объекты, внедрены данные о типе, можно исключить необходимость использования основной сборки взаимодействия (PIA).</span><span class="sxs-lookup"><span data-stu-id="30b0a-103">If you embed type information in an application that references COM objects, you can eliminate the need for a primary interop assembly (PIA).</span></span> <span data-ttu-id="30b0a-104">Кроме того внедренные данные о типах позволяют создать приложение, не зависящее от версии.</span><span class="sxs-lookup"><span data-stu-id="30b0a-104">Additionally, the embedded type information enables you to achieve version independence for your application.</span></span> <span data-ttu-id="30b0a-105">Это означает, что в программе можно использовать типы из нескольких версий библиотеки COM, т. е. необходимость использования конкретной основной сборки взаимодействия для каждой версии библиотеки COM отпадает.</span><span class="sxs-lookup"><span data-stu-id="30b0a-105">That is, your program can be written to use types from multiple versions of a COM library without requiring a specific PIA for each version.</span></span> <span data-ttu-id="30b0a-106">Это стандартный сценарий для приложений, использующих объекты из библиотек Microsoft Office.</span><span class="sxs-lookup"><span data-stu-id="30b0a-106">This is a common scenario for applications that use objects from Microsoft Office libraries.</span></span> <span data-ttu-id="30b0a-107">Внедрение данных о типе позволяет одной сборке программы работать с разными версиями приложения Microsoft Office на разных компьютерах без необходимости повторного развертывания программы или основной сборки взаимодействия для каждой версии приложения Microsoft Office.</span><span class="sxs-lookup"><span data-stu-id="30b0a-107">Embedding type information enables the same build of a program to work with different versions of Microsoft Office on different computers without the need to redeploy either the program or the PIA for each version of Microsoft Office.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="prerequisites"></a><span data-ttu-id="30b0a-108">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="30b0a-108">Prerequisites</span></span>  
 <span data-ttu-id="30b0a-109">Необходимо выполнить следующие требования.</span><span class="sxs-lookup"><span data-stu-id="30b0a-109">This walkthrough requires the following:</span></span>  
  
-   <span data-ttu-id="30b0a-110">Компьютер, на котором установлена среда Visual Studio и приложение Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="30b0a-110">A computer on which Visual Studio and Microsoft Excel are installed.</span></span>  
  
-   <span data-ttu-id="30b0a-111">Второй компьютер, на котором установлена платформа .NET Framework 4 или более поздняя версия и другая версия Excel.</span><span class="sxs-lookup"><span data-stu-id="30b0a-111">A second computer on which the .NET Framework 4 or higher and a different version of Excel are installed.</span></span>  
  
##  <a name="BKMK_createapp"></a> <span data-ttu-id="30b0a-112">Создание приложения, работающего с несколькими версиями Microsoft Office</span><span class="sxs-lookup"><span data-stu-id="30b0a-112">To create an application that works with multiple versions of Microsoft Office</span></span>  
  
1.  <span data-ttu-id="30b0a-113">Запустите Visual Studio на компьютере, на котором установлено приложение Excel.</span><span class="sxs-lookup"><span data-stu-id="30b0a-113">Start Visual Studio on a computer on which Excel is installed.</span></span>  
  
2.  <span data-ttu-id="30b0a-114">В меню **Файл** последовательно выберите пункты **Создать**и **Проект**.</span><span class="sxs-lookup"><span data-stu-id="30b0a-114">On the **File** menu, choose **New**, **Project**.</span></span>  
  
3.  <span data-ttu-id="30b0a-115">Убедитесь, что в диалоговом окне **Создание проекта** в области **Типы проектов** выбран пункт **Windows**.</span><span class="sxs-lookup"><span data-stu-id="30b0a-115">In the **New Project** dialog box, in the **Project Types** pane, make sure that **Windows** is selected.</span></span> <span data-ttu-id="30b0a-116">В области **Шаблоны** выберите пункт **Консольное приложение**.</span><span class="sxs-lookup"><span data-stu-id="30b0a-116">Select **Console Application** in the **Templates** pane.</span></span> <span data-ttu-id="30b0a-117">В поле **Имя** введите `CreateExcelWorkbook`, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="30b0a-117">In the **Name** box, enter `CreateExcelWorkbook`, and then choose the **OK** button.</span></span> <span data-ttu-id="30b0a-118">Проект создан.</span><span class="sxs-lookup"><span data-stu-id="30b0a-118">The new project is created.</span></span>  
  
4.  <span data-ttu-id="30b0a-119">Откройте контекстное меню для проекта CreateExcelWorkbook, а затем выберите **свойства**.</span><span class="sxs-lookup"><span data-stu-id="30b0a-119">Open the shortcut menu for the CreateExcelWorkbook project and then choose **Properties**.</span></span> <span data-ttu-id="30b0a-120">Выберите **ссылки** вкладки. Нажмите кнопку **Добавить** .</span><span class="sxs-lookup"><span data-stu-id="30b0a-120">Choose the **References** tab. Choose the **Add** button.</span></span>  
  
5.  <span data-ttu-id="30b0a-121">На вкладке **.NET** выберите самую последнюю версию `Microsoft.Office.Interop.Excel`.</span><span class="sxs-lookup"><span data-stu-id="30b0a-121">On the **.NET** tab, choose the most recent version of `Microsoft.Office.Interop.Excel`.</span></span> <span data-ttu-id="30b0a-122">Например, **Microsoft.Office.Interop.Excel 14.0.0.0**.</span><span class="sxs-lookup"><span data-stu-id="30b0a-122">For example, **Microsoft.Office.Interop.Excel 14.0.0.0**.</span></span> <span data-ttu-id="30b0a-123">Нажмите кнопку **ОК** .</span><span class="sxs-lookup"><span data-stu-id="30b0a-123">Choose the **OK** button.</span></span>  
  
6.  <span data-ttu-id="30b0a-124">В списке ссылок для проекта **CreateExcelWorkbook** выберите ссылку для `Microsoft.Office.Interop.Excel`, добавленную на предыдущем шаге.</span><span class="sxs-lookup"><span data-stu-id="30b0a-124">In the list of references for the **CreateExcelWorkbook** project, select the reference for `Microsoft.Office.Interop.Excel` that you added in the previous step.</span></span> <span data-ttu-id="30b0a-125">Убедитесь, что в окне **Свойства`Embed Interop Types` свойство**  имеет значение `True`.</span><span class="sxs-lookup"><span data-stu-id="30b0a-125">In the **Properties** window, make sure that the `Embed Interop Types` property is set to `True`.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="30b0a-126">Приложение, созданное в ходе данного пошагового руководства, запускается с разными версиями Microsoft Office, поскольку содержит внедренные данные о типе сборки взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="30b0a-126">The application created in this walkthrough runs with different versions of Microsoft Office because of the embedded interop type information.</span></span> <span data-ttu-id="30b0a-127">Если свойство `Embed Interop Types` имеет значение `False`, необходимо добавить основную сборку взаимодействия для каждой версии Microsoft Office, с которой будет запускаться приложение.</span><span class="sxs-lookup"><span data-stu-id="30b0a-127">If the `Embed Interop Types` property is set to `False`, you must include a PIA for each version of Microsoft Office that the application will run with.</span></span>  
  
7.  <span data-ttu-id="30b0a-128">Откройте файл Module1.vb.</span><span class="sxs-lookup"><span data-stu-id="30b0a-128">Open the Module1.vb file.</span></span> <span data-ttu-id="30b0a-129">Замените код в файле следующим кодом:</span><span class="sxs-lookup"><span data-stu-id="30b0a-129">Replace the code in the file with the following code:</span></span>  
  
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
  
8.  <span data-ttu-id="30b0a-130">Сохраните проект.</span><span class="sxs-lookup"><span data-stu-id="30b0a-130">Save the project.</span></span>  
  
9. <span data-ttu-id="30b0a-131">Нажмите сочетание клавиш CTRL+F5, чтобы собрать и запустить проект.</span><span class="sxs-lookup"><span data-stu-id="30b0a-131">Press CTRL+F5 to build and run the project.</span></span> <span data-ttu-id="30b0a-132">Убедитесь, что книга Excel была создана в расположении, указанном в примере кода: C:\SampleFolder\SampleWorkbook.xls.</span><span class="sxs-lookup"><span data-stu-id="30b0a-132">Verify that an Excel workbook has been created at the location specified in the example code: C:\SampleFolder\SampleWorkbook.xls.</span></span>  
  
##  <a name="BKMK_publishapp"></a> <span data-ttu-id="30b0a-133">Публикация приложения на компьютере, на котором установлены разные версии Microsoft Office</span><span class="sxs-lookup"><span data-stu-id="30b0a-133">To publish the application to a computer on which a different version of Microsoft Office is installed</span></span>  
  
1.  <span data-ttu-id="30b0a-134">В Visual Studio откройте проект, созданный в ходе этого пошагового руководства.</span><span class="sxs-lookup"><span data-stu-id="30b0a-134">Open the project created by this walkthrough in Visual Studio.</span></span>  
  
2.  <span data-ttu-id="30b0a-135">В меню **Сборка** выберите **Опубликовать CreateExcelWorkbook**.</span><span class="sxs-lookup"><span data-stu-id="30b0a-135">On the **Build** menu, choose **Publish CreateExcelWorkbook**.</span></span> <span data-ttu-id="30b0a-136">Чтобы создать устанавливаемую версию приложения, следуйте указаниям мастера публикации.</span><span class="sxs-lookup"><span data-stu-id="30b0a-136">Follow the steps of the Publish Wizard to create an installable version of the application.</span></span> <span data-ttu-id="30b0a-137">Дополнительные сведения см. в разделе [Мастер публикации (разработка для Office в Visual Studio)](https://msdn.microsoft.com/library/bb625071).</span><span class="sxs-lookup"><span data-stu-id="30b0a-137">For more information, see [Publish Wizard (Office Development in Visual Studio)](https://msdn.microsoft.com/library/bb625071).</span></span>  
  
3.  <span data-ttu-id="30b0a-138">Установите приложение на компьютере, на котором установлена платформа .NET Framework 4 или более поздняя версия и другая версия Excel.</span><span class="sxs-lookup"><span data-stu-id="30b0a-138">Install the application on a computer on which the .NET Framework 4 or higher and a different version of Excel are installed.</span></span>  
  
4.  <span data-ttu-id="30b0a-139">После завершения установки запустите установленную программу.</span><span class="sxs-lookup"><span data-stu-id="30b0a-139">When the installation is finished, run the installed program.</span></span>  
  
5.  <span data-ttu-id="30b0a-140">Убедитесь, что книга Excel была создана в расположении, указанном в примере кода: C:\SampleFolder\SampleWorkbook.xls.</span><span class="sxs-lookup"><span data-stu-id="30b0a-140">Verify that an Excel workbook has been created at the location specified in the sample code: C:\SampleFolder\SampleWorkbook.xls.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30b0a-141">См. также</span><span class="sxs-lookup"><span data-stu-id="30b0a-141">See Also</span></span>  
 [<span data-ttu-id="30b0a-142">Пошаговое руководство: Внедрение типов из управляемых сборок в Visual Studio (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="30b0a-142">Walkthrough: Embedding Types from Managed Assemblies in Visual Studio (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/assemblies-gac/walkthrough-embedding-types-from-managed-assemblies-in-vs.md)  
 [<span data-ttu-id="30b0a-143">/link (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="30b0a-143">/link (Visual Basic)</span></span>](../../../../visual-basic/reference/command-line-compiler/link.md)

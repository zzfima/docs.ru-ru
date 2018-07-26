---
title: Пошаговое руководство. Внедрение данных о типах из сборок Microsoft Office в Visual Studio (C#)
ms.date: 07/20/2015
ms.assetid: 3320e866-01f1-4b7f-8932-049a7b2d2a9b
ms.openlocfilehash: 8e7eb5c797ca87f87950d530112ec64f1327ae0c
ms.sourcegitcommit: 2d8b7488d94101b534ca3e9780b1c1e840233405
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/23/2018
ms.locfileid: "39198501"
---
# <a name="walkthrough-embedding-type-information-from-microsoft-office-assemblies-in-visual-studio-c"></a><span data-ttu-id="df3fa-102">Пошаговое руководство. Внедрение данных о типах из сборок Microsoft Office в Visual Studio (C#)</span><span class="sxs-lookup"><span data-stu-id="df3fa-102">Walkthrough: Embedding Type Information from Microsoft Office Assemblies in Visual Studio (C#)</span></span>
<span data-ttu-id="df3fa-103">Если в приложение, имеющее ссылки на COM-объекты, внедрены данные о типе, можно исключить необходимость использования основной сборки взаимодействия (PIA).</span><span class="sxs-lookup"><span data-stu-id="df3fa-103">If you embed type information in an application that references COM objects, you can eliminate the need for a primary interop assembly (PIA).</span></span> <span data-ttu-id="df3fa-104">Кроме того внедренные данные о типах позволяют создать приложение, не зависящее от версии.</span><span class="sxs-lookup"><span data-stu-id="df3fa-104">Additionally, the embedded type information enables you to achieve version independence for your application.</span></span> <span data-ttu-id="df3fa-105">Это означает, что в программе можно использовать типы из нескольких версий библиотеки COM, т. е. необходимость использования конкретной основной сборки взаимодействия для каждой версии библиотеки COM отпадает.</span><span class="sxs-lookup"><span data-stu-id="df3fa-105">That is, your program can be written to use types from multiple versions of a COM library without requiring a specific PIA for each version.</span></span> <span data-ttu-id="df3fa-106">Это стандартный сценарий для приложений, использующих объекты из библиотек Microsoft Office.</span><span class="sxs-lookup"><span data-stu-id="df3fa-106">This is a common scenario for applications that use objects from Microsoft Office libraries.</span></span> <span data-ttu-id="df3fa-107">Внедрение данных о типе позволяет одной сборке программы работать с разными версиями приложения Microsoft Office на разных компьютерах без необходимости повторного развертывания программы или основной сборки взаимодействия для каждой версии приложения Microsoft Office.</span><span class="sxs-lookup"><span data-stu-id="df3fa-107">Embedding type information enables the same build of a program to work with different versions of Microsoft Office on different computers without the need to redeploy either the program or the PIA for each version of Microsoft Office.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="prerequisites"></a><span data-ttu-id="df3fa-108">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="df3fa-108">Prerequisites</span></span>  
 <span data-ttu-id="df3fa-109">Необходимо выполнить следующие требования.</span><span class="sxs-lookup"><span data-stu-id="df3fa-109">This walkthrough requires the following:</span></span>  
  
-   <span data-ttu-id="df3fa-110">Компьютер, на котором установлена среда Visual Studio и приложение Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="df3fa-110">A computer on which Visual Studio and Microsoft Excel are installed.</span></span>  
  
-   <span data-ttu-id="df3fa-111">Второй компьютер, на котором установлена платформа .NET Framework 4 или более поздняя версия и другая версия Excel.</span><span class="sxs-lookup"><span data-stu-id="df3fa-111">A second computer on which the .NET Framework 4 or higher and a different version of Excel are installed.</span></span>  
  
##  <a name="BKMK_createapp"></a> <span data-ttu-id="df3fa-112">Создание приложения, работающего с несколькими версиями Microsoft Office</span><span class="sxs-lookup"><span data-stu-id="df3fa-112">To create an application that works with multiple versions of Microsoft Office</span></span>  
  
1.  <span data-ttu-id="df3fa-113">Запустите Visual Studio на компьютере, на котором установлено приложение Excel.</span><span class="sxs-lookup"><span data-stu-id="df3fa-113">Start Visual Studio on a computer on which Excel is installed.</span></span>  
  
2.  <span data-ttu-id="df3fa-114">В меню **Файл** последовательно выберите пункты **Создать**и **Проект**.</span><span class="sxs-lookup"><span data-stu-id="df3fa-114">On the **File** menu, choose **New**, **Project**.</span></span>  
  
3.  <span data-ttu-id="df3fa-115">Убедитесь, что в диалоговом окне **Создание проекта** в области **Типы проектов** выбран пункт **Windows**.</span><span class="sxs-lookup"><span data-stu-id="df3fa-115">In the **New Project** dialog box, in the **Project Types** pane, make sure that **Windows** is selected.</span></span> <span data-ttu-id="df3fa-116">В области **Шаблоны** выберите пункт **Консольное приложение**.</span><span class="sxs-lookup"><span data-stu-id="df3fa-116">Select **Console Application** in the **Templates** pane.</span></span> <span data-ttu-id="df3fa-117">В поле **Имя** введите `CreateExcelWorkbook`, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="df3fa-117">In the **Name** box, enter `CreateExcelWorkbook`, and then choose the **OK** button.</span></span> <span data-ttu-id="df3fa-118">Проект создан.</span><span class="sxs-lookup"><span data-stu-id="df3fa-118">The new project is created.</span></span>  
  
4.  <span data-ttu-id="df3fa-119">В **обозревателе решений** щелкните правой кнопкой мыши папку **Ссылки** и выберите команду **Добавить ссылку**.</span><span class="sxs-lookup"><span data-stu-id="df3fa-119">In **Solution Explorer**, open the shortcut menu for the **References** folder and then choose **Add Reference**.</span></span>  
  
5.  <span data-ttu-id="df3fa-120">На вкладке **.NET** выберите самую последнюю версию `Microsoft.Office.Interop.Excel`.</span><span class="sxs-lookup"><span data-stu-id="df3fa-120">On the **.NET** tab, choose the most recent version of `Microsoft.Office.Interop.Excel`.</span></span> <span data-ttu-id="df3fa-121">Например, **Microsoft.Office.Interop.Excel 14.0.0.0**.</span><span class="sxs-lookup"><span data-stu-id="df3fa-121">For example, **Microsoft.Office.Interop.Excel 14.0.0.0**.</span></span> <span data-ttu-id="df3fa-122">Нажмите кнопку **ОК** .</span><span class="sxs-lookup"><span data-stu-id="df3fa-122">Choose the **OK** button.</span></span>  
  
6.  <span data-ttu-id="df3fa-123">В списке ссылок для проекта **CreateExcelWorkbook** выберите ссылку для `Microsoft.Office.Interop.Excel`, добавленную на предыдущем шаге.</span><span class="sxs-lookup"><span data-stu-id="df3fa-123">In the list of references for the **CreateExcelWorkbook** project, select the reference for `Microsoft.Office.Interop.Excel` that you added in the previous step.</span></span> <span data-ttu-id="df3fa-124">Убедитесь, что в окне **Свойства`Embed Interop Types` свойство**  имеет значение `True`.</span><span class="sxs-lookup"><span data-stu-id="df3fa-124">In the **Properties** window, make sure that the `Embed Interop Types` property is set to `True`.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="df3fa-125">Приложение, созданное в ходе данного пошагового руководства, запускается с разными версиями Microsoft Office, поскольку содержит внедренные данные о типе сборки взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="df3fa-125">The application created in this walkthrough runs with different versions of Microsoft Office because of the embedded interop type information.</span></span> <span data-ttu-id="df3fa-126">Если свойство `Embed Interop Types` имеет значение `False`, необходимо добавить основную сборку взаимодействия для каждой версии Microsoft Office, с которой будет запускаться приложение.</span><span class="sxs-lookup"><span data-stu-id="df3fa-126">If the `Embed Interop Types` property is set to `False`, you must include a PIA for each version of Microsoft Office that the application will run with.</span></span>  
  
7.  <span data-ttu-id="df3fa-127">Откройте файл **Program.cs**.</span><span class="sxs-lookup"><span data-stu-id="df3fa-127">Open the **Program.cs** file.</span></span> <span data-ttu-id="df3fa-128">Замените код в файле следующим кодом:</span><span class="sxs-lookup"><span data-stu-id="df3fa-128">Replace the code in the file with the following code:</span></span>  
  
    ```csharp  
    using System;  
    using System.Collections.Generic;  
    using System.Linq;  
    using System.Text;  
    using System.IO;  
    using Excel = Microsoft.Office.Interop.Excel;  
  
    namespace CreateExcelWorkbook  
    {  
        class Program  
        {  
            static void Main(string[] args)  
            {  
                int[] values = {4, 6, 18, 2, 1, 76, 0, 3, 11};  
  
                CreateWorkbook(values, @"C:\SampleFolder\SampleWorkbook.xls");  
            }  
  
            static void CreateWorkbook(int[] values, string filePath)  
            {  
                Excel.Application excelApp = null;  
                Excel.Workbook wkbk;  
                Excel.Worksheet sheet;  
  
                try  
                {  
                        // Start Excel and create a workbook and worksheet.  
                        excelApp = new Excel.Application();  
                        wkbk = excelApp.Workbooks.Add();  
                        sheet = wkbk.Sheets.Add() as Excel.Worksheet;  
                        sheet.Name = "Sample Worksheet";  
  
                        // Write a column of values.  
                        // In the For loop, both the row index and array index start at 1.  
                        // Therefore the value of 4 at array index 0 is not included.  
                        for (int i = 1; i < values.Length; i++)  
                        {  
                            sheet.Cells[i, 1] = values[i];  
                        }  
  
                        // Suppress any alerts and save the file. Create the directory   
                        // if it does not exist. Overwrite the file if it exists.  
                        excelApp.DisplayAlerts = false;  
                        string folderPath = Path.GetDirectoryName(filePath);  
                        if (!Directory.Exists(folderPath))  
                        {  
                            Directory.CreateDirectory(folderPath);  
                        }  
                        wkbk.SaveAs(filePath);  
                }  
                catch  
                {  
                }  
                finally  
                {  
                    sheet = null;  
                    wkbk = null;  
  
                    // Close Excel.  
                    excelApp.Quit();  
                    excelApp = null;  
                }  
            }  
        }  
    }  
    ```  
  
8.  <span data-ttu-id="df3fa-129">Сохраните проект.</span><span class="sxs-lookup"><span data-stu-id="df3fa-129">Save the project.</span></span>  
  
9. <span data-ttu-id="df3fa-130">Нажмите сочетание клавиш CTRL+F5, чтобы собрать и запустить проект.</span><span class="sxs-lookup"><span data-stu-id="df3fa-130">Press CTRL+F5 to build and run the project.</span></span> <span data-ttu-id="df3fa-131">Убедитесь, что книга Excel была создана в расположении, указанном в примере кода: C:\SampleFolder\SampleWorkbook.xls.</span><span class="sxs-lookup"><span data-stu-id="df3fa-131">Verify that an Excel workbook has been created at the location specified in the example code: C:\SampleFolder\SampleWorkbook.xls.</span></span>  
  
##  <a name="BKMK_publishapp"></a> <span data-ttu-id="df3fa-132">Публикация приложения на компьютере, на котором установлены разные версии Microsoft Office</span><span class="sxs-lookup"><span data-stu-id="df3fa-132">To publish the application to a computer on which a different version of Microsoft Office is installed</span></span>  
  
1.  <span data-ttu-id="df3fa-133">В Visual Studio откройте проект, созданный в ходе этого пошагового руководства.</span><span class="sxs-lookup"><span data-stu-id="df3fa-133">Open the project created by this walkthrough in Visual Studio.</span></span>  
  
2.  <span data-ttu-id="df3fa-134">В меню **Сборка** выберите **Опубликовать CreateExcelWorkbook**.</span><span class="sxs-lookup"><span data-stu-id="df3fa-134">On the **Build** menu, choose **Publish CreateExcelWorkbook**.</span></span> <span data-ttu-id="df3fa-135">Чтобы создать устанавливаемую версию приложения, следуйте указаниям мастера публикации.</span><span class="sxs-lookup"><span data-stu-id="df3fa-135">Follow the steps of the Publish Wizard to create an installable version of the application.</span></span> <span data-ttu-id="df3fa-136">Дополнительные сведения см. в разделе [Мастер публикации (разработка для Office в Visual Studio)](https://msdn.microsoft.com/library/bb625071).</span><span class="sxs-lookup"><span data-stu-id="df3fa-136">For more information, see [Publish Wizard (Office Development in Visual Studio)](https://msdn.microsoft.com/library/bb625071).</span></span>  
  
3.  <span data-ttu-id="df3fa-137">Установите приложение на компьютере, на котором установлена платформа .NET Framework 4 или более поздняя версия и другая версия Excel.</span><span class="sxs-lookup"><span data-stu-id="df3fa-137">Install the application on a computer on which the .NET Framework 4 or higher and a different version of Excel are installed.</span></span>  
  
4.  <span data-ttu-id="df3fa-138">После завершения установки запустите установленную программу.</span><span class="sxs-lookup"><span data-stu-id="df3fa-138">When the installation is finished, run the installed program.</span></span>  
  
5.  <span data-ttu-id="df3fa-139">Убедитесь, что книга Excel была создана в расположении, указанном в примере кода: C:\SampleFolder\SampleWorkbook.xls.</span><span class="sxs-lookup"><span data-stu-id="df3fa-139">Verify that an Excel workbook has been created at the location specified in the sample code: C:\SampleFolder\SampleWorkbook.xls.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df3fa-140">См. также</span><span class="sxs-lookup"><span data-stu-id="df3fa-140">See Also</span></span>  
 [<span data-ttu-id="df3fa-141">Пошаговое руководство. Внедрение типов из управляемых сборок в Visual Studio (C#)</span><span class="sxs-lookup"><span data-stu-id="df3fa-141">Walkthrough: Embedding Types from Managed Assemblies in Visual Studio (C#)</span></span>](../../../../csharp/programming-guide/concepts/assemblies-gac/walkthrough-embedding-types-from-managed-assemblies-in-visual-studio.md)  
 [<span data-ttu-id="df3fa-142">/link (параметры компилятора C#)</span><span class="sxs-lookup"><span data-stu-id="df3fa-142">/link (C# Compiler Options)</span></span>](../../../../csharp/language-reference/compiler-options/link-compiler-option.md)

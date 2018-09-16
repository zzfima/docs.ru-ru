---
title: 'Пошаговое руководство: Внедрение данных о типе из сборок Microsoft Office в Visual Studio (Visual Basic)'
ms.date: 07/20/2015
ms.assetid: 26b44286-5066-4ad4-8e6a-c24902be347c
ms.openlocfilehash: bc8f7585964bdd60bac5d5a466f6276fab288c78
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/16/2018
ms.locfileid: "45668214"
---
# <a name="walkthrough-embedding-type-information-from-microsoft-office-assemblies-in-visual-studio-visual-basic"></a>Пошаговое руководство: Внедрение данных о типе из сборок Microsoft Office в Visual Studio (Visual Basic)
Если в приложение, имеющее ссылки на COM-объекты, внедрены данные о типе, можно исключить необходимость использования основной сборки взаимодействия (PIA). Кроме того внедренные данные о типах позволяют создать приложение, не зависящее от версии. Это означает, что в программе можно использовать типы из нескольких версий библиотеки COM, т. е. необходимость использования конкретной основной сборки взаимодействия для каждой версии библиотеки COM отпадает. Это стандартный сценарий для приложений, использующих объекты из библиотек Microsoft Office. Внедрение данных о типе позволяет одной сборке программы работать с разными версиями приложения Microsoft Office на разных компьютерах без необходимости повторного развертывания программы или основной сборки взаимодействия для каждой версии приложения Microsoft Office.  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="prerequisites"></a>Предварительные требования  
 Необходимо выполнить следующие требования.  
  
-   Компьютер, на котором установлена среда Visual Studio и приложение Microsoft Excel.  
  
-   Второй компьютер, на котором установлена платформа .NET Framework 4 или более поздняя версия и другая версия Excel.  
  
##  <a name="BKMK_createapp"></a> Создание приложения, работающего с несколькими версиями Microsoft Office  
  
1.  Запустите Visual Studio на компьютере, на котором установлено приложение Excel.  
  
2.  В меню **Файл** последовательно выберите пункты **Создать**и **Проект**.  
  
3.  Убедитесь, что в диалоговом окне **Создание проекта** в области **Типы проектов** выбран пункт **Windows**. В области **Шаблоны** выберите пункт **Консольное приложение**. В поле **Имя** введите `CreateExcelWorkbook`, а затем нажмите кнопку **ОК**. Проект создан.  
  
4.  Откройте контекстное меню для проекта CreateExcelWorkbook и выберите **свойства**. Выберите **ссылки** вкладки. Нажмите кнопку **Добавить** .  
  
5.  На вкладке **.NET** выберите самую последнюю версию `Microsoft.Office.Interop.Excel`. Например, **Microsoft.Office.Interop.Excel 14.0.0.0**. Нажмите кнопку **ОК** .  
  
6.  В списке ссылок для проекта **CreateExcelWorkbook** выберите ссылку для `Microsoft.Office.Interop.Excel`, добавленную на предыдущем шаге. Убедитесь, что в окне **Свойства`Embed Interop Types` свойство**  имеет значение `True`.  
  
    > [!NOTE]
    >  Приложение, созданное в ходе данного пошагового руководства, запускается с разными версиями Microsoft Office, поскольку содержит внедренные данные о типе сборки взаимодействия. Если свойство `Embed Interop Types` имеет значение `False`, необходимо добавить основную сборку взаимодействия для каждой версии Microsoft Office, с которой будет запускаться приложение.  
  
7.  Откройте файл Module1.vb. Замените код в файле следующим кодом:  
  
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
  
8.  Сохраните проект.  
  
9. Нажмите сочетание клавиш CTRL+F5, чтобы собрать и запустить проект. Убедитесь, что книга Excel была создана в расположении, указанном в примере кода: C:\SampleFolder\SampleWorkbook.xls.  
  
##  <a name="BKMK_publishapp"></a> Публикация приложения на компьютере, на котором установлены разные версии Microsoft Office  
  
1.  В Visual Studio откройте проект, созданный в ходе этого пошагового руководства.  
  
2.  В меню **Сборка** выберите **Опубликовать CreateExcelWorkbook**. Чтобы создать устанавливаемую версию приложения, следуйте указаниям мастера публикации. Дополнительные сведения см. в разделе [Мастер публикации (разработка для Office в Visual Studio)](/visualstudio/vsto/publish-wizard-office-development-in-visual-studio).  
  
3.  Установите приложение на компьютере, на котором установлена платформа .NET Framework 4 или более поздняя версия и другая версия Excel.  
  
4.  После завершения установки запустите установленную программу.  
  
5.  Убедитесь, что книга Excel была создана в расположении, указанном в примере кода: C:\SampleFolder\SampleWorkbook.xls.  
  
## <a name="see-also"></a>См. также

- [Пошаговое руководство: Внедрение типов из управляемых сборок в Visual Studio (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/walkthrough-embedding-types-from-managed-assemblies-in-vs.md)  
- [/link (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/link.md)

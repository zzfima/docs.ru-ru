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
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 4347ba0e740419b53a1aa662c43933dead107e9c
ms.contentlocale: ru-ru
ms.lasthandoff: 03/13/2017

---
# <a name="walkthrough-embedding-type-information-from-microsoft-office-assemblies-in-visual-studio-visual-basic"></a>Пошаговое руководство: Внедрение сведений о типах из сборок Microsoft Office в Visual Studio (Visual Basic)
Если внедрить сведения о типах в приложении, которое ссылается на COM-объекты, можно исключить потребность в основной сборки взаимодействия (PIA). Кроме того внедренные сведения о типах позволяет обеспечить независимость от версии приложения. То есть программы могут записываться использовать типы из нескольких версий библиотеки COM без конкретной основной сборки ВЗАИМОДЕЙСТВИЯ для каждой версии. Это типично для приложений, использующих объекты из библиотек Microsoft Office. Внедрение данных о типе позволяет одному построению программы работать с различными версиями Microsoft Office на разных компьютерах без необходимости повторного развертывания программы или основной сборки ВЗАИМОДЕЙСТВИЯ для каждой версии Microsoft Office.  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="prerequisites"></a>Предварительные требования  
 Необходимо выполнить следующие требования.  
  
-   Компьютер, на котором установлена Visual Studio и Microsoft Excel.  
  
-   Второй компьютер, на котором установлена .NET Framework 4 или более поздней версии и разными версиями Excel.  
  
##  <a name="BKMK_createapp"></a>Чтобы создать приложение, которое работает с различными версиями Microsoft Office  
  
1.  Запустите Visual Studio на компьютере, на котором установлен Microsoft Excel.  
  
2.  В меню **Файл** последовательно выберите пункты **Создать**и **Проект**.  
  
3.  В **новый проект** в диалоговом **типы проектов** область, убедитесь, что **Windows** выбран. Выберите **консольное приложение** в **шаблоны** области. В **имя** введите `CreateExcelWorkbook`, а затем выберите **ОК** кнопки. Создан новый проект.  
  
4.  Откройте контекстное меню для проекта CreateExcelWorkbook, а затем выберите **свойства**. Выберите **ссылки** вкладки. Нажмите кнопку **Добавить** .  
  
5.  На **.NET** выберите последнюю версию `Microsoft.Office.Interop.Excel`. Например **Microsoft.Office.Interop.Excel 14.0.0.0**. Нажмите кнопку **ОК** .  
  
6.  В списке ссылок для **CreateExcelWorkbook** проекта, выберите ссылку для `Microsoft.Office.Interop.Excel` , добавленного на предыдущем шаге. В **свойства** окна, убедитесь, что `Embed Interop Types` свойству `True`.  
  
    > [!NOTE]
    >  Приложения, созданного в этом пошаговом руководстве выполняется с различными версиями Microsoft Office благодаря сведениям о внедренного типа взаимодействия. Если `Embed Interop Types` свойству `False`, должен включать основные сборки ВЗАИМОДЕЙСТВИЯ для каждой версии Microsoft Office, приложение будет работать с.  
  
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
  
9. Нажмите CTRL + F5, чтобы построить и запустить проект. Убедитесь, что книга Excel был создан в расположении, указанном в примере кода: C:\SampleFolder\SampleWorkbook.xls.  
  
##  <a name="BKMK_publishapp"></a>Для публикации приложения на компьютере, на котором установлен другой версии Microsoft Office  
  
1.  Откройте проект, созданный в ходе этого пошагового руководства в Visual Studio.  
  
2.  На **построения** меню, выберите **CreateExcelWorkbook публикации**. Следуйте указаниям мастера публикации, чтобы создать устанавливаемую версию приложения. Дополнительные сведения см. в разделе [мастер публикации (Разработка решений Office в Visual Studio)](https://msdn.microsoft.com/library/bb625071).  
  
3.  Установите приложение на компьютере, на котором установлена .NET Framework 4 или более поздней версии и разными версиями Excel.  
  
4.  После завершения установки запустите установленную программу.  
  
5.  Убедитесь, что книга Excel был создан в расположении, указанном в образце кода: C:\SampleFolder\SampleWorkbook.xls.  
  
## <a name="see-also"></a>См. также  
 [Пошаговое руководство: Внедрение типов из управляемых сборок в Visual Studio (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/walkthrough-embedding-types-from-managed-assemblies-in-vs.md)   
 [/ LINK (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/link.md)


---
title: "Пошаговое руководство. Внедрение данных о типах из сборок Microsoft Office в Visual Studio (C#) | Документы Майкрософт"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 3320e866-01f1-4b7f-8932-049a7b2d2a9b
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: b698372d28198cfcd34aef69043334e3fc50ce6d
ms.contentlocale: ru-ru
ms.lasthandoff: 03/13/2017

---
# <a name="walkthrough-embedding-type-information-from-microsoft-office-assemblies-in-visual-studio-c"></a>Пошаговое руководство. Внедрение данных о типах из сборок Microsoft Office в Visual Studio (C#)
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
  
4.  В **обозревателе решений** щелкните правой кнопкой мыши папку **Ссылки** и выберите команду **Добавить ссылку**.  
  
5.  На вкладке **.NET** выберите самую последнюю версию `Microsoft.Office.Interop.Excel`. Например, **Microsoft.Office.Interop.Excel 14.0.0.0**. Нажмите кнопку **ОК** .  
  
6.  В списке ссылок для проекта **CreateExcelWorkbook** выберите ссылку для `Microsoft.Office.Interop.Excel`, добавленную на предыдущем шаге. Убедитесь, что в окне **Свойства`Embed Interop Types` свойство** имеет значение `True`.  
  
    > [!NOTE]
    >  Приложение, созданное в ходе данного пошагового руководства, запускается с разными версиями Microsoft Office, поскольку содержит внедренные данные о типе сборки взаимодействия. Если свойство `Embed Interop Types` имеет значение `False`, необходимо добавить основную сборку взаимодействия для каждой версии Microsoft Office, с которой будет запускаться приложение.  
  
7.  Откройте файл **Program.cs**. Замените код в файле следующим кодом:  
  
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
  
8.  Сохраните проект.  
  
9. Нажмите сочетание клавиш CTRL+F5, чтобы собрать и запустить проект. Убедитесь, что книга Excel была создана в расположении, указанном в примере кода: C:\SampleFolder\SampleWorkbook.xls.  
  
##  <a name="BKMK_publishapp"></a> Публикация приложения на компьютере, на котором установлены разные версии Microsoft Office  
  
1.  В Visual Studio откройте проект, созданный в ходе этого пошагового руководства.  
  
2.  В меню **Сборка** выберите **Опубликовать CreateExcelWorkbook**. Чтобы создать устанавливаемую версию приложения, следуйте указаниям мастера публикации. Дополнительные сведения см. в разделе [Мастер публикации (разработка для Office в Visual Studio)](https://msdn.microsoft.com/library/bb625071).  
  
3.  Установите приложение на компьютере, на котором установлена платформа .NET Framework 4 или более поздняя версия и другая версия Excel.  
  
4.  После завершения установки запустите установленную программу.  
  
5.  Убедитесь, что книга Excel была создана в расположении, указанном в примере кода: C:\SampleFolder\SampleWorkbook.xls.  
  
## <a name="see-also"></a>См. также  
 [Пошаговое руководство. Внедрение типов из управляемых сборок в Visual Studio (C#)](../../../../csharp/programming-guide/concepts/assemblies-gac/walkthrough-embedding-types-from-managed-assemblies-in-visual-studio.md)   
 [/link (параметры компилятора C#)](../../../../csharp/language-reference/compiler-options/link-compiler-option.md)


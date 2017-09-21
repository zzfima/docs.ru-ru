---
title: "Операции с файлами и каталогами в Visual Basic"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- files, reading text
- reading files, text
- I/O [Visual Basic], walkthroughs
- text, writing to files
- text, reading from files
- reading text from files, walkthroughs
- Visual Basic code, file access
- files, writing text
- I/O [Visual Basic], writing text to files
- file access, walkthroughs
- writing to files, walkthroughs
- I/O [Visual Basic], reading text from files
ms.assetid: cae77565-9f78-4e46-8e42-eb2f9f8e1ffd
caps.latest.revision: 49
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 9e66d062df07fc23dfbd5d509e08ccd08813db15
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="walkthrough-manipulating-files-and-directories-in-visual-basic"></a>Пошаговое руководство. Операции с файлами и каталогами в Visual Basic
В этом пошаговом руководстве приводятся основные сведения о файловом вводе-выводе в [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]. В нем описывается создание небольшого приложения, перечисляющего текстовые файлы в каталоге и анализирующего их. Для каждого выбранного текстового файла приложение предоставляет атрибуты файла и первую строку содержимого. Кроме того, предоставляется возможность записать информацию в файл журнала.  
  
 В этом пошаговом руководстве используются члены `My.Computer.FileSystem Object`, доступные в [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]. Дополнительные сведения см. в разделе <xref:Microsoft.VisualBasic.FileIO.FileSystem>. В конце пошагового руководства приводится эквивалентный пример, в котором используются классы пространства имен <xref:System.IO>.  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-the-project"></a>Создание проекта  
  
1.  В меню **Файл** выберите пункт **Создать проект**.  
  
     Откроется диалоговое окно **Новый проект** .  
  
2.  В области **Установленные шаблоны** разверните узел **Visual Basic** и выберите элемент **Windows**. В середине области **Шаблоны** щелкните **Приложение Windows Forms**.  
  
3.  В поле **Имя** введите `FileExplorer`, чтобы задать имя проекта, а затем нажмите кнопку **ОК**.  
  
     [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] добавит проект в **обозреватель решений**, после чего откроется конструктор Windows Forms.  
  
4.  Добавьте в форму элементы управления из приведенной ниже таблицы и установите для их свойств соответствующие значения.  
  
    |Control|Свойство|Значение|  
    |-------------|--------------|-----------|  
    |**ListBox**|**Имя**|`filesListBox`|  
    |**Button**|**Имя**<br /><br /> **Текст**|`browseButton`<br /><br /> **Обзор**|  
    |**Button**|**Имя**<br /><br /> **Текст**|`examineButton`<br /><br /> **Исследовать**|  
    |**CheckBox**|**Имя**<br /><br /> **Текст**|`saveCheckBox`<br /><br /> **Сохранить результаты**|  
    |**FolderBrowserDialog**|**Имя**|`FolderBrowserDialog1`|  
  
### <a name="to-select-a-folder-and-list-files-in-a-folder"></a>Выбор папки и перечисление файлов в ней  
  
1.  Создайте обработчик событий нажатия `Click` для кнопки `browseButton`, дважды щелкнув этот элемент управления в форме. Откроется редактор кода.  
  
2.  Добавьте следующий код в обработчик событий `Click`.  
  
     [!code-vb[VbVbcnMyFileSystem#103](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-and-directories_1.vb)]  
  
     Вызов `FolderBrowserDialog1.ShowDialog` открывает диалоговое окно **Выбор папки**. Когда пользователь нажимает **OK**, свойство <xref:System.Windows.Forms.FolderBrowserDialog.SelectedPath%2A> передается как аргумент методу `ListFiles`, который добавляется в следующем шаге.  
  
3.  Добавьте приведенный ниже метод `ListFiles`.  
  
     [!code-vb[VbVbcnMyFileSystem#104](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-and-directories_2.vb)]  
  
     Этот код сперва очищает элемент **ListBox**.  
  
     Затем метод <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFiles%2A> возвращает коллекцию строк — по одной для каждого файла в каталоге. Метод `GetFiles` принимает аргумент шаблона поиска, чтобы извлечь файлы, соответствующие определенному шаблону. В этом примере возвращаются только файлы с расширением TXT.  
  
     Строки, возвращаемые методом `GetFiles`, затем добавляются в элемент управления **ListBox**.  
  
4.  Запустите приложение. Нажмите кнопку **Обзор**. В диалоговом окне **Выбор папки** перейдите в папку, содержащую TXT-файлы, выберите папку и нажмите кнопку **ОК**.  
  
     Элемент `ListBox` содержит список TXT-файлов в выбранной папке.  
  
5.  Остановите работу приложения.  
  
### <a name="to-obtain-attributes-of-a-file-and-content-from-a-text-file"></a>Получение атрибутов файла и содержимого текстового файла  
  
1.  Создайте обработчик событий нажатия `Click` для кнопки `examineButton`, дважды щелкнув этот элемент управления в форме.  
  
2.  Добавьте следующий код в обработчик событий `Click`.  
  
     [!code-vb[VbVbcnMyFileSystem#105](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-and-directories_3.vb)]  
  
     Этот код проверяет, выбран ли элемент в элементе `ListBox`. Затем он получает запись пути к файлу из элемента `ListBox`. Метод <xref:Microsoft.VisualBasic.FileIO.FileSystem.FileExists%2A> позволяет проверить, существует ли файл.  
  
     Путь к файлу передается как аргумент методу `GetTextForOutput`, который добавляется в следующем шаге. Этот метод возвращает строку, содержащую информацию о файле. Информация о файле отображается в элементе **MessageBox**.  
  
3.  Добавьте приведенный ниже метод `GetTextForOutput`.  
  
     [!code-vb[VbVbcnMyFileSystem#107](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-and-directories_4.vb)]  
  
     Метод <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFileInfo%2A> используется в коде для получения параметров файла. Параметры файла добавляются в <xref:System.Text.StringBuilder>.  
  
     Метод <xref:Microsoft.VisualBasic.FileIO.FileSystem.OpenTextFileReader%2A> считывает содержимое файла в <xref:System.IO.StreamReader>. Первая строка содержимого файла извлекается из `StreamReader` и добавляется в `StringBuilder`.  
  
4.  Запустите приложение. Нажмите кнопку **Обзор** и перейдите в папку с TXT-файлами. Нажмите кнопку **ОК**.  
  
     Выберите файл в элементе `ListBox` и щелкните **Исследовать**. В окне `MessageBox` будет выведена информация о файле.  
  
5.  Остановите работу приложения.  
  
### <a name="to-add-a-log-entry"></a>Добавление записи в журнал  
  
1.  В конец обработчика событий `examineButton_Click` добавьте приведенный ниже код.  
  
     [!code-vb[VbVbcnMyFileSystem#106](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-and-directories_5.vb)]  
  
     Код задает путь к файлу журнала, чтобы файл журнала помещался в тот же каталог, где находится выбранный файл. Запись журнала должна содержать текущие дату и время, а далее информацию о файле.  
  
     Метод <xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllText%2A>, которому передается аргумент `append` со значением `True`, используется для создания записи в журнале.  
  
2.  Запустите приложение. Перейдите к текстовому файлу, выберите его в элементе `ListBox`, установите флажок **Сохранить результаты** и щелкните **Исследовать**. Проверьте, добавлена ли запись в файл `log.txt`.  
  
3.  Остановите работу приложения.  
  
### <a name="to-use-the-current-directory"></a>Использование текущего каталога  
  
1.  Создайте обработчик событий для события `Form1_Load`, дважды щелкнув форму.  
  
2.  Добавьте в обработчик событий приведенный ниже код.  
  
     [!code-vb[VbVbcnMyFileSystem#102](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-and-directories_6.vb)]  
  
     Этот код задает текущий каталог в качестве каталога по умолчанию для обозревателя папок.  
  
3.  Запустите приложение. При первом нажатии кнопки **Обзор** открывается диалоговое окно **Выбор папки** с текущим каталогом.  
  
4.  Остановите работу приложения.  
  
### <a name="to-selectively-enable-controls"></a>Выборочное включение элементов управления  
  
1.  Добавьте приведенный ниже метод `SetEnabled`.  
  
     [!code-vb[VbVbcnMyFileSystem#108](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-and-directories_7.vb)]  
  
     Метод `SetEnabled` включает и отключает элементы управления в зависимости от того, выбран ли элемент в элементе `ListBox`.  
  
2.  Создайте обработчик событий `SelectedIndexChanged` для элемента `filesListBox`, дважды щелкнув элемент управления `ListBox` в форме.  
  
3.  Добавьте вызов метода `SetEnabled` в новый обработчик событий `filesListBox_SelectedIndexChanged`.  
  
4.  Добавьте вызов метода `SetEnabled` в конце обработчика событий `browseButton_Click`.  
  
5.  Добавьте вызов метода `SetEnabled` в конце обработчика событий `Form1_Load`.  
  
6.  Запустите приложение. Флажок **Сохранить результаты** и кнопка **Исследовать** отключены, если элемент не выбран в элементе `ListBox`.  
  
## <a name="full-example-using-mycomputerfilesystem"></a>Полный пример с использованием My.Computer.FileSystem  
 Ниже приведен полный пример.  
  
 [!code-vb[VbVbcnMyFileSystem#101](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-and-directories_8.vb)]  
  
## <a name="full-example-using-systemio"></a>Полный пример с использованием System.IO  
 Следующий пример выполняет те же действия, используя классы из пространства имен <xref:System.IO> вместо объектов `My.Computer.FileSystem`.  
  
 [!code-vb[VbVbcnMyFileSystem#111](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-and-directories_9.vb)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.IO>   
 <xref:Microsoft.VisualBasic.FileIO.FileSystem>   
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.CurrentDirectory%2A>   
 [Пошаговое руководство. Управление файлами с помощью методов .NET Framework](../../../../visual-basic/developing-apps/programming/drives-directories-files/walkthrough-manipulating-files-by-using-net-framework-methods.md)


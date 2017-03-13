---
title: "Пошаговое руководство. Операции с файлами и каталогами в Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "доступ к файлам, пошаговые руководства"
  - "файлы, чтение текста"
  - "файлы, запись текста"
  - "ввод-вывод [Visual Basic], чтение текста из файлов"
  - "ввод-вывод [Visual Basic], пошаговые руководства"
  - "ввод-вывод [Visual Basic], запись текста в файлы"
  - "чтение файлов, текст"
  - "чтение текста из файлов, пошаговые руководства"
  - "текст, чтение из файлов"
  - "текст, запись в файлы"
  - "код Visual Basic, доступ к файлам"
  - "запись в файлы, пошаговые руководства"
ms.assetid: cae77565-9f78-4e46-8e42-eb2f9f8e1ffd
caps.latest.revision: 49
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 49
---
# Пошаговое руководство. Операции с файлами и каталогами в Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

В этом пошаговом руководстве дается введение в основы файлового ввода\-вывода в [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)].  Здесь описывается создание небольшого приложения, перечисляющего текстовые файлы в каталоге и анализирующего их.  Для каждого выбранного текстового файла приложение предоставляет атрибуты файла и первую строку содержимого.  Кроме того, предоставляется возможность записать информацию в файл журнала.  
  
 В этом пошаговом руководстве используются члены `My.Computer.FileSystem Object`, доступные в [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)].  Дополнительные сведения см. в разделе <xref:Microsoft.VisualBasic.FileIO.FileSystem>.  В конце пошагового руководства приводится эквивалентный пример, в котором используются классы пространства имен <xref:System.IO>.  
  
 [!INCLUDE[note_settings_general](../../../../csharp/language-reference/compiler-messages/includes/note-settings-general-md.md)]  
  
### Создание проекта  
  
1.  В меню **Файл** выберите команду **Создать проект**.  
  
     Откроется диалоговое окно **Новый проект**.  
  
2.  В области **Установленные шаблоны** разверните узел **Visual Basic** и выберите **Windows**.  В середине области **Шаблоны** щелкните **Приложение Windows Forms**.  
  
3.  В поле **Имя** введите `FileExplorer`, чтобы задать имя проекта, и затем нажмите кнопку **ОК**.  
  
     [!INCLUDE[vsprvs](../../../../csharp/includes/vsprvs-md.md)] добавит проект в **Обозреватель решений**, и откроется окно конструктора Windows Forms.  
  
4.  Добавьте в форму элементы управления из следующей таблицы и установите для их свойств соответствующие значения.  
  
    |Элемент управления|Свойство.|Значение|  
    |------------------------|---------------|--------------|  
    |**ListBox**|**Имя**|`filesListBox`|  
    |**Кнопка**|**Имя**<br /><br /> **Текст**|`browseButton`<br /><br /> Обзор|  
    |**Кнопка**|**Имя**<br /><br /> **Текст**|`examineButton`<br /><br /> Исследовать|  
    |**CheckBox**|**Имя**<br /><br /> **Текст**|`saveCheckBox`<br /><br /> Сохранить результаты|  
    |**FolderBrowserDialog**|**Имя**|`FolderBrowserDialog1`|  
  
### Выбор папки и перечисление файлов в этой папке  
  
1.  Создайте обработчик событий нажатия `Click` для кнопки `browseButton`, дважды щелкнув этот элемент управления в форме.  Открывается редактор кода.  
  
2.  В обработчик событий `Click` добавьте следующий код.  
  
     [!code-vb[VbVbcnMyFileSystem#103](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-and-directories_1.vb)]  
  
     Вызов `FolderBrowserDialog1.ShowDialog` открывает диалоговое окно **Выбрать папку**.  Когда пользователь нажимает кнопку **ОК**, свойство <xref:System.Windows.Forms.FolderBrowserDialog.SelectedPath%2A> передается как аргумент методу `ListFiles`, который добавляется на следующем шаге.  
  
3.  Добавьте следующий метод `ListFiles`.  
  
     [!code-vb[VbVbcnMyFileSystem#104](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-and-directories_2.vb)]  
  
     Этот код сперва очищает элемент **ListBox**.  
  
     Затем метод <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFiles%2A> извлекает коллекцию строк — по одной для каждого файла в каталоге.  Метод `GetFiles` принимает аргумент шаблона поиска, чтобы извлечь файлы, соответствующие определенному шаблону.  В этом примере возвращаются только файлы с расширением TXT.  
  
     Строки, возвращаемые методом `GetFiles`, затем добавляются в элемент управления **ListBox**.  
  
4.  Запустите приложение.  Нажмите кнопку **Обзор**.  В диалоговом окне **Выбрать папку** перейдите в папку, содержащую TXT\-файлы, выберите папку и нажмите кнопку **ОК**.  
  
     Элемент `ListBox` содержит список TXT\-файлов в выбранной папке.  
  
5.  Остановите работу приложения.  
  
### Получение атрибутов файла и содержимого текстового файла  
  
1.  Создайте обработчик событий нажатия `Click` для кнопки `examineButton`, дважды щелкнув этот элемент управления в форме.  
  
2.  В обработчик событий `Click` добавьте следующий код.  
  
     [!code-vb[VbVbcnMyFileSystem#105](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-and-directories_3.vb)]  
  
     Этот код проверяет, что элемент выбран в элементе `ListBox`.  Затем он получает запись пути к файлу из элемента `ListBox`.  Метод <xref:Microsoft.VisualBasic.FileIO.FileSystem.FileExists%2A> используется для проверки, что файл по прежнему существует.  
  
     Путь к файлу передается как аргумент методу `GetTextForOutput`, который добавляется на следующем шаге.  Этот метод возвращает строку, содержащую информацию о файле.  Информация о файле появляется в элементе **MessageBox**.  
  
3.  Добавьте следующий метод `GetTextForOutput`.  
  
     [!code-vb[VbVbcnMyFileSystem#107](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-and-directories_4.vb)]  
  
     Код использует метод <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFileInfo%2A> для получения параметров файла.  Параметры файла добавляются в <xref:System.Text.StringBuilder>.  
  
     Метод <xref:Microsoft.VisualBasic.FileIO.FileSystem.OpenTextFileReader%2A> считывает содержимое файла в <xref:System.IO.StreamReader>.  Первая строка содержимого файла извлекается из `StreamReader` и добавляется в `StringBuilder`.  
  
4.  Запустите приложение.  Щелкните **Обзор** и перейдите в папку с TXT\-файлами.  Нажмите кнопку **ОК**.  
  
     Выберите файл в элементе `ListBox` и щелкните **Исследовать**.  В окне `MessageBox` будет выведена информация о файле.  
  
5.  Остановите работу приложения.  
  
### Добавление записи в журнал  
  
1.  В конец обработчика событий `examineButton_Click` добавьте следующий код.  
  
     [!code-vb[VbVbcnMyFileSystem#106](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-and-directories_5.vb)]  
  
     Код задает путь к файлу журнала, чтобы файл журнала помещался в тот же каталог, где находится выбранный файл.  Настроено, что запись в журнал должна содержать текущую дату и время, а далее информацию о файле.  
  
     Метод <xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllText%2A> с аргументом `append` со значением `True` используется для создания записи журнала.  
  
2.  Запустите приложение.  Перейдите к текстовому файлу, выберите его в элементе `ListBox`, установите флажок **Сохранить результаты** и щелкните **Исследовать**.  Проверьте, что запись сделана в файл `log.txt`.  
  
3.  Остановите работу приложения.  
  
### Использование текущего каталога  
  
1.  Создайте обработчик событий для события `Form1_Load`, дважды щелкнув форму.  
  
2.  Добавьте в обработчик событий следующий код.  
  
     [!code-vb[VbVbcnMyFileSystem#102](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-and-directories_6.vb)]  
  
     Следующий код задает текущий каталог в качестве каталога по умолчанию для обозревателя папок.  
  
3.  Запустите приложение.  При первом нажатии кнопки **Обзор** диалоговое окно **Выбрать папку** открывается на текущем каталоге.  
  
4.  Остановите работу приложения.  
  
### Выборочное включение элементов управления  
  
1.  Добавьте следующий метод `SetEnabled`.  
  
     [!code-vb[VbVbcnMyFileSystem#108](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-and-directories_7.vb)]  
  
     Метод `SetEnabled` включает и отключает элементы управления в зависимости от того, выбран ли элемент в элементе `ListBox`.  
  
2.  Создайте обработчик событий `SelectedIndexChanged` для элемента `filesListBox`, дважды щелкнув элемент управления `ListBox` в форме.  
  
3.  Добавьте вызов метода `SetEnabled` в новый обработчик событий `filesListBox_SelectedIndexChanged`.  
  
4.  Добавьте вызов метода `SetEnabled` в конце обработчика событий `browseButton_Click`.  
  
5.  Добавьте вызов метода `SetEnabled` в конце обработчика событий `Form1_Load`.  
  
6.  Запустите приложение.  Флажок **Сохранить результаты** и кнопка **Исследовать** отключены, если элемент на выбран в элементе `ListBox`.  
  
## Полный пример с использованием My.Computer.FileSystem  
 Далее приведен полный пример.  
  
 [!code-vb[VbVbcnMyFileSystem#101](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-and-directories_8.vb)]  
  
## Полный пример с использованием System.IO  
 В следующем эквивалентном примере используются классы из пространства имен <xref:System.IO> вместо объектов `My.Computer.FileSystem`.  
  
 [!code-vb[VbVbcnMyFileSystem#111](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-and-directories_9.vb)]  
  
## См. также  
 <xref:System.IO>   
 <xref:Microsoft.VisualBasic.FileIO.FileSystem>   
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.CurrentDirectory%2A>   
 [Пошаговое руководство. Управление файлами с помощью методов .NET Framework](../../../../visual-basic/developing-apps/programming/drives-directories-files/walkthrough-manipulating-files-by-using-net-framework-methods.md)
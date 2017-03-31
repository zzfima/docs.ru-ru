---
title: "Пошаговое руководство. Управление файлами с помощью методов .NET Framework (Visual Basic) | Документы Майкрософт"
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
- I/O [Visual Basic], walkthroughs
- text files, writing to
- reading text files
- text, writing to files
- files, searching
- StreamReader class, walkthroughs
- files, accessing
- I/O [Visual Basic], writing text to files
- writing to files, walkthroughs
- StreamWriter class, walkthroughs
- text files, reading
- I/O [Visual Basic], reading text from files
ms.assetid: 7d2109eb-f98a-4389-b43d-30f384aaa7d5
caps.latest.revision: 18
author: stevehoag
ms.author: shoag
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
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: e8bf73f32dba51455542778ed91ef3bfd2898754
ms.lasthandoff: 03/13/2017

---
# <a name="walkthrough-manipulating-files-by-using-net-framework-methods-visual-basic"></a>Пошаговое руководство. Управление файлами с помощью методов .NET Framework (Visual Basic)
В этом пошаговом руководстве демонстрируется открытие и чтение файла с помощью класса <xref:System.IO.StreamReader>, проверка факта доступа к файлу в настоящий момент, поиск строки в файле, считанном с помощью экземпляра класса <xref:System.IO.StreamReader>, и запись в файл с помощью класса <xref:System.IO.StreamWriter>.  
  
[!INCLUDE[note_settings_general](../../../../csharp/language-reference/compiler-messages/includes/note_settings_general_md.md)]  
  
## <a name="creating-the-application"></a>Создание приложения  
 Запустите [!INCLUDE[vsprvs](../../../../csharp/includes/vsprvs_md.md)] и начните проект с создания формы, которую пользователь сможет использовать для записи в намеченный файл.  
  
#### <a name="to-create-the-project"></a>Создание проекта  
  
1.  В меню **Файл** выберите **Создать проект**.  
  
2.  В области **Новый проект** щелкните **Приложения Windows**.  
  
3.  В поле **Имя** введите `MyDiary`, а затем нажмите кнопку **ОК**.  
  
     [!INCLUDE[vsprvs](../../../../csharp/includes/vsprvs_md.md)] добавит проект в **обозреватель решений**, после чего откроется **конструктор Windows Forms**.  
  
4.  Добавьте в форму элементы управления из следующей таблицы и установите для их свойств соответствующие значения.  
  
|**Объект**|**Свойства**|**Значение**|  
|---|---|---|   
|<xref:System.Windows.Forms.Button>|**Имя**<br /><br /> **Текст**|`Submit`<br /><br /> **Сохранить запись**|  
|<xref:System.Windows.Forms.Button>|**Имя**<br /><br /> **Текст**|`Clear`<br /><br /> **Очистить запись**|  
|<xref:System.Windows.Forms.TextBox>|**Имя**<br /><br /> **Текст**<br /><br /> **Multiline**|`Entry`<br /><br /> **Введите произвольный текст.**<br /><br /> `False`|  
  
## <a name="writing-to-the-file"></a>Запись в файл  
 Чтобы добавить возможность записи в файл с помощью приложения, воспользуйтесь классом <xref:System.IO.StreamWriter>. Класс <xref:System.IO.StreamWriter> предназначен для вывода символов в определенной кодировке, тогда как класс <xref:System.IO.Stream> предназначен для ввода и вывода байтов. Класс <xref:System.IO.StreamWriter> следует использовать для записи строк данных в стандартный текстовый файл. Дополнительные сведения о классе <xref:System.IO.StreamWriter> см. в разделе <xref:System.IO.StreamWriter>.  
  
#### <a name="to-add-writing-functionality"></a>Добавление возможности записи  
  
1.  В меню **Вид** выберите пункт **Код**, чтобы открыть редактор кода.  
  
2.  Поскольку приложение ссылается на пространство имен <xref:System.IO>, добавьте следующие операторы в самом начале кода перед объявлением класса формы, которое начинается с `Public Class Form1`.  
  
     [!code-vb[VbVbcnMyFileSystem#35](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-by-using-net-framework-methods_1.vb)]  
  
     Перед записью в файл необходимо создать экземпляр класса <xref:System.IO.StreamWriter>.  
  
3.  В меню **Вид** выберите пункт **Конструктор** для возврата в окно **Конструктор Windows Forms**. Дважды щелкните кнопку `Submit`, чтобы создать обработчик событий <xref:System.Windows.Forms.Control.Click> для кнопки, а затем добавьте следующий код.  
  
     [!code-vb[VbVbcnMyFileSystem#36](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-by-using-net-framework-methods_2.vb)]  
  
> [!NOTE]
>  Интегрированная среда разработки (IDE) Visual Studio откроет редактор кода, а курсор будет помещен внутрь обработчика события, в который и следует добавить код.  
  
1.  Для записи в файл используйте метод <xref:System.IO.StreamWriter.Write%2A> класса <xref:System.IO.StreamWriter>. Добавьте следующий код сразу после `Dim fw As StreamWriter`. Не стоит беспокоиться о том, что возникнет исключение, если файл не существует, так как в этом случае он будет создан автоматически.  
  
     [!code-vb[VbVbcnMyFileSystem#37](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-by-using-net-framework-methods_3.vb)]  
  
2.  Чтобы пользователь не смог отправить пустую запись, добавьте следующий код сразу после `Dim ReadString As String`.  
  
     [!code-vb[VbVbcnMyFileSystem#38](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-by-using-net-framework-methods_4.vb)]  
  
3.  Поскольку речь идет о дневнике, пользователь захочет добавить к каждой записи дату. Вставьте следующий код после `fw = New StreamWriter("C:\MyDiary.txt", True)`, чтобы присвоить переменной `Today` значение текущей даты.  
  
     [!code-vb[VbVbcnMyFileSystem#39](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-by-using-net-framework-methods_5.vb)]  
  
4.  И, наконец добавьте код, очищающий элемент управления <xref:System.Windows.Forms.TextBox>. К событию <xref:System.Windows.Forms.Control.Click> для кнопки `Clear` добавьте следующий код.  
  
     [!code-vb[VbVbcnMyFileSystem#40](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-by-using-net-framework-methods_6.vb)]  
  
## <a name="adding-display-features-to-the-diary"></a>Добавление средств отображения в дневник  
 В этом разделе добавляется средство для отображения последней записи в элементе управления `DisplayEntry` <xref:System.Windows.Forms.TextBox>. Можно также добавить элемент управления <xref:System.Windows.Forms.ComboBox>, в котором будут отображаться различные записи и из которого пользователь сможет выбрать запись для отображения в элементе управления `DisplayEntry` <xref:System.Windows.Forms.TextBox>. Экземпляр класса <xref:System.IO.StreamReader> выполняет чтение из файла `MyDiary.txt`. Как и <xref:System.IO.StreamWriter>, класс <xref:System.IO.StreamReader> предназначен для работы с текстовыми файлами.  
  
 Для реализации следующей части пошагового руководства необходимо добавить в форму элементы управления из следующей таблицы и присвоить соответствующие значения их свойствам.  
  
|Control|Свойства|Значения|  
|-------------|----------------|------------|  
|<xref:System.Windows.Forms.TextBox>|**Имя**<br /><br /> **Visible**<br /><br /> **Size**<br /><br /> **Multiline**|`DisplayEntry`<br /><br /> `False`<br /><br /> `120,60`<br /><br /> `True`|  
|<xref:System.Windows.Forms.Button>|**Имя**<br /><br /> **Текст**|`Display`<br /><br /> **Отображение**|  
|<xref:System.Windows.Forms.Button>|**Имя**<br /><br /> **Текст**|`GetEntries`<br /><br /> **Показать записи**|  
|<xref:System.Windows.Forms.ComboBox>|**Имя**<br /><br /> **Текст**<br /><br /> **Enabled**|`PickEntries`<br /><br /> **Выберите запись**<br /><br /> `False`|  
  
#### <a name="to-populate-the-combo-box"></a>Заполнение элемента управления ComboBox  
  
1.  В элементе управления `PickEntries` <xref:System.Windows.Forms.ComboBox> отображается дата создания каждой из записей, чтобы пользователь мог выбрать запись за определенную дату. Создайте обработчик событий <xref:System.Windows.Forms.Control.Click> для кнопки `GetEntries` и добавьте следующий код.  
  
     [!code-vb[VbVbcnMyFileSystem#41](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-by-using-net-framework-methods_7.vb)]  
  
2.  Чтобы протестировать код, нажмите клавишу F5 для компиляции, а затем нажмите кнопку **Показать записи**. Щелкните стрелку раскрывающегося списка элемента управления <xref:System.Windows.Forms.ComboBox>, чтобы просмотреть даты создания всех записей.  
  
#### <a name="to-choose-and-display-individual-entries"></a>Выбор и просмотр отдельных записей  
  
1.  Создайте обработчик событий <xref:System.Windows.Forms.Control.Click> для кнопки `Display` и добавьте следующий код.  
  
     [!code-vb[VbVbcnMyFileSystem#42](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-by-using-net-framework-methods_8.vb)]  
  
2.  Чтобы протестировать код, нажмите клавишу F5 для компиляции, а затем введите запись. Нажмите кнопку **Показать записи**, выберите запись в элементе управления <xref:System.Windows.Forms.ComboBox>, а затем нажмите кнопку **Просмотреть**. Содержимое выбранной записи появится в элементе управления `DisplayEntry` <xref:System.Windows.Forms.TextBox>.  
  
## <a name="enabling-users-to-delete-or-modify-entries"></a>Предоставление пользователям возможности удалять и изменять записи  
 В заключение можно включить в приложение дополнительные функции, позволяющие пользователям удалять и изменять записи с помощью кнопок `DeleteEntry` и `EditEntry`. Обе кнопки неактивны, пока не выбрана ни одна запись.  
  
 Добавьте в форму элементы управления из следующей таблицы и установите для их свойств соответствующие значения.  
  
|Control|Свойства|Значения|  
|-------------|----------------|------------|  
|<xref:System.Windows.Forms.Button>|**Имя**<br /><br /> **Текст**<br /><br /> **Enabled**|`DeleteEntry`<br /><br /> **Удалить запись**<br /><br /> `False`|  
|<xref:System.Windows.Forms.Button>|**Имя**<br /><br /> **Текст**<br /><br /> **Enabled**|`EditEntry`<br /><br /> **Изменить запись**<br /><br /> `False`|  
|<xref:System.Windows.Forms.Button>|**Имя**<br /><br /> **Текст**<br /><br /> **Enabled**|`SubmitEdit`<br /><br /> **Сохранить изменения**<br /><br /> `False`|  
  
#### <a name="to-enable-deletion-and-modification-of-entries"></a>Включение возможности удаления и изменения записей  
  
1.  Добавьте следующий код к событию <xref:System.Windows.Forms.Control.Click> кнопки `Display` после `DisplayEntry.Text = ReadString`.  
  
     [!code-vb[VbVbcnMyFileSystem#43](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-by-using-net-framework-methods_9.vb)]  
  
2.  Создайте обработчик событий <xref:System.Windows.Forms.Control.Click> для кнопки `DeleteEntry` и добавьте следующий код.  
  
     [!code-vb[VbVbcnMyFileSystem#44](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-by-using-net-framework-methods_10.vb)]  
  
3.  Когда пользователь отображает запись, кнопка `EditEntry` становится доступной. Добавьте следующий код к событию <xref:System.Windows.Forms.Control.Click> кнопки `Display` после `DisplayEntry.Text = ReadString`.  
  
     [!code-vb[VbVbcnMyFileSystem#45](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-by-using-net-framework-methods_11.vb)]  
  
4.  Создайте обработчик событий <xref:System.Windows.Forms.Control.Click> для кнопки `EditEntry` и добавьте следующий код.  
  
     [!code-vb[VbVbcnMyFileSystem#46](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-by-using-net-framework-methods_12.vb)]  
  
5.  Создайте обработчик событий <xref:System.Windows.Forms.Control.Click> для кнопки `SubmitEdit` и добавьте следующий код.  
  
     [!code-vb[VbVbcnMyFileSystem#47](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-by-using-net-framework-methods_13.vb)]  
  
 Чтобы протестировать код, нажмите клавишу F5 для компиляции приложения. Щелкните **Показать записи**, выберите запись и нажмите кнопку **Посмотреть**. Запись будет отображена в элементе управления `DisplayEntry` <xref:System.Windows.Forms.TextBox>. Нажмите кнопку **Изменить запись**. Запись будет отображена в элементе управления `Entry` <xref:System.Windows.Forms.TextBox>. Отредактируйте запись в элементе управления `Entry` <xref:System.Windows.Forms.TextBox> и нажмите кнопку **Сохранить изменения**. Откройте `MyDiary.txt` файл, чтобы убедиться, что изменения внесены. Теперь выберите запись и нажмите кнопку **Удалить запись**. Когда появится окно сообщения <xref:System.Windows.Forms.MessageBox> с запросом подтверждения, нажмите кнопку **ОК**. Закройте приложение и откройте файл `MyDiary.txt` для подтверждения удаления.  
  
## <a name="see-also"></a>См. также  
 <xref:System.IO.StreamReader>   
 <xref:System.IO.StreamWriter>   
 [Пошаговые руководства](../../../../visual-basic/walkthroughs.md)


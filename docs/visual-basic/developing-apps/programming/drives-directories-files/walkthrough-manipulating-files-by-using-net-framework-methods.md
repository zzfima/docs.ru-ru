---
title: Управление файлами с помощью методов .NET Framework
ms.date: 07/20/2015
helpviewer_keywords:
- I/O [Visual Basic], walkthroughs
- text files [Visual Basic], writing to
- reading text files [Visual Basic]
- text, writing to files
- files [Visual Basic], searching
- StreamReader class, walkthroughs
- files [Visual Basic], accessing
- I/O [Visual Basic], writing text to files
- writing to files [Visual Basic], walkthroughs
- StreamWriter class, walkthroughs
- text files [Visual Basic], reading
- I/O [Visual Basic], reading text from files
ms.assetid: 7d2109eb-f98a-4389-b43d-30f384aaa7d5
ms.openlocfilehash: 02cdbcc59e8817ff4ec06c2f78f835cad77b10f2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "74333783"
---
# <a name="walkthrough-manipulating-files-by-using-net-framework-methods-visual-basic"></a>Пошаговое руководство. Управление файлами с помощью методов .NET Framework (Visual Basic)

В этом пошаговом руководстве демонстрируются открытие и чтение файла с помощью класса <xref:System.IO.StreamReader>, проверка доступа к файлу, поиск строки в файле, считанном с помощью экземпляра класса <xref:System.IO.StreamReader>, и запись в файл с помощью класса <xref:System.IO.StreamWriter>.

[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]

## <a name="creating-the-application"></a>Создание приложения

Запустите Visual Studio и начните проект с создания формы, которую пользователь сможет использовать для записи в намеченный файл.

### <a name="to-create-the-project"></a>Создание проекта

1. В меню **Файл** выберите **Создать проект**.

2. В области **Новый проект** щелкните **Приложения Windows**.

3. В поле **Имя** введите `MyDiary`, а затем нажмите кнопку **ОК**.

     Visual Studio добавит проект в **обозреватель решений**, после чего откроется **конструктор Windows Forms**.

4. Добавьте в форму элементы управления из следующей таблицы и установите для их свойств соответствующие значения.

|**Объект**|**Свойства**|**Value**|
|---|---|---|
|<xref:System.Windows.Forms.Button>|**Название**<br /><br /> **Текст**|`Submit`<br /><br /> **Сохранить запись**|
|<xref:System.Windows.Forms.Button>|**Название**<br /><br /> **Текст**|`Clear`<br /><br /> **Очистить запись**|
|<xref:System.Windows.Forms.TextBox>|**Название**<br /><br /> **Текст**<br /><br /> **Multiline**|`Entry`<br /><br /> **Введите произвольный текст.**<br /><br /> `False`|

## <a name="writing-to-the-file"></a>Запись в файл

Чтобы добавить возможность записи в файл с помощью приложения, воспользуйтесь классом <xref:System.IO.StreamWriter>. Класс <xref:System.IO.StreamWriter> предназначен для вывода символов в определенной кодировке, тогда как класс <xref:System.IO.Stream> предназначен для ввода и вывода двоичных данных. Класс <xref:System.IO.StreamWriter> следует использовать для записи строк данных в стандартный текстовый файл. Дополнительные сведения о классе <xref:System.IO.StreamWriter> см. в статье <xref:System.IO.StreamWriter>.

### <a name="to-add-writing-functionality"></a>Добавление возможности записи

1. В меню **Вид** выберите пункт **Код**, чтобы открыть редактор кода.

2. Поскольку приложение ссылается на пространство имен <xref:System.IO>, следует добавить следующие операторы в самом начале кода перед объявлением класса для формы, которое начинается с `Public Class Form1`.

     [!code-vb[VbVbcnMyFileSystem#35](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#35)]

     Перед записью в файл необходимо создать экземпляр класса <xref:System.IO.StreamWriter>.

3. В меню **Вид** выберите пункт **Конструктор** для возврата в окно **Конструктор Windows Forms**. Дважды щелкните кнопку `Submit`, чтобы создать для нее обработчик событий <xref:System.Windows.Forms.Control.Click>, а затем добавьте в него следующий код.

     [!code-vb[VbVbcnMyFileSystem#36](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#36)]

> [!NOTE]
> Интегрированная среда разработки (IDE) Visual Studio откроет редактор кода, а курсор будет помещен внутрь обработчика события, в который и следует добавить код.

1. Для записи в файл используйте метод <xref:System.IO.StreamWriter.Write%2A> класса <xref:System.IO.StreamWriter>. Добавьте следующий код сразу после `Dim fw As StreamWriter`. Не стоит беспокоиться о том, что возникнет исключение, если файл не существует, так как в этом случае он будет создан автоматически.

     [!code-vb[VbVbcnMyFileSystem#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#37)]

2. Чтобы пользователь не смог отправить пустую запись, добавьте следующий код сразу после `Dim ReadString As String`.

     [!code-vb[VbVbcnMyFileSystem#38](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#38)]

3. Поскольку речь идет о дневнике, пользователь захочет добавить к каждой записи дату. Вставьте следующий код после `fw = New StreamWriter("C:\MyDiary.txt", True)`, чтобы присвоить переменной `Today` значение текущей даты.

     [!code-vb[VbVbcnMyFileSystem#39](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#39)]

4. Наконец, добавьте код для очистки <xref:System.Windows.Forms.TextBox>. Добавьте следующий код в обработчик события `Clear` для кнопки <xref:System.Windows.Forms.Control.Click>.

     [!code-vb[VbVbcnMyFileSystem#40](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#40)]

## <a name="adding-display-features-to-the-diary"></a>Добавление средств отображения в дневник

В этом разделе вы добавите средство для отображения последней записи в элементе управления `DisplayEntry`<xref:System.Windows.Forms.TextBox>. Вы также можете добавить элемент <xref:System.Windows.Forms.ComboBox>, который отображает разные записи и позволяет пользователю выбрать запись для отображения в `DisplayEntry`<xref:System.Windows.Forms.TextBox>. Экземпляр класса <xref:System.IO.StreamReader> считывает информацию из `MyDiary.txt`. Как и класс <xref:System.IO.StreamWriter>, <xref:System.IO.StreamReader> предназначен для использования с текстовыми файлами.

Для реализации следующей части пошагового руководства необходимо добавить в форму элементы управления из следующей таблицы и присвоить соответствующие значения их свойствам.

|Элемент управления|Свойства|Значения|
|-------------|----------------|------------|
|<xref:System.Windows.Forms.TextBox>|**Название**<br /><br /> **Visible**<br /><br /> **Размер**<br /><br /> **Multiline**|`DisplayEntry`<br /><br /> `False`<br /><br /> `120,60`<br /><br /> `True`|
|<xref:System.Windows.Forms.Button>|**Название**<br /><br /> **Текст**|`Display`<br /><br /> **Отображение**|
|<xref:System.Windows.Forms.Button>|**Название**<br /><br /> **Текст**|`GetEntries`<br /><br /> **Показать записи**|
|<xref:System.Windows.Forms.ComboBox>|**Название**<br /><br /> **Текст**<br /><br /> **Включено**|`PickEntries`<br /><br /> **Выберите запись**<br /><br /> `False`|

### <a name="to-populate-the-combo-box"></a>Заполнение элемента управления ComboBox

1. В элементе управления `PickEntries`<xref:System.Windows.Forms.ComboBox> отображается дата создания каждой из записей, чтобы пользователь мог выбрать запись за определенную дату. Создайте обработчик события <xref:System.Windows.Forms.Control.Click> для кнопки `GetEntries` и добавьте в него следующий код.

     [!code-vb[VbVbcnMyFileSystem#41](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#41)]

2. Чтобы протестировать код, нажмите клавишу F5 для компиляции, а затем нажмите кнопку **Показать записи**. Щелкните стрелку раскрывающегося списка в <xref:System.Windows.Forms.ComboBox>, чтобы отобразить даты записей.

### <a name="to-choose-and-display-individual-entries"></a>Выбор и просмотр отдельных записей

1. Создайте обработчик события <xref:System.Windows.Forms.Control.Click> для кнопки `Display` и добавьте в него следующий код.

     [!code-vb[VbVbcnMyFileSystem#42](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#42)]

2. Чтобы протестировать код, нажмите клавишу F5 для компиляции, а затем введите запись. Щелкните **Показать записи**, выберите запись из списка <xref:System.Windows.Forms.ComboBox> и нажмите кнопку **Отображение**. Содержимое выбранной записи появится в элементе `DisplayEntry`<xref:System.Windows.Forms.TextBox>.

## <a name="enabling-users-to-delete-or-modify-entries"></a>Предоставление пользователям возможности удалять и изменять записи

В заключение можно включить в приложение дополнительные функции, позволяющие пользователям удалять и изменять записи с помощью кнопок `DeleteEntry` и `EditEntry`. Обе кнопки неактивны, пока не выбрана ни одна запись.

Добавьте в форму элементы управления из следующей таблицы и установите для их свойств соответствующие значения.

|Элемент управления|Свойства|Значения|
|-------------|----------------|------------|
|<xref:System.Windows.Forms.Button>|**Название**<br /><br /> **Текст**<br /><br /> **Включено**|`DeleteEntry`<br /><br /> **Удалить запись**<br /><br /> `False`|
|<xref:System.Windows.Forms.Button>|**Название**<br /><br /> **Текст**<br /><br /> **Включено**|`EditEntry`<br /><br /> **Изменить запись**<br /><br /> `False`|
|<xref:System.Windows.Forms.Button>|**Название**<br /><br /> **Текст**<br /><br /> **Включено**|`SubmitEdit`<br /><br /> **Сохранить изменения**<br /><br /> `False`|

### <a name="to-enable-deletion-and-modification-of-entries"></a>Включение возможности удаления и изменения записей

1. Добавьте следующий код в обработчик события `Display` для кнопки <xref:System.Windows.Forms.Control.Click> после элемента `DisplayEntry.Text = ReadString`.

     [!code-vb[VbVbcnMyFileSystem#43](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#43)]

2. Создайте обработчик события <xref:System.Windows.Forms.Control.Click> для кнопки `DeleteEntry` и добавьте в него следующий код.

     [!code-vb[VbVbcnMyFileSystem#44](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#44)]

3. Когда пользователь отображает запись, кнопка `EditEntry` становится доступной. Добавьте следующий код в обработчик событий <xref:System.Windows.Forms.Control.Click> для кнопки `Display` после элемента `DisplayEntry.Text = ReadString`.

     [!code-vb[VbVbcnMyFileSystem#45](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#45)]

4. Создайте обработчик события <xref:System.Windows.Forms.Control.Click> для кнопки `EditEntry` и добавьте в него следующий код.

     [!code-vb[VbVbcnMyFileSystem#46](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#46)]

5. Создайте обработчик события <xref:System.Windows.Forms.Control.Click> для кнопки `SubmitEdit` и добавьте в него следующий код.

     [!code-vb[VbVbcnMyFileSystem#47](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#47)]

Чтобы протестировать код, нажмите клавишу F5 для компиляции приложения. Щелкните **Показать записи**, выберите запись и нажмите кнопку **Посмотреть**. Выбранная запись появится в элементе `DisplayEntry`<xref:System.Windows.Forms.TextBox>. Нажмите кнопку **Изменить запись**. Выбранная запись появится в элементе `Entry`<xref:System.Windows.Forms.TextBox>. Измените запись в `Entry`<xref:System.Windows.Forms.TextBox> и щелкните действие **Сохранить изменения**. Откройте `MyDiary.txt` файл, чтобы убедиться, что изменения внесены. Теперь выберите запись и нажмите кнопку **Удалить запись**. Когда <xref:System.Windows.Forms.MessageBox> запросит подтверждение, нажмите кнопку **ОК**. Закройте приложение и откройте файл `MyDiary.txt` для подтверждения удаления.

## <a name="see-also"></a>См. также раздел

- <xref:System.IO.StreamReader>
- <xref:System.IO.StreamWriter>
- [Пошаговые руководства](../../../../visual-basic/walkthroughs.md)

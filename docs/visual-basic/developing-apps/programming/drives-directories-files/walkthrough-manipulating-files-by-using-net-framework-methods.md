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
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74333783"
---
# <a name="walkthrough-manipulating-files-by-using-net-framework-methods-visual-basic"></a><span data-ttu-id="3f3f7-102">Пошаговое руководство. Управление файлами с помощью методов .NET Framework (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3f3f7-102">Walkthrough: Manipulating Files by Using .NET Framework Methods (Visual Basic)</span></span>

<span data-ttu-id="3f3f7-103">В этом пошаговом руководстве демонстрируются открытие и чтение файла с помощью класса <xref:System.IO.StreamReader>, проверка доступа к файлу, поиск строки в файле, считанном с помощью экземпляра класса <xref:System.IO.StreamReader>, и запись в файл с помощью класса <xref:System.IO.StreamWriter>.</span><span class="sxs-lookup"><span data-stu-id="3f3f7-103">This walkthrough demonstrates how to open and read a file using the <xref:System.IO.StreamReader> class, check to see if a file is being accessed, search for a string within a file read with an instance of the <xref:System.IO.StreamReader> class, and write to a file using the <xref:System.IO.StreamWriter> class.</span></span>

[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]

## <a name="creating-the-application"></a><span data-ttu-id="3f3f7-104">Создание приложения</span><span class="sxs-lookup"><span data-stu-id="3f3f7-104">Creating the Application</span></span>

<span data-ttu-id="3f3f7-105">Запустите Visual Studio и начните проект с создания формы, которую пользователь сможет использовать для записи в намеченный файл.</span><span class="sxs-lookup"><span data-stu-id="3f3f7-105">Start Visual Studio and begin the project by creating a form that the user can use to write to the designated file.</span></span>

### <a name="to-create-the-project"></a><span data-ttu-id="3f3f7-106">Создание проекта</span><span class="sxs-lookup"><span data-stu-id="3f3f7-106">To create the project</span></span>

1. <span data-ttu-id="3f3f7-107">В меню **Файл** выберите **Создать проект**.</span><span class="sxs-lookup"><span data-stu-id="3f3f7-107">On the **File** menu, select **New Project**.</span></span>

2. <span data-ttu-id="3f3f7-108">В области **Новый проект** щелкните **Приложения Windows**.</span><span class="sxs-lookup"><span data-stu-id="3f3f7-108">In the **New Project** pane, click **Windows Application**.</span></span>

3. <span data-ttu-id="3f3f7-109">В поле **Имя** введите `MyDiary`, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="3f3f7-109">In the **Name** box type `MyDiary` and click **OK**.</span></span>

     <span data-ttu-id="3f3f7-110">Visual Studio добавит проект в **обозреватель решений**, после чего откроется **конструктор Windows Forms**.</span><span class="sxs-lookup"><span data-stu-id="3f3f7-110">Visual Studio adds the project to **Solution Explorer**, and the **Windows Forms Designer** opens.</span></span>

4. <span data-ttu-id="3f3f7-111">Добавьте в форму элементы управления из следующей таблицы и установите для их свойств соответствующие значения.</span><span class="sxs-lookup"><span data-stu-id="3f3f7-111">Add the controls in the following table to the form and set the corresponding values for their properties.</span></span>

|<span data-ttu-id="3f3f7-112">**Объект**</span><span class="sxs-lookup"><span data-stu-id="3f3f7-112">**Object**</span></span>|<span data-ttu-id="3f3f7-113">**Свойства**</span><span class="sxs-lookup"><span data-stu-id="3f3f7-113">**Properties**</span></span>|<span data-ttu-id="3f3f7-114">**Значение**</span><span class="sxs-lookup"><span data-stu-id="3f3f7-114">**Value**</span></span>|
|---|---|---|
|<xref:System.Windows.Forms.Button>|<span data-ttu-id="3f3f7-115">**Name**</span><span class="sxs-lookup"><span data-stu-id="3f3f7-115">**Name**</span></span><br /><br /> <span data-ttu-id="3f3f7-116">**Text**</span><span class="sxs-lookup"><span data-stu-id="3f3f7-116">**Text**</span></span>|`Submit`<br /><br /> <span data-ttu-id="3f3f7-117">**Сохранить запись**</span><span class="sxs-lookup"><span data-stu-id="3f3f7-117">**Submit Entry**</span></span>|
|<xref:System.Windows.Forms.Button>|<span data-ttu-id="3f3f7-118">**Name**</span><span class="sxs-lookup"><span data-stu-id="3f3f7-118">**Name**</span></span><br /><br /> <span data-ttu-id="3f3f7-119">**Text**</span><span class="sxs-lookup"><span data-stu-id="3f3f7-119">**Text**</span></span>|`Clear`<br /><br /> <span data-ttu-id="3f3f7-120">**Очистить запись**</span><span class="sxs-lookup"><span data-stu-id="3f3f7-120">**Clear Entry**</span></span>|
|<xref:System.Windows.Forms.TextBox>|<span data-ttu-id="3f3f7-121">**Name**</span><span class="sxs-lookup"><span data-stu-id="3f3f7-121">**Name**</span></span><br /><br /> <span data-ttu-id="3f3f7-122">**Text**</span><span class="sxs-lookup"><span data-stu-id="3f3f7-122">**Text**</span></span><br /><br /> <span data-ttu-id="3f3f7-123">**Multiline**</span><span class="sxs-lookup"><span data-stu-id="3f3f7-123">**Multiline**</span></span>|`Entry`<br /><br /> <span data-ttu-id="3f3f7-124">**Введите произвольный текст.**</span><span class="sxs-lookup"><span data-stu-id="3f3f7-124">**Please enter something.**</span></span><br /><br /> `False`|

## <a name="writing-to-the-file"></a><span data-ttu-id="3f3f7-125">Запись в файл</span><span class="sxs-lookup"><span data-stu-id="3f3f7-125">Writing to the File</span></span>

<span data-ttu-id="3f3f7-126">Чтобы добавить возможность записи в файл с помощью приложения, воспользуйтесь классом <xref:System.IO.StreamWriter>.</span><span class="sxs-lookup"><span data-stu-id="3f3f7-126">To add the ability to write to a file via the application, use the <xref:System.IO.StreamWriter> class.</span></span> <span data-ttu-id="3f3f7-127">Класс <xref:System.IO.StreamWriter> предназначен для вывода символов в определенной кодировке, тогда как класс <xref:System.IO.Stream> предназначен для ввода и вывода двоичных данных.</span><span class="sxs-lookup"><span data-stu-id="3f3f7-127"><xref:System.IO.StreamWriter> is designed for character output in a particular encoding, whereas the <xref:System.IO.Stream> class is designed for byte input and output.</span></span> <span data-ttu-id="3f3f7-128">Класс <xref:System.IO.StreamWriter> следует использовать для записи строк данных в стандартный текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="3f3f7-128">Use <xref:System.IO.StreamWriter> for writing lines of information to a standard text file.</span></span> <span data-ttu-id="3f3f7-129">Дополнительные сведения о классе <xref:System.IO.StreamWriter> см. в статье <xref:System.IO.StreamWriter>.</span><span class="sxs-lookup"><span data-stu-id="3f3f7-129">For more information on the <xref:System.IO.StreamWriter> class, see <xref:System.IO.StreamWriter>.</span></span>

### <a name="to-add-writing-functionality"></a><span data-ttu-id="3f3f7-130">Добавление возможности записи</span><span class="sxs-lookup"><span data-stu-id="3f3f7-130">To add writing functionality</span></span>

1. <span data-ttu-id="3f3f7-131">В меню **Вид** выберите пункт **Код**, чтобы открыть редактор кода.</span><span class="sxs-lookup"><span data-stu-id="3f3f7-131">From the **View** menu, choose **Code** to open the Code Editor.</span></span>

2. <span data-ttu-id="3f3f7-132">Поскольку приложение ссылается на пространство имен <xref:System.IO>, следует добавить следующие операторы в самом начале кода перед объявлением класса для формы, которое начинается с `Public Class Form1`.</span><span class="sxs-lookup"><span data-stu-id="3f3f7-132">Because the application references the <xref:System.IO> namespace, add the following statements at the very beginning of your code, before the class declaration for the form, which begins `Public Class Form1`.</span></span>

     [!code-vb[VbVbcnMyFileSystem#35](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#35)]

     <span data-ttu-id="3f3f7-133">Перед записью в файл необходимо создать экземпляр класса <xref:System.IO.StreamWriter>.</span><span class="sxs-lookup"><span data-stu-id="3f3f7-133">Before writing to the file, you must create an instance of a <xref:System.IO.StreamWriter> class.</span></span>

3. <span data-ttu-id="3f3f7-134">В меню **Вид** выберите пункт **Конструктор** для возврата в окно **Конструктор Windows Forms**.</span><span class="sxs-lookup"><span data-stu-id="3f3f7-134">From the **View** menu, choose **Designer** to return to the **Windows Forms Designer**.</span></span> <span data-ttu-id="3f3f7-135">Дважды щелкните кнопку `Submit`, чтобы создать для нее обработчик событий <xref:System.Windows.Forms.Control.Click>, а затем добавьте в него следующий код.</span><span class="sxs-lookup"><span data-stu-id="3f3f7-135">Double-click the `Submit` button to create a <xref:System.Windows.Forms.Control.Click> event handler for the button, and then add the following code.</span></span>

     [!code-vb[VbVbcnMyFileSystem#36](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#36)]

> [!NOTE]
> <span data-ttu-id="3f3f7-136">Интегрированная среда разработки (IDE) Visual Studio откроет редактор кода, а курсор будет помещен внутрь обработчика события, в который и следует добавить код.</span><span class="sxs-lookup"><span data-stu-id="3f3f7-136">The Visual Studio Integrated Development Environment (IDE) will return to the Code Editor and position the insertion point within the event handler where you should add the code.</span></span>

1. <span data-ttu-id="3f3f7-137">Для записи в файл используйте метод <xref:System.IO.StreamWriter.Write%2A> класса <xref:System.IO.StreamWriter>.</span><span class="sxs-lookup"><span data-stu-id="3f3f7-137">To write to the file, use the <xref:System.IO.StreamWriter.Write%2A> method of the <xref:System.IO.StreamWriter> class.</span></span> <span data-ttu-id="3f3f7-138">Добавьте следующий код сразу после `Dim fw As StreamWriter`.</span><span class="sxs-lookup"><span data-stu-id="3f3f7-138">Add the following code directly after `Dim fw As StreamWriter`.</span></span> <span data-ttu-id="3f3f7-139">Не стоит беспокоиться о том, что возникнет исключение, если файл не существует, так как в этом случае он будет создан автоматически.</span><span class="sxs-lookup"><span data-stu-id="3f3f7-139">You do not need to worry that an exception will be thrown if the file is not found, because it will be created if it does not already exist.</span></span>

     [!code-vb[VbVbcnMyFileSystem#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#37)]

2. <span data-ttu-id="3f3f7-140">Чтобы пользователь не смог отправить пустую запись, добавьте следующий код сразу после `Dim ReadString As String`.</span><span class="sxs-lookup"><span data-stu-id="3f3f7-140">Make sure that the user cannot submit a blank entry by adding the following code directly after `Dim ReadString As String`.</span></span>

     [!code-vb[VbVbcnMyFileSystem#38](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#38)]

3. <span data-ttu-id="3f3f7-141">Поскольку речь идет о дневнике, пользователь захочет добавить к каждой записи дату.</span><span class="sxs-lookup"><span data-stu-id="3f3f7-141">Because this is a diary, the user will want to assign a date to each entry.</span></span> <span data-ttu-id="3f3f7-142">Вставьте следующий код после `fw = New StreamWriter("C:\MyDiary.txt", True)`, чтобы присвоить переменной `Today` значение текущей даты.</span><span class="sxs-lookup"><span data-stu-id="3f3f7-142">Insert the following code after `fw = New StreamWriter("C:\MyDiary.txt", True)` to set the variable `Today` to the current date.</span></span>

     [!code-vb[VbVbcnMyFileSystem#39](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#39)]

4. <span data-ttu-id="3f3f7-143">Наконец, добавьте код для очистки <xref:System.Windows.Forms.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="3f3f7-143">Finally, attach code to clear the <xref:System.Windows.Forms.TextBox>.</span></span> <span data-ttu-id="3f3f7-144">Добавьте следующий код в обработчик события `Clear` для кнопки <xref:System.Windows.Forms.Control.Click>.</span><span class="sxs-lookup"><span data-stu-id="3f3f7-144">Add the following code to the `Clear` button's <xref:System.Windows.Forms.Control.Click> event.</span></span>

     [!code-vb[VbVbcnMyFileSystem#40](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#40)]

## <a name="adding-display-features-to-the-diary"></a><span data-ttu-id="3f3f7-145">Добавление средств отображения в дневник</span><span class="sxs-lookup"><span data-stu-id="3f3f7-145">Adding Display Features to the Diary</span></span>

<span data-ttu-id="3f3f7-146">В этом разделе вы добавите средство для отображения последней записи в элементе управления `DisplayEntry`<xref:System.Windows.Forms.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="3f3f7-146">In this section, you add a feature that displays the latest entry in the `DisplayEntry`<xref:System.Windows.Forms.TextBox>.</span></span> <span data-ttu-id="3f3f7-147">Вы также можете добавить элемент <xref:System.Windows.Forms.ComboBox>, который отображает разные записи и позволяет пользователю выбрать запись для отображения в `DisplayEntry`<xref:System.Windows.Forms.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="3f3f7-147">You can also add a <xref:System.Windows.Forms.ComboBox> that displays various entries and from which a user can select an entry to display in the `DisplayEntry`<xref:System.Windows.Forms.TextBox>.</span></span> <span data-ttu-id="3f3f7-148">Экземпляр класса <xref:System.IO.StreamReader> считывает информацию из `MyDiary.txt`.</span><span class="sxs-lookup"><span data-stu-id="3f3f7-148">An instance of the <xref:System.IO.StreamReader> class reads from `MyDiary.txt`.</span></span> <span data-ttu-id="3f3f7-149">Как и класс <xref:System.IO.StreamWriter>, <xref:System.IO.StreamReader> предназначен для использования с текстовыми файлами.</span><span class="sxs-lookup"><span data-stu-id="3f3f7-149">Like the <xref:System.IO.StreamWriter> class, <xref:System.IO.StreamReader> is intended for use with text files.</span></span>

<span data-ttu-id="3f3f7-150">Для реализации следующей части пошагового руководства необходимо добавить в форму элементы управления из следующей таблицы и присвоить соответствующие значения их свойствам.</span><span class="sxs-lookup"><span data-stu-id="3f3f7-150">For this section of the walkthrough, add the controls in the following table to the form and set the corresponding values for their properties.</span></span>

|<span data-ttu-id="3f3f7-151">Элемент управления</span><span class="sxs-lookup"><span data-stu-id="3f3f7-151">Control</span></span>|<span data-ttu-id="3f3f7-152">Свойства</span><span class="sxs-lookup"><span data-stu-id="3f3f7-152">Properties</span></span>|<span data-ttu-id="3f3f7-153">Значения</span><span class="sxs-lookup"><span data-stu-id="3f3f7-153">Values</span></span>|
|-------------|----------------|------------|
|<xref:System.Windows.Forms.TextBox>|<span data-ttu-id="3f3f7-154">**Name**</span><span class="sxs-lookup"><span data-stu-id="3f3f7-154">**Name**</span></span><br /><br /> <span data-ttu-id="3f3f7-155">**Показывается**</span><span class="sxs-lookup"><span data-stu-id="3f3f7-155">**Visible**</span></span><br /><br /> <span data-ttu-id="3f3f7-156">**Size**</span><span class="sxs-lookup"><span data-stu-id="3f3f7-156">**Size**</span></span><br /><br /> <span data-ttu-id="3f3f7-157">**Multiline**</span><span class="sxs-lookup"><span data-stu-id="3f3f7-157">**Multiline**</span></span>|`DisplayEntry`<br /><br /> `False`<br /><br /> `120,60`<br /><br /> `True`|
|<xref:System.Windows.Forms.Button>|<span data-ttu-id="3f3f7-158">**Name**</span><span class="sxs-lookup"><span data-stu-id="3f3f7-158">**Name**</span></span><br /><br /> <span data-ttu-id="3f3f7-159">**Text**</span><span class="sxs-lookup"><span data-stu-id="3f3f7-159">**Text**</span></span>|`Display`<br /><br /> <span data-ttu-id="3f3f7-160">**Отображение**</span><span class="sxs-lookup"><span data-stu-id="3f3f7-160">**Display**</span></span>|
|<xref:System.Windows.Forms.Button>|<span data-ttu-id="3f3f7-161">**Name**</span><span class="sxs-lookup"><span data-stu-id="3f3f7-161">**Name**</span></span><br /><br /> <span data-ttu-id="3f3f7-162">**Текст**</span><span class="sxs-lookup"><span data-stu-id="3f3f7-162">**Text**</span></span>|`GetEntries`<br /><br /> <span data-ttu-id="3f3f7-163">**Показать записи**</span><span class="sxs-lookup"><span data-stu-id="3f3f7-163">**Get Entries**</span></span>|
|<xref:System.Windows.Forms.ComboBox>|<span data-ttu-id="3f3f7-164">**Name**</span><span class="sxs-lookup"><span data-stu-id="3f3f7-164">**Name**</span></span><br /><br /> <span data-ttu-id="3f3f7-165">**Text**</span><span class="sxs-lookup"><span data-stu-id="3f3f7-165">**Text**</span></span><br /><br /> <span data-ttu-id="3f3f7-166">**Включено**</span><span class="sxs-lookup"><span data-stu-id="3f3f7-166">**Enabled**</span></span>|`PickEntries`<br /><br /> <span data-ttu-id="3f3f7-167">**Выберите запись**</span><span class="sxs-lookup"><span data-stu-id="3f3f7-167">**Select an Entry**</span></span><br /><br /> `False`|

### <a name="to-populate-the-combo-box"></a><span data-ttu-id="3f3f7-168">Заполнение элемента управления ComboBox</span><span class="sxs-lookup"><span data-stu-id="3f3f7-168">To populate the combo box</span></span>

1. <span data-ttu-id="3f3f7-169">В элементе управления `PickEntries`<xref:System.Windows.Forms.ComboBox> отображается дата создания каждой из записей, чтобы пользователь мог выбрать запись за определенную дату.</span><span class="sxs-lookup"><span data-stu-id="3f3f7-169">The `PickEntries`<xref:System.Windows.Forms.ComboBox> is used to display the dates on which a user submits each entry, so the user can select an entry from a specific date.</span></span> <span data-ttu-id="3f3f7-170">Создайте обработчик события <xref:System.Windows.Forms.Control.Click> для кнопки `GetEntries` и добавьте в него следующий код.</span><span class="sxs-lookup"><span data-stu-id="3f3f7-170">Create a <xref:System.Windows.Forms.Control.Click> event handler to the `GetEntries` button and add the following code.</span></span>

     [!code-vb[VbVbcnMyFileSystem#41](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#41)]

2. <span data-ttu-id="3f3f7-171">Чтобы протестировать код, нажмите клавишу F5 для компиляции, а затем нажмите кнопку **Показать записи**.</span><span class="sxs-lookup"><span data-stu-id="3f3f7-171">To test your code, press F5 to compile the application, and then click **Get Entries**.</span></span> <span data-ttu-id="3f3f7-172">Щелкните стрелку раскрывающегося списка в <xref:System.Windows.Forms.ComboBox>, чтобы отобразить даты записей.</span><span class="sxs-lookup"><span data-stu-id="3f3f7-172">Click the drop-down arrow in the <xref:System.Windows.Forms.ComboBox> to display the entry dates.</span></span>

### <a name="to-choose-and-display-individual-entries"></a><span data-ttu-id="3f3f7-173">Выбор и просмотр отдельных записей</span><span class="sxs-lookup"><span data-stu-id="3f3f7-173">To choose and display individual entries</span></span>

1. <span data-ttu-id="3f3f7-174">Создайте обработчик события <xref:System.Windows.Forms.Control.Click> для кнопки `Display` и добавьте в него следующий код.</span><span class="sxs-lookup"><span data-stu-id="3f3f7-174">Create a <xref:System.Windows.Forms.Control.Click> event handler for the `Display` button and add the following code.</span></span>

     [!code-vb[VbVbcnMyFileSystem#42](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#42)]

2. <span data-ttu-id="3f3f7-175">Чтобы протестировать код, нажмите клавишу F5 для компиляции, а затем введите запись.</span><span class="sxs-lookup"><span data-stu-id="3f3f7-175">To test your code, press F5 to compile the application, and then submit an entry.</span></span> <span data-ttu-id="3f3f7-176">Щелкните **Показать записи**, выберите запись из списка <xref:System.Windows.Forms.ComboBox> и нажмите кнопку **Отображение**.</span><span class="sxs-lookup"><span data-stu-id="3f3f7-176">Click **Get Entries**, select an entry from the <xref:System.Windows.Forms.ComboBox>, and then click **Display**.</span></span> <span data-ttu-id="3f3f7-177">Содержимое выбранной записи появится в элементе `DisplayEntry`<xref:System.Windows.Forms.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="3f3f7-177">The contents of the selected entry appear in the `DisplayEntry`<xref:System.Windows.Forms.TextBox>.</span></span>

## <a name="enabling-users-to-delete-or-modify-entries"></a><span data-ttu-id="3f3f7-178">Предоставление пользователям возможности удалять и изменять записи</span><span class="sxs-lookup"><span data-stu-id="3f3f7-178">Enabling Users to Delete or Modify Entries</span></span>

<span data-ttu-id="3f3f7-179">В заключение можно включить в приложение дополнительные функции, позволяющие пользователям удалять и изменять записи с помощью кнопок `DeleteEntry` и `EditEntry`.</span><span class="sxs-lookup"><span data-stu-id="3f3f7-179">Finally, you can include additional functionality enables users to delete or modify an entry by using `DeleteEntry` and `EditEntry` buttons.</span></span> <span data-ttu-id="3f3f7-180">Обе кнопки неактивны, пока не выбрана ни одна запись.</span><span class="sxs-lookup"><span data-stu-id="3f3f7-180">Both buttons remain disabled unless an entry is displayed.</span></span>

<span data-ttu-id="3f3f7-181">Добавьте в форму элементы управления из следующей таблицы и установите для их свойств соответствующие значения.</span><span class="sxs-lookup"><span data-stu-id="3f3f7-181">Add the controls in the following table to the form and set the corresponding values for their properties.</span></span>

|<span data-ttu-id="3f3f7-182">Элемент управления</span><span class="sxs-lookup"><span data-stu-id="3f3f7-182">Control</span></span>|<span data-ttu-id="3f3f7-183">Свойства</span><span class="sxs-lookup"><span data-stu-id="3f3f7-183">Properties</span></span>|<span data-ttu-id="3f3f7-184">Значения</span><span class="sxs-lookup"><span data-stu-id="3f3f7-184">Values</span></span>|
|-------------|----------------|------------|
|<xref:System.Windows.Forms.Button>|<span data-ttu-id="3f3f7-185">**Name**</span><span class="sxs-lookup"><span data-stu-id="3f3f7-185">**Name**</span></span><br /><br /> <span data-ttu-id="3f3f7-186">**Text**</span><span class="sxs-lookup"><span data-stu-id="3f3f7-186">**Text**</span></span><br /><br /> <span data-ttu-id="3f3f7-187">**Включено**</span><span class="sxs-lookup"><span data-stu-id="3f3f7-187">**Enabled**</span></span>|`DeleteEntry`<br /><br /> <span data-ttu-id="3f3f7-188">**Удалить запись**</span><span class="sxs-lookup"><span data-stu-id="3f3f7-188">**Delete Entry**</span></span><br /><br /> `False`|
|<xref:System.Windows.Forms.Button>|<span data-ttu-id="3f3f7-189">**Name**</span><span class="sxs-lookup"><span data-stu-id="3f3f7-189">**Name**</span></span><br /><br /> <span data-ttu-id="3f3f7-190">**Text**</span><span class="sxs-lookup"><span data-stu-id="3f3f7-190">**Text**</span></span><br /><br /> <span data-ttu-id="3f3f7-191">**Включено**</span><span class="sxs-lookup"><span data-stu-id="3f3f7-191">**Enabled**</span></span>|`EditEntry`<br /><br /> <span data-ttu-id="3f3f7-192">**Изменить запись**</span><span class="sxs-lookup"><span data-stu-id="3f3f7-192">**Edit Entry**</span></span><br /><br /> `False`|
|<xref:System.Windows.Forms.Button>|<span data-ttu-id="3f3f7-193">**Name**</span><span class="sxs-lookup"><span data-stu-id="3f3f7-193">**Name**</span></span><br /><br /> <span data-ttu-id="3f3f7-194">**Text**</span><span class="sxs-lookup"><span data-stu-id="3f3f7-194">**Text**</span></span><br /><br /> <span data-ttu-id="3f3f7-195">**Enabled**</span><span class="sxs-lookup"><span data-stu-id="3f3f7-195">**Enabled**</span></span>|`SubmitEdit`<br /><br /> <span data-ttu-id="3f3f7-196">**Сохранить изменения**</span><span class="sxs-lookup"><span data-stu-id="3f3f7-196">**Submit Edit**</span></span><br /><br /> `False`|

### <a name="to-enable-deletion-and-modification-of-entries"></a><span data-ttu-id="3f3f7-197">Включение возможности удаления и изменения записей</span><span class="sxs-lookup"><span data-stu-id="3f3f7-197">To enable deletion and modification of entries</span></span>

1. <span data-ttu-id="3f3f7-198">Добавьте следующий код в обработчик события `Display` для кнопки <xref:System.Windows.Forms.Control.Click> после элемента `DisplayEntry.Text = ReadString`.</span><span class="sxs-lookup"><span data-stu-id="3f3f7-198">Add the following code to the `Display` button's <xref:System.Windows.Forms.Control.Click> event, after `DisplayEntry.Text = ReadString`.</span></span>

     [!code-vb[VbVbcnMyFileSystem#43](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#43)]

2. <span data-ttu-id="3f3f7-199">Создайте обработчик события <xref:System.Windows.Forms.Control.Click> для кнопки `DeleteEntry` и добавьте в него следующий код.</span><span class="sxs-lookup"><span data-stu-id="3f3f7-199">Create a <xref:System.Windows.Forms.Control.Click> event handler for the `DeleteEntry` button and add the following code.</span></span>

     [!code-vb[VbVbcnMyFileSystem#44](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#44)]

3. <span data-ttu-id="3f3f7-200">Когда пользователь отображает запись, кнопка `EditEntry` становится доступной.</span><span class="sxs-lookup"><span data-stu-id="3f3f7-200">When a user displays an entry, the `EditEntry` button becomes enabled.</span></span> <span data-ttu-id="3f3f7-201">Добавьте следующий код в обработчик событий <xref:System.Windows.Forms.Control.Click> для кнопки `Display` после элемента `DisplayEntry.Text = ReadString`.</span><span class="sxs-lookup"><span data-stu-id="3f3f7-201">Add the following code to the <xref:System.Windows.Forms.Control.Click> event of the `Display` button after `DisplayEntry.Text = ReadString`.</span></span>

     [!code-vb[VbVbcnMyFileSystem#45](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#45)]

4. <span data-ttu-id="3f3f7-202">Создайте обработчик события <xref:System.Windows.Forms.Control.Click> для кнопки `EditEntry` и добавьте в него следующий код.</span><span class="sxs-lookup"><span data-stu-id="3f3f7-202">Create a <xref:System.Windows.Forms.Control.Click> event handler for the `EditEntry` button and add the following code.</span></span>

     [!code-vb[VbVbcnMyFileSystem#46](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#46)]

5. <span data-ttu-id="3f3f7-203">Создайте обработчик события <xref:System.Windows.Forms.Control.Click> для кнопки `SubmitEdit` и добавьте в него следующий код.</span><span class="sxs-lookup"><span data-stu-id="3f3f7-203">Create a <xref:System.Windows.Forms.Control.Click> event handler for the `SubmitEdit` button and add the following code</span></span>

     [!code-vb[VbVbcnMyFileSystem#47](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#47)]

<span data-ttu-id="3f3f7-204">Чтобы протестировать код, нажмите клавишу F5 для компиляции приложения.</span><span class="sxs-lookup"><span data-stu-id="3f3f7-204">To test your code, press F5 to compile the application.</span></span> <span data-ttu-id="3f3f7-205">Щелкните **Показать записи**, выберите запись и нажмите кнопку **Посмотреть**.</span><span class="sxs-lookup"><span data-stu-id="3f3f7-205">Click **Get Entries**, select an entry, and then click **Display**.</span></span> <span data-ttu-id="3f3f7-206">Выбранная запись появится в элементе `DisplayEntry`<xref:System.Windows.Forms.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="3f3f7-206">The entry appears in the `DisplayEntry`<xref:System.Windows.Forms.TextBox>.</span></span> <span data-ttu-id="3f3f7-207">Нажмите кнопку **Изменить запись**.</span><span class="sxs-lookup"><span data-stu-id="3f3f7-207">Click **Edit Entry**.</span></span> <span data-ttu-id="3f3f7-208">Выбранная запись появится в элементе `Entry`<xref:System.Windows.Forms.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="3f3f7-208">The entry appears in the `Entry`<xref:System.Windows.Forms.TextBox>.</span></span> <span data-ttu-id="3f3f7-209">Измените запись в `Entry`<xref:System.Windows.Forms.TextBox> и щелкните действие **Сохранить изменения**.</span><span class="sxs-lookup"><span data-stu-id="3f3f7-209">Edit the entry in the `Entry`<xref:System.Windows.Forms.TextBox> and click **Submit Edit**.</span></span> <span data-ttu-id="3f3f7-210">Откройте `MyDiary.txt` файл, чтобы убедиться, что изменения внесены.</span><span class="sxs-lookup"><span data-stu-id="3f3f7-210">Open the `MyDiary.txt` file to confirm your correction.</span></span> <span data-ttu-id="3f3f7-211">Теперь выберите запись и нажмите кнопку **Удалить запись**.</span><span class="sxs-lookup"><span data-stu-id="3f3f7-211">Now select an entry and click **Delete Entry**.</span></span> <span data-ttu-id="3f3f7-212">Когда <xref:System.Windows.Forms.MessageBox> запросит подтверждение, нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="3f3f7-212">When the <xref:System.Windows.Forms.MessageBox> requests confirmation, click **OK**.</span></span> <span data-ttu-id="3f3f7-213">Закройте приложение и откройте файл `MyDiary.txt` для подтверждения удаления.</span><span class="sxs-lookup"><span data-stu-id="3f3f7-213">Close the application and open `MyDiary.txt` to confirm the deletion.</span></span>

## <a name="see-also"></a><span data-ttu-id="3f3f7-214">См. также</span><span class="sxs-lookup"><span data-stu-id="3f3f7-214">See also</span></span>

- <xref:System.IO.StreamReader>
- <xref:System.IO.StreamWriter>
- [<span data-ttu-id="3f3f7-215">Пошаговые руководства</span><span class="sxs-lookup"><span data-stu-id="3f3f7-215">Walkthroughs</span></span>](../../../../visual-basic/walkthroughs.md)

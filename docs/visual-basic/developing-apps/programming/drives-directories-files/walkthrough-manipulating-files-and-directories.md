---
title: Операции с файлами и каталогами
ms.date: 07/20/2015
helpviewer_keywords:
- files [Visual Basic], reading text
- reading files [Visual Basic], text
- I/O [Visual Basic], walkthroughs
- text, writing to files
- text, reading from files
- reading text from files [Visual Basic], walkthroughs
- Visual Basic code, file access
- files [Visual Basic], writing text
- I/O [Visual Basic], writing text to files
- file access, walkthroughs
- writing to files [Visual Basic], walkthroughs
- I/O [Visual Basic], reading text from files
ms.assetid: cae77565-9f78-4e46-8e42-eb2f9f8e1ffd
ms.openlocfilehash: 83dc6ce0d29c1c368c36b51fc84ecad34d72e01f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "74333806"
---
# <a name="walkthrough-manipulating-files-and-directories-in-visual-basic"></a><span data-ttu-id="293f4-102">Пошаговое руководство. Операции с файлами и каталогами в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="293f4-102">Walkthrough: Manipulating Files and Directories in Visual Basic</span></span>

<span data-ttu-id="293f4-103">В этом пошаговом руководстве приводятся основные сведения о файловом вводе-выводе в Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="293f4-103">This walkthrough provides an introduction to the fundamentals of file I/O in Visual Basic.</span></span> <span data-ttu-id="293f4-104">В нем описывается создание небольшого приложения, перечисляющего текстовые файлы в каталоге и анализирующего их.</span><span class="sxs-lookup"><span data-stu-id="293f4-104">It describes how to create a small application that lists and examines text files in a directory.</span></span> <span data-ttu-id="293f4-105">Для каждого выбранного текстового файла приложение предоставляет атрибуты файла и первую строку содержимого.</span><span class="sxs-lookup"><span data-stu-id="293f4-105">For each selected text file, the application provides file attributes and the first line of content.</span></span> <span data-ttu-id="293f4-106">Кроме того, предоставляется возможность записать информацию в файл журнала.</span><span class="sxs-lookup"><span data-stu-id="293f4-106">There is an option to write information to a log file.</span></span>  
  
 <span data-ttu-id="293f4-107">В этом пошаговом руководстве используются члены `My.Computer.FileSystem Object`, доступные в Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="293f4-107">This walkthrough uses members of the `My.Computer.FileSystem Object`, which are available in Visual Basic.</span></span> <span data-ttu-id="293f4-108">Дополнительные сведения см. в разделе <xref:Microsoft.VisualBasic.FileIO.FileSystem>.</span><span class="sxs-lookup"><span data-stu-id="293f4-108">See <xref:Microsoft.VisualBasic.FileIO.FileSystem> for more information.</span></span> <span data-ttu-id="293f4-109">В конце пошагового руководства приводится эквивалентный пример, в котором используются классы пространства имен <xref:System.IO>.</span><span class="sxs-lookup"><span data-stu-id="293f4-109">At the end of the walkthrough, an equivalent example is provided that uses classes from the <xref:System.IO> namespace.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-the-project"></a><span data-ttu-id="293f4-110">Создание проекта</span><span class="sxs-lookup"><span data-stu-id="293f4-110">To create the project</span></span>  
  
1. <span data-ttu-id="293f4-111">В меню **Файл** выберите пункт **Создать проект**.</span><span class="sxs-lookup"><span data-stu-id="293f4-111">On the **File** menu, click **New Project**.</span></span>  
  
     <span data-ttu-id="293f4-112">Откроется диалоговое окно **Новый проект** .</span><span class="sxs-lookup"><span data-stu-id="293f4-112">The **New Project** dialog box appears.</span></span>  
  
2. <span data-ttu-id="293f4-113">В области **Установленные шаблоны** разверните узел **Visual Basic** и выберите элемент **Windows**.</span><span class="sxs-lookup"><span data-stu-id="293f4-113">In the **Installed Templates** pane, expand **Visual Basic**, and then click **Windows**.</span></span> <span data-ttu-id="293f4-114">В середине области **Шаблоны** щелкните **Приложение Windows Forms**.</span><span class="sxs-lookup"><span data-stu-id="293f4-114">In the **Templates** pane in the middle, click **Windows Forms Application**.</span></span>  
  
3. <span data-ttu-id="293f4-115">В поле **Имя** введите `FileExplorer`, чтобы задать имя проекта, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="293f4-115">In the **Name** box, type `FileExplorer` to set the project name, and then click **OK**.</span></span>  
  
     <span data-ttu-id="293f4-116">Visual Studio добавит проект в **обозреватель решений**, после чего откроется конструктор Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="293f4-116">Visual Studio adds the project to **Solution Explorer**, and the Windows Forms Designer opens.</span></span>  
  
4. <span data-ttu-id="293f4-117">Добавьте в форму элементы управления из приведенной ниже таблицы и установите для их свойств соответствующие значения.</span><span class="sxs-lookup"><span data-stu-id="293f4-117">Add the controls in the following table to the form, and set the corresponding values for their properties.</span></span>  
  
    |<span data-ttu-id="293f4-118">Элемент управления</span><span class="sxs-lookup"><span data-stu-id="293f4-118">Control</span></span>|<span data-ttu-id="293f4-119">Свойство</span><span class="sxs-lookup"><span data-stu-id="293f4-119">Property</span></span>|<span data-ttu-id="293f4-120">Значение</span><span class="sxs-lookup"><span data-stu-id="293f4-120">Value</span></span>|  
    |-------------|--------------|-----------|  
    |<span data-ttu-id="293f4-121">**ListBox**</span><span class="sxs-lookup"><span data-stu-id="293f4-121">**ListBox**</span></span>|<span data-ttu-id="293f4-122">**Название**</span><span class="sxs-lookup"><span data-stu-id="293f4-122">**Name**</span></span>|`filesListBox`|  
    |<span data-ttu-id="293f4-123">**Кнопка**</span><span class="sxs-lookup"><span data-stu-id="293f4-123">**Button**</span></span>|<span data-ttu-id="293f4-124">**Название**</span><span class="sxs-lookup"><span data-stu-id="293f4-124">**Name**</span></span><br /><br /> <span data-ttu-id="293f4-125">**Текст**</span><span class="sxs-lookup"><span data-stu-id="293f4-125">**Text**</span></span>|`browseButton`<br /><br /> <span data-ttu-id="293f4-126">**Обзор**</span><span class="sxs-lookup"><span data-stu-id="293f4-126">**Browse**</span></span>|  
    |<span data-ttu-id="293f4-127">**Кнопка**</span><span class="sxs-lookup"><span data-stu-id="293f4-127">**Button**</span></span>|<span data-ttu-id="293f4-128">**Название**</span><span class="sxs-lookup"><span data-stu-id="293f4-128">**Name**</span></span><br /><br /> <span data-ttu-id="293f4-129">**Текст**</span><span class="sxs-lookup"><span data-stu-id="293f4-129">**Text**</span></span>|`examineButton`<br /><br /> <span data-ttu-id="293f4-130">**Исследовать**</span><span class="sxs-lookup"><span data-stu-id="293f4-130">**Examine**</span></span>|  
    |<span data-ttu-id="293f4-131">**CheckBox**</span><span class="sxs-lookup"><span data-stu-id="293f4-131">**CheckBox**</span></span>|<span data-ttu-id="293f4-132">**Название**</span><span class="sxs-lookup"><span data-stu-id="293f4-132">**Name**</span></span><br /><br /> <span data-ttu-id="293f4-133">**Текст**</span><span class="sxs-lookup"><span data-stu-id="293f4-133">**Text**</span></span>|`saveCheckBox`<br /><br /> <span data-ttu-id="293f4-134">**Сохранить результаты**</span><span class="sxs-lookup"><span data-stu-id="293f4-134">**Save Results**</span></span>|  
    |<span data-ttu-id="293f4-135">**FolderBrowserDialog**</span><span class="sxs-lookup"><span data-stu-id="293f4-135">**FolderBrowserDialog**</span></span>|<span data-ttu-id="293f4-136">**Название**</span><span class="sxs-lookup"><span data-stu-id="293f4-136">**Name**</span></span>|`FolderBrowserDialog1`|  
  
### <a name="to-select-a-folder-and-list-files-in-a-folder"></a><span data-ttu-id="293f4-137">Выбор папки и перечисление файлов в ней</span><span class="sxs-lookup"><span data-stu-id="293f4-137">To select a folder, and list files in a folder</span></span>  
  
1. <span data-ttu-id="293f4-138">Создайте обработчик событий нажатия `Click` для кнопки `browseButton`, дважды щелкнув этот элемент управления в форме.</span><span class="sxs-lookup"><span data-stu-id="293f4-138">Create a `Click` event handler for `browseButton` by double-clicking the control on the form.</span></span> <span data-ttu-id="293f4-139">Откроется редактор кода.</span><span class="sxs-lookup"><span data-stu-id="293f4-139">The Code Editor opens.</span></span>  
  
2. <span data-ttu-id="293f4-140">Добавьте следующий код в обработчик событий `Click`.</span><span class="sxs-lookup"><span data-stu-id="293f4-140">Add the following code to the `Click` event handler.</span></span>  
  
     [!code-vb[VbVbcnMyFileSystem#103](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/class2.vb#103)]  
  
     <span data-ttu-id="293f4-141">Вызов `FolderBrowserDialog1.ShowDialog` открывает диалоговое окно **Выбор папки**.</span><span class="sxs-lookup"><span data-stu-id="293f4-141">The `FolderBrowserDialog1.ShowDialog` call opens the **Browse For Folder** dialog box.</span></span> <span data-ttu-id="293f4-142">Когда пользователь нажимает **OK**, свойство <xref:System.Windows.Forms.FolderBrowserDialog.SelectedPath%2A> передается как аргумент методу `ListFiles`, который добавляется в следующем шаге.</span><span class="sxs-lookup"><span data-stu-id="293f4-142">After the user clicks **OK**, the <xref:System.Windows.Forms.FolderBrowserDialog.SelectedPath%2A> property is sent as an argument to the `ListFiles` method, which is added in the next step.</span></span>  
  
3. <span data-ttu-id="293f4-143">Добавьте приведенный ниже метод `ListFiles`.</span><span class="sxs-lookup"><span data-stu-id="293f4-143">Add the following `ListFiles` method.</span></span>  
  
     [!code-vb[VbVbcnMyFileSystem#104](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/class2.vb#104)]  
  
     <span data-ttu-id="293f4-144">Этот код сперва очищает элемент **ListBox**.</span><span class="sxs-lookup"><span data-stu-id="293f4-144">This code first clears the **ListBox**.</span></span>  
  
     <span data-ttu-id="293f4-145">Затем метод <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFiles%2A> возвращает коллекцию строк — по одной для каждого файла в каталоге.</span><span class="sxs-lookup"><span data-stu-id="293f4-145">The <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFiles%2A> method then retrieves a collection of strings, one for each file in the directory.</span></span> <span data-ttu-id="293f4-146">Метод `GetFiles` принимает аргумент шаблона поиска, чтобы извлечь файлы, соответствующие определенному шаблону.</span><span class="sxs-lookup"><span data-stu-id="293f4-146">The `GetFiles` method accepts a search pattern argument to retrieve files that match a particular pattern.</span></span> <span data-ttu-id="293f4-147">В этом примере возвращаются только файлы с расширением TXT.</span><span class="sxs-lookup"><span data-stu-id="293f4-147">In this example, only files that have the extension .txt are returned.</span></span>  
  
     <span data-ttu-id="293f4-148">Строки, возвращаемые методом `GetFiles`, затем добавляются в элемент управления **ListBox**.</span><span class="sxs-lookup"><span data-stu-id="293f4-148">The strings that are returned by the `GetFiles` method are then added to the **ListBox**.</span></span>  
  
4. <span data-ttu-id="293f4-149">Запустите приложение.</span><span class="sxs-lookup"><span data-stu-id="293f4-149">Run the application.</span></span> <span data-ttu-id="293f4-150">Нажмите кнопку **Обзор**.</span><span class="sxs-lookup"><span data-stu-id="293f4-150">Click the **Browse** button.</span></span> <span data-ttu-id="293f4-151">В диалоговом окне **Выбор папки** перейдите в папку, содержащую TXT-файлы, выберите папку и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="293f4-151">In the **Browse For Folder** dialog box, browse to a folder that contains .txt files, and then select the folder and click **OK**.</span></span>  
  
     <span data-ttu-id="293f4-152">Элемент `ListBox` содержит список TXT-файлов в выбранной папке.</span><span class="sxs-lookup"><span data-stu-id="293f4-152">The `ListBox` contains a list of .txt files in the selected folder.</span></span>  
  
5. <span data-ttu-id="293f4-153">Остановите работу приложения.</span><span class="sxs-lookup"><span data-stu-id="293f4-153">Stop running the application.</span></span>  
  
### <a name="to-obtain-attributes-of-a-file-and-content-from-a-text-file"></a><span data-ttu-id="293f4-154">Получение атрибутов файла и содержимого текстового файла</span><span class="sxs-lookup"><span data-stu-id="293f4-154">To obtain attributes of a file, and content from a text file</span></span>  
  
1. <span data-ttu-id="293f4-155">Создайте обработчик событий нажатия `Click` для кнопки `examineButton`, дважды щелкнув этот элемент управления в форме.</span><span class="sxs-lookup"><span data-stu-id="293f4-155">Create a `Click` event handler for `examineButton` by double-clicking the control on the form.</span></span>  
  
2. <span data-ttu-id="293f4-156">Добавьте следующий код в обработчик событий `Click`.</span><span class="sxs-lookup"><span data-stu-id="293f4-156">Add the following code to the `Click` event handler.</span></span>  
  
     [!code-vb[VbVbcnMyFileSystem#105](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/class2.vb#105)]  
  
     <span data-ttu-id="293f4-157">Этот код проверяет, выбран ли элемент в элементе `ListBox`.</span><span class="sxs-lookup"><span data-stu-id="293f4-157">The code verifies that an item is selected in the `ListBox`.</span></span> <span data-ttu-id="293f4-158">Затем он получает запись пути к файлу из элемента `ListBox`.</span><span class="sxs-lookup"><span data-stu-id="293f4-158">It then obtains the file path entry from the `ListBox`.</span></span> <span data-ttu-id="293f4-159">Метод <xref:Microsoft.VisualBasic.FileIO.FileSystem.FileExists%2A> позволяет проверить, существует ли файл.</span><span class="sxs-lookup"><span data-stu-id="293f4-159">The <xref:Microsoft.VisualBasic.FileIO.FileSystem.FileExists%2A> method is used to check whether the file still exists.</span></span>  
  
     <span data-ttu-id="293f4-160">Путь к файлу передается как аргумент методу `GetTextForOutput`, который добавляется в следующем шаге.</span><span class="sxs-lookup"><span data-stu-id="293f4-160">The file path is sent as an argument to the `GetTextForOutput` method, which is added in the next step.</span></span> <span data-ttu-id="293f4-161">Этот метод возвращает строку, содержащую информацию о файле.</span><span class="sxs-lookup"><span data-stu-id="293f4-161">This method returns a string that contains file information.</span></span> <span data-ttu-id="293f4-162">Информация о файле отображается в элементе **MessageBox**.</span><span class="sxs-lookup"><span data-stu-id="293f4-162">The file information appears in a **MessageBox**.</span></span>  
  
3. <span data-ttu-id="293f4-163">Добавьте приведенный ниже метод `GetTextForOutput`.</span><span class="sxs-lookup"><span data-stu-id="293f4-163">Add the following `GetTextForOutput` method.</span></span>  
  
     [!code-vb[VbVbcnMyFileSystem#107](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/class2.vb#107)]  
  
     <span data-ttu-id="293f4-164">Метод <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFileInfo%2A> используется в коде для получения параметров файла.</span><span class="sxs-lookup"><span data-stu-id="293f4-164">The code uses the <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFileInfo%2A> method to obtain file parameters.</span></span> <span data-ttu-id="293f4-165">Параметры файла добавляются в <xref:System.Text.StringBuilder>.</span><span class="sxs-lookup"><span data-stu-id="293f4-165">The file parameters are added to a <xref:System.Text.StringBuilder>.</span></span>  
  
     <span data-ttu-id="293f4-166">Метод <xref:Microsoft.VisualBasic.FileIO.FileSystem.OpenTextFileReader%2A> считывает содержимое файла в <xref:System.IO.StreamReader>.</span><span class="sxs-lookup"><span data-stu-id="293f4-166">The <xref:Microsoft.VisualBasic.FileIO.FileSystem.OpenTextFileReader%2A> method reads the file contents into a <xref:System.IO.StreamReader>.</span></span> <span data-ttu-id="293f4-167">Первая строка содержимого файла извлекается из `StreamReader` и добавляется в `StringBuilder`.</span><span class="sxs-lookup"><span data-stu-id="293f4-167">The first line of the contents is obtained from the `StreamReader` and is added to the `StringBuilder`.</span></span>  
  
4. <span data-ttu-id="293f4-168">Запустите приложение.</span><span class="sxs-lookup"><span data-stu-id="293f4-168">Run the application.</span></span> <span data-ttu-id="293f4-169">Нажмите кнопку **Обзор** и перейдите в папку с TXT-файлами.</span><span class="sxs-lookup"><span data-stu-id="293f4-169">Click **Browse**, and browse to a folder that contains .txt files.</span></span> <span data-ttu-id="293f4-170">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="293f4-170">Click **OK**.</span></span>  
  
     <span data-ttu-id="293f4-171">Выберите файл в элементе `ListBox` и щелкните **Исследовать**.</span><span class="sxs-lookup"><span data-stu-id="293f4-171">Select a file in the `ListBox`, and then click **Examine**.</span></span> <span data-ttu-id="293f4-172">В окне `MessageBox` будет выведена информация о файле.</span><span class="sxs-lookup"><span data-stu-id="293f4-172">A `MessageBox` shows the file information.</span></span>  
  
5. <span data-ttu-id="293f4-173">Остановите работу приложения.</span><span class="sxs-lookup"><span data-stu-id="293f4-173">Stop running the application.</span></span>  
  
### <a name="to-add-a-log-entry"></a><span data-ttu-id="293f4-174">Добавление записи в журнал</span><span class="sxs-lookup"><span data-stu-id="293f4-174">To add a log entry</span></span>  
  
1. <span data-ttu-id="293f4-175">В конец обработчика событий `examineButton_Click` добавьте приведенный ниже код.</span><span class="sxs-lookup"><span data-stu-id="293f4-175">Add the following code to the end of the `examineButton_Click` event handler.</span></span>  
  
     [!code-vb[VbVbcnMyFileSystem#106](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/class2.vb#106)]  
  
     <span data-ttu-id="293f4-176">Код задает путь к файлу журнала, чтобы файл журнала помещался в тот же каталог, где находится выбранный файл.</span><span class="sxs-lookup"><span data-stu-id="293f4-176">The code sets the log file path to put the log file in the same directory as that of the selected file.</span></span> <span data-ttu-id="293f4-177">Запись журнала должна содержать текущие дату и время, а далее информацию о файле.</span><span class="sxs-lookup"><span data-stu-id="293f4-177">The text of the log entry is set to the current date and time followed by the file information.</span></span>  
  
     <span data-ttu-id="293f4-178">Метод <xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllText%2A>, которому передается аргумент `append` со значением `True`, используется для создания записи в журнале.</span><span class="sxs-lookup"><span data-stu-id="293f4-178">The <xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllText%2A> method, with the `append` argument set to `True`, is used to create the log entry.</span></span>  
  
2. <span data-ttu-id="293f4-179">Запустите приложение.</span><span class="sxs-lookup"><span data-stu-id="293f4-179">Run the application.</span></span> <span data-ttu-id="293f4-180">Перейдите к текстовому файлу, выберите его в элементе `ListBox`, установите флажок **Сохранить результаты** и щелкните **Исследовать**.</span><span class="sxs-lookup"><span data-stu-id="293f4-180">Browse to a text file, select it in the `ListBox`, select the **Save Results** check box, and then click **Examine**.</span></span> <span data-ttu-id="293f4-181">Проверьте, добавлена ли запись в файл `log.txt`.</span><span class="sxs-lookup"><span data-stu-id="293f4-181">Verify that the log entry is written to the `log.txt` file.</span></span>  
  
3. <span data-ttu-id="293f4-182">Остановите работу приложения.</span><span class="sxs-lookup"><span data-stu-id="293f4-182">Stop running the application.</span></span>  
  
### <a name="to-use-the-current-directory"></a><span data-ttu-id="293f4-183">Использование текущего каталога</span><span class="sxs-lookup"><span data-stu-id="293f4-183">To use the current directory</span></span>  
  
1. <span data-ttu-id="293f4-184">Создайте обработчик событий для события `Form1_Load`, дважды щелкнув форму.</span><span class="sxs-lookup"><span data-stu-id="293f4-184">Create an event handler for `Form1_Load` by double-clicking the form.</span></span>  
  
2. <span data-ttu-id="293f4-185">Добавьте в обработчик событий приведенный ниже код.</span><span class="sxs-lookup"><span data-stu-id="293f4-185">Add the following code to the event handler.</span></span>  
  
     [!code-vb[VbVbcnMyFileSystem#102](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/class2.vb#102)]  
  
     <span data-ttu-id="293f4-186">Этот код задает текущий каталог в качестве каталога по умолчанию для обозревателя папок.</span><span class="sxs-lookup"><span data-stu-id="293f4-186">This code sets the default directory of the folder browser to the current directory.</span></span>  
  
3. <span data-ttu-id="293f4-187">Запустите приложение.</span><span class="sxs-lookup"><span data-stu-id="293f4-187">Run the application.</span></span> <span data-ttu-id="293f4-188">При первом нажатии кнопки **Обзор** открывается диалоговое окно **Выбор папки** с текущим каталогом.</span><span class="sxs-lookup"><span data-stu-id="293f4-188">When you click **Browse** the first time, the **Browse For Folder** dialog box opens to the current directory.</span></span>  
  
4. <span data-ttu-id="293f4-189">Остановите работу приложения.</span><span class="sxs-lookup"><span data-stu-id="293f4-189">Stop running the application.</span></span>  
  
### <a name="to-selectively-enable-controls"></a><span data-ttu-id="293f4-190">Выборочное включение элементов управления</span><span class="sxs-lookup"><span data-stu-id="293f4-190">To selectively enable controls</span></span>  
  
1. <span data-ttu-id="293f4-191">Добавьте приведенный ниже метод `SetEnabled`.</span><span class="sxs-lookup"><span data-stu-id="293f4-191">Add the following `SetEnabled` method.</span></span>  
  
     [!code-vb[VbVbcnMyFileSystem#108](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/class2.vb#108)]  
  
     <span data-ttu-id="293f4-192">Метод `SetEnabled` включает и отключает элементы управления в зависимости от того, выбран ли элемент в элементе `ListBox`.</span><span class="sxs-lookup"><span data-stu-id="293f4-192">The `SetEnabled` method enables or disables controls depending on whether an item is selected in the `ListBox`.</span></span>  
  
2. <span data-ttu-id="293f4-193">Создайте обработчик событий `SelectedIndexChanged` для элемента `filesListBox`, дважды щелкнув элемент управления `ListBox` в форме.</span><span class="sxs-lookup"><span data-stu-id="293f4-193">Create a `SelectedIndexChanged` event handler for `filesListBox` by double-clicking the `ListBox` control on the form.</span></span>  
  
3. <span data-ttu-id="293f4-194">Добавьте вызов метода `SetEnabled` в новый обработчик событий `filesListBox_SelectedIndexChanged`.</span><span class="sxs-lookup"><span data-stu-id="293f4-194">Add a call to `SetEnabled` in the new `filesListBox_SelectedIndexChanged` event handler.</span></span>  
  
4. <span data-ttu-id="293f4-195">Добавьте вызов метода `SetEnabled` в конце обработчика событий `browseButton_Click`.</span><span class="sxs-lookup"><span data-stu-id="293f4-195">Add a call to `SetEnabled` at the end of the `browseButton_Click` event handler.</span></span>  
  
5. <span data-ttu-id="293f4-196">Добавьте вызов метода `SetEnabled` в конце обработчика событий `Form1_Load`.</span><span class="sxs-lookup"><span data-stu-id="293f4-196">Add a call to `SetEnabled` at the end of the `Form1_Load` event handler.</span></span>  
  
6. <span data-ttu-id="293f4-197">Запустите приложение.</span><span class="sxs-lookup"><span data-stu-id="293f4-197">Run the application.</span></span> <span data-ttu-id="293f4-198">Флажок **Сохранить результаты** и кнопка **Исследовать** отключены, если элемент не выбран в элементе `ListBox`.</span><span class="sxs-lookup"><span data-stu-id="293f4-198">The **Save Results** check box and the **Examine** button are disabled if an item is not selected in the `ListBox`.</span></span>  
  
## <a name="full-example-using-mycomputerfilesystem"></a><span data-ttu-id="293f4-199">Полный пример с использованием My.Computer.FileSystem</span><span class="sxs-lookup"><span data-stu-id="293f4-199">Full example using My.Computer.FileSystem</span></span>  

 <span data-ttu-id="293f4-200">Ниже приведен полный пример.</span><span class="sxs-lookup"><span data-stu-id="293f4-200">Following is the complete example.</span></span>  
  
 [!code-vb[VbVbcnMyFileSystem#101](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/class2.vb#101)]  
  
## <a name="full-example-using-systemio"></a><span data-ttu-id="293f4-201">Полный пример с использованием System.IO</span><span class="sxs-lookup"><span data-stu-id="293f4-201">Full example using System.IO</span></span>  

 <span data-ttu-id="293f4-202">Следующий пример выполняет те же действия, используя классы из пространства имен <xref:System.IO> вместо объектов `My.Computer.FileSystem`.</span><span class="sxs-lookup"><span data-stu-id="293f4-202">The following equivalent example uses classes from the <xref:System.IO> namespace instead of using `My.Computer.FileSystem` objects.</span></span>  
  
 [!code-vb[VbVbcnMyFileSystem#111](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/class3.vb#111)]  
  
## <a name="see-also"></a><span data-ttu-id="293f4-203">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="293f4-203">See also</span></span>

- <xref:System.IO>
- <xref:Microsoft.VisualBasic.FileIO.FileSystem>
- <xref:Microsoft.VisualBasic.FileIO.FileSystem.CurrentDirectory%2A>
- [<span data-ttu-id="293f4-204">Пошаговое руководство. Управление файлами с помощью методов .NET Framework</span><span class="sxs-lookup"><span data-stu-id="293f4-204">Walkthrough: Manipulating Files by Using .NET Framework Methods</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/walkthrough-manipulating-files-by-using-net-framework-methods.md)

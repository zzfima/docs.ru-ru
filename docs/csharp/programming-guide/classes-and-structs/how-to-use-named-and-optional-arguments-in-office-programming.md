---
title: Практическое руководство. Использование именованных и необязательных аргументов в программировании приложений Office (Руководство по программированию на C#)
ms.date: 07/20/2015
helpviewer_keywords:
- named and optional arguments [C#], Office programming
- optional arguments [C#], Office programming
- named arguments [C#], Office programming
ms.assetid: 65b8a222-bcd8-454c-845f-84adff5a356f
ms.openlocfilehash: 3fce8a30e9ed663f06fa04c462fc1e1fd249d27a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-use-named-and-optional-arguments-in-office-programming-c-programming-guide"></a><span data-ttu-id="0113b-102">Практическое руководство. Использование именованных и необязательных аргументов в программировании приложений Office (Руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="0113b-102">How to: Use Named and Optional Arguments in Office Programming (C# Programming Guide)</span></span>
<span data-ttu-id="0113b-103">Появившиеся в [!INCLUDE[csharp_dev10_long](~/includes/csharp-dev10-long-md.md)] именованные и необязательные аргументы повышают удобство, гибкость и удобочитаемость программирования на C#.</span><span class="sxs-lookup"><span data-stu-id="0113b-103">Named arguments and optional arguments, introduced in [!INCLUDE[csharp_dev10_long](~/includes/csharp-dev10-long-md.md)], enhance convenience, flexibility, and readability in C# programming.</span></span> <span data-ttu-id="0113b-104">Кроме того, эти функции значительно упрощают доступ к COM-интерфейсам, таким как интерфейсы API автоматизации Microsoft Office.</span><span class="sxs-lookup"><span data-stu-id="0113b-104">In addition, these features greatly facilitate access to COM interfaces such as the Microsoft Office automation APIs.</span></span>  
  
 <span data-ttu-id="0113b-105">В следующем примере у метода [ConvertToTable](https://msdn.microsoft.com/library/bb216993.aspx) имеется шестнадцать параметров, представляющих характеристики таблицы, например число столбцов и строк, форматирование, границы и цвета.</span><span class="sxs-lookup"><span data-stu-id="0113b-105">In the following example, method [ConvertToTable](https://msdn.microsoft.com/library/bb216993.aspx) has sixteen parameters that represent characteristics of a table, such as number of columns and rows, formatting, borders, fonts, and colors.</span></span> <span data-ttu-id="0113b-106">Все шестнадцать параметров являются необязательными, поскольку в большинстве случаев не требуется задавать конкретные значения для всех этих параметров.</span><span class="sxs-lookup"><span data-stu-id="0113b-106">All sixteen parameters are optional, because most of the time you do not want to specify particular values for all of them.</span></span> <span data-ttu-id="0113b-107">Однако без именованных и необязательных аргументов приходилось указывать значение или значение-заполнитель для каждого из параметров.</span><span class="sxs-lookup"><span data-stu-id="0113b-107">However, without named and optional arguments, a value or a placeholder value has to be provided for each parameter.</span></span> <span data-ttu-id="0113b-108">Именованные и необязательные параметры позволяют задавать значения только для тех параметров, которые требуются в конкретном проекте.</span><span class="sxs-lookup"><span data-stu-id="0113b-108">With named and optional arguments, you specify values only for the parameters that are required for your project.</span></span>  
  
 <span data-ttu-id="0113b-109">Для выполнения этих процедур на компьютере должно быть установлено приложение Microsoft Office Word.</span><span class="sxs-lookup"><span data-stu-id="0113b-109">You must have Microsoft Office Word installed on your computer to complete these procedures.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-new-console-application"></a><span data-ttu-id="0113b-110">Создание нового проекта консольного приложения</span><span class="sxs-lookup"><span data-stu-id="0113b-110">To create a new console application</span></span>  
  
1.  <span data-ttu-id="0113b-111">Запустите Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="0113b-111">Start Visual Studio.</span></span>  
  
2.  <span data-ttu-id="0113b-112">В меню **Файл** выберите пункт **Создать**, а затем команду **Проект**.</span><span class="sxs-lookup"><span data-stu-id="0113b-112">On the **File** menu, point to **New**, and then click **Project**.</span></span>  
  
3.  <span data-ttu-id="0113b-113">В области **Категории шаблонов** разверните узел **Visual C#** и выберите **Windows**.</span><span class="sxs-lookup"><span data-stu-id="0113b-113">In the **Templates Categories** pane, expand **Visual C#**, and then click **Windows**.</span></span>  
  
4.  <span data-ttu-id="0113b-114">В верхней части области **Шаблоны** в поле **Требуемая версия .NET Framework** должно отображаться значение **.NET Framework 4**.</span><span class="sxs-lookup"><span data-stu-id="0113b-114">Look in the top of the **Templates** pane to make sure that **.NET Framework 4** appears in the **Target Framework** box.</span></span>  
  
5.  <span data-ttu-id="0113b-115">В области **Шаблоны** щелкните **Консольное приложение**.</span><span class="sxs-lookup"><span data-stu-id="0113b-115">In the **Templates** pane, click **Console Application**.</span></span>  
  
6.  <span data-ttu-id="0113b-116">Введите имя проекта в поле **Имя**.</span><span class="sxs-lookup"><span data-stu-id="0113b-116">Type a name for your project in the **Name** field.</span></span>  
  
7.  <span data-ttu-id="0113b-117">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="0113b-117">Click **OK**.</span></span>  
  
     <span data-ttu-id="0113b-118">В **обозревателе решений** появится новый проект.</span><span class="sxs-lookup"><span data-stu-id="0113b-118">The new project appears in **Solution Explorer**.</span></span>  
  
### <a name="to-add-a-reference"></a><span data-ttu-id="0113b-119">Добавление ссылки</span><span class="sxs-lookup"><span data-stu-id="0113b-119">To add a reference</span></span>  
  
1.  <span data-ttu-id="0113b-120">В **обозревателе решений** щелкните имя проекта правой кнопкой мыши и выберите пункт **Добавить ссылку**.</span><span class="sxs-lookup"><span data-stu-id="0113b-120">In **Solution Explorer**, right-click your project's name and then click **Add Reference**.</span></span> <span data-ttu-id="0113b-121">Откроется диалоговое окно **Добавление ссылки**.</span><span class="sxs-lookup"><span data-stu-id="0113b-121">The **Add Reference** dialog box appears.</span></span>  
  
2.  <span data-ttu-id="0113b-122">На странице **.NET** выберите **Microsoft.Office.Interop.Word** в списке **Имя компонента**.</span><span class="sxs-lookup"><span data-stu-id="0113b-122">On the **.NET** page, select **Microsoft.Office.Interop.Word** in the **Component Name** list.</span></span>  
  
3.  <span data-ttu-id="0113b-123">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="0113b-123">Click **OK**.</span></span>  
  
### <a name="to-add-necessary-using-directives"></a><span data-ttu-id="0113b-124">Добавление необходимых директив using</span><span class="sxs-lookup"><span data-stu-id="0113b-124">To add necessary using directives</span></span>  
  
1.  <span data-ttu-id="0113b-125">В **обозревателе решений** щелкните правой кнопкой мыши файл **Program.cs** и выберите пункт **Просмотреть код**.</span><span class="sxs-lookup"><span data-stu-id="0113b-125">In **Solution Explorer**, right-click the **Program.cs** file and then click **View Code**.</span></span>  
  
2.  <span data-ttu-id="0113b-126">В начало файла кода добавьте следующие директивы `using`.</span><span class="sxs-lookup"><span data-stu-id="0113b-126">Add the following `using` directives to the top of the code file.</span></span>  
  
     [!code-csharp[csProgGuideNamedAndOptional#4](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-use-named-and-optional-arguments-in-office-programming_1.cs)]  
  
### <a name="to-display-text-in-a-word-document"></a><span data-ttu-id="0113b-127">Отображение текста в документ Word</span><span class="sxs-lookup"><span data-stu-id="0113b-127">To display text in a Word document</span></span>  
  
1.  <span data-ttu-id="0113b-128">В класс `Program` в файле Program.cs добавьте следующий метод для создания приложения Word и документа Word.</span><span class="sxs-lookup"><span data-stu-id="0113b-128">In the `Program` class in Program.cs, add the following method to create a Word application and a Word document.</span></span> <span data-ttu-id="0113b-129">Метод [Add](https://msdn.microsoft.com/library/microsoft.office.interop.word.documents.add.aspx) имеет четыре необязательных параметра.</span><span class="sxs-lookup"><span data-stu-id="0113b-129">The [Add](https://msdn.microsoft.com/library/microsoft.office.interop.word.documents.add.aspx) method has four optional parameters.</span></span> <span data-ttu-id="0113b-130">В этом примере используются значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="0113b-130">This example uses their default values.</span></span> <span data-ttu-id="0113b-131">Поэтому в операторе вызова указывать аргументы не требуется.</span><span class="sxs-lookup"><span data-stu-id="0113b-131">Therefore, no arguments are necessary in the calling statement.</span></span>  
  
     [!code-csharp[csProgGuideNamedAndOptional#6](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-use-named-and-optional-arguments-in-office-programming_2.cs)]  
  
2.  <span data-ttu-id="0113b-132">Добавьте в конец метода следующий код, чтобы определить место отображения текста в документе и текст для отображения.</span><span class="sxs-lookup"><span data-stu-id="0113b-132">Add the following code at the end of the method to define where to display text in the document, and what text to display.</span></span>  
  
     [!code-csharp[csProgGuideNamedAndOptional#7](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-use-named-and-optional-arguments-in-office-programming_3.cs)]  
  
### <a name="to-run-the-application"></a><span data-ttu-id="0113b-133">Запуск приложения</span><span class="sxs-lookup"><span data-stu-id="0113b-133">To run the application</span></span>  
  
1.  <span data-ttu-id="0113b-134">Добавьте в метод Main следующую инструкцию.</span><span class="sxs-lookup"><span data-stu-id="0113b-134">Add the following statement to Main.</span></span>  
  
     [!code-csharp[csProgGuideNamedAndOptional#8](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-use-named-and-optional-arguments-in-office-programming_4.cs)]  
  
2.  <span data-ttu-id="0113b-135">Нажмите клавиши CTRL+F5, чтобы запустить проект.</span><span class="sxs-lookup"><span data-stu-id="0113b-135">Press CTRL+F5 to run the project.</span></span> <span data-ttu-id="0113b-136">Появится документ Word, содержащий указанный текст.</span><span class="sxs-lookup"><span data-stu-id="0113b-136">A Word document appears that contains the specified text.</span></span>  
  
### <a name="to-change-the-text-to-a-table"></a><span data-ttu-id="0113b-137">Замена текста на таблицу</span><span class="sxs-lookup"><span data-stu-id="0113b-137">To change the text to a table</span></span>  
  
1.  <span data-ttu-id="0113b-138">Метод `ConvertToTable` служит для преобразования текста в таблицу.</span><span class="sxs-lookup"><span data-stu-id="0113b-138">Use the `ConvertToTable` method to enclose the text in a table.</span></span> <span data-ttu-id="0113b-139">У метода имеется шестнадцать необязательных параметров.</span><span class="sxs-lookup"><span data-stu-id="0113b-139">The method has sixteen optional parameters.</span></span> <span data-ttu-id="0113b-140">IntelliSense заключает необязательные параметры в квадратные скобки, как показано на следующем рисунке.</span><span class="sxs-lookup"><span data-stu-id="0113b-140">IntelliSense encloses optional parameters in brackets, as shown in the following illustration.</span></span>  
  
     <span data-ttu-id="0113b-141">![Список параметров для метода ConvertToTable](../../../csharp/programming-guide/classes-and-structs/media/convert_tableparameters.png "Convert_TableParameters")</span><span class="sxs-lookup"><span data-stu-id="0113b-141">![List of parameters for ConvertToTable method.](../../../csharp/programming-guide/classes-and-structs/media/convert_tableparameters.png "Convert_TableParameters")</span></span>  
<span data-ttu-id="0113b-142">Параметры ConvertToTable</span><span class="sxs-lookup"><span data-stu-id="0113b-142">ConvertToTable parameters</span></span>  
  
     <span data-ttu-id="0113b-143">Именованные и необязательные аргументы позволяют задавать значения только для тех параметров, которые требуется изменить.</span><span class="sxs-lookup"><span data-stu-id="0113b-143">Named and optional arguments enable you to specify values for only the parameters that you want to change.</span></span> <span data-ttu-id="0113b-144">Добавьте в конец метода `DisplayInWord` следующий код, чтобы создать простую таблицу.</span><span class="sxs-lookup"><span data-stu-id="0113b-144">Add the following code to the end of method `DisplayInWord` to create a simple table.</span></span> <span data-ttu-id="0113b-145">Аргумент указывает, что запятые в текстовой строке в `range` разделяют ячейки таблицы.</span><span class="sxs-lookup"><span data-stu-id="0113b-145">The argument specifies that the commas in the text string in `range` separate the cells of the table.</span></span>  
  
     [!code-csharp[csProgGuideNamedAndOptional#9](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-use-named-and-optional-arguments-in-office-programming_5.cs)]  
  
     <span data-ttu-id="0113b-146">В более ранних версиях C# для вызова `ConvertToTable` каждому параметру требовался ссылочный аргумент, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="0113b-146">In earlier versions of C#, the call to `ConvertToTable` requires a reference argument for each parameter, as shown in the following code.</span></span>  
  
     [!code-csharp[csProgGuideNamedAndOptional#14](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-use-named-and-optional-arguments-in-office-programming_6.cs)]  
  
2.  <span data-ttu-id="0113b-147">Нажмите клавиши CTRL+F5, чтобы запустить проект.</span><span class="sxs-lookup"><span data-stu-id="0113b-147">Press CTRL+F5 to run the project.</span></span>  
  
### <a name="to-experiment-with-other-parameters"></a><span data-ttu-id="0113b-148">Экспериментирование с другими параметрами</span><span class="sxs-lookup"><span data-stu-id="0113b-148">To experiment with other parameters</span></span>  
  
1.  <span data-ttu-id="0113b-149">Для изменения таблицы, чтобы она содержала один столбец и три строки, замените последнюю строку метода `DisplayInWord` следующей инструкцией и нажмите сочетание клавиш CTRL+F5.</span><span class="sxs-lookup"><span data-stu-id="0113b-149">To change the table so that it has one column and three rows, replace the last line in `DisplayInWord` with the following statement and then type CTRL+F5.</span></span>  
  
     [!code-csharp[csProgGuideNamedAndOptional#10](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-use-named-and-optional-arguments-in-office-programming_7.cs)]  
  
2.  <span data-ttu-id="0113b-150">Чтобы использовать заранее определенный формат таблицы, замените последнюю строку метода `DisplayInWord` следующей инструкцией и нажмите сочетание клавиш CTRL+F5.</span><span class="sxs-lookup"><span data-stu-id="0113b-150">To specify a predefined format for the table, replace the last line in `DisplayInWord` with the following statement and then type CTRL+F5.</span></span> <span data-ttu-id="0113b-151">В качестве формата можно использовать любую из констант [WdTableFormat](https://msdn.microsoft.com/library/microsoft.office.interop.word.wdtableformat.aspx).</span><span class="sxs-lookup"><span data-stu-id="0113b-151">The format can be any of the [WdTableFormat](https://msdn.microsoft.com/library/microsoft.office.interop.word.wdtableformat.aspx) constants.</span></span>  
  
     [!code-csharp[csProgGuideNamedAndOptional#11](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-use-named-and-optional-arguments-in-office-programming_8.cs)]  
  
## <a name="example"></a><span data-ttu-id="0113b-152">Пример</span><span class="sxs-lookup"><span data-stu-id="0113b-152">Example</span></span>  
 <span data-ttu-id="0113b-153">Следующий код включает полный пример.</span><span class="sxs-lookup"><span data-stu-id="0113b-153">The following code includes the full example.</span></span>  
  
 [!code-csharp[csProgGuideNamedAndOptional#12](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-use-named-and-optional-arguments-in-office-programming_9.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="0113b-154">См. также</span><span class="sxs-lookup"><span data-stu-id="0113b-154">See Also</span></span>  
 [<span data-ttu-id="0113b-155">Именованные и необязательные аргументы</span><span class="sxs-lookup"><span data-stu-id="0113b-155">Named and Optional Arguments</span></span>](../../../csharp/programming-guide/classes-and-structs/named-and-optional-arguments.md)

---
title: "Практическое руководство. Использование именованных и необязательных аргументов в программировании приложений Office (Руководство по программированию на C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- named and optional arguments [C#], Office programming
- optional arguments [C#], Office programming
- named arguments [C#], Office programming
ms.assetid: 65b8a222-bcd8-454c-845f-84adff5a356f
caps.latest.revision: 34
author: BillWagner
ms.author: wiwagn
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
ms.openlocfilehash: c773e7a6d902b9e61e724a69c9fdf5d61606de50
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-use-named-and-optional-arguments-in-office-programming-c-programming-guide"></a><span data-ttu-id="6de25-102">Практическое руководство. Использование именованных и необязательных аргументов в программировании приложений Office (Руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="6de25-102">How to: Use Named and Optional Arguments in Office Programming (C# Programming Guide)</span></span>
<span data-ttu-id="6de25-103">Появившиеся в [!INCLUDE[csharp_dev10_long](~/includes/csharp-dev10-long-md.md)] именованные и необязательные аргументы повышают удобство, гибкость и удобочитаемость программирования на C#.</span><span class="sxs-lookup"><span data-stu-id="6de25-103">Named arguments and optional arguments, introduced in [!INCLUDE[csharp_dev10_long](~/includes/csharp-dev10-long-md.md)], enhance convenience, flexibility, and readability in C# programming.</span></span> <span data-ttu-id="6de25-104">Кроме того, эти функции значительно упрощают доступ к COM-интерфейсам, таким как интерфейсы API автоматизации Microsoft Office.</span><span class="sxs-lookup"><span data-stu-id="6de25-104">In addition, these features greatly facilitate access to COM interfaces such as the Microsoft Office automation APIs.</span></span>  
  
 <span data-ttu-id="6de25-105">В следующем примере у метода [ConvertToTable](http://go.microsoft.com/fwlink/?LinkId=145378) имеется шестнадцать параметров, представляющих характеристики таблицы, например число столбцов и строк, форматирование, границы и цвета.</span><span class="sxs-lookup"><span data-stu-id="6de25-105">In the following example, method [ConvertToTable](http://go.microsoft.com/fwlink/?LinkId=145378) has sixteen parameters that represent characteristics of a table, such as number of columns and rows, formatting, borders, fonts, and colors.</span></span> <span data-ttu-id="6de25-106">Все шестнадцать параметров являются необязательными, поскольку в большинстве случаев не требуется задавать конкретные значения для всех этих параметров.</span><span class="sxs-lookup"><span data-stu-id="6de25-106">All sixteen parameters are optional, because most of the time you do not want to specify particular values for all of them.</span></span> <span data-ttu-id="6de25-107">Однако без именованных и необязательных аргументов приходилось указывать значение или значение-заполнитель для каждого из параметров.</span><span class="sxs-lookup"><span data-stu-id="6de25-107">However, without named and optional arguments, a value or a placeholder value has to be provided for each parameter.</span></span> <span data-ttu-id="6de25-108">Именованные и необязательные параметры позволяют задавать значения только для тех параметров, которые требуются в конкретном проекте.</span><span class="sxs-lookup"><span data-stu-id="6de25-108">With named and optional arguments, you specify values only for the parameters that are required for your project.</span></span>  
  
 <span data-ttu-id="6de25-109">Для выполнения этих процедур на компьютере должно быть установлено приложение Microsoft Office Word.</span><span class="sxs-lookup"><span data-stu-id="6de25-109">You must have Microsoft Office Word installed on your computer to complete these procedures.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-new-console-application"></a><span data-ttu-id="6de25-110">Создание нового проекта консольного приложения</span><span class="sxs-lookup"><span data-stu-id="6de25-110">To create a new console application</span></span>  
  
1.  <span data-ttu-id="6de25-111">Запустите Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="6de25-111">Start Visual Studio.</span></span>  
  
2.  <span data-ttu-id="6de25-112">В меню **Файл** выберите пункт **Создать**, а затем команду **Проект**.</span><span class="sxs-lookup"><span data-stu-id="6de25-112">On the **File** menu, point to **New**, and then click **Project**.</span></span>  
  
3.  <span data-ttu-id="6de25-113">В области **Категории шаблонов** разверните узел **Visual C#** и выберите **Windows**.</span><span class="sxs-lookup"><span data-stu-id="6de25-113">In the **Templates Categories** pane, expand **Visual C#**, and then click **Windows**.</span></span>  
  
4.  <span data-ttu-id="6de25-114">В верхней части области **Шаблоны** в поле **Требуемая версия .NET Framework** должно отображаться значение **.NET Framework 4**.</span><span class="sxs-lookup"><span data-stu-id="6de25-114">Look in the top of the **Templates** pane to make sure that **.NET Framework 4** appears in the **Target Framework** box.</span></span>  
  
5.  <span data-ttu-id="6de25-115">В области **Шаблоны** щелкните **Консольное приложение**.</span><span class="sxs-lookup"><span data-stu-id="6de25-115">In the **Templates** pane, click **Console Application**.</span></span>  
  
6.  <span data-ttu-id="6de25-116">Введите имя проекта в поле **Имя**.</span><span class="sxs-lookup"><span data-stu-id="6de25-116">Type a name for your project in the **Name** field.</span></span>  
  
7.  <span data-ttu-id="6de25-117">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="6de25-117">Click **OK**.</span></span>  
  
     <span data-ttu-id="6de25-118">В **обозревателе решений** появится новый проект.</span><span class="sxs-lookup"><span data-stu-id="6de25-118">The new project appears in **Solution Explorer**.</span></span>  
  
### <a name="to-add-a-reference"></a><span data-ttu-id="6de25-119">Добавление ссылки</span><span class="sxs-lookup"><span data-stu-id="6de25-119">To add a reference</span></span>  
  
1.  <span data-ttu-id="6de25-120">В **обозревателе решений** щелкните имя проекта правой кнопкой мыши и выберите пункт **Добавить ссылку**.</span><span class="sxs-lookup"><span data-stu-id="6de25-120">In **Solution Explorer**, right-click your project's name and then click **Add Reference**.</span></span> <span data-ttu-id="6de25-121">Откроется диалоговое окно **Добавление ссылки**.</span><span class="sxs-lookup"><span data-stu-id="6de25-121">The **Add Reference** dialog box appears.</span></span>  
  
2.  <span data-ttu-id="6de25-122">На странице **.NET** выберите **Microsoft.Office.Interop.Word** в списке **Имя компонента**.</span><span class="sxs-lookup"><span data-stu-id="6de25-122">On the **.NET** page, select **Microsoft.Office.Interop.Word** in the **Component Name** list.</span></span>  
  
3.  <span data-ttu-id="6de25-123">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="6de25-123">Click **OK**.</span></span>  
  
### <a name="to-add-necessary-using-directives"></a><span data-ttu-id="6de25-124">Добавление необходимых директив using</span><span class="sxs-lookup"><span data-stu-id="6de25-124">To add necessary using directives</span></span>  
  
1.  <span data-ttu-id="6de25-125">В **обозревателе решений** щелкните правой кнопкой мыши файл **Program.cs** и выберите пункт **Просмотреть код**.</span><span class="sxs-lookup"><span data-stu-id="6de25-125">In **Solution Explorer**, right-click the **Program.cs** file and then click **View Code**.</span></span>  
  
2.  <span data-ttu-id="6de25-126">В начало файла кода добавьте следующие директивы `using`.</span><span class="sxs-lookup"><span data-stu-id="6de25-126">Add the following `using` directives to the top of the code file.</span></span>  
  
     <span data-ttu-id="6de25-127">[!code-cs[csProgGuideNamedAndOptional#4](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-use-named-and-optional-arguments-in-office-programming_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="6de25-127">[!code-cs[csProgGuideNamedAndOptional#4](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-use-named-and-optional-arguments-in-office-programming_1.cs)]</span></span>  
  
### <a name="to-display-text-in-a-word-document"></a><span data-ttu-id="6de25-128">Отображение текста в документ Word</span><span class="sxs-lookup"><span data-stu-id="6de25-128">To display text in a Word document</span></span>  
  
1.  <span data-ttu-id="6de25-129">В класс `Program` в файле Program.cs добавьте следующий метод для создания приложения Word и документа Word.</span><span class="sxs-lookup"><span data-stu-id="6de25-129">In the `Program` class in Program.cs, add the following method to create a Word application and a Word document.</span></span> <span data-ttu-id="6de25-130">Метод [Add](http://go.microsoft.com/fwlink/?LinkId=145381) имеет четыре необязательных параметра.</span><span class="sxs-lookup"><span data-stu-id="6de25-130">The [Add](http://go.microsoft.com/fwlink/?LinkId=145381) method has four optional parameters.</span></span> <span data-ttu-id="6de25-131">В этом примере используются значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="6de25-131">This example uses their default values.</span></span> <span data-ttu-id="6de25-132">Поэтому в операторе вызова указывать аргументы не требуется.</span><span class="sxs-lookup"><span data-stu-id="6de25-132">Therefore, no arguments are necessary in the calling statement.</span></span>  
  
     <span data-ttu-id="6de25-133">[!code-cs[csProgGuideNamedAndOptional#6](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-use-named-and-optional-arguments-in-office-programming_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="6de25-133">[!code-cs[csProgGuideNamedAndOptional#6](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-use-named-and-optional-arguments-in-office-programming_2.cs)]</span></span>  
  
2.  <span data-ttu-id="6de25-134">Добавьте в конец метода следующий код, чтобы определить место отображения текста в документе и текст для отображения.</span><span class="sxs-lookup"><span data-stu-id="6de25-134">Add the following code at the end of the method to define where to display text in the document, and what text to display.</span></span>  
  
     <span data-ttu-id="6de25-135">[!code-cs[csProgGuideNamedAndOptional#7](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-use-named-and-optional-arguments-in-office-programming_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="6de25-135">[!code-cs[csProgGuideNamedAndOptional#7](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-use-named-and-optional-arguments-in-office-programming_3.cs)]</span></span>  
  
### <a name="to-run-the-application"></a><span data-ttu-id="6de25-136">Запуск приложения</span><span class="sxs-lookup"><span data-stu-id="6de25-136">To run the application</span></span>  
  
1.  <span data-ttu-id="6de25-137">Добавьте в метод Main следующую инструкцию.</span><span class="sxs-lookup"><span data-stu-id="6de25-137">Add the following statement to Main.</span></span>  
  
     <span data-ttu-id="6de25-138">[!code-cs[csProgGuideNamedAndOptional#8](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-use-named-and-optional-arguments-in-office-programming_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="6de25-138">[!code-cs[csProgGuideNamedAndOptional#8](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-use-named-and-optional-arguments-in-office-programming_4.cs)]</span></span>  
  
2.  <span data-ttu-id="6de25-139">Нажмите клавиши CTRL+F5, чтобы запустить проект.</span><span class="sxs-lookup"><span data-stu-id="6de25-139">Press CTRL+F5 to run the project.</span></span> <span data-ttu-id="6de25-140">Появится документ Word, содержащий указанный текст.</span><span class="sxs-lookup"><span data-stu-id="6de25-140">A Word document appears that contains the specified text.</span></span>  
  
### <a name="to-change-the-text-to-a-table"></a><span data-ttu-id="6de25-141">Замена текста на таблицу</span><span class="sxs-lookup"><span data-stu-id="6de25-141">To change the text to a table</span></span>  
  
1.  <span data-ttu-id="6de25-142">Метод `ConvertToTable` служит для преобразования текста в таблицу.</span><span class="sxs-lookup"><span data-stu-id="6de25-142">Use the `ConvertToTable` method to enclose the text in a table.</span></span> <span data-ttu-id="6de25-143">У метода имеется шестнадцать необязательных параметров.</span><span class="sxs-lookup"><span data-stu-id="6de25-143">The method has sixteen optional parameters.</span></span> <span data-ttu-id="6de25-144">IntelliSense заключает необязательные параметры в квадратные скобки, как показано на следующем рисунке.</span><span class="sxs-lookup"><span data-stu-id="6de25-144">IntelliSense encloses optional parameters in brackets, as shown in the following illustration.</span></span>  
  
     <span data-ttu-id="6de25-145">![Список параметров для метода ConvertToTable](../../../csharp/programming-guide/classes-and-structs/media/convert_tableparameters.png "Convert_TableParameters")</span><span class="sxs-lookup"><span data-stu-id="6de25-145">![List of parameters for ConvertToTable method.](../../../csharp/programming-guide/classes-and-structs/media/convert_tableparameters.png "Convert_TableParameters")</span></span>  
<span data-ttu-id="6de25-146">Параметры ConvertToTable</span><span class="sxs-lookup"><span data-stu-id="6de25-146">ConvertToTable parameters</span></span>  
  
     <span data-ttu-id="6de25-147">Именованные и необязательные аргументы позволяют задавать значения только для тех параметров, которые требуется изменить.</span><span class="sxs-lookup"><span data-stu-id="6de25-147">Named and optional arguments enable you to specify values for only the parameters that you want to change.</span></span> <span data-ttu-id="6de25-148">Добавьте в конец метода `DisplayInWord` следующий код, чтобы создать простую таблицу.</span><span class="sxs-lookup"><span data-stu-id="6de25-148">Add the following code to the end of method `DisplayInWord` to create a simple table.</span></span> <span data-ttu-id="6de25-149">Аргумент указывает, что запятые в текстовой строке в `range` разделяют ячейки таблицы.</span><span class="sxs-lookup"><span data-stu-id="6de25-149">The argument specifies that the commas in the text string in `range` separate the cells of the table.</span></span>  
  
     <span data-ttu-id="6de25-150">[!code-cs[csProgGuideNamedAndOptional#9](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-use-named-and-optional-arguments-in-office-programming_5.cs)]</span><span class="sxs-lookup"><span data-stu-id="6de25-150">[!code-cs[csProgGuideNamedAndOptional#9](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-use-named-and-optional-arguments-in-office-programming_5.cs)]</span></span>  
  
     <span data-ttu-id="6de25-151">В более ранних версиях C# для вызова `ConvertToTable` каждому параметру требовался ссылочный аргумент, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="6de25-151">In earlier versions of C#, the call to `ConvertToTable` requires a reference argument for each parameter, as shown in the following code.</span></span>  
  
     <span data-ttu-id="6de25-152">[!code-cs[csProgGuideNamedAndOptional#14](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-use-named-and-optional-arguments-in-office-programming_6.cs)]</span><span class="sxs-lookup"><span data-stu-id="6de25-152">[!code-cs[csProgGuideNamedAndOptional#14](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-use-named-and-optional-arguments-in-office-programming_6.cs)]</span></span>  
  
2.  <span data-ttu-id="6de25-153">Нажмите клавиши CTRL+F5, чтобы запустить проект.</span><span class="sxs-lookup"><span data-stu-id="6de25-153">Press CTRL+F5 to run the project.</span></span>  
  
### <a name="to-experiment-with-other-parameters"></a><span data-ttu-id="6de25-154">Экспериментирование с другими параметрами</span><span class="sxs-lookup"><span data-stu-id="6de25-154">To experiment with other parameters</span></span>  
  
1.  <span data-ttu-id="6de25-155">Для изменения таблицы, чтобы она содержала один столбец и три строки, замените последнюю строку метода `DisplayInWord` следующей инструкцией и нажмите сочетание клавиш CTRL+F5.</span><span class="sxs-lookup"><span data-stu-id="6de25-155">To change the table so that it has one column and three rows, replace the last line in `DisplayInWord` with the following statement and then type CTRL+F5.</span></span>  
  
     <span data-ttu-id="6de25-156">[!code-cs[csProgGuideNamedAndOptional#10](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-use-named-and-optional-arguments-in-office-programming_7.cs)]</span><span class="sxs-lookup"><span data-stu-id="6de25-156">[!code-cs[csProgGuideNamedAndOptional#10](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-use-named-and-optional-arguments-in-office-programming_7.cs)]</span></span>  
  
2.  <span data-ttu-id="6de25-157">Чтобы использовать заранее определенный формат таблицы, замените последнюю строку метода `DisplayInWord` следующей инструкцией и нажмите сочетание клавиш CTRL+F5.</span><span class="sxs-lookup"><span data-stu-id="6de25-157">To specify a predefined format for the table, replace the last line in `DisplayInWord` with the following statement and then type CTRL+F5.</span></span> <span data-ttu-id="6de25-158">В качестве формата можно использовать любую из констант [WdTableFormat](http://go.microsoft.com/fwlink/?LinkId=145382).</span><span class="sxs-lookup"><span data-stu-id="6de25-158">The format can be any of the [WdTableFormat](http://go.microsoft.com/fwlink/?LinkId=145382) constants.</span></span>  
  
     <span data-ttu-id="6de25-159">[!code-cs[csProgGuideNamedAndOptional#11](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-use-named-and-optional-arguments-in-office-programming_8.cs)]</span><span class="sxs-lookup"><span data-stu-id="6de25-159">[!code-cs[csProgGuideNamedAndOptional#11](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-use-named-and-optional-arguments-in-office-programming_8.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="6de25-160">Пример</span><span class="sxs-lookup"><span data-stu-id="6de25-160">Example</span></span>  
 <span data-ttu-id="6de25-161">Следующий код включает полный пример.</span><span class="sxs-lookup"><span data-stu-id="6de25-161">The following code includes the full example.</span></span>  
  
 <span data-ttu-id="6de25-162">[!code-cs[csProgGuideNamedAndOptional#12](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-use-named-and-optional-arguments-in-office-programming_9.cs)]</span><span class="sxs-lookup"><span data-stu-id="6de25-162">[!code-cs[csProgGuideNamedAndOptional#12](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-use-named-and-optional-arguments-in-office-programming_9.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6de25-163">См. также</span><span class="sxs-lookup"><span data-stu-id="6de25-163">See Also</span></span>  
 [<span data-ttu-id="6de25-164">Именованные и необязательные аргументы</span><span class="sxs-lookup"><span data-stu-id="6de25-164">Named and Optional Arguments</span></span>](../../../csharp/programming-guide/classes-and-structs/named-and-optional-arguments.md)


---
title: Действия с регулярными выражениями
ms.date: 03/30/2017
ms.assetid: b8f24694-49db-4339-92ec-014e3d4ae63b
ms.openlocfilehash: 50daa5b6d7baab37f372de4c30c2e0d12b4fa943
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/08/2018
ms.locfileid: "44201014"
---
# <a name="regular-expression-activities"></a><span data-ttu-id="635cb-102">Действия с регулярными выражениями</span><span class="sxs-lookup"><span data-stu-id="635cb-102">Regular Expression Activities</span></span>
<span data-ttu-id="635cb-103">Этот образец демонстрирует способ создания набора действий, которые представляют функциональные возможности регулярного выражения пространства имен <xref:System.Text.RegularExpressions>.</span><span class="sxs-lookup"><span data-stu-id="635cb-103">This sample demonstrates how to create a set of activities that expose the regular expression functionality of the <xref:System.Text.RegularExpressions> namespace.</span></span> <span data-ttu-id="635cb-104">Такие пользовательские действия можно использовать в приложении рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="635cb-104">These custom activities can be used within a workflow application.</span></span> <span data-ttu-id="635cb-105">Дополнительные сведения о регулярных выражениях см. в разделе [N:System.Text.RegularExpressions](https://go.microsoft.com/fwlink/?LinkId=150434) пространства имен.</span><span class="sxs-lookup"><span data-stu-id="635cb-105">For more information about regular expressions, see [N:System.Text.RegularExpressions](https://go.microsoft.com/fwlink/?LinkId=150434) Namespace.</span></span>  
  
 <span data-ttu-id="635cb-106">В следующей таблице приведены сведения о пользовательских действиях, выполняемых в данном образце.</span><span class="sxs-lookup"><span data-stu-id="635cb-106">The following table details the custom activities in this sample.</span></span>  
  
|<span data-ttu-id="635cb-107">Действие</span><span class="sxs-lookup"><span data-stu-id="635cb-107">Activity</span></span>|<span data-ttu-id="635cb-108">Описание</span><span class="sxs-lookup"><span data-stu-id="635cb-108">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="635cb-109">IsMatch</span><span class="sxs-lookup"><span data-stu-id="635cb-109">IsMatch</span></span>|<span data-ttu-id="635cb-110">Указывает, были ли найдены совпадения во входной строке в результате выполнения регулярного выражения.</span><span class="sxs-lookup"><span data-stu-id="635cb-110">Specifies whether the regular expression found a match in the input string.</span></span>|  
|<span data-ttu-id="635cb-111">Соответствия</span><span class="sxs-lookup"><span data-stu-id="635cb-111">Matches</span></span>|<span data-ttu-id="635cb-112">Выполняет поиск всех вхождений регулярного выражения во входной строке и возвращает все найденные совпадения.</span><span class="sxs-lookup"><span data-stu-id="635cb-112">Searches an input string for all occurrences of a regular expression and returns all the successful matches.</span></span>|  
|<span data-ttu-id="635cb-113">Заменить</span><span class="sxs-lookup"><span data-stu-id="635cb-113">Replace</span></span>|<span data-ttu-id="635cb-114">Заменяет в указанной входной строке все строки, совпадающие с шаблоном регулярного выражения, на указанную строку замены.</span><span class="sxs-lookup"><span data-stu-id="635cb-114">Within a specified input string, replaces strings that match a regular expression pattern with a specified replacement string.</span></span>|  
  
## <a name="ismatch"></a><span data-ttu-id="635cb-115">IsMatch</span><span class="sxs-lookup"><span data-stu-id="635cb-115">IsMatch</span></span>  
 <span data-ttu-id="635cb-116">Пользовательское действие `IsMatch` возвращает `true`, если свойство строки `Input` совпадает с регулярным выражением, указанным в свойстве `Pattern`.</span><span class="sxs-lookup"><span data-stu-id="635cb-116">The `IsMatch` custom activity returns `true` if the `Input` string property finds a match in the regular expression specified in the `Pattern` property.</span></span> <span data-ttu-id="635cb-117">Действие является производным от <xref:System.Activities.CodeActivity%601>, и в методе <xref:System.Activities.CodeActivity%601.Execute%2A> вызывается метод <xref:System.Text.RegularExpressions.Regex.IsMatch%2A>.</span><span class="sxs-lookup"><span data-stu-id="635cb-117">The activity derives from <xref:System.Activities.CodeActivity%601> and within the <xref:System.Activities.CodeActivity%601.Execute%2A> method calls the <xref:System.Text.RegularExpressions.Regex.IsMatch%2A> method.</span></span>  
  
 <span data-ttu-id="635cb-118">В следующей таблице описываются свойства и возвращаемое значение для настраиваемого действия `IsMatch`.</span><span class="sxs-lookup"><span data-stu-id="635cb-118">The following table describes the properties and return value for the `IsMatch` custom activity.</span></span>  
  
|<span data-ttu-id="635cb-119">Свойство или возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="635cb-119">Property or Return Value</span></span>|<span data-ttu-id="635cb-120">Описание</span><span class="sxs-lookup"><span data-stu-id="635cb-120">Description</span></span>|  
|------------------------------|-----------------|  
|<span data-ttu-id="635cb-121">Шаблон (обязательно)</span><span class="sxs-lookup"><span data-stu-id="635cb-121">Pattern (required)</span></span>|<span data-ttu-id="635cb-122">Регулярное выражение, по которому выполняется поиск.</span><span class="sxs-lookup"><span data-stu-id="635cb-122">The regular expression to search with.</span></span>|  
|<span data-ttu-id="635cb-123">Входные данные (обязательно)</span><span class="sxs-lookup"><span data-stu-id="635cb-123">Input (required)</span></span>|<span data-ttu-id="635cb-124">Входная строка для поиска.</span><span class="sxs-lookup"><span data-stu-id="635cb-124">The input string to search.</span></span>|  
|<span data-ttu-id="635cb-125">RegexOptions</span><span class="sxs-lookup"><span data-stu-id="635cb-125">RegexOptions</span></span>|<span data-ttu-id="635cb-126">Побитовое сочетание OR [RegexOptions](https://go.microsoft.com/fwlink/?LinkId=150446) значений перечисления.</span><span class="sxs-lookup"><span data-stu-id="635cb-126">Bitwise OR combination of [RegexOptions](https://go.microsoft.com/fwlink/?LinkId=150446) enumeration values.</span></span>|  
|<span data-ttu-id="635cb-127">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="635cb-127">Return value</span></span>|<span data-ttu-id="635cb-128">`true`, если входная строка совпадает с указанным шаблоном. В противном случае `false`.</span><span class="sxs-lookup"><span data-stu-id="635cb-128">`true` if the input finds a match in the provided pattern; otherwise `false`.</span></span>|  
  
 <span data-ttu-id="635cb-129">В следующем примере кода показано использование настраиваемого действия `IsMatch`.</span><span class="sxs-lookup"><span data-stu-id="635cb-129">The following code example demonstrates how to use the `IsMatch` custom activity.</span></span>  
  
```  
new IsMatch  
{  
    Pattern = new InArgument<string>( @"^-?\d+(\.\d{2})?$"),  
    Input = "20.00",  
};  
```  
  
## <a name="matches"></a><span data-ttu-id="635cb-130">Соответствия</span><span class="sxs-lookup"><span data-stu-id="635cb-130">Matches</span></span>  
 <span data-ttu-id="635cb-131">Пользовательское действие `Matches` выполняет поиск всех вхождений регулярного выражения во входной строке и возвращает все найденные совпадения.</span><span class="sxs-lookup"><span data-stu-id="635cb-131">The `Matches` custom activity searches an input string for all occurrences of a regular expression and returns all the successful matches.</span></span> <span data-ttu-id="635cb-132">Действие является производным от <xref:System.Activities.CodeActivity%601>, и в методе <xref:System.Activities.CodeActivity%601.Execute%2A> вызывается метод <xref:System.Text.RegularExpressions.Regex.Matches%2A>.</span><span class="sxs-lookup"><span data-stu-id="635cb-132">The activity derives from <xref:System.Activities.CodeActivity%601> and within the <xref:System.Activities.CodeActivity%601.Execute%2A> method calls the <xref:System.Text.RegularExpressions.Regex.Matches%2A> method.</span></span>  
  
 <span data-ttu-id="635cb-133">В следующей таблице описываются свойства и возвращаемое значение для настраиваемого действия `IsMatch`.</span><span class="sxs-lookup"><span data-stu-id="635cb-133">The following table describes the properties and return value for the `IsMatch` custom activity.</span></span>  
  
|<span data-ttu-id="635cb-134">Свойство или возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="635cb-134">Property or Return Value</span></span>|<span data-ttu-id="635cb-135">Описание</span><span class="sxs-lookup"><span data-stu-id="635cb-135">Description</span></span>|  
|------------------------------|-----------------|  
|<span data-ttu-id="635cb-136">Шаблон (обязательно)</span><span class="sxs-lookup"><span data-stu-id="635cb-136">Pattern (required)</span></span>|<span data-ttu-id="635cb-137">Регулярное выражение, по которому выполняется поиск.</span><span class="sxs-lookup"><span data-stu-id="635cb-137">The regular expression to search with.</span></span>|  
|<span data-ttu-id="635cb-138">Входные данные (обязательно)</span><span class="sxs-lookup"><span data-stu-id="635cb-138">Input (required)</span></span>|<span data-ttu-id="635cb-139">Входная строка для поиска.</span><span class="sxs-lookup"><span data-stu-id="635cb-139">The input string to search.</span></span>|  
|<span data-ttu-id="635cb-140">RegexOptions</span><span class="sxs-lookup"><span data-stu-id="635cb-140">RegexOptions</span></span>|<span data-ttu-id="635cb-141">Побитовое сочетание OR [RegexOptions](https://go.microsoft.com/fwlink/?LinkId=150446) значений перечисления.</span><span class="sxs-lookup"><span data-stu-id="635cb-141">Bitwise OR combination of [RegexOptions](https://go.microsoft.com/fwlink/?LinkId=150446) enumeration values.</span></span>|  
|<span data-ttu-id="635cb-142">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="635cb-142">Return Value</span></span>|<span data-ttu-id="635cb-143">Объект <xref:System.Text.RegularExpressions.MatchCollection>, содержащий коллекцию успешных совпадений.</span><span class="sxs-lookup"><span data-stu-id="635cb-143">A <xref:System.Text.RegularExpressions.MatchCollection> that contains the collection of successful matches.</span></span>|  
  
 <span data-ttu-id="635cb-144">В следующем примере кода показано использование настраиваемого действия `Matches`.</span><span class="sxs-lookup"><span data-stu-id="635cb-144">The following code example demonstrates how to use the `Matches` custom activity.</span></span>  
  
```  
new Matches  
{  
    Pattern = @"\b(?<word>\w+)\s+(\k<word>)\b",  
    Input = "The quick brown fox  fox jumped over over the lazy dog dog.",  
};  
```  
  
## <a name="replace"></a><span data-ttu-id="635cb-145">Заменить</span><span class="sxs-lookup"><span data-stu-id="635cb-145">Replace</span></span>  
 <span data-ttu-id="635cb-146">Пользовательское действие `Replace` выполняет поиск во входной строке и заменяет в этой строке все строки, совпадающие с указанным регулярным выражением.</span><span class="sxs-lookup"><span data-stu-id="635cb-146">The `Replace` custom activity searches an input string and replaces all strings that match a specified regular expression with a string.</span></span> <span data-ttu-id="635cb-147">Действие является производным от <xref:System.Activities.CodeActivity%601>, и в методе <xref:System.Activities.CodeActivity%601.Execute%2A> вызывается метод <xref:System.Text.RegularExpressions.Regex.Replace%2A>.</span><span class="sxs-lookup"><span data-stu-id="635cb-147">The activity derives from <xref:System.Activities.CodeActivity%601> and within the <xref:System.Activities.CodeActivity%601.Execute%2A> method calls the <xref:System.Text.RegularExpressions.Regex.Replace%2A> method.</span></span>  
  
 <span data-ttu-id="635cb-148">В следующей таблице описываются свойства и возвращаемое значение для настраиваемого действия `Replace`.</span><span class="sxs-lookup"><span data-stu-id="635cb-148">The following table describes the properties and return value for the `Replace` custom activity.</span></span>  
  
|<span data-ttu-id="635cb-149">Свойство или возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="635cb-149">Property or Return Value</span></span>|<span data-ttu-id="635cb-150">Описание</span><span class="sxs-lookup"><span data-stu-id="635cb-150">Description</span></span>|  
|------------------------------|-----------------|  
|<span data-ttu-id="635cb-151">Шаблон (обязательно)</span><span class="sxs-lookup"><span data-stu-id="635cb-151">Pattern (required)</span></span>|<span data-ttu-id="635cb-152">Регулярное выражение, по которому выполняется поиск.</span><span class="sxs-lookup"><span data-stu-id="635cb-152">The regular expression to search with.</span></span>|  
|<span data-ttu-id="635cb-153">Входные данные (обязательно)</span><span class="sxs-lookup"><span data-stu-id="635cb-153">Input (required)</span></span>|<span data-ttu-id="635cb-154">Входная строка для поиска.</span><span class="sxs-lookup"><span data-stu-id="635cb-154">The input string to search.</span></span>|  
|<span data-ttu-id="635cb-155">Замена</span><span class="sxs-lookup"><span data-stu-id="635cb-155">Replacement</span></span>|<span data-ttu-id="635cb-156">Строка замены.</span><span class="sxs-lookup"><span data-stu-id="635cb-156">The replacement string.</span></span><br /><br /> <span data-ttu-id="635cb-157">Если задано свойство `Replacement`, то свойство `MatchEvaluator` не учитывается.</span><span class="sxs-lookup"><span data-stu-id="635cb-157">If a `Replacement` is specified, then the `MatchEvaluator` property is ignored.</span></span> <span data-ttu-id="635cb-158">Необходимо задать либо свойство `Replacement`, либо свойство `MatchEvaluator`.</span><span class="sxs-lookup"><span data-stu-id="635cb-158">Either the `Replacement` or `MatchEvaluator` property must be set.</span></span>|  
|<span data-ttu-id="635cb-159">MatchEvaluator</span><span class="sxs-lookup"><span data-stu-id="635cb-159">MatchEvaluator</span></span>|<span data-ttu-id="635cb-160">Пользовательский метод, анализирующий каждое совпадение и возвращающий либо исходную строку с совпадениями, либо строку замены.</span><span class="sxs-lookup"><span data-stu-id="635cb-160">A custom method that examines each match and returns either the original matched string or a replacement string.</span></span><br /><br /> <span data-ttu-id="635cb-161">Если задано свойство `Replacement`, то свойство `MatchEvaluator` не учитывается.</span><span class="sxs-lookup"><span data-stu-id="635cb-161">If a `Replacement` is specified, then the `MatchEvaluator` property is ignored.</span></span> <span data-ttu-id="635cb-162">Необходимо задать либо свойство `Replacement`, либо свойство `MatchEvaluator`.</span><span class="sxs-lookup"><span data-stu-id="635cb-162">Either the `Replacement` or `MatchEvaluator` property must be set.</span></span>|  
|<span data-ttu-id="635cb-163">RegexOptions</span><span class="sxs-lookup"><span data-stu-id="635cb-163">RegexOptions</span></span>|<span data-ttu-id="635cb-164">Побитовое сочетание OR [RegexOptions](https://go.microsoft.com/fwlink/?LinkId=150446) значений перечисления.</span><span class="sxs-lookup"><span data-stu-id="635cb-164">Bitwise OR combination of [RegexOptions](https://go.microsoft.com/fwlink/?LinkId=150446) enumeration values.</span></span>|  
|<span data-ttu-id="635cb-165">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="635cb-165">Return Value</span></span>|<span data-ttu-id="635cb-166">Объект <xref:System.Text.RegularExpressions.MatchCollection>, содержащий коллекцию успешных совпадений.</span><span class="sxs-lookup"><span data-stu-id="635cb-166">A <xref:System.Text.RegularExpressions.MatchCollection> that contains the collection of successful matches.</span></span>|  
  
 <span data-ttu-id="635cb-167">В следующем примере кода показано использование настраиваемого действия `Replace`.</span><span class="sxs-lookup"><span data-stu-id="635cb-167">The following code example demonstrates how to use the `Replace` custom activity.</span></span>  
  
```  
// Using the replacement string.  
new Replace  
{  
    Pattern = @"\bWorld\b",  
    Input = "Hello World! This is a wonderful World",  
    Replacement = "Universe"  
};  
  
// Using a match evaluator.  
new Replace  
{  
    Pattern = new InArgument<string>(pattern),  
    Input = new InArgument<string>(input),  
    MatchEvaluator = new MatchEvaluator(CapText)                  
};  
```  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="635cb-168">Использование этого образца</span><span class="sxs-lookup"><span data-stu-id="635cb-168">To use this sample</span></span>  
  
1.  <span data-ttu-id="635cb-169">Откройте файл решения RegexActivities.sln в среде [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="635cb-169">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the RegexActivities.sln solution file.</span></span>  
  
2.  <span data-ttu-id="635cb-170">Для построения решения нажмите CTRL+SHIFT+B.</span><span class="sxs-lookup"><span data-stu-id="635cb-170">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="635cb-171">Чтобы запустить решение, нажмите клавиши CTRL+F5.</span><span class="sxs-lookup"><span data-stu-id="635cb-171">To run the solution, press CTRL+F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="635cb-172">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="635cb-172">The samples may already be installed on your machine.</span></span> <span data-ttu-id="635cb-173">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="635cb-173">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="635cb-174">Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] примеры.</span><span class="sxs-lookup"><span data-stu-id="635cb-174">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="635cb-175">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="635cb-175">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\Regex`
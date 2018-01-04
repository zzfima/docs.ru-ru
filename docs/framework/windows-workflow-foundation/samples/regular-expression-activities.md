---
title: "Действия с регулярными выражениями"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b8f24694-49db-4339-92ec-014e3d4ae63b
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3d40d33a5d93ecce07a2e264dcfe9fcde3778437
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="regular-expression-activities"></a><span data-ttu-id="090e3-102">Действия с регулярными выражениями</span><span class="sxs-lookup"><span data-stu-id="090e3-102">Regular Expression Activities</span></span>
<span data-ttu-id="090e3-103">Этот образец демонстрирует способ создания набора действий, которые представляют функциональные возможности регулярного выражения пространства имен <xref:System.Text.RegularExpressions>.</span><span class="sxs-lookup"><span data-stu-id="090e3-103">This sample demonstrates how to create a set of activities that expose the regular expression functionality of the <xref:System.Text.RegularExpressions> namespace.</span></span> <span data-ttu-id="090e3-104">Такие пользовательские действия можно использовать в приложении рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="090e3-104">These custom activities can be used within a workflow application.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="090e3-105">в разделе Регулярные выражения [N:System.Text.RegularExpressions](http://go.microsoft.com/fwlink/?LinkId=150434) пространства имен.</span><span class="sxs-lookup"><span data-stu-id="090e3-105"> regular expressions, see [N:System.Text.RegularExpressions](http://go.microsoft.com/fwlink/?LinkId=150434) Namespace.</span></span>  
  
 <span data-ttu-id="090e3-106">В следующей таблице приведены сведения о пользовательских действиях, выполняемых в данном образце.</span><span class="sxs-lookup"><span data-stu-id="090e3-106">The following table details the custom activities in this sample.</span></span>  
  
|<span data-ttu-id="090e3-107">Действие</span><span class="sxs-lookup"><span data-stu-id="090e3-107">Activity</span></span>|<span data-ttu-id="090e3-108">Описание</span><span class="sxs-lookup"><span data-stu-id="090e3-108">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="090e3-109">IsMatch</span><span class="sxs-lookup"><span data-stu-id="090e3-109">IsMatch</span></span>|<span data-ttu-id="090e3-110">Указывает, были ли найдены совпадения во входной строке в результате выполнения регулярного выражения.</span><span class="sxs-lookup"><span data-stu-id="090e3-110">Specifies whether the regular expression found a match in the input string.</span></span>|  
|<span data-ttu-id="090e3-111">Соответствия</span><span class="sxs-lookup"><span data-stu-id="090e3-111">Matches</span></span>|<span data-ttu-id="090e3-112">Выполняет поиск всех вхождений регулярного выражения во входной строке и возвращает все найденные совпадения.</span><span class="sxs-lookup"><span data-stu-id="090e3-112">Searches an input string for all occurrences of a regular expression and returns all the successful matches.</span></span>|  
|<span data-ttu-id="090e3-113">Заменить</span><span class="sxs-lookup"><span data-stu-id="090e3-113">Replace</span></span>|<span data-ttu-id="090e3-114">Заменяет в указанной входной строке все строки, совпадающие с шаблоном регулярного выражения, на указанную строку замены.</span><span class="sxs-lookup"><span data-stu-id="090e3-114">Within a specified input string, replaces strings that match a regular expression pattern with a specified replacement string.</span></span>|  
  
## <a name="ismatch"></a><span data-ttu-id="090e3-115">IsMatch</span><span class="sxs-lookup"><span data-stu-id="090e3-115">IsMatch</span></span>  
 <span data-ttu-id="090e3-116">Пользовательское действие `IsMatch` возвращает `true`, если свойство строки `Input` совпадает с регулярным выражением, указанным в свойстве `Pattern`.</span><span class="sxs-lookup"><span data-stu-id="090e3-116">The `IsMatch` custom activity returns `true` if the `Input` string property finds a match in the regular expression specified in the `Pattern` property.</span></span> <span data-ttu-id="090e3-117">Действие является производным от <xref:System.Activities.CodeActivity%601>, и в методе <xref:System.Activities.CodeActivity%601.Execute%2A> вызывается метод <xref:System.Text.RegularExpressions.Regex.IsMatch%2A>.</span><span class="sxs-lookup"><span data-stu-id="090e3-117">The activity derives from <xref:System.Activities.CodeActivity%601> and within the <xref:System.Activities.CodeActivity%601.Execute%2A> method calls the <xref:System.Text.RegularExpressions.Regex.IsMatch%2A> method.</span></span>  
  
 <span data-ttu-id="090e3-118">В следующей таблице описываются свойства и возвращаемое значение для настраиваемого действия `IsMatch`.</span><span class="sxs-lookup"><span data-stu-id="090e3-118">The following table describes the properties and return value for the `IsMatch` custom activity.</span></span>  
  
|<span data-ttu-id="090e3-119">Свойство или возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="090e3-119">Property or Return Value</span></span>|<span data-ttu-id="090e3-120">Описание</span><span class="sxs-lookup"><span data-stu-id="090e3-120">Description</span></span>|  
|------------------------------|-----------------|  
|<span data-ttu-id="090e3-121">Шаблон (обязательно)</span><span class="sxs-lookup"><span data-stu-id="090e3-121">Pattern (required)</span></span>|<span data-ttu-id="090e3-122">Регулярное выражение, по которому выполняется поиск.</span><span class="sxs-lookup"><span data-stu-id="090e3-122">The regular expression to search with.</span></span>|  
|<span data-ttu-id="090e3-123">Входные данные (обязательно)</span><span class="sxs-lookup"><span data-stu-id="090e3-123">Input (required)</span></span>|<span data-ttu-id="090e3-124">Входная строка для поиска.</span><span class="sxs-lookup"><span data-stu-id="090e3-124">The input string to search.</span></span>|  
|<span data-ttu-id="090e3-125">RegexOptions</span><span class="sxs-lookup"><span data-stu-id="090e3-125">RegexOptions</span></span>|<span data-ttu-id="090e3-126">Побитовое сочетание OR [RegexOptions](http://go.microsoft.com/fwlink/?LinkId=150446) значений перечисления.</span><span class="sxs-lookup"><span data-stu-id="090e3-126">Bitwise OR combination of [RegexOptions](http://go.microsoft.com/fwlink/?LinkId=150446) enumeration values.</span></span>|  
|<span data-ttu-id="090e3-127">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="090e3-127">Return value</span></span>|<span data-ttu-id="090e3-128">`true`, если входная строка совпадает с указанным шаблоном. В противном случае `false`.</span><span class="sxs-lookup"><span data-stu-id="090e3-128">`true` if the input finds a match in the provided pattern; otherwise `false`.</span></span>|  
  
 <span data-ttu-id="090e3-129">В следующем примере кода показано использование настраиваемого действия `IsMatch`.</span><span class="sxs-lookup"><span data-stu-id="090e3-129">The following code example demonstrates how to use the `IsMatch` custom activity.</span></span>  
  
```  
new IsMatch  
{  
    Pattern = new InArgument<string>( @"^-?\d+(\.\d{2})?$"),  
    Input = "20.00",  
};  
```  
  
## <a name="matches"></a><span data-ttu-id="090e3-130">Соответствия</span><span class="sxs-lookup"><span data-stu-id="090e3-130">Matches</span></span>  
 <span data-ttu-id="090e3-131">Пользовательское действие `Matches` выполняет поиск всех вхождений регулярного выражения во входной строке и возвращает все найденные совпадения.</span><span class="sxs-lookup"><span data-stu-id="090e3-131">The `Matches` custom activity searches an input string for all occurrences of a regular expression and returns all the successful matches.</span></span> <span data-ttu-id="090e3-132">Действие является производным от <xref:System.Activities.CodeActivity%601>, и в методе <xref:System.Activities.CodeActivity%601.Execute%2A> вызывается метод <xref:System.Text.RegularExpressions.Regex.Matches%2A>.</span><span class="sxs-lookup"><span data-stu-id="090e3-132">The activity derives from <xref:System.Activities.CodeActivity%601> and within the <xref:System.Activities.CodeActivity%601.Execute%2A> method calls the <xref:System.Text.RegularExpressions.Regex.Matches%2A> method.</span></span>  
  
 <span data-ttu-id="090e3-133">В следующей таблице описываются свойства и возвращаемое значение для настраиваемого действия `IsMatch`.</span><span class="sxs-lookup"><span data-stu-id="090e3-133">The following table describes the properties and return value for the `IsMatch` custom activity.</span></span>  
  
|<span data-ttu-id="090e3-134">Свойство или возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="090e3-134">Property or Return Value</span></span>|<span data-ttu-id="090e3-135">Описание</span><span class="sxs-lookup"><span data-stu-id="090e3-135">Description</span></span>|  
|------------------------------|-----------------|  
|<span data-ttu-id="090e3-136">Шаблон (обязательно)</span><span class="sxs-lookup"><span data-stu-id="090e3-136">Pattern (required)</span></span>|<span data-ttu-id="090e3-137">Регулярное выражение, по которому выполняется поиск.</span><span class="sxs-lookup"><span data-stu-id="090e3-137">The regular expression to search with.</span></span>|  
|<span data-ttu-id="090e3-138">Входные данные (обязательно)</span><span class="sxs-lookup"><span data-stu-id="090e3-138">Input (required)</span></span>|<span data-ttu-id="090e3-139">Входная строка для поиска.</span><span class="sxs-lookup"><span data-stu-id="090e3-139">The input string to search.</span></span>|  
|<span data-ttu-id="090e3-140">RegexOptions</span><span class="sxs-lookup"><span data-stu-id="090e3-140">RegexOptions</span></span>|<span data-ttu-id="090e3-141">Побитовое сочетание OR [RegexOptions](http://go.microsoft.com/fwlink/?LinkId=150446) значений перечисления.</span><span class="sxs-lookup"><span data-stu-id="090e3-141">Bitwise OR combination of [RegexOptions](http://go.microsoft.com/fwlink/?LinkId=150446) enumeration values.</span></span>|  
|<span data-ttu-id="090e3-142">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="090e3-142">Return Value</span></span>|<span data-ttu-id="090e3-143">Объект <xref:System.Text.RegularExpressions.MatchCollection>, содержащий коллекцию успешных совпадений.</span><span class="sxs-lookup"><span data-stu-id="090e3-143">A <xref:System.Text.RegularExpressions.MatchCollection> that contains the collection of successful matches.</span></span>|  
  
 <span data-ttu-id="090e3-144">В следующем примере кода показано использование настраиваемого действия `Matches`.</span><span class="sxs-lookup"><span data-stu-id="090e3-144">The following code example demonstrates how to use the `Matches` custom activity.</span></span>  
  
```  
new Matches  
{  
    Pattern = @"\b(?<word>\w+)\s+(\k<word>)\b",  
    Input = "The quick brown fox  fox jumped over over the lazy dog dog.",  
};  
```  
  
## <a name="replace"></a><span data-ttu-id="090e3-145">Заменить</span><span class="sxs-lookup"><span data-stu-id="090e3-145">Replace</span></span>  
 <span data-ttu-id="090e3-146">Пользовательское действие `Replace` выполняет поиск во входной строке и заменяет в этой строке все строки, совпадающие с указанным регулярным выражением.</span><span class="sxs-lookup"><span data-stu-id="090e3-146">The `Replace` custom activity searches an input string and replaces all strings that match a specified regular expression with a string.</span></span> <span data-ttu-id="090e3-147">Действие является производным от <xref:System.Activities.CodeActivity%601>, и в методе <xref:System.Activities.CodeActivity%601.Execute%2A> вызывается метод <xref:System.Text.RegularExpressions.Regex.Replace%2A>.</span><span class="sxs-lookup"><span data-stu-id="090e3-147">The activity derives from <xref:System.Activities.CodeActivity%601> and within the <xref:System.Activities.CodeActivity%601.Execute%2A> method calls the <xref:System.Text.RegularExpressions.Regex.Replace%2A> method.</span></span>  
  
 <span data-ttu-id="090e3-148">В следующей таблице описываются свойства и возвращаемое значение для настраиваемого действия `Replace`.</span><span class="sxs-lookup"><span data-stu-id="090e3-148">The following table describes the properties and return value for the `Replace` custom activity.</span></span>  
  
|<span data-ttu-id="090e3-149">Свойство или возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="090e3-149">Property or Return Value</span></span>|<span data-ttu-id="090e3-150">Описание</span><span class="sxs-lookup"><span data-stu-id="090e3-150">Description</span></span>|  
|------------------------------|-----------------|  
|<span data-ttu-id="090e3-151">Шаблон (обязательно)</span><span class="sxs-lookup"><span data-stu-id="090e3-151">Pattern (required)</span></span>|<span data-ttu-id="090e3-152">Регулярное выражение, по которому выполняется поиск.</span><span class="sxs-lookup"><span data-stu-id="090e3-152">The regular expression to search with.</span></span>|  
|<span data-ttu-id="090e3-153">Входные данные (обязательно)</span><span class="sxs-lookup"><span data-stu-id="090e3-153">Input (required)</span></span>|<span data-ttu-id="090e3-154">Входная строка для поиска.</span><span class="sxs-lookup"><span data-stu-id="090e3-154">The input string to search.</span></span>|  
|<span data-ttu-id="090e3-155">Замена</span><span class="sxs-lookup"><span data-stu-id="090e3-155">Replacement</span></span>|<span data-ttu-id="090e3-156">Строка замены.</span><span class="sxs-lookup"><span data-stu-id="090e3-156">The replacement string.</span></span><br /><br /> <span data-ttu-id="090e3-157">Если задано свойство `Replacement`, то свойство `MatchEvaluator` не учитывается.</span><span class="sxs-lookup"><span data-stu-id="090e3-157">If a `Replacement` is specified, then the `MatchEvaluator` property is ignored.</span></span> <span data-ttu-id="090e3-158">Необходимо задать либо свойство `Replacement`, либо свойство `MatchEvaluator`.</span><span class="sxs-lookup"><span data-stu-id="090e3-158">Either the `Replacement` or `MatchEvaluator` property must be set.</span></span>|  
|<span data-ttu-id="090e3-159">MatchEvaluator</span><span class="sxs-lookup"><span data-stu-id="090e3-159">MatchEvaluator</span></span>|<span data-ttu-id="090e3-160">Пользовательский метод, анализирующий каждое совпадение и возвращающий либо исходную строку с совпадениями, либо строку замены.</span><span class="sxs-lookup"><span data-stu-id="090e3-160">A custom method that examines each match and returns either the original matched string or a replacement string.</span></span><br /><br /> <span data-ttu-id="090e3-161">Если задано свойство `Replacement`, то свойство `MatchEvaluator` не учитывается.</span><span class="sxs-lookup"><span data-stu-id="090e3-161">If a `Replacement` is specified, then the `MatchEvaluator` property is ignored.</span></span> <span data-ttu-id="090e3-162">Необходимо задать либо свойство `Replacement`, либо свойство `MatchEvaluator`.</span><span class="sxs-lookup"><span data-stu-id="090e3-162">Either the `Replacement` or `MatchEvaluator` property must be set.</span></span>|  
|<span data-ttu-id="090e3-163">RegexOptions</span><span class="sxs-lookup"><span data-stu-id="090e3-163">RegexOptions</span></span>|<span data-ttu-id="090e3-164">Побитовое сочетание OR [RegexOptions](http://go.microsoft.com/fwlink/?LinkId=150446) значений перечисления.</span><span class="sxs-lookup"><span data-stu-id="090e3-164">Bitwise OR combination of [RegexOptions](http://go.microsoft.com/fwlink/?LinkId=150446) enumeration values.</span></span>|  
|<span data-ttu-id="090e3-165">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="090e3-165">Return Value</span></span>|<span data-ttu-id="090e3-166">Объект <xref:System.Text.RegularExpressions.MatchCollection>, содержащий коллекцию успешных совпадений.</span><span class="sxs-lookup"><span data-stu-id="090e3-166">A <xref:System.Text.RegularExpressions.MatchCollection> that contains the collection of successful matches.</span></span>|  
  
 <span data-ttu-id="090e3-167">В следующем примере кода показано использование настраиваемого действия `Replace`.</span><span class="sxs-lookup"><span data-stu-id="090e3-167">The following code example demonstrates how to use the `Replace` custom activity.</span></span>  
  
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
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="090e3-168">Использование этого образца</span><span class="sxs-lookup"><span data-stu-id="090e3-168">To use this sample</span></span>  
  
1.  <span data-ttu-id="090e3-169">Откройте файл решения RegexActivities.sln в среде [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="090e3-169">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the RegexActivities.sln solution file.</span></span>  
  
2.  <span data-ttu-id="090e3-170">Для построения решения нажмите CTRL+SHIFT+B.</span><span class="sxs-lookup"><span data-stu-id="090e3-170">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="090e3-171">Чтобы запустить решение, нажмите клавиши CTRL+F5.</span><span class="sxs-lookup"><span data-stu-id="090e3-171">To run the solution, press CTRL+F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="090e3-172">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="090e3-172">The samples may already be installed on your machine.</span></span> <span data-ttu-id="090e3-173">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="090e3-173">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="090e3-174">Если этот каталог не существует, перейдите на страницу [Примеры Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все примеры [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="090e3-174">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="090e3-175">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="090e3-175">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\Regex`
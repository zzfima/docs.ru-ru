---
title: Действия с регулярными выражениями
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b8f24694-49db-4339-92ec-014e3d4ae63b
caps.latest.revision: 9
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 74aef126011789cfd48aa962973cc67a4132c224
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/30/2018
---
# <a name="regular-expression-activities"></a><span data-ttu-id="bcac9-102">Действия с регулярными выражениями</span><span class="sxs-lookup"><span data-stu-id="bcac9-102">Regular Expression Activities</span></span>
<span data-ttu-id="bcac9-103">Этот образец демонстрирует способ создания набора действий, которые представляют функциональные возможности регулярного выражения пространства имен <xref:System.Text.RegularExpressions>.</span><span class="sxs-lookup"><span data-stu-id="bcac9-103">This sample demonstrates how to create a set of activities that expose the regular expression functionality of the <xref:System.Text.RegularExpressions> namespace.</span></span> <span data-ttu-id="bcac9-104">Такие пользовательские действия можно использовать в приложении рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="bcac9-104">These custom activities can be used within a workflow application.</span></span> <span data-ttu-id="bcac9-105">Дополнительные сведения о регулярных выражениях см. в разделе [N:System.Text.RegularExpressions](http://go.microsoft.com/fwlink/?LinkId=150434) пространства имен.</span><span class="sxs-lookup"><span data-stu-id="bcac9-105">For more information about regular expressions, see [N:System.Text.RegularExpressions](http://go.microsoft.com/fwlink/?LinkId=150434) Namespace.</span></span>  
  
 <span data-ttu-id="bcac9-106">В следующей таблице приведены сведения о пользовательских действиях, выполняемых в данном образце.</span><span class="sxs-lookup"><span data-stu-id="bcac9-106">The following table details the custom activities in this sample.</span></span>  
  
|<span data-ttu-id="bcac9-107">Действие</span><span class="sxs-lookup"><span data-stu-id="bcac9-107">Activity</span></span>|<span data-ttu-id="bcac9-108">Описание</span><span class="sxs-lookup"><span data-stu-id="bcac9-108">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="bcac9-109">IsMatch</span><span class="sxs-lookup"><span data-stu-id="bcac9-109">IsMatch</span></span>|<span data-ttu-id="bcac9-110">Указывает, были ли найдены совпадения во входной строке в результате выполнения регулярного выражения.</span><span class="sxs-lookup"><span data-stu-id="bcac9-110">Specifies whether the regular expression found a match in the input string.</span></span>|  
|<span data-ttu-id="bcac9-111">Соответствия</span><span class="sxs-lookup"><span data-stu-id="bcac9-111">Matches</span></span>|<span data-ttu-id="bcac9-112">Выполняет поиск всех вхождений регулярного выражения во входной строке и возвращает все найденные совпадения.</span><span class="sxs-lookup"><span data-stu-id="bcac9-112">Searches an input string for all occurrences of a regular expression and returns all the successful matches.</span></span>|  
|<span data-ttu-id="bcac9-113">Заменить</span><span class="sxs-lookup"><span data-stu-id="bcac9-113">Replace</span></span>|<span data-ttu-id="bcac9-114">Заменяет в указанной входной строке все строки, совпадающие с шаблоном регулярного выражения, на указанную строку замены.</span><span class="sxs-lookup"><span data-stu-id="bcac9-114">Within a specified input string, replaces strings that match a regular expression pattern with a specified replacement string.</span></span>|  
  
## <a name="ismatch"></a><span data-ttu-id="bcac9-115">IsMatch</span><span class="sxs-lookup"><span data-stu-id="bcac9-115">IsMatch</span></span>  
 <span data-ttu-id="bcac9-116">Пользовательское действие `IsMatch` возвращает `true`, если свойство строки `Input` совпадает с регулярным выражением, указанным в свойстве `Pattern`.</span><span class="sxs-lookup"><span data-stu-id="bcac9-116">The `IsMatch` custom activity returns `true` if the `Input` string property finds a match in the regular expression specified in the `Pattern` property.</span></span> <span data-ttu-id="bcac9-117">Действие является производным от <xref:System.Activities.CodeActivity%601>, и в методе <xref:System.Activities.CodeActivity%601.Execute%2A> вызывается метод <xref:System.Text.RegularExpressions.Regex.IsMatch%2A>.</span><span class="sxs-lookup"><span data-stu-id="bcac9-117">The activity derives from <xref:System.Activities.CodeActivity%601> and within the <xref:System.Activities.CodeActivity%601.Execute%2A> method calls the <xref:System.Text.RegularExpressions.Regex.IsMatch%2A> method.</span></span>  
  
 <span data-ttu-id="bcac9-118">В следующей таблице описываются свойства и возвращаемое значение для настраиваемого действия `IsMatch`.</span><span class="sxs-lookup"><span data-stu-id="bcac9-118">The following table describes the properties and return value for the `IsMatch` custom activity.</span></span>  
  
|<span data-ttu-id="bcac9-119">Свойство или возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="bcac9-119">Property or Return Value</span></span>|<span data-ttu-id="bcac9-120">Описание</span><span class="sxs-lookup"><span data-stu-id="bcac9-120">Description</span></span>|  
|------------------------------|-----------------|  
|<span data-ttu-id="bcac9-121">Шаблон (обязательно)</span><span class="sxs-lookup"><span data-stu-id="bcac9-121">Pattern (required)</span></span>|<span data-ttu-id="bcac9-122">Регулярное выражение, по которому выполняется поиск.</span><span class="sxs-lookup"><span data-stu-id="bcac9-122">The regular expression to search with.</span></span>|  
|<span data-ttu-id="bcac9-123">Входные данные (обязательно)</span><span class="sxs-lookup"><span data-stu-id="bcac9-123">Input (required)</span></span>|<span data-ttu-id="bcac9-124">Входная строка для поиска.</span><span class="sxs-lookup"><span data-stu-id="bcac9-124">The input string to search.</span></span>|  
|<span data-ttu-id="bcac9-125">RegexOptions</span><span class="sxs-lookup"><span data-stu-id="bcac9-125">RegexOptions</span></span>|<span data-ttu-id="bcac9-126">Побитовое сочетание OR [RegexOptions](http://go.microsoft.com/fwlink/?LinkId=150446) значений перечисления.</span><span class="sxs-lookup"><span data-stu-id="bcac9-126">Bitwise OR combination of [RegexOptions](http://go.microsoft.com/fwlink/?LinkId=150446) enumeration values.</span></span>|  
|<span data-ttu-id="bcac9-127">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="bcac9-127">Return value</span></span>|<span data-ttu-id="bcac9-128">`true`, если входная строка совпадает с указанным шаблоном. В противном случае `false`.</span><span class="sxs-lookup"><span data-stu-id="bcac9-128">`true` if the input finds a match in the provided pattern; otherwise `false`.</span></span>|  
  
 <span data-ttu-id="bcac9-129">В следующем примере кода показано использование настраиваемого действия `IsMatch`.</span><span class="sxs-lookup"><span data-stu-id="bcac9-129">The following code example demonstrates how to use the `IsMatch` custom activity.</span></span>  
  
```  
new IsMatch  
{  
    Pattern = new InArgument<string>( @"^-?\d+(\.\d{2})?$"),  
    Input = "20.00",  
};  
```  
  
## <a name="matches"></a><span data-ttu-id="bcac9-130">Соответствия</span><span class="sxs-lookup"><span data-stu-id="bcac9-130">Matches</span></span>  
 <span data-ttu-id="bcac9-131">Пользовательское действие `Matches` выполняет поиск всех вхождений регулярного выражения во входной строке и возвращает все найденные совпадения.</span><span class="sxs-lookup"><span data-stu-id="bcac9-131">The `Matches` custom activity searches an input string for all occurrences of a regular expression and returns all the successful matches.</span></span> <span data-ttu-id="bcac9-132">Действие является производным от <xref:System.Activities.CodeActivity%601>, и в методе <xref:System.Activities.CodeActivity%601.Execute%2A> вызывается метод <xref:System.Text.RegularExpressions.Regex.Matches%2A>.</span><span class="sxs-lookup"><span data-stu-id="bcac9-132">The activity derives from <xref:System.Activities.CodeActivity%601> and within the <xref:System.Activities.CodeActivity%601.Execute%2A> method calls the <xref:System.Text.RegularExpressions.Regex.Matches%2A> method.</span></span>  
  
 <span data-ttu-id="bcac9-133">В следующей таблице описываются свойства и возвращаемое значение для настраиваемого действия `IsMatch`.</span><span class="sxs-lookup"><span data-stu-id="bcac9-133">The following table describes the properties and return value for the `IsMatch` custom activity.</span></span>  
  
|<span data-ttu-id="bcac9-134">Свойство или возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="bcac9-134">Property or Return Value</span></span>|<span data-ttu-id="bcac9-135">Описание</span><span class="sxs-lookup"><span data-stu-id="bcac9-135">Description</span></span>|  
|------------------------------|-----------------|  
|<span data-ttu-id="bcac9-136">Шаблон (обязательно)</span><span class="sxs-lookup"><span data-stu-id="bcac9-136">Pattern (required)</span></span>|<span data-ttu-id="bcac9-137">Регулярное выражение, по которому выполняется поиск.</span><span class="sxs-lookup"><span data-stu-id="bcac9-137">The regular expression to search with.</span></span>|  
|<span data-ttu-id="bcac9-138">Входные данные (обязательно)</span><span class="sxs-lookup"><span data-stu-id="bcac9-138">Input (required)</span></span>|<span data-ttu-id="bcac9-139">Входная строка для поиска.</span><span class="sxs-lookup"><span data-stu-id="bcac9-139">The input string to search.</span></span>|  
|<span data-ttu-id="bcac9-140">RegexOptions</span><span class="sxs-lookup"><span data-stu-id="bcac9-140">RegexOptions</span></span>|<span data-ttu-id="bcac9-141">Побитовое сочетание OR [RegexOptions](http://go.microsoft.com/fwlink/?LinkId=150446) значений перечисления.</span><span class="sxs-lookup"><span data-stu-id="bcac9-141">Bitwise OR combination of [RegexOptions](http://go.microsoft.com/fwlink/?LinkId=150446) enumeration values.</span></span>|  
|<span data-ttu-id="bcac9-142">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="bcac9-142">Return Value</span></span>|<span data-ttu-id="bcac9-143">Объект <xref:System.Text.RegularExpressions.MatchCollection>, содержащий коллекцию успешных совпадений.</span><span class="sxs-lookup"><span data-stu-id="bcac9-143">A <xref:System.Text.RegularExpressions.MatchCollection> that contains the collection of successful matches.</span></span>|  
  
 <span data-ttu-id="bcac9-144">В следующем примере кода показано использование настраиваемого действия `Matches`.</span><span class="sxs-lookup"><span data-stu-id="bcac9-144">The following code example demonstrates how to use the `Matches` custom activity.</span></span>  
  
```  
new Matches  
{  
    Pattern = @"\b(?<word>\w+)\s+(\k<word>)\b",  
    Input = "The quick brown fox  fox jumped over over the lazy dog dog.",  
};  
```  
  
## <a name="replace"></a><span data-ttu-id="bcac9-145">Заменить</span><span class="sxs-lookup"><span data-stu-id="bcac9-145">Replace</span></span>  
 <span data-ttu-id="bcac9-146">Пользовательское действие `Replace` выполняет поиск во входной строке и заменяет в этой строке все строки, совпадающие с указанным регулярным выражением.</span><span class="sxs-lookup"><span data-stu-id="bcac9-146">The `Replace` custom activity searches an input string and replaces all strings that match a specified regular expression with a string.</span></span> <span data-ttu-id="bcac9-147">Действие является производным от <xref:System.Activities.CodeActivity%601>, и в методе <xref:System.Activities.CodeActivity%601.Execute%2A> вызывается метод <xref:System.Text.RegularExpressions.Regex.Replace%2A>.</span><span class="sxs-lookup"><span data-stu-id="bcac9-147">The activity derives from <xref:System.Activities.CodeActivity%601> and within the <xref:System.Activities.CodeActivity%601.Execute%2A> method calls the <xref:System.Text.RegularExpressions.Regex.Replace%2A> method.</span></span>  
  
 <span data-ttu-id="bcac9-148">В следующей таблице описываются свойства и возвращаемое значение для настраиваемого действия `Replace`.</span><span class="sxs-lookup"><span data-stu-id="bcac9-148">The following table describes the properties and return value for the `Replace` custom activity.</span></span>  
  
|<span data-ttu-id="bcac9-149">Свойство или возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="bcac9-149">Property or Return Value</span></span>|<span data-ttu-id="bcac9-150">Описание</span><span class="sxs-lookup"><span data-stu-id="bcac9-150">Description</span></span>|  
|------------------------------|-----------------|  
|<span data-ttu-id="bcac9-151">Шаблон (обязательно)</span><span class="sxs-lookup"><span data-stu-id="bcac9-151">Pattern (required)</span></span>|<span data-ttu-id="bcac9-152">Регулярное выражение, по которому выполняется поиск.</span><span class="sxs-lookup"><span data-stu-id="bcac9-152">The regular expression to search with.</span></span>|  
|<span data-ttu-id="bcac9-153">Входные данные (обязательно)</span><span class="sxs-lookup"><span data-stu-id="bcac9-153">Input (required)</span></span>|<span data-ttu-id="bcac9-154">Входная строка для поиска.</span><span class="sxs-lookup"><span data-stu-id="bcac9-154">The input string to search.</span></span>|  
|<span data-ttu-id="bcac9-155">Замена</span><span class="sxs-lookup"><span data-stu-id="bcac9-155">Replacement</span></span>|<span data-ttu-id="bcac9-156">Строка замены.</span><span class="sxs-lookup"><span data-stu-id="bcac9-156">The replacement string.</span></span><br /><br /> <span data-ttu-id="bcac9-157">Если задано свойство `Replacement`, то свойство `MatchEvaluator` не учитывается.</span><span class="sxs-lookup"><span data-stu-id="bcac9-157">If a `Replacement` is specified, then the `MatchEvaluator` property is ignored.</span></span> <span data-ttu-id="bcac9-158">Необходимо задать либо свойство `Replacement`, либо свойство `MatchEvaluator`.</span><span class="sxs-lookup"><span data-stu-id="bcac9-158">Either the `Replacement` or `MatchEvaluator` property must be set.</span></span>|  
|<span data-ttu-id="bcac9-159">MatchEvaluator</span><span class="sxs-lookup"><span data-stu-id="bcac9-159">MatchEvaluator</span></span>|<span data-ttu-id="bcac9-160">Пользовательский метод, анализирующий каждое совпадение и возвращающий либо исходную строку с совпадениями, либо строку замены.</span><span class="sxs-lookup"><span data-stu-id="bcac9-160">A custom method that examines each match and returns either the original matched string or a replacement string.</span></span><br /><br /> <span data-ttu-id="bcac9-161">Если задано свойство `Replacement`, то свойство `MatchEvaluator` не учитывается.</span><span class="sxs-lookup"><span data-stu-id="bcac9-161">If a `Replacement` is specified, then the `MatchEvaluator` property is ignored.</span></span> <span data-ttu-id="bcac9-162">Необходимо задать либо свойство `Replacement`, либо свойство `MatchEvaluator`.</span><span class="sxs-lookup"><span data-stu-id="bcac9-162">Either the `Replacement` or `MatchEvaluator` property must be set.</span></span>|  
|<span data-ttu-id="bcac9-163">RegexOptions</span><span class="sxs-lookup"><span data-stu-id="bcac9-163">RegexOptions</span></span>|<span data-ttu-id="bcac9-164">Побитовое сочетание OR [RegexOptions](http://go.microsoft.com/fwlink/?LinkId=150446) значений перечисления.</span><span class="sxs-lookup"><span data-stu-id="bcac9-164">Bitwise OR combination of [RegexOptions](http://go.microsoft.com/fwlink/?LinkId=150446) enumeration values.</span></span>|  
|<span data-ttu-id="bcac9-165">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="bcac9-165">Return Value</span></span>|<span data-ttu-id="bcac9-166">Объект <xref:System.Text.RegularExpressions.MatchCollection>, содержащий коллекцию успешных совпадений.</span><span class="sxs-lookup"><span data-stu-id="bcac9-166">A <xref:System.Text.RegularExpressions.MatchCollection> that contains the collection of successful matches.</span></span>|  
  
 <span data-ttu-id="bcac9-167">В следующем примере кода показано использование настраиваемого действия `Replace`.</span><span class="sxs-lookup"><span data-stu-id="bcac9-167">The following code example demonstrates how to use the `Replace` custom activity.</span></span>  
  
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
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="bcac9-168">Использование этого образца</span><span class="sxs-lookup"><span data-stu-id="bcac9-168">To use this sample</span></span>  
  
1.  <span data-ttu-id="bcac9-169">Откройте файл решения RegexActivities.sln в среде [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bcac9-169">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the RegexActivities.sln solution file.</span></span>  
  
2.  <span data-ttu-id="bcac9-170">Для построения решения нажмите CTRL+SHIFT+B.</span><span class="sxs-lookup"><span data-stu-id="bcac9-170">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="bcac9-171">Чтобы запустить решение, нажмите клавиши CTRL+F5.</span><span class="sxs-lookup"><span data-stu-id="bcac9-171">To run the solution, press CTRL+F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="bcac9-172">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="bcac9-172">The samples may already be installed on your machine.</span></span> <span data-ttu-id="bcac9-173">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="bcac9-173">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="bcac9-174">Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) Чтобы загрузить все [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] образцов.</span><span class="sxs-lookup"><span data-stu-id="bcac9-174">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="bcac9-175">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="bcac9-175">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\Regex`
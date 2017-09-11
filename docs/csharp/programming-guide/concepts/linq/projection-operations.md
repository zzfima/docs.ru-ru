---
title: "Операции проекции (C#)"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 98df573a-aad9-4b8c-9a71-844be2c4fb41
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 2b95072bf6e53ef090a7a7b398fa873bb0bf5b46
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="projection-operations-c"></a><span data-ttu-id="2fdfc-102">Операции проекции (C#)</span><span class="sxs-lookup"><span data-stu-id="2fdfc-102">Projection Operations (C#)</span></span>
<span data-ttu-id="2fdfc-103">Проекцией называют операцию преобразования объекта в новую форму, которая часто состоит только из тех его свойств, которые будут использоваться впоследствии.</span><span class="sxs-lookup"><span data-stu-id="2fdfc-103">Projection refers to the operation of transforming an object into a new form that often consists only of those properties that will be subsequently used.</span></span> <span data-ttu-id="2fdfc-104">С помощью проекции можно создать новый тип, построенный из каждого объекта.</span><span class="sxs-lookup"><span data-stu-id="2fdfc-104">By using projection, you can construct a new type that is built from each object.</span></span> <span data-ttu-id="2fdfc-105">Вы можете проецировать свойство и выполнять над ним математические функции.</span><span class="sxs-lookup"><span data-stu-id="2fdfc-105">You can project a property and perform a mathematical function on it.</span></span> <span data-ttu-id="2fdfc-106">Также можно проецировать исходный объект, не изменяя его.</span><span class="sxs-lookup"><span data-stu-id="2fdfc-106">You can also project the original object without changing it.</span></span>  
  
 <span data-ttu-id="2fdfc-107">Методы стандартных операторов запросов, которые выполняют проецирование, перечислены в следующем разделе.</span><span class="sxs-lookup"><span data-stu-id="2fdfc-107">The standard query operator methods that perform projection are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="2fdfc-108">Методы</span><span class="sxs-lookup"><span data-stu-id="2fdfc-108">Methods</span></span>  
  
|<span data-ttu-id="2fdfc-109">Имя метода</span><span class="sxs-lookup"><span data-stu-id="2fdfc-109">Method Name</span></span>|<span data-ttu-id="2fdfc-110">Описание</span><span class="sxs-lookup"><span data-stu-id="2fdfc-110">Description</span></span>|<span data-ttu-id="2fdfc-111">Синтаксис выражения запроса C#</span><span class="sxs-lookup"><span data-stu-id="2fdfc-111">C# Query Expression Syntax</span></span>|<span data-ttu-id="2fdfc-112">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="2fdfc-112">More Information</span></span>|  
|-----------------|-----------------|---------------------------------|----------------------|  
|<span data-ttu-id="2fdfc-113">Выбрать</span><span class="sxs-lookup"><span data-stu-id="2fdfc-113">Select</span></span>|<span data-ttu-id="2fdfc-114">Проецирует значения, основанные на функции преобразования.</span><span class="sxs-lookup"><span data-stu-id="2fdfc-114">Projects values that are based on a transform function.</span></span>|`select`|<xref:System.Linq.Enumerable.Select%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.Select%2A?displayProperty=fullName>|  
|<span data-ttu-id="2fdfc-115">SelectMany</span><span class="sxs-lookup"><span data-stu-id="2fdfc-115">SelectMany</span></span>|<span data-ttu-id="2fdfc-116">Проецирует последовательности значений, основанных на функции преобразования, а затем выравнивает их в одну последовательность.</span><span class="sxs-lookup"><span data-stu-id="2fdfc-116">Projects sequences of values that are based on a transform function and then flattens them into one sequence.</span></span>|<span data-ttu-id="2fdfc-117">Использование нескольких предложений `from`</span><span class="sxs-lookup"><span data-stu-id="2fdfc-117">Use multiple `from` clauses</span></span>|<xref:System.Linq.Enumerable.SelectMany%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.SelectMany%2A?displayProperty=fullName>|  
  
## <a name="query-expression-syntax-examples"></a><span data-ttu-id="2fdfc-118">Примеры синтаксиса выражений запросов</span><span class="sxs-lookup"><span data-stu-id="2fdfc-118">Query Expression Syntax Examples</span></span>  
  
### <a name="select"></a><span data-ttu-id="2fdfc-119">Выбрать</span><span class="sxs-lookup"><span data-stu-id="2fdfc-119">Select</span></span>  
 <span data-ttu-id="2fdfc-120">В приведенном ниже примере предложение `select` используется для проецирования первой буквы из каждой строки в списке строк.</span><span class="sxs-lookup"><span data-stu-id="2fdfc-120">The following example uses the `select` clause to project the first letter from each string in a list of strings.</span></span>  
  
```csharp  
List<string> words = new List<string>() { "an", "apple", "a", "day" };  
  
var query = from word in words  
            select word.Substring(0, 1);  
  
foreach (string s in query)  
    Console.WriteLine(s);  
  
/* This code produces the following output:  
  
    a  
    a  
    a  
    d  
*/  
```  
  
### <a name="selectmany"></a><span data-ttu-id="2fdfc-121">SelectMany</span><span class="sxs-lookup"><span data-stu-id="2fdfc-121">SelectMany</span></span>  
 <span data-ttu-id="2fdfc-122">В приведенном ниже примере несколько предложений `from` используются для проецирования каждого слова из каждой строки в списке строк.</span><span class="sxs-lookup"><span data-stu-id="2fdfc-122">The following example uses multiple `from` clauses  to project each word from each string in a list of strings.</span></span>  
  
```csharp  
List<string> phrases = new List<string>() { "an apple a day", "the quick brown fox" };  
  
var query = from phrase in phrases  
            from word in phrase.Split(' ')  
            select word;  
  
foreach (string s in query)  
    Console.WriteLine(s);  
  
/* This code produces the following output:  
  
    an  
    apple  
    a  
    day  
    the  
    quick  
    brown  
    fox  
*/  
```  
  
## <a name="select-versus-selectmany"></a><span data-ttu-id="2fdfc-123">Select или SelectMany</span><span class="sxs-lookup"><span data-stu-id="2fdfc-123">Select versus SelectMany</span></span>  
 <span data-ttu-id="2fdfc-124">Задача обоих методов `Select()` и `SelectMany()` заключается в создании результирующего значения (или значений) из исходных значений.</span><span class="sxs-lookup"><span data-stu-id="2fdfc-124">The work of both `Select()` and `SelectMany()` is to produce a result value (or values) from source values.</span></span> <span data-ttu-id="2fdfc-125">`Select()` создает один результат для каждого исходного значения.</span><span class="sxs-lookup"><span data-stu-id="2fdfc-125">`Select()` produces one result value for every source value.</span></span> <span data-ttu-id="2fdfc-126">Таким образом, общий результат является коллекцией, имеющей то же количество элементов, что и исходная коллекция.</span><span class="sxs-lookup"><span data-stu-id="2fdfc-126">The overall result is therefore a collection that has the same number of elements as the source collection.</span></span> <span data-ttu-id="2fdfc-127">`SelectMany()`, напротив, создает общий результат, содержащий соединенные подколлекции из каждого исходного значения.</span><span class="sxs-lookup"><span data-stu-id="2fdfc-127">In contrast, `SelectMany()` produces a single overall result that contains concatenated sub-collections from each source value.</span></span> <span data-ttu-id="2fdfc-128">Функция преобразования, которая передается в качестве аргумента методу `SelectMany()`, должна возвращать перечисляемую последовательность значений для каждого исходного значения.</span><span class="sxs-lookup"><span data-stu-id="2fdfc-128">The transform function that is passed as an argument to `SelectMany()` must return an enumerable sequence of values for each source value.</span></span> <span data-ttu-id="2fdfc-129">Эти перечисляемые последовательности затем объединяются `SelectMany()` для создания одной большой последовательности.</span><span class="sxs-lookup"><span data-stu-id="2fdfc-129">These enumerable sequences are then concatenated by `SelectMany()` to create one large sequence.</span></span>  
  
 <span data-ttu-id="2fdfc-130">На двух рисунках, приведенных ниже, показаны принципиальные различия между работой этих двух методов.</span><span class="sxs-lookup"><span data-stu-id="2fdfc-130">The following two illustrations show the conceptual difference between the actions of these two methods.</span></span> <span data-ttu-id="2fdfc-131">В обоих случаях предполагается, что функция выбора (преобразования) выбирает массив цветов из каждого исходного значения.</span><span class="sxs-lookup"><span data-stu-id="2fdfc-131">In each case, assume that the selector (transform) function selects the array of flowers from each source value.</span></span>  
  
 <span data-ttu-id="2fdfc-132">На этом рисунке представлено, как `Select()` возвращает коллекцию, которая имеет то же количество элементов, что и исходная коллекция.</span><span class="sxs-lookup"><span data-stu-id="2fdfc-132">This illustration depicts how `Select()` returns a collection that has the same number of elements as the source collection.</span></span>  
  
 <span data-ttu-id="2fdfc-133">![Концептуальная иллюстрация действия Select&#40;&#41;](../../../../csharp/programming-guide/concepts/linq/media/selectaction.png "SelectAction")</span><span class="sxs-lookup"><span data-stu-id="2fdfc-133">![Conceptual illustration of the action of Select&#40;&#41;](../../../../csharp/programming-guide/concepts/linq/media/selectaction.png "SelectAction")</span></span>  
  
 <span data-ttu-id="2fdfc-134">На этом рисунке показано, как `SelectMany()` объединяет промежуточные последовательности массивов в один конечный результат, содержащий все значения из промежуточных массивов.</span><span class="sxs-lookup"><span data-stu-id="2fdfc-134">This illustration depicts how `SelectMany()` concatenates the intermediate sequence of arrays into one final result value that contains each value from each intermediate array.</span></span>  
  
 <span data-ttu-id="2fdfc-135">![Схема работы SelectMany&#40;&#41;.](../../../../csharp/programming-guide/concepts/linq/media/selectmany.png "SelectMany")</span><span class="sxs-lookup"><span data-stu-id="2fdfc-135">![Graphic showing the action of SelectMany&#40;&#41;.](../../../../csharp/programming-guide/concepts/linq/media/selectmany.png "SelectMany")</span></span>  
  
### <a name="code-example"></a><span data-ttu-id="2fdfc-136">Пример кода</span><span class="sxs-lookup"><span data-stu-id="2fdfc-136">Code Example</span></span>  
 <span data-ttu-id="2fdfc-137">В приведенном ниже примере сравнивается действие `Select()` и `SelectMany()`.</span><span class="sxs-lookup"><span data-stu-id="2fdfc-137">The following example compares the behavior of `Select()` and `SelectMany()`.</span></span> <span data-ttu-id="2fdfc-138">Код создает "букет" из цветов путем получения первых двух элементов из каждого списка названий цветов в исходной коллекции.</span><span class="sxs-lookup"><span data-stu-id="2fdfc-138">The code creates a "bouquet" of flowers by taking the first two items from each list of flower names in the source collection.</span></span> <span data-ttu-id="2fdfc-139">В этом примере отдельное значение, используемое функцией преобразования <xref:System.Linq.Enumerable.Select%60%602%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2C%60%601%7D%29>, представляет собой коллекцию значений.</span><span class="sxs-lookup"><span data-stu-id="2fdfc-139">In this example, the "single value" that the transform function <xref:System.Linq.Enumerable.Select%60%602%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2C%60%601%7D%29> uses is itself a collection of values.</span></span> <span data-ttu-id="2fdfc-140">Этот требует дополнительного цикла `foreach` для перечисления каждой строки в каждой подпоследовательности.</span><span class="sxs-lookup"><span data-stu-id="2fdfc-140">This requires the extra `foreach` loop in order to enumerate each string in each sub-sequence.</span></span>  
  
```csharp  
class Bouquet  
{  
    public List<string> Flowers { get; set; }  
}  
  
static void SelectVsSelectMany()  
{  
    List<Bouquet> bouquets = new List<Bouquet>() {  
        new Bouquet { Flowers = new List<string> { "sunflower", "daisy", "daffodil", "larkspur" }},  
        new Bouquet{ Flowers = new List<string> { "tulip", "rose", "orchid" }},  
        new Bouquet{ Flowers = new List<string> { "gladiolis", "lily", "snapdragon", "aster", "protea" }},  
        new Bouquet{ Flowers = new List<string> { "larkspur", "lilac", "iris", "dahlia" }}  
    };  
  
    // *********** Select ***********              
    IEnumerable<List<string>> query1 = bouquets.Select(bq => bq.Flowers);  
  
    // ********* SelectMany *********  
    IEnumerable<string> query2 = bouquets.SelectMany(bq => bq.Flowers);  
  
    Console.WriteLine("Results by using Select():");  
    // Note the extra foreach loop here.  
    foreach (IEnumerable<String> collection in query1)  
        foreach (string item in collection)  
            Console.WriteLine(item);  
  
    Console.WriteLine("\nResults by using SelectMany():");  
    foreach (string item in query2)  
        Console.WriteLine(item);  
  
    /* This code produces the following output:  
  
       Results by using Select():  
        sunflower  
        daisy  
        daffodil  
        larkspur  
        tulip  
        rose  
        orchid  
        gladiolis  
        lily  
        snapdragon  
        aster  
        protea  
        larkspur  
        lilac  
        iris  
        dahlia  
  
       Results by using SelectMany():  
        sunflower  
        daisy  
        daffodil  
        larkspur  
        tulip  
        rose  
        orchid  
        gladiolis  
        lily  
        snapdragon  
        aster  
        protea  
        larkspur  
        lilac  
        iris  
        dahlia  
    */  
  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="2fdfc-141">См. также</span><span class="sxs-lookup"><span data-stu-id="2fdfc-141">See Also</span></span>  
 <span data-ttu-id="2fdfc-142"><xref:System.Linq></span><span class="sxs-lookup"><span data-stu-id="2fdfc-142"><xref:System.Linq></span></span>   
 <span data-ttu-id="2fdfc-143">[Общие сведения о стандартных операторах запроса (C#)](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md) </span><span class="sxs-lookup"><span data-stu-id="2fdfc-143">[Standard Query Operators Overview (C#)](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md) </span></span>  
 <span data-ttu-id="2fdfc-144">[Предложение select](../../../../csharp/language-reference/keywords/select-clause.md) </span><span class="sxs-lookup"><span data-stu-id="2fdfc-144">[select clause](../../../../csharp/language-reference/keywords/select-clause.md) </span></span>  
 <span data-ttu-id="2fdfc-145">[Практическое руководство. Заполнение коллекций объектов из нескольких источников (LINQ) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-populate-object-collections-from-multiple-sources-linq.md) </span><span class="sxs-lookup"><span data-stu-id="2fdfc-145">[How to: Populate Object Collections from Multiple Sources (LINQ) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-populate-object-collections-from-multiple-sources-linq.md) </span></span>  
 [<span data-ttu-id="2fdfc-146">Практическое руководство. Разделение файла на несколько файлов с помощью групп (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="2fdfc-146">How to: Split a File Into Many Files by Using Groups (LINQ) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-split-a-file-into-many-files-by-using-groups-linq.md)


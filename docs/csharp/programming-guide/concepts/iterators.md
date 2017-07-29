---
title: "Итераторы (C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: c93f6dd4-e72a-4a06-be1c-a98b3255b734
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
ms.openlocfilehash: 5d5543a48d0c835f5270067d1e5ad514c28842b2
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="iterators-c"></a>Итераторы (C#)
*Итератор* можно использовать для прохода по коллекции, такой как список или массив.  
  
 Метод итератора или метод доступа `get` выполняет настраиваемую итерацию по коллекции. Метод итератора использует оператор [yield return](../../../csharp/language-reference/keywords/yield.md) для поочередного возврата каждого элемента. При достижении оператора `yield return` текущее расположение в коде запоминается. При следующем вызове функции итератора выполнение возобновляется с этого места.  
  
 Итератор используется из клиентского кода с помощью оператора [foreach](../../../csharp/language-reference/keywords/foreach-in.md) или с помощью запроса LINQ.  
  
 В приведенном ниже примере первая итерация цикла `foreach` приводит к вызову метода итератора `SomeNumbers`, пока не будет достигнут первый оператор `yield return`. Эта итерация возвращает значение 3. Текущее расположение в методе итератора сохраняется. В следующей итерации цикла выполнение метода итератора возобновляется с того же места и снова приостанавливается при достижении оператора `yield return`. Эта итерация возвращает значение 5. Текущее расположение в методе итератора снова сохраняется. Цикл завершается при достижении конца метода итератора.  
  
```csharp  
static void Main()  
{  
    foreach (int number in SomeNumbers())  
    {  
        Console.Write(number.ToString() + " ");  
    }  
    // Output: 3 5 8  
    Console.ReadKey();  
}  
  
public static System.Collections.IEnumerable SomeNumbers()  
{  
    yield return 3;  
    yield return 5;  
    yield return 8;  
}  
```  
  
 Типом возвращаемого метода итератора или метода доступа `get` может быть <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator> или <xref:System.Collections.Generic.IEnumerator%601>.  
  
 Для завершения итерации можно использовать оператор `yield break`.  
  
 Итераторы были введены в C# в Visual Studio 2005.  
  
 **Содержание раздела**  
  
-   [Простой итератор](#BKMK_SimpleIterator)  
  
-   [Создание класса коллекции](#BKMK_CollectionClass)  
  
-   [Использование итераторов с универсальным списком](#BKMK_GenericList)  
  
-   [Сведения о синтаксисе](#BKMK_SyntaxInformation)  
  
-   [Техническая реализация](#BKMK_Technical)  
  
-   [Использование итераторов](#BKMK_UseOfIterators)  
  
> [!NOTE]
>  Все примеры в этом разделе, кроме примера простого итератора, включают директивы [using](../../../csharp/language-reference/keywords/using-directive.md) для пространств имен `System.Collections` и `System.Collections.Generic`.  
  
##  <a name="BKMK_SimpleIterator"></a> Простой итератор  
 В следующем примере имеется один оператор `yield return`, который находится внутри цикла [for](../../../csharp/language-reference/keywords/for.md). В методе `Main` каждая итерация оператора `foreach` создает вызов функции итератора, которая выполняет следующий оператор `yield return`.  
  
```csharp  
static void Main()  
{  
    foreach (int number in EvenSequence(5, 18))  
    {  
        Console.Write(number.ToString() + " ");  
    }  
    // Output: 6 8 10 12 14 16 18  
    Console.ReadKey();  
}  
  
public static System.Collections.Generic.IEnumerable<int>  
    EvenSequence(int firstNumber, int lastNumber)  
{  
    // Yield even numbers in the range.  
    for (int number = firstNumber; number <= lastNumber; number++)  
    {  
        if (number % 2 == 0)  
        {  
            yield return number;  
        }  
    }  
}  
```  
  
##  <a name="BKMK_CollectionClass"></a> Создание класса коллекции  
 В следующем примере класс `DaysOfTheWeek` реализует интерфейс <xref:System.Collections.IEnumerable>, которому требуется метод <xref:System.Collections.IEnumerable.GetEnumerator%2A>. Компилятор неявно вызывает метод `GetEnumerator`, который возвращает <xref:System.Collections.IEnumerator>.  
  
 Метод `GetEnumerator` возвращает каждую строку поочередно с помощью оператора `yield return`.  
  
```csharp  
static void Main()  
{  
    DaysOfTheWeek days = new DaysOfTheWeek();  
  
    foreach (string day in days)  
    {  
        Console.Write(day + " ");  
    }  
    // Output: Sun Mon Tue Wed Thu Fri Sat  
    Console.ReadKey();  
}  
  
public class DaysOfTheWeek : IEnumerable  
{  
    private string[] days = { "Sun", "Mon", "Tue", "Wed", "Thu", "Fri", "Sat" };  
  
    public IEnumerator GetEnumerator()  
    {  
        for (int index = 0; index < days.Length; index++)  
        {  
            // Yield each day of the week.  
            yield return days[index];  
        }  
    }  
}  
```  
  
 В приведенном ниже примере создается класс `Zoo`, содержащий коллекцию животных.  
  
 Оператор `foreach`, который обращается к экземпляру класса (`theZoo`), неявно вызывает метод `GetEnumerator`. Операторы `foreach`, которые обращаются к свойствам `Birds` и `Mammals`, используют метод итератора с именем `AnimalsForType`.  
  
```csharp  
static void Main()  
{  
    Zoo theZoo = new Zoo();  
  
    theZoo.AddMammal("Whale");  
    theZoo.AddMammal("Rhinoceros");  
    theZoo.AddBird("Penguin");  
    theZoo.AddBird("Warbler");  
  
    foreach (string name in theZoo)  
    {  
        Console.Write(name + " ");  
    }  
    Console.WriteLine();  
    // Output: Whale Rhinoceros Penguin Warbler  
  
    foreach (string name in theZoo.Birds)  
    {  
        Console.Write(name + " ");  
    }  
    Console.WriteLine();  
    // Output: Penguin Warbler  
  
    foreach (string name in theZoo.Mammals)  
    {  
        Console.Write(name + " ");  
    }  
    Console.WriteLine();  
    // Output: Whale Rhinoceros  
  
    Console.ReadKey();  
}  
  
public class Zoo : IEnumerable  
{  
    // Private members.  
    private List<Animal> animals = new List<Animal>();  
  
    // Public methods.  
    public void AddMammal(string name)  
    {  
        animals.Add(new Animal { Name = name, Type = Animal.TypeEnum.Mammal });  
    }  
  
    public void AddBird(string name)  
    {  
        animals.Add(new Animal { Name = name, Type = Animal.TypeEnum.Bird });  
    }  
  
    public IEnumerator GetEnumerator()  
    {  
        foreach (Animal theAnimal in animals)  
        {  
            yield return theAnimal.Name;  
        }  
    }  
  
    // Public members.  
    public IEnumerable Mammals  
    {  
        get { return AnimalsForType(Animal.TypeEnum.Mammal); }  
    }  
  
    public IEnumerable Birds  
    {  
        get { return AnimalsForType(Animal.TypeEnum.Bird); }  
    }  
  
    // Private methods.  
    private IEnumerable AnimalsForType(Animal.TypeEnum type)  
    {  
        foreach (Animal theAnimal in animals)  
        {  
            if (theAnimal.Type == type)  
            {  
                yield return theAnimal.Name;  
            }  
        }  
    }  
  
    // Private class.  
    private class Animal  
    {  
        public enum TypeEnum { Bird, Mammal }  
  
        public string Name { get; set; }  
        public TypeEnum Type { get; set; }  
    }  
}  
```  
  
##  <a name="BKMK_GenericList"></a> Использование итераторов с универсальным списком  
 В следующем примере универсальный класс `Stack(Of T)` также реализует универсальный интерфейс <xref:System.Collections.Generic.IEnumerable%601>. Метод `Push` присваивает значения массиву типа `T`. Метод <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A> возвращает массив значений с помощью оператора `yield return`.  
  
 Помимо универсального метода <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A> должен быть реализован и неуниверсальный метод <xref:System.Collections.IEnumerable.GetEnumerator%2A>. Это связано с тем, что <xref:System.Collections.Generic.IEnumerable%601> наследуется от <xref:System.Collections.IEnumerable>. Неуниверсальная реализация подчиняется универсальной реализации.  
  
 В этом примере используются именованные итераторы для поддержки различных способов итерации по одной и той же коллекции данных. Эти именованные итераторы являются свойствами `TopToBottom` и `BottomToTop` и методом `TopN`.  
  
 Свойство `BottomToTop` использует итератор в методе доступа `get`.  
  
```csharp  
static void Main()  
{  
    Stack<int> theStack = new Stack<int>();  
  
    //  Add items to the stack.  
    for (int number = 0; number <= 9; number++)  
    {  
        theStack.Push(number);  
    }  
  
    // Retrieve items from the stack.  
    // foreach is allowed because theStack implements  
    // IEnumerable<int>.  
    foreach (int number in theStack)  
    {  
        Console.Write("{0} ", number);  
    }  
    Console.WriteLine();  
    // Output: 9 8 7 6 5 4 3 2 1 0  
  
    // foreach is allowed, because theStack.TopToBottom  
    // returns IEnumerable(Of Integer).  
    foreach (int number in theStack.TopToBottom)  
    {  
        Console.Write("{0} ", number);  
    }  
    Console.WriteLine();  
    // Output: 9 8 7 6 5 4 3 2 1 0  
  
    foreach (int number in theStack.BottomToTop)  
    {  
        Console.Write("{0} ", number);  
    }  
    Console.WriteLine();  
    // Output: 0 1 2 3 4 5 6 7 8 9  
  
    foreach (int number in theStack.TopN(7))  
    {  
        Console.Write("{0} ", number);  
    }  
    Console.WriteLine();  
    // Output: 9 8 7 6 5 4 3  
  
    Console.ReadKey();  
}  
  
public class Stack<T> : IEnumerable<T>  
{  
    private T[] values = new T[100];  
    private int top = 0;  
  
    public void Push(T t)  
    {  
        values[top] = t;  
        top++;  
    }  
    public T Pop()  
    {  
        top--;  
        return values[top];  
    }  
  
    // This method implements the GetEnumerator method. It allows  
    // an instance of the class to be used in a foreach statement.  
    public IEnumerator<T> GetEnumerator()  
    {  
        for (int index = top - 1; index >= 0; index--)  
        {  
            yield return values[index];  
        }  
    }  
  
    IEnumerator IEnumerable.GetEnumerator()  
    {  
        return GetEnumerator();  
    }  
  
    public IEnumerable<T> TopToBottom  
    {  
        get { return this; }  
    }  
  
    public IEnumerable<T> BottomToTop  
    {  
        get  
        {  
            for (int index = 0; index <= top - 1; index++)  
            {  
                yield return values[index];  
            }  
        }  
    }  
  
    public IEnumerable<T> TopN(int itemsFromTop)  
    {  
        // Return less than itemsFromTop if necessary.  
        int startIndex = itemsFromTop >= top ? 0 : top - itemsFromTop;  
  
        for (int index = top - 1; index >= startIndex; index--)  
        {  
            yield return values[index];  
        }  
    }  
  
}  
```  
  
##  <a name="BKMK_SyntaxInformation"></a> Сведения о синтаксисе  
 Итератор может являться методом или методом доступа `get`. Итератор не может использоваться в событии, конструкторе экземпляра, статическом конструкторе или статическом методе завершения.  
  
 Должно существовать неявное преобразование выражения типа в операторе `yield return` в возвращаемый тип итератора.  
  
 В C# методы итератора не могут иметь параметры `ref` или `out`.  
  
 В C# yield не является зарезервированным словом и имеет специальное значение, только если используется перед ключевым словом `return` или `break`.  
  
##  <a name="BKMK_Technical"></a> Техническая реализация  
 Хотя итератор создается как метод, компилятор переводит его во вложенный класс, который фактически является конечным автоматом. Этот класс отслеживает положение итератора, пока в клиентском коде выполняется цикл `foreach`.  
  
 Чтобы просмотреть операции компилятора, воспользуйтесь средством Ildasm.exe для отображения кода промежуточного языка Майкрософт, создаваемого для метода итератора.  
  
 При создании итератора для [класса](../../../csharp/language-reference/keywords/class.md) или [структуры](../../../csharp/language-reference/keywords/struct.md) реализация всего интерфейса <xref:System.Collections.IEnumerator> не требуется. Когда компилятор обнаруживает итератор, он автоматически создает методы `Current`, `MoveNext` и `Dispose` интерфейса <xref:System.Collections.IEnumerator> или <xref:System.Collections.Generic.IEnumerator%601>.  
  
 В каждой последовательной итерации цикла `foreach` (или непосредственном вызове метода `IEnumerator.MoveNext`) код тела следующего итератора возобновляет выполнение после предыдущего оператора `yield return`. Затем он выполняется до следующего оператора `yield return` до тех пор, пока не будет достигнут конец тела итератора или пока не будет обнаружен оператор `yield break`.  
  
 Итераторы не поддерживают метод <xref:System.Collections.IEnumerator.Reset%2A?displayProperty=fullName>. Для повторной итерации сначала необходимо получить новый итератор.  
  
 Дополнительные сведения см. в [спецификации языка C#](../../../csharp/language-reference/language-specification/index.md).  
  
##  <a name="BKMK_UseOfIterators"></a> Использование итераторов  
 Итераторы позволяют поддерживать простоту цикла `foreach`, когда необходимо использовать сложный код для заполнения последовательности списков. Это может оказаться полезным в следующих случаях:  
  
-   Изменение последовательности списков после первой итерации цикла `foreach`.  
  
-   Если необходимо избежать полной загрузки большого списка перед первой итерацией цикла `foreach`. Пример: при постраничной загрузке пакета строк таблицы. Другой пример — метод <xref:System.IO.DirectoryInfo.EnumerateFiles%2A>, реализующий итераторы в .NET Framework.  
  
-   Инкапсулирование построения списка в итераторе. В методе итератора можно построить список, а затем выдавать каждый результат в цикле.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Collections.Generic>   
 <xref:System.Collections.Generic.IEnumerable%601>   
 [foreach, in](../../../csharp/language-reference/keywords/foreach-in.md)   
 [yield](../../../csharp/language-reference/keywords/yield.md)   
 [Использование оператора foreach с массивами](../../../csharp/programming-guide/arrays/using-foreach-with-arrays.md)   
 [Универсальные шаблоны](../../../csharp/programming-guide/generics/index.md)


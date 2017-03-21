---
title: "Коллекции (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: get-started-article
dev_langs:
- VB
ms.assetid: 5f7749f3-aaf2-4319-b63c-bfa72e1e2b7a
caps.latest.revision: 6
author: stevehoag
ms.author: shoag
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: b3c8de3e22075d576f86bcd4eb599946740ebe16
ms.lasthandoff: 03/13/2017

---
# <a name="collections-visual-basic"></a>Коллекции (Visual Basic)
Во многих приложениях требуется создавать группы связанных объектов и управлять ими. Существует два способа группировки объектов: создать массив объектов и создать коллекцию.  
  
 Массивы удобнее всего использовать для создания и работы с фиксированным числом строго типизированных объектов. Сведения о массивах см. в разделе [массивы](../../../visual-basic/programming-guide/language-features/arrays/index.md).  
  
 Коллекции предоставляют более гибкий способ работы с группами объектов. В отличие от массивов, коллекция, с которой вы работаете, может расти или уменьшаться динамически при необходимости. Некоторые коллекции допускают назначение ключа любому объекту, который добавляется в коллекцию, чтобы в дальнейшем можно было быстро извлечь связанный с ключом объект из коллекции.  
  
 Коллекция является классом, поэтому необходимо объявить экземпляр класса перед добавлением в коллекцию элементов.  
  
 Если коллекция содержит элементы только одного типа данных, можно использовать один из классов в <xref:System.Collections.Generic?displayProperty=fullName>имен.</xref:System.Collections.Generic?displayProperty=fullName> Универсальная коллекция обеспечивает строгую типизацию, так что в нее нельзя добавить другие типы данных. При извлечении элемента из универсальной коллекции не нужно определять или преобразовывать его тип данных.  
  
> [!NOTE]
>  Примеры в этом разделе, включают [импорта](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) инструкции для `System.Collections.Generic` и `System.Linq` пространства имен.  
  
 **Содержание раздела**  
  
-   [С помощью простой коллекции](#BKMK_SimpleCollection)  
  
-   [Типы коллекций](#BKMK_KindsOfCollections)  
  
    -   [Классы System.Collections.Generic](#BKMK_Generic)  
  
    -   [Классы System.Collections.Concurrent](#BKMK_Concurrent)  
  
    -   [Классы System.Collections](#BKMK_Collections)  
  
    -   [Класс коллекции Visual Basic](#BKMK_VisualBasic)  
  
-   [Реализации коллекции пар «ключ значение»](#BKMK_KeyValuePairs)  
  
-   [Использование LINQ для доступа к коллекции](#BKMK_LINQ)  
  
-   [Сортировка коллекции](#BKMK_Sorting)  
  
-   [Определение настраиваемой коллекции](#BKMK_CustomCollection)  
  
-   [Итераторы](#BKMK_Iterators)  
  
<a name="BKMK_SimpleCollection"></a>
## <a name="using-a-simple-collection"></a>Использование простой коллекции  
 В примерах этого раздела используется универсальный <xref:System.Collections.Generic.List%601>класс, который позволяет работать со строго типизированный список объектов.</xref:System.Collections.Generic.List%601>  
  
 В следующем примере создается список строк и затем выполняется перебор строк с помощью [For Each... Далее](../../../visual-basic/language-reference/statements/for-each-next-statement.md) инструкции.  
  
```vb  
' Create a list of strings.  
Dim salmons As New List(Of String)  
salmons.Add("chinook")  
salmons.Add("coho")  
salmons.Add("pink")  
salmons.Add("sockeye")  
  
' Iterate through the list.  
For Each salmon As String In salmons  
    Console.Write(salmon & " ")  
Next  
'Output: chinook coho pink sockeye  
```  
  
 Если содержимое коллекции известны заранее, можно использовать *инициализатора коллекции* для инициализации коллекции. Дополнительные сведения см. в разделе [инициализаторы](../../../visual-basic/programming-guide/language-features/collection-initializers/index.md).  
  
 Следующий пример аналогичен предыдущему за исключением того, что для добавления элементов в коллекцию используется инициализатор коллекции.  
  
```vb  
' Create a list of strings by using a  
' collection initializer.  
Dim salmons As New List(Of String) From  
    {"chinook", "coho", "pink", "sockeye"}  
  
For Each salmon As String In salmons  
    Console.Write(salmon & " ")  
Next  
'Output: chinook coho pink sockeye  
```  
  
 Можно использовать [для... Далее](../../../visual-basic/language-reference/statements/for-next-statement.md) инструкции вместо `For Each` инструкции для прохода по коллекции. Для этого доступ к элементам коллекции осуществляется по позиции индекса. Индекс элементов начинается с 0 и заканчивается числом, равным количеству элементов минус 1.  
  
 Следующий пример итерацию по элементам коллекции с помощью `For…Next` вместо `For Each`.  
  
```vb  
Dim salmons As New List(Of String) From  
    {"chinook", "coho", "pink", "sockeye"}  
  
For index = 0 To salmons.Count - 1  
    Console.Write(salmons(index) & " ")  
Next  
'Output: chinook coho pink sockeye  
```  
  
 В приведенном ниже примере элемент удаляется из коллекции путем указания удаляемого объекта.  
  
```vb  
' Create a list of strings by using a  
' collection initializer.  
Dim salmons As New List(Of String) From  
    {"chinook", "coho", "pink", "sockeye"}  
  
' Remove an element in the list by specifying  
' the object.  
salmons.Remove("coho")  
  
For Each salmon As String In salmons  
    Console.Write(salmon & " ")  
Next  
'Output: chinook pink sockeye  
```  
  
 В приведенном ниже примере удаляются элементы из универсального списка. Вместо `For Each` инструкции [для... Далее](../../../visual-basic/language-reference/statements/for-next-statement.md) используется инструкция, проходящий по убыванию. Это вызвано <xref:System.Collections.Generic.List%601.RemoveAt%2A>метод вызывает элементы после удаленный элемент должен иметь значение нижнего индекса.</xref:System.Collections.Generic.List%601.RemoveAt%2A>  
  
```vb  
Dim numbers As New List(Of Integer) From  
    {0, 1, 2, 3, 4, 5, 6, 7, 8, 9}  
  
' Remove odd numbers.  
For index As Integer = numbers.Count - 1 To 0 Step -1  
    If numbers(index) Mod 2 = 1 Then  
        ' Remove the element by specifying  
        ' the zero-based index in the list.  
        numbers.RemoveAt(index)  
    End If  
Next  
  
' Iterate through the list.  
' A lambda expression is placed in the ForEach method  
' of the List(T) object.  
numbers.ForEach(  
    Sub(number) Console.Write(number & " "))  
' Output: 0 2 4 6 8  
```  
  
 Для типа элементов массива <xref:System.Collections.Generic.List%601>можно также определить собственный класс.</xref:System.Collections.Generic.List%601> В следующем примере `Galaxy` класс, используемый <xref:System.Collections.Generic.List%601>определяется в коде.</xref:System.Collections.Generic.List%601>  
  
```vb  
Private Sub IterateThroughList()  
    Dim theGalaxies As New List(Of Galaxy) From  
        {  
            New Galaxy With {.Name = "Tadpole", .MegaLightYears = 400},  
            New Galaxy With {.Name = "Pinwheel", .MegaLightYears = 25},  
            New Galaxy With {.Name = "Milky Way", .MegaLightYears = 0},  
            New Galaxy With {.Name = "Andromeda", .MegaLightYears = 3}  
        }  
  
    For Each theGalaxy In theGalaxies  
        With theGalaxy  
            Console.WriteLine(.Name & "  " & .MegaLightYears)  
        End With  
    Next  
  
    ' Output:  
    '  Tadpole  400  
    '  Pinwheel  25  
    '  Milky Way  0  
    '  Andromeda  3  
End Sub  
  
Public Class Galaxy  
    Public Property Name As String  
    Public Property MegaLightYears As Integer  
End Class  
```  
  
<a name="BKMK_KindsOfCollections"></a>
## <a name="kinds-of-collections"></a>Виды коллекций   
 Многие типовые коллекции предоставляются платформой .NET Framework. Каждый тип коллекции предназначен для определенной цели.  
  
 В этом разделе описываются следующие часто используемые классы коллекций:  
  
-   @System.Collections.Genericклассы  
  
-   @System.Collections.Concurrentклассы  
  
-   @System.Collectionsклассы  
  
-   Visual Basic `Collection` класса  
  
<a name="BKMK_Generic"></a>
### <a name="systemcollectionsgeneric-classes"></a>Классы System.Collections.Generic  

 Можно создать универсальную коллекцию с помощью одного из классов в <xref:System.Collections.Generic>имен.</xref:System.Collections.Generic> Универсальная коллекция применяется в том случае, если все элементы в коллекции имеют одинаковый тип данных. Универсальная коллекция обеспечивает строгую типизацию, позволяя добавлять данные только необходимого типа.  
  
 В следующей таблице перечислены некоторые часто используемые классы <xref:System.Collections.Generic?displayProperty=fullName>пространство имен:</xref:System.Collections.Generic?displayProperty=fullName>  
  
|Класс|Описание|  
|---|---|  
|<xref:System.Collections.Generic.Dictionary%602></xref:System.Collections.Generic.Dictionary%602>|Предоставляет коллекцию пар «ключ-значение», которые упорядочены по ключу.|  
|<xref:System.Collections.Generic.List%601></xref:System.Collections.Generic.List%601>|Представляет список объектов, доступных по индексу. Предоставляет методы для поиска по списку, его сортировки и изменения.|  
|<xref:System.Collections.Generic.Queue%601></xref:System.Collections.Generic.Queue%601>|Представляет коллекцию объектов, которая обслуживается в порядке поступления (FIFO).|  
|<xref:System.Collections.Generic.SortedList%602></xref:System.Collections.Generic.SortedList%602>|Представляет коллекцию пар "ключ значение", упорядоченных по ключу на основе <xref:System.Collections.Generic.IComparer%601>реализацию.</xref:System.Collections.Generic.IComparer%601>|  
|<xref:System.Collections.Generic.Stack%601></xref:System.Collections.Generic.Stack%601>|Представляет коллекцию объектов, которая обслуживается в обратном порядке (LIFO).|  
  
 Дополнительные сведения см. в разделе [часто используемые типы коллекций](http://msdn.microsoft.com/library/f5d4c6a4-0d7b-4944-a9fb-3b12d9ebfd55), [Выбор класса коллекции](../../../standard/collections/selecting-a-collection-class.md)и <xref:System.Collections.Generic?displayProperty=fullName>.</xref:System.Collections.Generic?displayProperty=fullName>  
  
<a name="BKMK_Concurrent"></a>
### <a name="systemcollectionsconcurrent-classes"></a>Классы System.Collections.Concurrent   
 В платформе .NET Framework 4 или более поздней версии, в коллекции <xref:System.Collections.Concurrent>пространства имен предоставляют эффективный потокобезопасные операции для доступа к элементам коллекций из нескольких потоков.</xref:System.Collections.Concurrent>  
  
 Классы в <xref:System.Collections.Concurrent>имен следует использовать вместо соответствующих типов в <xref:System.Collections.Generic?displayProperty=fullName>и <xref:System.Collections?displayProperty=fullName>пространства имен, когда несколько потоков параллельно обращаются к коллекции.</xref:System.Collections?displayProperty=fullName> </xref:System.Collections.Generic?displayProperty=fullName> </xref:System.Collections.Concurrent> Дополнительные сведения см. в разделе [потокобезопасных коллекций](../../../standard/collections/threadsafe/index.md) и <xref:System.Collections.Concurrent>.</xref:System.Collections.Concurrent>  
  
 Некоторые классы, включенные в <xref:System.Collections.Concurrent>пространства имен являются <xref:System.Collections.Concurrent.BlockingCollection%601>, <xref:System.Collections.Concurrent.ConcurrentDictionary%602>, <xref:System.Collections.Concurrent.ConcurrentQueue%601>и <xref:System.Collections.Concurrent.ConcurrentStack%601>.</xref:System.Collections.Concurrent.ConcurrentStack%601> </xref:System.Collections.Concurrent.ConcurrentQueue%601> </xref:System.Collections.Concurrent.ConcurrentDictionary%602> </xref:System.Collections.Concurrent.BlockingCollection%601> </xref:System.Collections.Concurrent>  
  
<a name="BKMK_Collections"></a>
### <a name="systemcollections-classes"></a>Классы System.Collections    
 Классы в <xref:System.Collections?displayProperty=fullName>пространства имен не храните элементы конкретно типизированных объектов, а объекты типа `Object`.</xref:System.Collections?displayProperty=fullName>  
  
 По возможности следует использовать универсальные коллекции в <xref:System.Collections.Generic?displayProperty=fullName>пространства имен или <xref:System.Collections.Concurrent>имен вместо устаревших типов в `System.Collections` имен.</xref:System.Collections.Concurrent> </xref:System.Collections.Generic?displayProperty=fullName>  
  
 В следующей таблице перечислены некоторые часто используемые классы в `System.Collections` пространство имен:  
  
|Класс|Описание|  
|---|---|  
|<xref:System.Collections.ArrayList></xref:System.Collections.ArrayList>|Представляет массив объектов, размер которого динамически увеличивается по мере необходимости.|  
|<xref:System.Collections.Hashtable></xref:System.Collections.Hashtable>|Представляет коллекцию пар «ключ-значение», которые упорядочены по хэш-коду ключа.|  
|<xref:System.Collections.Queue></xref:System.Collections.Queue>|Представляет коллекцию объектов, которая обслуживается в порядке поступления (FIFO).|  
|<xref:System.Collections.Stack></xref:System.Collections.Stack>|Представляет коллекцию объектов, которая обслуживается в обратном порядке (LIFO).|  
  
 <xref:System.Collections.Specialized>Пространство имен предоставляет классы, специализированные и строго типизированные коллекции, такие как коллекции строк и связанные списки и гибридные словари.</xref:System.Collections.Specialized>  

<a name="BKMK_VisualBasic"></a> 
###  <a name="visual-basic-collection-class"></a>Класс Collection в Visual Basic  
 Можно использовать Visual Basic <xref:Microsoft.VisualBasic.Collection>класса для доступа к коллекции элементов с помощью числовой индекс или объект `String` ключ.</xref:Microsoft.VisualBasic.Collection> Элементы можно добавлять в объект коллекции с указанием или без указания ключа. Если добавить объект без ключа, необходимо использовать его числовой индекс для доступа к нему.  
  
 Visual Basic `Collection` класс хранит все его элементы как тип `Object`, поэтому можно добавить элемент любого типа данных. Нет никакой защиты от добавления неподходящих типов данных.  
  
 При использовании Visual Basic `Collection` класс, первый элемент в коллекции имеет индекс 1. Этим он отличается от классов коллекций платформы .NET Framework, для которых начальный индекс равен 0.  
  
 По возможности следует использовать универсальные коллекции в <xref:System.Collections.Generic?displayProperty=fullName>пространства имен или <xref:System.Collections.Concurrent>имен вместо Visual Basic `Collection` класса</xref:System.Collections.Concurrent> </xref:System.Collections.Generic?displayProperty=fullName>  
  
 Дополнительные сведения см. в разделе <xref:Microsoft.VisualBasic.Collection>.</xref:Microsoft.VisualBasic.Collection>  
  
<a name="BKMK_KeyValuePairs"></a>
## <a name="implementing-a-collection-of-keyvalue-pairs"></a>Реализация коллекции пар «ключ-значение»   
 <xref:System.Collections.Generic.Dictionary%602>Обеспечивает доступ к элементам в коллекции с помощью ключа каждого элемента универсальной коллекции.</xref:System.Collections.Generic.Dictionary%602> Каждый элемент, добавляемый в словарь, состоит из значения и связанного с ним ключа. Получение значения, используя свой ключ — быстро, так как `Dictionary` класс реализован в виде хэш-таблицы.  
  
 В следующем примере создается `Dictionary` коллекции и перебор элементов словаря с помощью `For Each` инструкции.  
  
```vb  
Private Sub IterateThroughDictionary()  
    Dim elements As Dictionary(Of String, Element) = BuildDictionary()  
  
    For Each kvp As KeyValuePair(Of String, Element) In elements  
        Dim theElement As Element = kvp.Value  
  
        Console.WriteLine("key: " & kvp.Key)  
        With theElement  
            Console.WriteLine("values: " & .Symbol & " " &  
                .Name & " " & .AtomicNumber)  
        End With  
    Next  
End Sub  
  
Private Function BuildDictionary() As Dictionary(Of String, Element)  
    Dim elements As New Dictionary(Of String, Element)  
  
    AddToDictionary(elements, "K", "Potassium", 19)  
    AddToDictionary(elements, "Ca", "Calcium", 20)  
    AddToDictionary(elements, "Sc", "Scandium", 21)  
    AddToDictionary(elements, "Ti", "Titanium", 22)  
  
    Return elements  
End Function  
  
Private Sub AddToDictionary(ByVal elements As Dictionary(Of String, Element),  
ByVal symbol As String, ByVal name As String, ByVal atomicNumber As Integer)  
    Dim theElement As New Element  
  
    theElement.Symbol = symbol  
    theElement.Name = name  
    theElement.AtomicNumber = atomicNumber  
  
    elements.Add(Key:=theElement.Symbol, value:=theElement)  
End Sub  
  
Public Class Element  
    Public Property Symbol As String  
    Public Property Name As String  
    Public Property AtomicNumber As Integer  
End Class  
```  
  
 Вместо этого использовать инициализатор коллекции для создания `Dictionary` коллекции, можно заменить `BuildDictionary` и `AddToDictionary` методов, с помощью следующего метода.  
  
```vb  
Private Function BuildDictionary2() As Dictionary(Of String, Element)  
    Return New Dictionary(Of String, Element) From  
        {  
            {"K", New Element With  
                {.Symbol = "K", .Name = "Potassium", .AtomicNumber = 19}},  
            {"Ca", New Element With  
                {.Symbol = "Ca", .Name = "Calcium", .AtomicNumber = 20}},  
            {"Sc", New Element With  
                {.Symbol = "Sc", .Name = "Scandium", .AtomicNumber = 21}},  
            {"Ti", New Element With  
                {.Symbol = "Ti", .Name = "Titanium", .AtomicNumber = 22}}  
        }  
End Function  
```  
  
 В следующем примере используется <xref:System.Collections.Generic.Dictionary%602.ContainsKey%2A>метод и <xref:System.Collections.Generic.Dictionary%602.Item%2A>Свойства `Dictionary` быстро найти элемент с ключом.</xref:System.Collections.Generic.Dictionary%602.Item%2A> </xref:System.Collections.Generic.Dictionary%602.ContainsKey%2A> `Item` Позволяет доступ к элементу в `elements` коллекции с помощью `elements(symbol)` кода в Visual Basic.  
  
```vb  
Private Sub FindInDictionary(ByVal symbol As String)  
    Dim elements As Dictionary(Of String, Element) = BuildDictionary()  
  
    If elements.ContainsKey(symbol) = False Then  
        Console.WriteLine(symbol & " not found")  
    Else  
        Dim theElement = elements(symbol)  
        Console.WriteLine("found: " & theElement.Name)  
    End If  
End Sub  
```  
  
 В следующем примере используется вместо <xref:System.Collections.Generic.Dictionary%602.TryGetValue%2A>метод быстро найти элемент с ключом.</xref:System.Collections.Generic.Dictionary%602.TryGetValue%2A>  
  
```vb  
Private Sub FindInDictionary2(ByVal symbol As String)  
    Dim elements As Dictionary(Of String, Element) = BuildDictionary()  
  
    Dim theElement As Element = Nothing  
    If elements.TryGetValue(symbol, theElement) = False Then  
        Console.WriteLine(symbol & " not found")  
    Else  
        Console.WriteLine("found: " & theElement.Name)  
    End If  
End Sub  
```  
  
<a name="BKMK_LINQ"></a> 
##  <a name="using-linq-to-access-a-collection"></a>Использование LINQ для доступа к коллекции  
 Для доступа к коллекции можно использовать язык LINQ. Запросы LINQ обеспечивают возможности фильтрации, упорядочения и группировки. Дополнительные сведения см. в разделе [Приступая к работе с LINQ в Visual Basic](../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md).  
  
 В следующем примере выполняется запрос LINQ к универсальным `List`. Запрос LINQ возвращает другую коллекцию, содержащую результаты.  
  
```vb  
Private Sub ShowLINQ()  
    Dim elements As List(Of Element) = BuildList()  
  
    ' LINQ Query.  
    Dim subset = From theElement In elements  
                  Where theElement.AtomicNumber < 22  
                  Order By theElement.Name  
  
    For Each theElement In subset  
        Console.WriteLine(theElement.Name & " " & theElement.AtomicNumber)  
    Next  
  
    ' Output:  
    '  Calcium 20  
    '  Potassium 19  
    '  Scandium 21  
End Sub  
  
Private Function BuildList() As List(Of Element)  
    Return New List(Of Element) From  
        {  
            {New Element With  
                {.Symbol = "K", .Name = "Potassium", .AtomicNumber = 19}},  
            {New Element With  
                {.Symbol = "Ca", .Name = "Calcium", .AtomicNumber = 20}},  
            {New Element With  
                {.Symbol = "Sc", .Name = "Scandium", .AtomicNumber = 21}},  
            {New Element With  
                {.Symbol = "Ti", .Name = "Titanium", .AtomicNumber = 22}}  
        }  
End Function  
  
Public Class Element  
    Public Property Symbol As String  
    Public Property Name As String  
    Public Property AtomicNumber As Integer  
End Class  
```  
  
 <a name="BKMK_Sorting"></a> 
## <a name="sorting-a-collection"></a>Сортировка коллекции  
 Приведенный ниже пример демонстрирует процедуру сортировки коллекции. В примере выполняется сортировка экземпляров `Car` класса, которые хранятся в папке <xref:System.Collections.Generic.List%601>.</xref:System.Collections.Generic.List%601> `Car` Реализует <xref:System.IComparable%601>интерфейс, который требует <xref:System.IComparable%601.CompareTo%2A>метод будет реализован.</xref:System.IComparable%601.CompareTo%2A> </xref:System.IComparable%601>  
  
 Каждый вызов <xref:System.IComparable%601.CompareTo%2A>метод делает одну сравнения, используемый для сортировки.</xref:System.IComparable%601.CompareTo%2A> Пользовательский код в `CompareTo` метод возвращает значение для каждого сравнения текущего объекта с другим объектом. Возвращаемое значение меньше нуля, если текущий объект меньше другого объекта, больше нуля, если текущий объект больше другого объекта, и равняется нулю, если объекты равны. Это позволяет определить в коде условия для отношения «больше», «меньше» и «равно».  
  
 В `ListCars` метода `cars.Sort()` инструкция сортирует список. Этот вызов <xref:System.Collections.Generic.List%601.Sort%2A>метод <xref:System.Collections.Generic.List%601>вызывает `CompareTo` метод, который вызывается автоматически для `Car` объектов в `List`.</xref:System.Collections.Generic.List%601> </xref:System.Collections.Generic.List%601.Sort%2A>  
  
```vb  
Public Sub ListCars()  
  
    ' Create some new cars.  
    Dim cars As New List(Of Car) From  
    {  
        New Car With {.Name = "car1", .Color = "blue", .Speed = 20},  
        New Car With {.Name = "car2", .Color = "red", .Speed = 50},  
        New Car With {.Name = "car3", .Color = "green", .Speed = 10},  
        New Car With {.Name = "car4", .Color = "blue", .Speed = 50},  
        New Car With {.Name = "car5", .Color = "blue", .Speed = 30},  
        New Car With {.Name = "car6", .Color = "red", .Speed = 60},  
        New Car With {.Name = "car7", .Color = "green", .Speed = 50}  
    }  
  
    ' Sort the cars by color alphabetically, and then by speed  
    ' in descending order.  
    cars.Sort()  
  
    ' View all of the cars.  
    For Each thisCar As Car In cars  
        Console.Write(thisCar.Color.PadRight(5) & " ")  
        Console.Write(thisCar.Speed.ToString & " ")  
        Console.Write(thisCar.Name)  
        Console.WriteLine()  
    Next  
  
    ' Output:  
    '  blue  50 car4  
    '  blue  30 car5  
    '  blue  20 car1  
    '  green 50 car7  
    '  green 10 car3  
    '  red   60 car6  
    '  red   50 car2  
End Sub  
  
Public Class Car  
    Implements IComparable(Of Car)  
  
    Public Property Name As String  
    Public Property Speed As Integer  
    Public Property Color As String  
  
    Public Function CompareTo(ByVal other As Car) As Integer _  
        Implements System.IComparable(Of Car).CompareTo  
        ' A call to this method makes a single comparison that is  
        ' used for sorting.  
  
        ' Determine the relative order of the objects being compared.  
        ' Sort by color alphabetically, and then by speed in  
        ' descending order.  
  
        ' Compare the colors.  
        Dim compare As Integer  
        compare = String.Compare(Me.Color, other.Color, True)  
  
        ' If the colors are the same, compare the speeds.  
        If compare = 0 Then  
            compare = Me.Speed.CompareTo(other.Speed)  
  
            ' Use descending order for speed.  
            compare = -compare  
        End If  
  
        Return compare  
    End Function  
End Class  
```  
  
<a name="BKMK_CustomCollection"></a> 
## <a name="defining-a-custom-collection"></a>Определение настраиваемой коллекции  
 Можно определить коллекцию путем реализации <xref:System.Collections.Generic.IEnumerable%601>или <xref:System.Collections.IEnumerable>интерфейса.</xref:System.Collections.IEnumerable> </xref:System.Collections.Generic.IEnumerable%601> Дополнительные сведения см. в разделе [перечисление коллекции](http://msdn.microsoft.com/en-us/71807ea7-9180-48a6-916f-35a5251d477f).  
  
 Несмотря на то, что можно определить пользовательскую коллекцию, обычно лучше вместо этого использовать коллекций, включенных в .NET Framework, которые описаны в [типов коллекций](http://msdn.microsoft.com/library/e76533a9-5033-4a0b-b003-9c2be60d185b) ранее в этом разделе.  
  
 В следующем примере определяется пользовательский класс коллекции с именем `AllColors`. Этот класс реализует <xref:System.Collections.IEnumerable>интерфейс, который требует <xref:System.Collections.IEnumerable.GetEnumerator%2A>метод будет реализован.</xref:System.Collections.IEnumerable.GetEnumerator%2A> </xref:System.Collections.IEnumerable>  
  
 `GetEnumerator` Метод возвращает экземпляр `ColorEnumerator` класса. `ColorEnumerator`реализует <xref:System.Collections.IEnumerator>интерфейс, который требует <xref:System.Collections.IEnumerator.Current%2A>свойство, <xref:System.Collections.IEnumerator.MoveNext%2A>метод, и <xref:System.Collections.IEnumerator.Reset%2A>метод будет реализован.</xref:System.Collections.IEnumerator.Reset%2A> </xref:System.Collections.IEnumerator.MoveNext%2A> </xref:System.Collections.IEnumerator.Current%2A> </xref:System.Collections.IEnumerator>  
  
```vb  
Public Sub ListColors()  
    Dim colors As New AllColors()  
  
    For Each theColor As Color In colors  
        Console.Write(theColor.Name & " ")  
    Next  
    Console.WriteLine()  
    ' Output: red blue green  
End Sub  
  
' Collection class.  
Public Class AllColors  
    Implements System.Collections.IEnumerable  
  
    Private _colors() As Color =  
    {  
        New Color With {.Name = "red"},  
        New Color With {.Name = "blue"},  
        New Color With {.Name = "green"}  
    }  
  
    Public Function GetEnumerator() As System.Collections.IEnumerator _  
        Implements System.Collections.IEnumerable.GetEnumerator  
  
        Return New ColorEnumerator(_colors)  
  
        ' Instead of creating a custom enumerator, you could  
        ' use the GetEnumerator of the array.  
        'Return _colors.GetEnumerator  
    End Function  
  
    ' Custom enumerator.  
    Private Class ColorEnumerator  
        Implements System.Collections.IEnumerator  
  
        Private _colors() As Color  
        Private _position As Integer = -1  
  
        Public Sub New(ByVal colors() As Color)  
            _colors = colors  
        End Sub  
  
        Public ReadOnly Property Current() As Object _  
            Implements System.Collections.IEnumerator.Current  
            Get  
                Return _colors(_position)  
            End Get  
        End Property  
  
        Public Function MoveNext() As Boolean _  
            Implements System.Collections.IEnumerator.MoveNext  
            _position += 1  
            Return (_position < _colors.Length)  
        End Function  
  
        Public Sub Reset() Implements System.Collections.IEnumerator.Reset  
            _position = -1  
        End Sub  
    End Class  
End Class  
  
' Element class.  
Public Class Color  
    Public Property Name As String  
End Class  
```  
  
<a name="BKMK_Iterators"></a>
##  <a name="iterators"></a>Итераторы  
 *Итератор* используется для выполнения пользовательских итерации по коллекции. Метод может быть итератора или `get` доступа. Использует итератор [Yield](../../../visual-basic/language-reference/statements/yield-statement.md) инструкции для возврата каждого элемента коллекции одной за раз.  
  
 Итератор вызывается с помощью [For Each... Далее](../../../visual-basic/language-reference/statements/for-each-next-statement.md) инструкции. Каждая итерация `For Each` цикл вызывает итератор. Когда `Yield` достижении оператора в итераторе, выражения возвращается и сохраняется текущее расположение в коде. При следующем вызове итератора выполнение возобновляется с этого места.  
  
 Дополнительные сведения см. в разделе [итераторы (Visual Basic)](../../../visual-basic/programming-guide/concepts/iterators.md).  
  
 В приведенном ниже примере используется метод-итератор. Метод итератора имеет `Yield` оператор, находящийся внутри [для... Далее](../../../visual-basic/language-reference/statements/for-next-statement.md) цикла. В `ListEvenNumbers` метод, каждая итерация `For Each` тела оператора создает вызов метода итератора, который переходит к следующему `Yield` инструкции.  
  
```vb  
Public Sub ListEvenNumbers()  
    For Each number As Integer In EvenSequence(5, 18)  
        Console.Write(number & " ")  
    Next  
    Console.WriteLine()  
    ' Output: 6 8 10 12 14 16 18  
End Sub  
  
Private Iterator Function EvenSequence(  
ByVal firstNumber As Integer, ByVal lastNumber As Integer) _  
As IEnumerable(Of Integer)  
  
' Yield even numbers in the range.  
    For number = firstNumber To lastNumber  
        If number Mod 2 = 0 Then  
            Yield number  
        End If  
    Next  
End Function  
```  
  
## <a name="see-also"></a>См. также  
 [Инициализаторы коллекций](../../../visual-basic/programming-guide/language-features/collection-initializers/index.md)   
 [Основные понятия программирования (Visual Basic)](../../../visual-basic/programming-guide/concepts/index.md)   
 [Оператор Option Strict](../../../visual-basic/language-reference/statements/option-strict-statement.md)   
 [LINQ to Objects (Visual Basic)](../../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md)   
 [Параллельный LINQ (PLINQ)](http://msdn.microsoft.com/library/3d4d0cd3-bde4-490b-99e7-f4e41be96455)   
 [Коллекции и структуры данных](../../../standard/collections/index.md)   
 [Создание коллекций и управление ими](http://msdn.microsoft.com/en-us/2065398e-eb1a-4821-9188-75f16e42e069)   
 [Выбор класса коллекции](../../../standard/collections/selecting-a-collection-class.md)   
 [Сравнение и сортировка в коллекциях](../../../standard/collections/comparisons-and-sorts-within-collections.md)   
 [Когда следует использовать универсальные коллекции](../../../standard/collections/when-to-use-generic-collections.md)

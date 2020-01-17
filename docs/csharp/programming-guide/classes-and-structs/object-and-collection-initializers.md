---
title: Руководство по программированию на C#. Инициализаторы объектов и набора
ms.date: 12/19/2018
helpviewer_keywords:
- object initializers [C#]
- collection initializers [C#]
ms.assetid: c58f3db5-d7d4-4651-bd2d-5a3a97357f61
ms.openlocfilehash: 5565f37c9cfd8cb84c07f9ecc6f6c2edf8c66c61
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75714755"
---
# <a name="object-and-collection-initializers-c-programming-guide"></a>Инициализаторы объектов и коллекций (Руководство по программированию в C#)

C# позволяет создать экземпляр объекта или коллекции и выполнять присваивания его членов в одной инструкции.

## <a name="object-initializers"></a>Инициализаторы объектов

Инициализаторы объектов позволяют присваивать значения всем доступным полям и свойствам объекта во время создания без вызова конструктора, за которым следуют строки операторов присваивания. Синтаксис инициализатора объекта позволяет задавать аргументы конструктора или опускать их (и синтаксис в скобках).  В приведенном ниже примере демонстрируется использование инициализатора объекта с именованным типом `Cat` и вызов конструктора без параметров. Обратите внимание на использование в классе `Cat` автоматически внедренных свойств. Дополнительные сведения см. в разделе [Автоматически реализуемые свойства](auto-implemented-properties.md).  
  
[!code-csharp[ObjectInitializer1](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/BasicObjectInitializers.cs#CatDeclaration)]  
[!code-csharp[ObjectInitializer1a](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/BasicObjectInitializers.cs#ObjectPropertyInitialization)]  
 
Синтаксис инициализаторов объектов позволяет создать экземпляр, а затем присваивает созданный объект, включая назначенные ему свойства, переменной в назначении.

Начиная с C# 6 инициализаторы объектов могут задавать индексаторы, кроме назначения полей и свойств. Рассмотрим следующий базовый класс `Matrix`:

[!code-csharp[ObjectInitializer2](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/BasicObjectInitializers.cs#MatrixDeclaration)]  

Можно инициализировать единичную матрицу следующим кодом:

[!code-csharp[ObjectInitializer2a](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/BasicObjectInitializers.cs#MatrixInitialization)]  

Любой доступный индексатор, который содержит доступный метод задания, можно использовать как одно из выражений в инициализаторе объекта независимо от количества или типов аргументов. Аргументы индекса формируют левую часть присваивания, а значение стоит в его правой части.  Например, все нижеприведенные конструкции допустимы, если `IndexersExample` имеет соответствующие индексаторы:

```csharp
var thing = new IndexersExample {
    name = "object one",
    [1] = '1',
    [2] = '4',
    [3] = '9',
    Size = Math.PI,
    ['C',4] = "Middle C"
}
```

Для компиляции приведенного выше кода тип `IndexersExample` должен иметь следующие члены:

```csharp
public string name;
public double Size { set { ... }; }
public char this[int i] { set { ... }; }
public string this[char c, int i] {  set { ... }; }
```

## <a name="object-initializers-with-anonymous-types"></a>Инициализаторы объектов с анонимными типами

Хотя инициализаторы объектов можно использовать в любом контексте, они особенно полезны в выражениях запросов LINQ. В выражениях запросов часто используются [анонимные типы](./anonymous-types.md), которые можно инициализировать только с помощью инициализаторов объектов, как показано в приведенном ниже объявлении.  

```csharp
var pet = new { Age = 10, Name = "Fluffy" };  
```

Анонимные типы позволяют предложению `select` в выражении запроса LINQ преобразовывать объекты исходной последовательности в объекты, значение и форма которых могут отличаться от исходных. Это бывает полезно, если требуется сохранить лишь часть информации от каждого объекта последовательности. В приведенном ниже примере предполагается, что у объекта продукта (`p`) имеется множество полей и методов, и требуется создать последовательность объектов, содержащую только имя продукта и его цену.  
  
[!code-csharp[ObjectInitializer3](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/BasicObjectInitializers.cs#AnonymousUse)]  

При выполнении этого запроса переменная `productInfos` будет содержать последовательность объектов, доступных в операторе `foreach`, как показано в следующем примере.  

```csharp
foreach(var p in productInfos){...}  
```

Каждый объект нового анонимного типа содержит два общедоступных свойства, имеющих те же имена, что и у свойств или полей исходного объекта. Кроме того, при создании анонимного типа можно переименовать поле; в следующем примере выполняется переименование поля `UnitPrice` в `Price`.  

```csharp
select new {p.ProductName, Price = p.UnitPrice};  
```

## <a name="collection-initializers"></a>Инициализаторы коллекций

Инициализаторы коллекций позволяют задавать один или несколько инициализаторов элементов при инициализации типа коллекции, который реализует интерфейс <xref:System.Collections.IEnumerable> и включает `Add` с соответствующей сигнатурой как метод экземпляра или метод расширения. Инициализаторами элементов могут быть простые значения, выражения и инициализаторы объектов. При использовании инициализатора коллекции не требуется указывать несколько вызовов; эти вызовы добавляет компилятор.  
  
Ниже приведен пример двух простых инициализаторов коллекций.  

```csharp
List<int> digits = new List<int> { 0, 1, 2, 3, 4, 5, 6, 7, 8, 9 };  
List<int> digits2 = new List<int> { 0 + 1, 12 % 3, MakeInt() };  
```

В следующем инициализаторе коллекции используются инициализаторы объектов класса `Cat`, определенного в предыдущем примере. Обратите внимание, что инициализаторы отдельных объектов заключены в скобки и разделены запятыми.  
  
[!code-csharp[ListInitializer](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/BasicObjectInitializers.cs#ListInitializer)]  
  
В качестве элемента инициализатора коллекции можно указать значение [null](../../language-reference/keywords/null.md), если метод `Add` коллекции допускает это.  
  
[!code-csharp[ListInitializerNull](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/BasicObjectInitializers.cs#ListInitialerWithNull)]  
  
 Можно указать индексированные элементы, если коллекция поддерживает индексирование чтения и записи.
  
[!code-csharp[DictionaryInitializer](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/BasicObjectInitializers.cs#DictionaryIndexerInitializer)]  

В предыдущем примере создается код, который вызывает <xref:System.Collections.Generic.Dictionary%602.Item(%600)> для задания значений. В версиях C# ниже 6 можно было инициализировать словари и другие ассоциативные контейнеры, используя указанный ниже синтаксис. Обратите внимание, что вместо синтаксиса индексатора с круглыми скобками и присваиванием он использует объект с несколькими значениями:

[!code-csharp[DictionaryAddInitializer](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/BasicObjectInitializers.cs#DictionaryAddInitializer)]  

В этом примере инициализатор вызывает <xref:System.Collections.Generic.Dictionary%602.Add(%600,%601)> для добавления трех элементов в словарь. Эти два разных способа инициализации ассоциативных коллекций немного отличаются из-за вызовов методов, которые создает компилятор. Оба варианта могут работать с классом `Dictionary`. Другие типы могут поддерживать только один из них в зависимости от своего открытого API.

## <a name="examples"></a>Примеры

В следующем примере объединяются понятия инициализаторов коллекций и объектов.

[!code-csharp[InitializerExample](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/BasicObjectInitializers.cs#FullExample)]  

В примере ниже представлен объект, в котором реализован интерфейс <xref:System.Collections.IEnumerable>. Он содержит метод `Add` с несколькими параметрами, позволяющими использовать инициализаторы коллекций с несколькими элементами для каждого пункта списка, который соответствует сигнатуре метода `Add`.

[!code-csharp[InitializerListExample](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/BasicObjectInitializers.cs#FullListExample)]  

В методах `Add` можно использовать ключевое слово `params`, чтобы принимать переменное число аргументов, как показано в приведенном ниже примере. Здесь также демонстрируется пользовательская реализация индексатора, которая также применяется для инициализации коллекции с помощью индексов.

[!code-csharp[InitializerListExample](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/BasicObjectInitializers.cs#FullDictionaryInitializer)]  

## <a name="see-also"></a>См. также

- [Руководство по программированию на C#](../index.md)
- [LINQ в C#](../../linq/index.md)
- [Анонимные типы](anonymous-types.md)

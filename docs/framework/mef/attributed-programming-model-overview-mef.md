---
title: Общие сведения о модели атрибутивного программирования (MEF)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- MEF, attributed programming model
- attributed programming model [MEF]
ms.assetid: 49b787ff-2741-4836-ad51-c3017dc592d4
ms.openlocfilehash: 63fb3d627364810fac5ddb0bfd3adc3c0421c9cc
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73126389"
---
# <a name="attributed-programming-model-overview-mef"></a><span data-ttu-id="037c1-102">Общие сведения о модели атрибутивного программирования (MEF)</span><span class="sxs-lookup"><span data-stu-id="037c1-102">Attributed Programming Model Overview (MEF)</span></span>

<span data-ttu-id="037c1-103">В Managed Extensibility Framework (MEF) *модель программирования* представляет собой определенный способ задания набора концептуальных объектов, с которыми MEF работает.</span><span class="sxs-lookup"><span data-stu-id="037c1-103">In the Managed Extensibility Framework (MEF), a *programming model* is a particular method of defining the set of conceptual objects on which MEF operates.</span></span> <span data-ttu-id="037c1-104">Такие концептуальные объекты включают в себя части, импорты и экспорты.</span><span class="sxs-lookup"><span data-stu-id="037c1-104">These conceptual objects include parts, imports, and exports.</span></span> <span data-ttu-id="037c1-105">MEF использует их, но не указывает, как они должны быть представлены.</span><span class="sxs-lookup"><span data-stu-id="037c1-105">MEF uses these objects, but does not specify how they should be represented.</span></span> <span data-ttu-id="037c1-106">Это делает возможным применение широкого спектра моделей программирования, включая настраиваемые.</span><span class="sxs-lookup"><span data-stu-id="037c1-106">Therefore, a wide variety of programming models are possible, including customized programming models.</span></span>

<span data-ttu-id="037c1-107">По умолчанию в MEF используется *атрибутивная модель программирования*.</span><span class="sxs-lookup"><span data-stu-id="037c1-107">The default programming model used in MEF is the *attributed programming model*.</span></span> <span data-ttu-id="037c1-108">В атрибутивной модели программирования части, импорты, экспорты и другие объекты определены с атрибутами, которые декорируют рядовые классы платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="037c1-108">In the attributed programming model parts, imports, exports, and other objects are defined with attributes that decorate ordinary .NET Framework classes.</span></span> <span data-ttu-id="037c1-109">Этот раздел описывает использование атрибутов, предоставляемых атрибутивной моделью программирования, для создания приложения MEF.</span><span class="sxs-lookup"><span data-stu-id="037c1-109">This topic explains how to use the attributes provided by the attributed programming model to create a MEF application.</span></span>

<a name="import_and_export_basics"></a>

## <a name="import-and-export-basics"></a><span data-ttu-id="037c1-110">Основы импорта и экспорта</span><span class="sxs-lookup"><span data-stu-id="037c1-110">Import and Export Basics</span></span>

<span data-ttu-id="037c1-111">*Экспорт* — это значение, которое часть предоставляет другим частям в контейнере, а *импорт* — это требование, которое часть выражает для контейнера и заполняется из доступных экспортов.</span><span class="sxs-lookup"><span data-stu-id="037c1-111">An *export* is a value that a part provides to other parts in the container, and an *import* is a requirement that a part expresses to the container, to be filled from the available exports.</span></span> <span data-ttu-id="037c1-112">В атрибутивной модели программирования импорты и экспорты объявляются за счет декорирования классов или членов атрибутами `Import` и `Export` .</span><span class="sxs-lookup"><span data-stu-id="037c1-112">In the attributed programming model, imports and exports are declared by decorating classes or members with the `Import` and `Export` attributes.</span></span> <span data-ttu-id="037c1-113">Атрибут `Export` может декорировать класс, поле, свойство или метод, а атрибут `Import` может декорировать поле, свойство или параметр конструктора.</span><span class="sxs-lookup"><span data-stu-id="037c1-113">The `Export` attribute can decorate a class, field, property, or method, while the `Import` attribute can decorate a field, property, or constructor parameter.</span></span>

<span data-ttu-id="037c1-114">Для сопоставления импорта с экспортом они должны иметь один *контракт*.</span><span class="sxs-lookup"><span data-stu-id="037c1-114">In order for an import to be matched with an export, the import and export must have the same *contract*.</span></span> <span data-ttu-id="037c1-115">Контракт состоит из строки, называемой *именем контракта*, и типа экспортированного или импортированного объекта, называемого *типом контракта*.</span><span class="sxs-lookup"><span data-stu-id="037c1-115">The contract consists of a string, called the *contract name*, and the type of the exported or imported object, called the *contract type*.</span></span> <span data-ttu-id="037c1-116">Только в случае совпадения имени контракта и типа контракта считается, что экспорт выполняет определенный импорт.</span><span class="sxs-lookup"><span data-stu-id="037c1-116">Only if both the contract name and contract type match is an export considered to fulfill a particular import.</span></span>

<span data-ttu-id="037c1-117">Любой из параметров контракта или оба этих параметра могут быть неявными или явными.</span><span class="sxs-lookup"><span data-stu-id="037c1-117">Either or both of the contract parameters can be implicit or explicit.</span></span> <span data-ttu-id="037c1-118">В следующем коде показан класс, объявляющий базовый импорт.</span><span class="sxs-lookup"><span data-stu-id="037c1-118">The following code shows a class that declares a basic import.</span></span>

```vb
Public Class MyClass1
    <Import()>
    Public Property MyAddin As IMyAddin
End Class
```

```csharp
public class MyClass
{
    [Import]
    public IMyAddin MyAddin { get; set; }
}
```

<span data-ttu-id="037c1-119">В этом импорте атрибут `Import` не имеет прикрепленного параметра ни для типа, ни для имени контракта.</span><span class="sxs-lookup"><span data-stu-id="037c1-119">In this import, the `Import` attribute has neither a contract type nor a contract name parameter attached.</span></span> <span data-ttu-id="037c1-120">Таким образом, они оба будут выведены из декорированного свойства.</span><span class="sxs-lookup"><span data-stu-id="037c1-120">Therefore, both will be inferred from the decorated property.</span></span> <span data-ttu-id="037c1-121">В данном случае тип контракта будет иметь значение `IMyAddin`, а именем контракта будет уникальная строка, созданная из типа контракта.</span><span class="sxs-lookup"><span data-stu-id="037c1-121">In this case, the contract type will be `IMyAddin`, and the contract name will be a unique string created from the contract type.</span></span> <span data-ttu-id="037c1-122">(Другими словами, имя контракта будет соответствовать только экспортам, имена которых также выведены из типа `IMyAddin`.)</span><span class="sxs-lookup"><span data-stu-id="037c1-122">(In other words, the contract name will match only exports whose names are also inferred from the type `IMyAddin`.)</span></span>

<span data-ttu-id="037c1-123">Ниже показан экспорт, соответствующий предыдущему импорту.</span><span class="sxs-lookup"><span data-stu-id="037c1-123">The following shows an export that matches the previous import.</span></span>

```vb
<Export(GetType(IMyAddin))>
Public Class MyLogger
    Implements IMyAddin

End Class
```

```csharp
[Export(typeof(IMyAddin))]
public class MyLogger : IMyAddin { }
```

<span data-ttu-id="037c1-124">В данном экспорте тип контракта имеет значение `IMyAddin` , так как оно указано в качестве параметра атрибута `Export` .</span><span class="sxs-lookup"><span data-stu-id="037c1-124">In this export, the contract type is `IMyAddin` because it is specified as a parameter of the `Export` attribute.</span></span> <span data-ttu-id="037c1-125">Экспортированный тип должен совпадать с типом контракта, быть производным от типа контракта либо реализовывать тип контракта, если он является интерфейсом.</span><span class="sxs-lookup"><span data-stu-id="037c1-125">The exported type must be either the same as the contract type, derive from the contract type, or implement the contract type if it is an interface.</span></span> <span data-ttu-id="037c1-126">В этом экспорте фактический тип `MyLogger` реализует интерфейс `IMyAddin`.</span><span class="sxs-lookup"><span data-stu-id="037c1-126">In this export, the actual type `MyLogger` implements the interface `IMyAddin`.</span></span> <span data-ttu-id="037c1-127">Имя контракта выводится из типа контракта, значит, этот экспорт будет соответствовать предыдущему импорту.</span><span class="sxs-lookup"><span data-stu-id="037c1-127">The contract name is inferred from the contract type, which means that this export will match the previous import.</span></span>

> [!NOTE]
> <span data-ttu-id="037c1-128">В общем случае экспорты и импорты следует объявлять в открытых классах или членах.</span><span class="sxs-lookup"><span data-stu-id="037c1-128">Exports and imports should usually be declared on public classes or members.</span></span> <span data-ttu-id="037c1-129">Другие объявления поддерживаются, однако экспорт или импорт закрытого, защищенного внутреннего члена нарушает модель изоляции для данной части и поэтому не рекомендуется к применению.</span><span class="sxs-lookup"><span data-stu-id="037c1-129">Other declarations are supported, but exporting or importing a private, protected, or internal member breaks the isolation model for the part and is therefore not recommended.</span></span>

<span data-ttu-id="037c1-130">Для соответствия экспорта и импорта требуется полное совпадение типа контракта.</span><span class="sxs-lookup"><span data-stu-id="037c1-130">The contract type must match exactly for the export and import to be considered a match.</span></span> <span data-ttu-id="037c1-131">Рассмотрим следующий экспорт.</span><span class="sxs-lookup"><span data-stu-id="037c1-131">Consider the following export.</span></span>

```vb
<Export()> 'WILL NOT match the previous import!
Public Class MyLogger
    Implements IMyAddin

End Class
```

```csharp
[Export] //WILL NOT match the previous import!
public class MyLogger : IMyAddin { }
```

<span data-ttu-id="037c1-132">В данном экспорте тип контракта имеет значение `MyLogger` вместо `IMyAddin`.</span><span class="sxs-lookup"><span data-stu-id="037c1-132">In this export, the contract type is `MyLogger` instead of `IMyAddin`.</span></span> <span data-ttu-id="037c1-133">Хотя `MyLogger` реализует `IMyAddin`и поэтому может быть сведен к объекту `IMyAddin` , данный экспорт не соответствует предыдущему импорту из-за несовпадения типов контракта.</span><span class="sxs-lookup"><span data-stu-id="037c1-133">Even though `MyLogger` implements `IMyAddin`, and therefore could be cast to an `IMyAddin` object, this export will not match the previous import because the contract types are not the same.</span></span>

<span data-ttu-id="037c1-134">В общем случае указывать имя контракта не требуется, и большинство контрактов следует определять с учетом типа контракта и метаданных.</span><span class="sxs-lookup"><span data-stu-id="037c1-134">In general, it is not necessary to specify the contract name, and most contracts should be defined in terms of the contract type and metadata.</span></span> <span data-ttu-id="037c1-135">Однако при определенных условиях важно напрямую указать имя контракта.</span><span class="sxs-lookup"><span data-stu-id="037c1-135">However, under certain circumstances, it is important to specify the contract name directly.</span></span> <span data-ttu-id="037c1-136">Чаще всего это происходит, когда класс экспортирует несколько значений, использующих общий тип, например, примитивы.</span><span class="sxs-lookup"><span data-stu-id="037c1-136">The most common case is when a class exports several values that share a common type, such as primitives.</span></span> <span data-ttu-id="037c1-137">Имя контракта можно указать в качестве первого параметра атрибута `Import` или `Export` .</span><span class="sxs-lookup"><span data-stu-id="037c1-137">The contract name can be specified as the first parameter of the `Import` or `Export` attribute.</span></span> <span data-ttu-id="037c1-138">В следующем коде показан импорт и экспорт с заданным именем контракта `MajorRevision`.</span><span class="sxs-lookup"><span data-stu-id="037c1-138">The following code shows an import and an export with a specified contract name of `MajorRevision`.</span></span>

```vb
Public Class MyExportClass

    'This one will match
    <Export("MajorRevision")>
    Public ReadOnly Property MajorRevision As Integer
        Get
            Return 4
        End Get
    End Property

    <Export("MinorRevision")>
    Public ReadOnly Property MinorRevision As Integer
        Get
            Return 16
        End Get
    End Property
End Class
```

```csharp
public class MyClass
{
    [Import("MajorRevision")]
    public int MajorRevision { get; set; }
}

public class MyExportClass
{
    [Export("MajorRevision")] //This one will match.
    public int MajorRevision = 4;

    [Export("MinorRevision")]
    public int MinorRevision = 16;
}
```

<span data-ttu-id="037c1-139">Если тип контракта не задан, он все равно выводится из типа импорта или экспорта.</span><span class="sxs-lookup"><span data-stu-id="037c1-139">If the contract type is not specified, it will still be inferred from the type of the import or export.</span></span> <span data-ttu-id="037c1-140">Однако даже в случае явного указания имени контракта для признания соответствия экспорта и импорта требуется полное совпадение типа контракта.</span><span class="sxs-lookup"><span data-stu-id="037c1-140">However, even if the contract name is specified explicitly, the contract type must also match exactly for the import and export to be considered a match.</span></span> <span data-ttu-id="037c1-141">Например, если бы поле `MajorRevision` было строкой, выводимые типы контракта не совпадали, поэтому экспорт не соответствовал бы импорту, несмотря на одинаковое имя контракта.</span><span class="sxs-lookup"><span data-stu-id="037c1-141">For example, if the `MajorRevision` field was a string, the inferred contract types would not match and the export would not match the import, despite having the same contract name.</span></span>

### <a name="importing-and-exporting-a-method"></a><span data-ttu-id="037c1-142">Импортирование и экспортирование метода</span><span class="sxs-lookup"><span data-stu-id="037c1-142">Importing and Exporting a Method</span></span>

<span data-ttu-id="037c1-143">Атрибут `Export` может декорировать метод по аналогии с декорированием класса, свойства или функции.</span><span class="sxs-lookup"><span data-stu-id="037c1-143">The `Export` attribute can also decorate a method, in the same way as a class, property, or function.</span></span> <span data-ttu-id="037c1-144">Экспорты метода должны указывать тип или имя контракта, так как тип нельзя вывести.</span><span class="sxs-lookup"><span data-stu-id="037c1-144">Method exports must specify a contract type or contract name, as the type cannot be inferred.</span></span> <span data-ttu-id="037c1-145">Указанный тип может быть настраиваемым делегатом или универсальным типом, например `Func`.</span><span class="sxs-lookup"><span data-stu-id="037c1-145">The specified type can be either a custom delegate or a generic type, such as `Func`.</span></span> <span data-ttu-id="037c1-146">Следующий класс экспортирует метод с именем `DoSomething`.</span><span class="sxs-lookup"><span data-stu-id="037c1-146">The following class exports a method named `DoSomething`.</span></span>

```vb
Public Class MyAddin

    'Explicitly specifying a generic type
    <Export(GetType(Func(Of Integer, String)))>
    Public Function DoSomething(ByVal TheParam As Integer) As String
        Return Nothing 'Function body goes here
    End Function

End Class
```

```csharp
public class MyAddin
{
    //Explicitly specifying a generic type.
    [Export(typeof(Func<int, string>))]
    public string DoSomething(int TheParam);
}
```

<span data-ttu-id="037c1-147">В этом классе метод `DoSomething` принимает один параметр `int` и возвращает `string`.</span><span class="sxs-lookup"><span data-stu-id="037c1-147">In this class, the `DoSomething` method takes a single `int` parameter and returns a `string`.</span></span> <span data-ttu-id="037c1-148">Для соответствия данному экспорту часть импорта должна объявить подходящий член.</span><span class="sxs-lookup"><span data-stu-id="037c1-148">To match this export, the importing part must declare an appropriate member.</span></span> <span data-ttu-id="037c1-149">Следующий класс импортирует метод `DoSomething` .</span><span class="sxs-lookup"><span data-stu-id="037c1-149">The following class imports the `DoSomething` method.</span></span>

```vb
Public Class MyClass1

    'Contract name must match!
    <Import()>
    Public Property MajorRevision As Func(Of Integer, String)
End Class
```

```csharp
public class MyClass
{
    [Import] //Contract name must match!
    public Func<int, string> DoSomething { get; set; }
}
```

<span data-ttu-id="037c1-150">Дополнительные сведения об использовании объекта `Func<T, T>` см. в разделе <xref:System.Func%602>.</span><span class="sxs-lookup"><span data-stu-id="037c1-150">For more information about how to use of the `Func<T, T>` object, see <xref:System.Func%602>.</span></span>

<a name="types_of_imports"></a>

## <a name="types-of-imports"></a><span data-ttu-id="037c1-151">Типы импортов</span><span class="sxs-lookup"><span data-stu-id="037c1-151">Types of Imports</span></span>

<span data-ttu-id="037c1-152">MEF поддерживает несколько типов импортов, включая динамический, отложенный, предварительный и необязательный.</span><span class="sxs-lookup"><span data-stu-id="037c1-152">MEF support several import types, including dynamic, lazy, prerequisite, and optional.</span></span>

### <a name="dynamic-imports"></a><span data-ttu-id="037c1-153">Динамические импорты</span><span class="sxs-lookup"><span data-stu-id="037c1-153">Dynamic Imports</span></span>

<span data-ttu-id="037c1-154">В некоторых случаях импортирующему классу может потребоваться сопоставить экспорты любого типа с определенным именем контракта.</span><span class="sxs-lookup"><span data-stu-id="037c1-154">In some cases, the importing class may want to match exports of any type that have a particular contract name.</span></span> <span data-ttu-id="037c1-155">В этом сценарии класс может объявить *динамический импорт*.</span><span class="sxs-lookup"><span data-stu-id="037c1-155">In this scenario, the class can declare a *dynamic import*.</span></span> <span data-ttu-id="037c1-156">Следующий импорт соответствует любому экспорту с именем контракта "TheString".</span><span class="sxs-lookup"><span data-stu-id="037c1-156">The following import matches any export with contract name "TheString".</span></span>

```vb
Public Class MyClass1

    <Import("TheString")>
    Public Property MyAddin

End Class
```

```csharp
public class MyClass
{
    [Import("TheString")]
    public dynamic MyAddin { get; set; }
}
```

<span data-ttu-id="037c1-157">Когда тип контракта выводится из ключевого слова `dynamic` , он будет соответствовать любому типу контракта.</span><span class="sxs-lookup"><span data-stu-id="037c1-157">When the contract type is inferred from the `dynamic` keyword, it will match any contract type.</span></span> <span data-ttu-id="037c1-158">В этом случае импорт должен **всегда** указывать имя контракта для сопоставления.</span><span class="sxs-lookup"><span data-stu-id="037c1-158">In this case, an import should **always** specify a contract name to match on.</span></span> <span data-ttu-id="037c1-159">(Если имя контракта не указано, импорт будет рассматриваться как не совпадающий экспорт.) Оба следующих экспорта будут соответствовать предыдущему импорту.</span><span class="sxs-lookup"><span data-stu-id="037c1-159">(If no contract name is specified, the import will be considered to match no exports.) Both of the following exports would match the previous import.</span></span>

```vb
<Export("TheString", GetType(IMyAddin))>
Public Class MyLogger
    Implements IMyAddin

End Class

<Export("TheString")>
Public Class MyToolbar

End Class
```

```csharp
[Export("TheString", typeof(IMyAddin))]
public class MyLogger : IMyAddin { }

[Export("TheString")]
public class MyToolbar { }
```

<span data-ttu-id="037c1-160">Очевидно, что импортирующий класс должен быть готов к работе с объектом произвольного типа.</span><span class="sxs-lookup"><span data-stu-id="037c1-160">Obviously, the importing class must be prepared to deal with an object of arbitrary type.</span></span>

### <a name="lazy-imports"></a><span data-ttu-id="037c1-161">Отложенные импорты</span><span class="sxs-lookup"><span data-stu-id="037c1-161">Lazy Imports</span></span>

<span data-ttu-id="037c1-162">В некоторых случаях импортирующему классу может потребоваться косвенная ссылка на импортированный объект, чтобы не создавать экземпляр этого объекта немедленно.</span><span class="sxs-lookup"><span data-stu-id="037c1-162">In some cases, the importing class may require an indirect reference to the imported object, so that the object is not instantiated immediately.</span></span> <span data-ttu-id="037c1-163">В этом сценарии класс может объявить *отложенный импорт* , используя тип контракта `Lazy<T>`.</span><span class="sxs-lookup"><span data-stu-id="037c1-163">In this scenario, the class can declare a *lazy import* by using a contract type of `Lazy<T>`.</span></span> <span data-ttu-id="037c1-164">Следующее свойство импорта объявляет отложенный импорт.</span><span class="sxs-lookup"><span data-stu-id="037c1-164">The following importing property declares a lazy import.</span></span>

```vb
Public Class MyClass1

    <Import()>
    Public Property MyAddin As Lazy(Of IMyAddin)

End Class
```

```csharp
public class MyClass
{
    [Import]
    public Lazy<IMyAddin> MyAddin { get; set; }
}
```

<span data-ttu-id="037c1-165">С точки зрения подсистемы композиции тип контракта `Lazy<T>` считается идентичным типу контракта `T`.</span><span class="sxs-lookup"><span data-stu-id="037c1-165">From the point of view of the composition engine, a contract type of `Lazy<T>` is considered identical to contract type of `T`.</span></span> <span data-ttu-id="037c1-166">Таким образом, предыдущий импорт будет соответствовать следующему экспорту.</span><span class="sxs-lookup"><span data-stu-id="037c1-166">Therefore, the previous import would match the following export.</span></span>

```vb
<Export(GetType(IMyAddin))>
Public Class MyLogger
    Implements IMyAddin

End Class
```

```csharp
[Export(typeof(IMyAddin))]
public class MyLogger : IMyAddin { }
```

<span data-ttu-id="037c1-167">Имя контракта и тип контракта можно указать в атрибуте `Import` для отложенного импорта, как описано выше в разделе "Основы импорта и экспорта".</span><span class="sxs-lookup"><span data-stu-id="037c1-167">The contract name and contract type can be specified in the `Import` attribute for a lazy import, as described earlier in the "Basic Imports and Exports" section.</span></span>

### <a name="prerequisite-imports"></a><span data-ttu-id="037c1-168">Предварительные импорты</span><span class="sxs-lookup"><span data-stu-id="037c1-168">Prerequisite Imports</span></span>

<span data-ttu-id="037c1-169">Экспортированные части MEF обычно создаются подсистемой композиции, когда поступает непосредственный запрос или требуется заполнить соответствующий импорт.</span><span class="sxs-lookup"><span data-stu-id="037c1-169">Exported MEF parts are typically created by the composition engine, in response to a direct request or the need to fill a matched import.</span></span> <span data-ttu-id="037c1-170">По умолчанию при создании части подсистема композиции использует конструктор без параметров.</span><span class="sxs-lookup"><span data-stu-id="037c1-170">By default, when creating a part, the composition engine uses the parameter-less constructor.</span></span> <span data-ttu-id="037c1-171">Чтобы подсистема использовала другой конструктор, можно отметить его с помощью атрибута `ImportingConstructor` .</span><span class="sxs-lookup"><span data-stu-id="037c1-171">To make the engine use a different constructor, you can mark it with the `ImportingConstructor` attribute.</span></span>

<span data-ttu-id="037c1-172">Для каждой части подсистема композиции может использовать только один конструктор.</span><span class="sxs-lookup"><span data-stu-id="037c1-172">Each part may have only one constructor for use by the composition engine.</span></span> <span data-ttu-id="037c1-173">Если не указать конструктор без параметров и атрибут `ImportingConstructor` или указать несколько атрибутов `ImportingConstructor`, возникает ошибка.</span><span class="sxs-lookup"><span data-stu-id="037c1-173">Providing no parameterless constructor and no `ImportingConstructor` attribute, or providing more than one `ImportingConstructor` attribute, will produce an error.</span></span>

<span data-ttu-id="037c1-174">Для заполнения параметров конструктора, помеченного атрибутом `ImportingConstructor` , все они автоматически объявляются в качестве импортов.</span><span class="sxs-lookup"><span data-stu-id="037c1-174">To fill the parameters of a constructor marked with the `ImportingConstructor` attribute, all of those parameters are automatically declared as imports.</span></span> <span data-ttu-id="037c1-175">Это удобный способ для объявления импортов, используемых во время инициализации части.</span><span class="sxs-lookup"><span data-stu-id="037c1-175">This is a convenient way to declare imports that are used during part initialization.</span></span> <span data-ttu-id="037c1-176">Следующий класс использует `ImportingConstructor` для объявления импорта.</span><span class="sxs-lookup"><span data-stu-id="037c1-176">The following class uses `ImportingConstructor` to declare an import.</span></span>

```vb
Public Class MyClass1

    Private _theAddin As IMyAddin

    'Parameterless constructor will NOT be used
    'because the ImportingConstructor
    'attribute is present.
    Public Sub New()

    End Sub

    'This constructor will be used.
    'An import with contract type IMyAddin
    'is declared automatically.
    <ImportingConstructor()>
    Public Sub New(ByVal MyAddin As IMyAddin)
        _theAddin = MyAddin
    End Sub

End Class
```

```csharp
public class MyClass
{
    private IMyAddin _theAddin;

    //Parameterless constructor will NOT be
    //used because the ImportingConstructor
    //attribute is present.
    public MyClass() { }

    //This constructor will be used.
    //An import with contract type IMyAddin is
    //declared automatically.
    [ImportingConstructor]
    public MyClass(IMyAddin MyAddin)
    {
        _theAddin = MyAddin;
    }
}
```

<span data-ttu-id="037c1-177">По умолчанию атрибут `ImportingConstructor` использует выводимые типы и имена контракта для всех импортов параметров.</span><span class="sxs-lookup"><span data-stu-id="037c1-177">By default, the `ImportingConstructor` attribute uses inferred contract types and contract names for all of the parameter imports.</span></span> <span data-ttu-id="037c1-178">Это можно переопределить посредством декорирования параметров с помощью атрибутов `Import` , которые затем могут явным образом определить тип контракта и имя контракта.</span><span class="sxs-lookup"><span data-stu-id="037c1-178">It is possible to override this by decorating the parameters with `Import` attributes, which can then define the contract type and contract name explicitly.</span></span> <span data-ttu-id="037c1-179">Следующий код демонстрирует конструктор, использующий такой синтаксис для импорта производного класса вместо родительского класса.</span><span class="sxs-lookup"><span data-stu-id="037c1-179">The following code demonstrates a constructor that uses this syntax to import a derived class instead of a parent class.</span></span>

```vb
<ImportingConstructor()>
Public Sub New(<Import(GetType(IMySubAddin))> ByVal MyAddin As IMyAddin)

End Sub
```

```csharp
[ImportingConstructor]
public MyClass([Import(typeof(IMySubAddin))]IMyAddin MyAddin)
{
    _theAddin = MyAddin;
}
```

<span data-ttu-id="037c1-180">В частности, вам следует внимательно отнестись к параметрам коллекции.</span><span class="sxs-lookup"><span data-stu-id="037c1-180">In particular, you should be careful with collection parameters.</span></span> <span data-ttu-id="037c1-181">Например, если вы задаете `ImportingConstructor` в конструкторе с параметром типа `IEnumerable<int>`, импорт будет соответствовать отдельному экспорту типа `IEnumerable<int>`, а не наборе экспортов типа `int`.</span><span class="sxs-lookup"><span data-stu-id="037c1-181">For example, if you specify `ImportingConstructor` on a constructor with a parameter of type `IEnumerable<int>`, the import will match a single export of type `IEnumerable<int>`, instead of a set of exports of type `int`.</span></span> <span data-ttu-id="037c1-182">Для соответствия набору экспортов типа `int`необходимо декорировать параметр атрибутом `ImportMany` .</span><span class="sxs-lookup"><span data-stu-id="037c1-182">To match a set of exports of type `int`, you have to decorate the parameter with the `ImportMany` attribute.</span></span>

<span data-ttu-id="037c1-183">Параметры, объявленные атрибутом `ImportingConstructor` в качестве импортов, также помечаются как *предварительные импорты*.</span><span class="sxs-lookup"><span data-stu-id="037c1-183">Parameters declared as imports by the `ImportingConstructor` attribute are also marked as *prerequisite imports*.</span></span> <span data-ttu-id="037c1-184">В общем случае MEF разрешает экспортам и импортам формировать *цикл*.</span><span class="sxs-lookup"><span data-stu-id="037c1-184">MEF normally allows exports and imports to form a *cycle*.</span></span> <span data-ttu-id="037c1-185">Например, цикл, в котором объект А импортирует объект Б, который в свою очередь импортирует объект А. В рядовой ситуации этот цикл не вызывает проблем, и контейнер композиции создает оба объекта обычным образом.</span><span class="sxs-lookup"><span data-stu-id="037c1-185">For example, a cycle is where object A imports object B, which in turn imports object A. Under ordinary circumstances, a cycle is not a problem, and the composition container constructs both objects normally.</span></span>

<span data-ttu-id="037c1-186">Если импортированное значение требуется конструктору части, этот объект не может принимать участие в цикле.</span><span class="sxs-lookup"><span data-stu-id="037c1-186">When an imported value is required by the constructor of a part, that object cannot participate in a cycle.</span></span> <span data-ttu-id="037c1-187">Если объект А требует, чтобы перед его созданием был создан объект Б, а объект Б импортирует объект А, такой цикл будет невозможно разрешить, и возникнет ошибка композиции.</span><span class="sxs-lookup"><span data-stu-id="037c1-187">If object A requires that object B be constructed before it can be constructed itself, and object B imports object A, then the cycle will be unable to resolve and a composition error will occur.</span></span> <span data-ttu-id="037c1-188">Таким образом, импорты, объявленные в параметрах конструктора, являются предварительными и должны быть заполнены до того, как можно будет использовать любой экспорт из объекта, которому требуются такие импорты.</span><span class="sxs-lookup"><span data-stu-id="037c1-188">Imports declared on constructor parameters are therefore prerequisite imports, which must all be filled before any of the exports from the object that requires them can be used.</span></span>

### <a name="optional-imports"></a><span data-ttu-id="037c1-189">Необязательные импорты</span><span class="sxs-lookup"><span data-stu-id="037c1-189">Optional Imports</span></span>

<span data-ttu-id="037c1-190">Атрибут `Import` указывает требования для части к функции.</span><span class="sxs-lookup"><span data-stu-id="037c1-190">The `Import` attribute specifies a requirement for the part to function.</span></span> <span data-ttu-id="037c1-191">Если импорт нельзя выполнить, произойдет сбой композиции этой части, а сама часть будет недоступна.</span><span class="sxs-lookup"><span data-stu-id="037c1-191">If an import cannot be fulfilled, the composition of that part will fail and the part will not be available.</span></span>

<span data-ttu-id="037c1-192">Вы можете указать, что импорт является *необязательным* , с помощью свойства `AllowDefault` .</span><span class="sxs-lookup"><span data-stu-id="037c1-192">You can specify that an import is *optional* by using the `AllowDefault` property.</span></span> <span data-ttu-id="037c1-193">В этом случае композиция будет выполнена, даже если импорт не соответствует ни одному из доступных экспортов, а для свойства импорта будет задано значение по умолчанию для его типа свойства (`null` для свойств объекта, `false` для логических значений или ноль для числовых свойств). Следующий класс использует необязательный импорт.</span><span class="sxs-lookup"><span data-stu-id="037c1-193">In this case, the composition will succeed even if the import does not match any available exports, and the importing property will be set to the default for its property type (`null` for object properties, `false` for Booleans, or zero for numeric properties.) The following class uses an optional import.</span></span>

```vb
Public Class MyClass1

    <Import(AllowDefault:=True)>
    Public Property thePlugin As Plugin

    'If no matching export is available,
    'thePlugin will be set to null.
End Class
```

```csharp
public class MyClass
{
    [Import(AllowDefault = true)]
    public Plugin thePlugin { get; set; }

    //If no matching export is available,
    //thePlugin will be set to null.
}
```

### <a name="importing-multiple-objects"></a><span data-ttu-id="037c1-194">Импорт нескольких объектов</span><span class="sxs-lookup"><span data-stu-id="037c1-194">Importing Multiple Objects</span></span>

<span data-ttu-id="037c1-195">Создание атрибута `Import` выполняется успешно только тогда, когда он соответствует одному и только одному экспорту.</span><span class="sxs-lookup"><span data-stu-id="037c1-195">The `Import` attribute will only be successfully composed when it matches one and only one export.</span></span> <span data-ttu-id="037c1-196">В других случаях возникает ошибка композиции.</span><span class="sxs-lookup"><span data-stu-id="037c1-196">Other cases will produce a composition error.</span></span> <span data-ttu-id="037c1-197">Чтобы импортировать несколько экспортов, соответствующих одному контракту, используйте атрибут `ImportMany` .</span><span class="sxs-lookup"><span data-stu-id="037c1-197">To import more than one export that matches the same contract, use the `ImportMany` attribute.</span></span> <span data-ttu-id="037c1-198">Помеченные им импорты всегда являются необязательными.</span><span class="sxs-lookup"><span data-stu-id="037c1-198">Imports marked with this attribute are always optional.</span></span> <span data-ttu-id="037c1-199">Например, сбой композиции не возникнет, если отсутствуют соответствующие экспорты.</span><span class="sxs-lookup"><span data-stu-id="037c1-199">For example, composition will not fail if no matching exports are present.</span></span> <span data-ttu-id="037c1-200">Следующий класс импортирует любое число экспортов типа `IMyAddin`.</span><span class="sxs-lookup"><span data-stu-id="037c1-200">The following class imports any number of exports of type `IMyAddin`.</span></span>

```vb
Public Class MyClass1

    <ImportMany()>
    Public Property MyAddin As IEnumerable(Of IMyAddin)

End Class
```

```csharp
public class MyClass
{
    [ImportMany]
    public IEnumerable<IMyAddin> MyAddin { get; set; }
}
```

<span data-ttu-id="037c1-201">Для доступа к импортированному массиву можно использовать стандартные методы и синтаксис `IEnumerable<T>` .</span><span class="sxs-lookup"><span data-stu-id="037c1-201">The imported array can be accessed by using ordinary `IEnumerable<T>` syntax and methods.</span></span> <span data-ttu-id="037c1-202">Вместо этого можно также использовать обычный массив (`IMyAddin[]`).</span><span class="sxs-lookup"><span data-stu-id="037c1-202">It is also possible to use an ordinary array (`IMyAddin[]`) instead.</span></span>

<span data-ttu-id="037c1-203">Такой подход может быть очень важен при его использовании совместно с синтаксисом `Lazy<T>` .</span><span class="sxs-lookup"><span data-stu-id="037c1-203">This pattern can be very important when you use it in combination with the `Lazy<T>` syntax.</span></span> <span data-ttu-id="037c1-204">Например, с помощью `ImportMany`, `IEnumerable<T>`и `Lazy<T>`вы можете импортировать косвенные ссылки на любое число объектов и создать экземпляры только для тех из них, в которых возникает необходимость.</span><span class="sxs-lookup"><span data-stu-id="037c1-204">For example, by using `ImportMany`, `IEnumerable<T>`, and `Lazy<T>`, you can import indirect references to any number of objects and only instantiate the ones that become necessary.</span></span> <span data-ttu-id="037c1-205">Этот подход продемонстрирован в следующем классе.</span><span class="sxs-lookup"><span data-stu-id="037c1-205">The following class shows this pattern.</span></span>

```vb
Public Class MyClass1

    <ImportMany()>
    Public Property MyAddin As IEnumerable(Of Lazy(Of IMyAddin))

End Class
```

```csharp
public class MyClass
{
    [ImportMany]
    public IEnumerable<Lazy<IMyAddin>> MyAddin { get; set; }
}
```

<a name="avoiding_discovery"></a>

## <a name="avoiding-discovery"></a><span data-ttu-id="037c1-206">Предотвращение обнаружения</span><span class="sxs-lookup"><span data-stu-id="037c1-206">Avoiding Discovery</span></span>

<span data-ttu-id="037c1-207">В некоторых случаях вам может понадобиться предотвратить обнаружение вхождения части в каталог.</span><span class="sxs-lookup"><span data-stu-id="037c1-207">In some cases, you may want to prevent a part from being discovered as part of a catalog.</span></span> <span data-ttu-id="037c1-208">Например, часть может быть базовым классом, предназначенным для наследования, а не для использования.</span><span class="sxs-lookup"><span data-stu-id="037c1-208">For example, the part may be a base class intended to be inherited from, but not used.</span></span> <span data-ttu-id="037c1-209">Этого можно добиться двумя следующими способами.</span><span class="sxs-lookup"><span data-stu-id="037c1-209">There are two ways to accomplish this.</span></span> <span data-ttu-id="037c1-210">Во-первых, вы можете использовать ключевое слово `abstract` для класса части.</span><span class="sxs-lookup"><span data-stu-id="037c1-210">First, you can use the `abstract` keyword on the part class.</span></span> <span data-ttu-id="037c1-211">Абстрактные классы никогда не предоставляют экспорты, хотя могут предоставлять унаследованные экспорты производным от них классам.</span><span class="sxs-lookup"><span data-stu-id="037c1-211">Abstract classes never provide exports, although they can provide inherited exports to classes that derive from them.</span></span>

<span data-ttu-id="037c1-212">Если класс нельзя сделать абстрактным, вы можете декорировать его атрибутом `PartNotDiscoverable` .</span><span class="sxs-lookup"><span data-stu-id="037c1-212">If the class cannot be made abstract, you can decorate it with the `PartNotDiscoverable` attribute.</span></span> <span data-ttu-id="037c1-213">Часть, декорированная этим атрибутом, не будет включена ни в какие каталоги.</span><span class="sxs-lookup"><span data-stu-id="037c1-213">A part decorated with this attribute will not be included in any catalogs.</span></span> <span data-ttu-id="037c1-214">В следующем примере демонстрируются такие подходы.</span><span class="sxs-lookup"><span data-stu-id="037c1-214">The following example demonstrates these patterns.</span></span> <span data-ttu-id="037c1-215">`DataOne` будет обнаружен каталогом.</span><span class="sxs-lookup"><span data-stu-id="037c1-215">`DataOne` will be discovered by the catalog.</span></span> <span data-ttu-id="037c1-216">Поскольку `DataTwo` является абстрактным, он не будет обнаружен.</span><span class="sxs-lookup"><span data-stu-id="037c1-216">Since `DataTwo` is abstract, it will not be discovered.</span></span> <span data-ttu-id="037c1-217">Поскольку `DataThree` использовал атрибут `PartNotDiscoverable` , он не будет обнаружен.</span><span class="sxs-lookup"><span data-stu-id="037c1-217">Since `DataThree` used the `PartNotDiscoverable` attribute, it will not be discovered.</span></span>

```vb
<Export()>
Public Class DataOne
    'This part will be discovered
    'as normal by the catalog.
End Class

<Export()>
Public MustInherit Class DataTwo
    'This part will not be discovered
    'by the catalog.
End Class

<PartNotDiscoverable()>
<Export()>
Public Class DataThree
    'This part will also not be discovered
    'by the catalog.
End Class
```

```csharp
[Export]
public class DataOne
{
    //This part will be discovered
    //as normal by the catalog.
}

[Export]
public abstract class DataTwo
{
    //This part will not be discovered
    //by the catalog.
}

[PartNotDiscoverable]
[Export]
public class DataThree
{
    //This part will also not be discovered
    //by the catalog.
}
```

<a name="metadata_and_metadata_views"></a>

## <a name="metadata-and-metadata-views"></a><span data-ttu-id="037c1-218">Метаданные и их представления</span><span class="sxs-lookup"><span data-stu-id="037c1-218">Metadata and Metadata Views</span></span>

<span data-ttu-id="037c1-219">Экспорты могут предоставлять дополнительные сведения о себе, которые называются *метаданными*.</span><span class="sxs-lookup"><span data-stu-id="037c1-219">Exports can provide additional information about themselves known as *metadata*.</span></span> <span data-ttu-id="037c1-220">Метаданные можно использовать для передачи свойств экспортированного объекта в импортирующую часть.</span><span class="sxs-lookup"><span data-stu-id="037c1-220">Metadata can be used to convey properties of the exported object to the importing part.</span></span> <span data-ttu-id="037c1-221">Импортирующая часть может использовать эти данные для выбора используемого экспорта или для сбора информации об экспорте без необходимости его создания.</span><span class="sxs-lookup"><span data-stu-id="037c1-221">The importing part can use this data to decide which exports to use, or to gather information about an export without having to construct it.</span></span> <span data-ttu-id="037c1-222">По этой причине для использования метаданных импорт должен быть отложенным.</span><span class="sxs-lookup"><span data-stu-id="037c1-222">For this reason, an import must be lazy to use metadata.</span></span>

<span data-ttu-id="037c1-223">Чтобы использовать метаданные обычно объявляется интерфейс, называемый *представлением метаданных*, который объявляет о доступности метаданных.</span><span class="sxs-lookup"><span data-stu-id="037c1-223">To use metadata, you typically declare an interface known as a *metadata view*, which declares what metadata will be available.</span></span> <span data-ttu-id="037c1-224">Интерфейс представления метаданных должен иметь только свойства, и эти свойства должны иметь методы доступа `get` .</span><span class="sxs-lookup"><span data-stu-id="037c1-224">The metadata view interface must have only properties, and those properties must have `get` accessors.</span></span> <span data-ttu-id="037c1-225">Следующий интерфейс является примером представления метаданных.</span><span class="sxs-lookup"><span data-stu-id="037c1-225">The following interface is an example metadata view.</span></span>

```vb
Public Interface IPluginMetadata

    ReadOnly Property Name As String

    <DefaultValue(1)>
    ReadOnly Property Version As Integer

End Interface
```

```csharp
public interface IPluginMetadata
{
    string Name { get; }

    [DefaultValue(1)]
    int Version { get; }
}
```

<span data-ttu-id="037c1-226">В качестве представления метаданных также можно использовать общую коллекцию `IDictionary<string, object>`, однако это нивелирует преимущества проверки типа и поэтому не рекомендовано к применению.</span><span class="sxs-lookup"><span data-stu-id="037c1-226">It is also possible to use a generic collection, `IDictionary<string, object>`, as a metadata view, but this forfeits the benefits of type checking and should be avoided.</span></span>

<span data-ttu-id="037c1-227">В общем случае все указанные в представлении метаданных свойства являются обязательными, а любые экспорты, которые их не предоставляют, не будут считаться соответствующими.</span><span class="sxs-lookup"><span data-stu-id="037c1-227">Ordinarily, all of the properties named in the metadata view are required, and any exports that do not provide them will not be considered a match.</span></span> <span data-ttu-id="037c1-228">Атрибут `DefaultValue` указывает на то, что свойство является необязательным.</span><span class="sxs-lookup"><span data-stu-id="037c1-228">The `DefaultValue` attribute specifies that a property is optional.</span></span> <span data-ttu-id="037c1-229">Если свойство не задано, ему назначается значение по умолчанию, указанное в качестве параметра `DefaultValue`.</span><span class="sxs-lookup"><span data-stu-id="037c1-229">If the property is not included, it will be assigned the default value specified as a parameter of `DefaultValue`.</span></span> <span data-ttu-id="037c1-230">Ниже приведены два разных класса, декорированных метаданными.</span><span class="sxs-lookup"><span data-stu-id="037c1-230">The following are two different classes decorated with metadata.</span></span> <span data-ttu-id="037c1-231">Оба этих класса будут соответствовать предыдущему представлению метаданных.</span><span class="sxs-lookup"><span data-stu-id="037c1-231">Both of these classes would match the previous metadata view.</span></span>

```vb
<Export(GetType(IPlugin))>
<ExportMetadata("Name", "Logger")>
<ExportMetadata("Version", 4)>
Public Class MyLogger
    Implements IPlugin

End Class

'Version is not required because of the DefaultValue
<Export(GetType(IPlugin))>
<ExportMetadata("Name", "Disk Writer")>
Public Class DWriter
    Implements IPlugin

End Class
```

```csharp
[Export(typeof(IPlugin)),
    ExportMetadata("Name", "Logger"),
    ExportMetadata("Version", 4)]
public class Logger : IPlugin
{
}

[Export(typeof(IPlugin)),
    ExportMetadata("Name", "Disk Writer")]
    //Version is not required because of the DefaultValue
public class DWriter : IPlugin
{
}
```

<span data-ttu-id="037c1-232">Метаданные указываются после атрибута `Export` с помощью атрибута `ExportMetadata` .</span><span class="sxs-lookup"><span data-stu-id="037c1-232">Metadata is expressed after the `Export` attribute by using the `ExportMetadata` attribute.</span></span> <span data-ttu-id="037c1-233">Каждый элемент метаданных состоит из пары имя-значение.</span><span class="sxs-lookup"><span data-stu-id="037c1-233">Each piece of metadata is composed of a name/value pair.</span></span> <span data-ttu-id="037c1-234">Часть имени в метаданных должна совпадать с именем соответствующего свойства в представлении метаданных, а значение будет назначено этому свойству.</span><span class="sxs-lookup"><span data-stu-id="037c1-234">The name portion of the metadata must match the name of the appropriate property in the metadata view, and the value will be assigned to that property.</span></span>

<span data-ttu-id="037c1-235">Используемое представление метаданных (если оно имеется) задает импортер.</span><span class="sxs-lookup"><span data-stu-id="037c1-235">It is the importer that specifies what metadata view, if any, will be in use.</span></span> <span data-ttu-id="037c1-236">Импорт с метаданными объявляется как отложенный, при этом интерфейс метаданных используется в качестве второго параметра типа для `Lazy<T,T>`.</span><span class="sxs-lookup"><span data-stu-id="037c1-236">An import with metadata is declared as a lazy import, with the metadata interface as the second type parameter to `Lazy<T,T>`.</span></span> <span data-ttu-id="037c1-237">Следующий класс импортирует предыдущую часть с метаданными.</span><span class="sxs-lookup"><span data-stu-id="037c1-237">The following class imports the previous part with metadata.</span></span>

```vb
Public Class Addin

    <Import()>
    Public Property plugin As Lazy(Of IPlugin, IPluginMetadata)
End Class
```

```csharp
public class Addin
{
    [Import]
    public Lazy<IPlugin, IPluginMetadata> plugin;
}
```

<span data-ttu-id="037c1-238">Во многих случаях вам потребуется объединить метаданные с атрибутом `ImportMany` , чтобы выполнить синтаксический анализ доступных импортов, выбрать один из них и создать его экземпляр либо отфильтровать коллекцию для соответствия определенному условию.</span><span class="sxs-lookup"><span data-stu-id="037c1-238">In many cases, you will want to combine metadata with the `ImportMany` attribute, in order to parse through the available imports and choose and instantiate only one, or filter a collection to match a certain condition.</span></span> <span data-ttu-id="037c1-239">Следующий класс создает экземпляры только тех объектов `IPlugin` , у которых `Name` имеет значение "Logger".</span><span class="sxs-lookup"><span data-stu-id="037c1-239">The following class instantiates only `IPlugin` objects that have the `Name` value "Logger".</span></span>

```vb
Public Class User

    <ImportMany()>
    Public Property plugins As IEnumerable(Of Lazy(Of IPlugin, IPluginMetadata))

    Public Function InstantiateLogger() As IPlugin

        Dim logger As IPlugin
        logger = Nothing

        For Each Plugin As Lazy(Of IPlugin, IPluginMetadata) In plugins
            If Plugin.Metadata.Name = "Logger" Then
                logger = Plugin.Value
            End If
        Next
        Return logger
    End Function

End Class
```

```csharp
public class User
{
    [ImportMany]
    public IEnumerable<Lazy<IPlugin, IPluginMetadata>> plugins;

    public IPlugin InstantiateLogger()
    {
        IPlugin logger = null;

        foreach (Lazy<IPlugin, IPluginMetadata> plugin in plugins)
        {
            if (plugin.Metadata.Name == "Logger")
                logger = plugin.Value;
        }
        return logger;
    }
}
```

<a name="import_and_export_inheritance"></a>

## <a name="import-and-export-inheritance"></a><span data-ttu-id="037c1-240">Наследование импорта и экспорта</span><span class="sxs-lookup"><span data-stu-id="037c1-240">Import and Export Inheritance</span></span>

<span data-ttu-id="037c1-241">Если класс наследует от части, он также может стать частью.</span><span class="sxs-lookup"><span data-stu-id="037c1-241">If a class inherits from a part, that class may also become a part.</span></span> <span data-ttu-id="037c1-242">Импорты всегда наследуются подклассами.</span><span class="sxs-lookup"><span data-stu-id="037c1-242">Imports are always inherited by subclasses.</span></span> <span data-ttu-id="037c1-243">Таким образом, подкласс части всегда будет частью и будет иметь те же импорты, что и его родительский класс.</span><span class="sxs-lookup"><span data-stu-id="037c1-243">Therefore, a subclass of a part will always be a part, with the same imports as its parent class.</span></span>

<span data-ttu-id="037c1-244">Экспорты, объявленные с помощью атрибута `Export` , не наследуются подклассами.</span><span class="sxs-lookup"><span data-stu-id="037c1-244">Exports declared by using the `Export` attribute are not inherited by subclasses.</span></span> <span data-ttu-id="037c1-245">Однако часть может экспортировать сама себя с помощью атрибута `InheritedExport` .</span><span class="sxs-lookup"><span data-stu-id="037c1-245">However, a part can export itself by using the `InheritedExport` attribute.</span></span> <span data-ttu-id="037c1-246">Подклассы этой части будут наследовать и предоставлять тот же экспорт, включая имя и тип контракта.</span><span class="sxs-lookup"><span data-stu-id="037c1-246">Subclasses of the part will inherit and provide the same export, including contract name and contract type.</span></span> <span data-ttu-id="037c1-247">В отличие от атрибута `Export` атрибут `InheritedExport` можно применить не на уровне членов, а только на уровне классов.</span><span class="sxs-lookup"><span data-stu-id="037c1-247">Unlike an `Export` attribute, `InheritedExport` can be applied only at the class level, and not at the member level.</span></span> <span data-ttu-id="037c1-248">Таким образом, экспорты на уровне членов никогда не наследуются.</span><span class="sxs-lookup"><span data-stu-id="037c1-248">Therefore, member-level exports can never be inherited.</span></span>

<span data-ttu-id="037c1-249">Четыре следующих класса демонстрируют принципы наследования импорта и экспорта.</span><span class="sxs-lookup"><span data-stu-id="037c1-249">The following four classes demonstrate the principles of import and export inheritance.</span></span> <span data-ttu-id="037c1-250">`NumTwo` наследует от `NumOne`, поэтому `NumTwo` импортирует `IMyData`.</span><span class="sxs-lookup"><span data-stu-id="037c1-250">`NumTwo` inherits from `NumOne`, so `NumTwo` will import `IMyData`.</span></span> <span data-ttu-id="037c1-251">Обычные импорты не наследуются, поэтому `NumTwo` ничего не экспортирует.</span><span class="sxs-lookup"><span data-stu-id="037c1-251">Ordinary exports are not inherited, so `NumTwo` will not export anything.</span></span> <span data-ttu-id="037c1-252">Тип`NumFour` наследуется от типа `NumThree`.</span><span class="sxs-lookup"><span data-stu-id="037c1-252">`NumFour` inherits from `NumThree`.</span></span> <span data-ttu-id="037c1-253">Поскольку `NumThree` использовал `InheritedExport`, `NumFour` имеет один экспорт с типом контракта `NumThree`.</span><span class="sxs-lookup"><span data-stu-id="037c1-253">Because `NumThree` used `InheritedExport`, `NumFour` has one export with contract type `NumThree`.</span></span> <span data-ttu-id="037c1-254">Экспорты на уровне членов никогда не наследуются, поэтому `IMyData` не экспортируется.</span><span class="sxs-lookup"><span data-stu-id="037c1-254">Member-level exports are never inherited, so `IMyData` is not exported.</span></span>

```vb
<Export()>
Public Class NumOne
    <Import()>
    Public Property MyData As IMyData
End Class

Public Class NumTwo
    Inherits NumOne

    'Imports are always inherited, so NumTwo will
    'Import IMyData

    'Ordinary exports are not inherited, so
    'NumTwo will NOT export anything.  As a result it
    'will not be discovered by the catalog!

End Class

<InheritedExport()>
Public Class NumThree

    <Export()>
    Public Property MyData As IMyData

    'This part provides two exports, one of
    'contract type NumThree, and one of
    'contract type IMyData.

End Class

Public Class NumFour
    Inherits NumThree

    'Because NumThree used InheritedExport,
    'this part has one export with contract
    'type NumThree.

    'Member-level exports are never inherited,
    'so IMyData is not exported.

End Class
```

```csharp
[Export]
public class NumOne
{
    [Import]
    public IMyData MyData { get; set; }
}

public class NumTwo : NumOne
{
    //Imports are always inherited, so NumTwo will
    //import IMyData.

    //Ordinary exports are not inherited, so
    //NumTwo will NOT export anything. As a result it
    //will not be discovered by the catalog!
}

[InheritedExport]
public class NumThree
{
    [Export]
    Public IMyData MyData { get; set; }

    //This part provides two exports, one of
    //contract type NumThree, and one of
    //contract type IMyData.
}

public class NumFour : NumThree
{
    //Because NumThree used InheritedExport,
    //this part has one export with contract
    //type NumThree.

    //Member-level exports are never inherited,
    //so IMyData is not exported.
}
```

<span data-ttu-id="037c1-255">При наличии метаданных, связанных с атрибутом `InheritedExport` , они также наследуются.</span><span class="sxs-lookup"><span data-stu-id="037c1-255">If there is metadata associated with an `InheritedExport` attribute, that metadata will also be inherited.</span></span> <span data-ttu-id="037c1-256">(Дополнительные сведения см. в разделе "метаданные и представления метаданных" выше.) Наследованные метаданные не могут быть изменены подклассом.</span><span class="sxs-lookup"><span data-stu-id="037c1-256">(For more information, see the earlier "Metadata and Metadata Views" section.) Inherited metadata cannot be modified by the subclass.</span></span> <span data-ttu-id="037c1-257">Однако за счет повторного объявления атрибута `InheritedExport` с таким же именем и типом контракта и новыми метаданными подкласс может заменить унаследованные метаданные на новые.</span><span class="sxs-lookup"><span data-stu-id="037c1-257">However, by re-declaring the `InheritedExport` attribute with the same contract name and contract type, but with new metadata, the subclass can replace the inherited metadata with new metadata.</span></span> <span data-ttu-id="037c1-258">Следующий класс демонстрирует этот принцип.</span><span class="sxs-lookup"><span data-stu-id="037c1-258">The following class demonstrates this principle.</span></span> <span data-ttu-id="037c1-259">Часть `MegaLogger` наследует от `Logger` и включает атрибут `InheritedExport` .</span><span class="sxs-lookup"><span data-stu-id="037c1-259">The `MegaLogger` part inherits from `Logger` and includes the `InheritedExport` attribute.</span></span> <span data-ttu-id="037c1-260">Поскольку `MegaLogger` повторно объявляет новые метаданные с именем Status, он не наследует метаданные Name и Version от `Logger`.</span><span class="sxs-lookup"><span data-stu-id="037c1-260">Since `MegaLogger` re-declares new metadata named Status, it does not inherit the Name and Version metadata from `Logger`.</span></span>

```vb
<InheritedExport(GetType(IPlugin))>
<ExportMetadata("Name", "Logger")>
<ExportMetadata("Version", 4)>
Public Class Logger
    Implements IPlugin

    'Exports with contract type IPlugin
    'and metadata "Name" and "Version".
End Class

Public Class SuperLogger
    Inherits Logger

    'Exports with contract type IPlugin and
    'metadata "Name" and "Version", exactly the same
    'as the Logger class.

End Class

<InheritedExport(GetType(IPlugin))>
<ExportMetadata("Status", "Green")>
Public Class MegaLogger
    Inherits Logger

    'Exports with contract type IPlugin and
    'metadata "Status" only. Re-declaring
    'the attribute replaces all metadata.

End Class
```

```csharp
[InheritedExport(typeof(IPlugin)),
    ExportMetadata("Name", "Logger"),
    ExportMetadata("Version", 4)]
public class Logger : IPlugin
{
    //Exports with contract type IPlugin and
    //metadata "Name" and "Version".
}

public class SuperLogger : Logger
{
    //Exports with contract type IPlugin and
    //metadata "Name" and "Version", exactly the same
    //as the Logger class.
}

[InheritedExport(typeof(IPlugin)),
    ExportMetadata("Status", "Green")]
public class MegaLogger : Logger        {
    //Exports with contract type IPlugin and
    //metadata "Status" only. Re-declaring
    //the attribute replaces all metadata.
}
```

<span data-ttu-id="037c1-261">При повторном объявлении атрибута `InheritedExport` для переопределения метаданных убедитесь в совпадении типов контракта.</span><span class="sxs-lookup"><span data-stu-id="037c1-261">When re-declaring the `InheritedExport` attribute to override metadata, make sure that the contract types are the same.</span></span> <span data-ttu-id="037c1-262">(В предыдущем примере `IPlugin` является типом контракта.) Если они отличаются, вместо переопределения второй атрибут будет создавать второй, Независимый экспорт из части.</span><span class="sxs-lookup"><span data-stu-id="037c1-262">(In the previous example, `IPlugin` is the contract type.) If they differ, instead of overriding, the second attribute will create a second, independent export from the part.</span></span> <span data-ttu-id="037c1-263">В общем случае это означает, что нужно явно задавать тип контракта при переопределении атрибута `InheritedExport` , как показано в предыдущем примере.</span><span class="sxs-lookup"><span data-stu-id="037c1-263">Generally, this means that you will have to explicitly specify the contract type when you override an `InheritedExport` attribute, as shown in the previous example.</span></span>

<span data-ttu-id="037c1-264">Поскольку экземпляры для интерфейсов нельзя создавать непосредственно, в общем случае их нельзя декорировать атрибутами `Export` или `Import` .</span><span class="sxs-lookup"><span data-stu-id="037c1-264">Since interfaces cannot be instantiated directly, they generally cannot be decorated with `Export` or `Import` attributes.</span></span> <span data-ttu-id="037c1-265">Однако интерфейс можно декорировать атрибутом `InheritedExport` на уровне интерфейсов, и этот экспорт наравне со всеми сопоставленными метаданными будет наследоваться любыми реализующими классами.</span><span class="sxs-lookup"><span data-stu-id="037c1-265">However, an interface can be decorated with an `InheritedExport` attribute at the interface level, and that export along with any associated metadata will be inherited by any implementing classes.</span></span> <span data-ttu-id="037c1-266">Однако сам интерфейс не будет доступен в качестве части.</span><span class="sxs-lookup"><span data-stu-id="037c1-266">The interface itself will not be available as a part, however.</span></span>

<a name="custom_export_attributes"></a>

## <a name="custom-export-attributes"></a><span data-ttu-id="037c1-267">Настраиваемые атрибуты экспорта</span><span class="sxs-lookup"><span data-stu-id="037c1-267">Custom Export Attributes</span></span>

<span data-ttu-id="037c1-268">Базовые атрибуты экспорта `Export` и `InheritedExport`можно расширить для включения метаданных в качестве свойств атрибута.</span><span class="sxs-lookup"><span data-stu-id="037c1-268">The basic export attributes, `Export` and `InheritedExport`, can be extended to include metadata as attribute properties.</span></span> <span data-ttu-id="037c1-269">Эту методику удобно использовать для применения одних метаданных многим частям или создания дерева наследования атрибутов метаданных.</span><span class="sxs-lookup"><span data-stu-id="037c1-269">This technique is useful for applying similar metadata to many parts, or creating an inheritance tree of metadata attributes.</span></span>

<span data-ttu-id="037c1-270">Настраиваемый атрибут может задавать тип контракта, имя контракта или любые другие метаданные.</span><span class="sxs-lookup"><span data-stu-id="037c1-270">A custom attribute can specify the contract type, the contract name, or any other metadata.</span></span> <span data-ttu-id="037c1-271">Чтобы определить настраиваемый атрибут, наследующий от `ExportAttribute` (или `InheritedExportAttribute`) класс должен быть декорирован атрибутом `MetadataAttribute` .</span><span class="sxs-lookup"><span data-stu-id="037c1-271">In order to define a custom attribute, a class inheriting from `ExportAttribute` (or `InheritedExportAttribute`) must be decorated with the `MetadataAttribute` attribute.</span></span> <span data-ttu-id="037c1-272">Следующий класс определяет настраиваемый атрибут.</span><span class="sxs-lookup"><span data-stu-id="037c1-272">The following class defines a custom attribute.</span></span>

```vb
<MetadataAttribute()>
<AttributeUsage(AttributeTargets.Class, AllowMultiple:=false)>
Public Class MyAttribute
    Inherits ExportAttribute

    Public Property MyMetadata As String

    Public Sub New(ByVal myMetadata As String)
        MyBase.New(GetType(IMyAddin))

        myMetadata = myMetadata
    End Sub

End Class
```

```csharp
[MetadataAttribute]
[AttributeUsage(AttributeTargets.Class, AllowMultiple=false)]
public class MyAttribute : ExportAttribute
{
    public MyAttribute(string myMetadata)
        : base(typeof(IMyAddin))
    {
        MyMetadata = myMetadata;
    }

    public string MyMetadata { get; private set; }
}
```

<span data-ttu-id="037c1-273">Этот класс определяет настраиваемый атрибут, имеющий имя `MyAttribute` , тип контракта `IMyData` и некоторые метаданные с именем `MyMetadata`.</span><span class="sxs-lookup"><span data-stu-id="037c1-273">This class defines a custom attribute named `MyAttribute` with contract type `IMyData` and some metadata named `MyMetadata`.</span></span> <span data-ttu-id="037c1-274">Все свойства в классе, помеченном атрибутом `MetadataAttribute` , считаются метаданными, определенными в настраиваемом атрибуте.</span><span class="sxs-lookup"><span data-stu-id="037c1-274">All properties in a class marked with the `MetadataAttribute` attribute are considered to be metadata defined in the custom attribute.</span></span> <span data-ttu-id="037c1-275">Два следующих объявления эквивалентны.</span><span class="sxs-lookup"><span data-stu-id="037c1-275">The following two declarations are equivalent.</span></span>

```vb
<Export(GetType(IMyAddin))>
<ExportMetadata("MyMetadata", "theData")>
Public Property myAddin As MyAddin
```

```vb
<MyAttribute("theData")>
Public Property myAddin As MyAddin
```

```csharp
[Export(typeof(IMyAddin)),
    ExportMetadata("MyMetadata", "theData")]
public MyAddin myAddin { get; set; }
```

```csharp
[MyAttribute("theData")]
public MyAddin myAddin { get; set; }
```

<span data-ttu-id="037c1-276">В первом объявлении тип контракта и метаданные заданы явным образом.</span><span class="sxs-lookup"><span data-stu-id="037c1-276">In the first declaration, the contract type and metadata are explicitly defined.</span></span> <span data-ttu-id="037c1-277">Во втором объявлении тип контракта и метаданные заданы неявно в настраиваемом атрибуте.</span><span class="sxs-lookup"><span data-stu-id="037c1-277">In the second declaration, the contract type and metadata are implicit in the customized attribute.</span></span> <span data-ttu-id="037c1-278">В случаях, когда большой объем одинаковых метаданных необходимо применить к множеству частей (например, информация об авторе или авторских правах), использование настраиваемого атрибута позволяет сэкономить много времени и избежать повторений.</span><span class="sxs-lookup"><span data-stu-id="037c1-278">Particularly in cases where a large amount of identical metadata must be applied to many parts (for example, author or copyright information), using a custom attribute can save a lot of time and duplication.</span></span> <span data-ttu-id="037c1-279">Кроме того, для внесения отличий можно создавать деревья наследования настраиваемых атрибутов.</span><span class="sxs-lookup"><span data-stu-id="037c1-279">Further, inheritance trees of custom attributes can be created to allow for variations.</span></span>

<span data-ttu-id="037c1-280">Чтобы создать необязательные метаданные в настраиваемом атрибуте, можно воспользоваться атрибутом `DefaultValue` .</span><span class="sxs-lookup"><span data-stu-id="037c1-280">To create optional metadata in a custom attribute, you can use the `DefaultValue` attribute.</span></span> <span data-ttu-id="037c1-281">При применении к свойству в классе настраиваемых атрибутов этот атрибут указывает, что декорированное свойство является необязательным и может не предоставляться экспортером.</span><span class="sxs-lookup"><span data-stu-id="037c1-281">When this attribute is applied to a property in a custom attribute class, it specifies that the decorated property is optional and does not have to be supplied by an exporter.</span></span> <span data-ttu-id="037c1-282">Если значение свойства не задано, ему назначается значение по умолчанию для данного типа свойства (обычно это `null`, `false`или 0).</span><span class="sxs-lookup"><span data-stu-id="037c1-282">If a value for the property is not supplied, it will be assigned the default value for its property type (usually `null`, `false`, or 0.)</span></span>

<a name="creation_policies"></a>

## <a name="creation-policies"></a><span data-ttu-id="037c1-283">Политики создания</span><span class="sxs-lookup"><span data-stu-id="037c1-283">Creation Policies</span></span>

<span data-ttu-id="037c1-284">Когда часть указывает импорт и выполняется композиция, контейнер композиции пытается найти соответствующий экспорт.</span><span class="sxs-lookup"><span data-stu-id="037c1-284">When a part specifies an import and composition is performed, the composition container attempts to find a matching export.</span></span> <span data-ttu-id="037c1-285">Если он успешно сопоставляет импорт с экспортом, для импортирующего члена устанавливается экземпляр экспортированного объекта.</span><span class="sxs-lookup"><span data-stu-id="037c1-285">If it matches the import with an export successfully, the importing member is set to an instance of the exported object.</span></span> <span data-ttu-id="037c1-286">Источник этого экземпляра контролируется *политикой создания*экспортирующей части.</span><span class="sxs-lookup"><span data-stu-id="037c1-286">Where this instance comes from is controlled by the exporting part's *creation policy*.</span></span>

<span data-ttu-id="037c1-287">Возможны две политики создания — *общая* и *не общая*.</span><span class="sxs-lookup"><span data-stu-id="037c1-287">The two possible creation policies are *shared* and *non-shared*.</span></span> <span data-ttu-id="037c1-288">Часть с общей политикой создания предоставляется для общего доступа всем импортам в контейнере для части с таким контрактом.</span><span class="sxs-lookup"><span data-stu-id="037c1-288">A part with a creation policy of shared will be shared between every import in the container for a part with that contract.</span></span> <span data-ttu-id="037c1-289">Когда подсистема композиции находит соответствие и должна задать импортирующее свойство, она создает экземпляр новой копии этой части, если такая копия еще не существует, в противном случае она предоставляет имеющуюся копию.</span><span class="sxs-lookup"><span data-stu-id="037c1-289">When the composition engine finds a match and has to set an importing property, it will instantiate a new copy of the part only if one does not already exist; otherwise, it will supply the existing copy.</span></span> <span data-ttu-id="037c1-290">Это означает, что несколько объектов могут иметь ссылки на одну часть.</span><span class="sxs-lookup"><span data-stu-id="037c1-290">This means that many objects may have references to the same part.</span></span> <span data-ttu-id="037c1-291">Такие части не должны полагаться на внутреннее состояние, которое может быть изменено из разных мест.</span><span class="sxs-lookup"><span data-stu-id="037c1-291">Such parts should not rely on internal state that might be changed from many places.</span></span> <span data-ttu-id="037c1-292">Эта политика подходит для статических частей, частей, предоставляющих службы, и частей, потребляющих большой объем памяти или других ресурсов.</span><span class="sxs-lookup"><span data-stu-id="037c1-292">This policy is appropriate for static parts, parts that provide services, and parts that consume a lot of memory or other resources.</span></span>

<span data-ttu-id="037c1-293">Часть с политикой создания, не являющейся общей, будет создаваться каждый раз при обнаружении соответствующего импорта для одного из ее экспортов.</span><span class="sxs-lookup"><span data-stu-id="037c1-293">A part with the creation policy of non-shared will be created every time a matching import for one of its exports is found.</span></span> <span data-ttu-id="037c1-294">Таким образом, экземпляр новой копии будет создаваться для каждого импорта в контейнере, соответствующем одному из экспортированных контактов части.</span><span class="sxs-lookup"><span data-stu-id="037c1-294">A new copy will therefore be instantiated for every import in the container that matches one of the part's exported contracts.</span></span> <span data-ttu-id="037c1-295">Внутреннее состояние этих копий не предоставляется для общего доступа.</span><span class="sxs-lookup"><span data-stu-id="037c1-295">The internal state of these copies will not be shared.</span></span> <span data-ttu-id="037c1-296">Эта политика подходит для частей, в которых каждому импорту требуется свое внутреннее состояние.</span><span class="sxs-lookup"><span data-stu-id="037c1-296">This policy is appropriate for parts where each import requires its own internal state.</span></span>

<span data-ttu-id="037c1-297">Политику создания для части может указывать как импорт, так и экспорт, для этого доступны следующие значения: `Shared`, `NonShared`и `Any`.</span><span class="sxs-lookup"><span data-stu-id="037c1-297">Both the import and the export can specify the creation policy of a part, from among the values `Shared`, `NonShared`, or `Any`.</span></span> <span data-ttu-id="037c1-298">По умолчанию как для импортов, так и для экспортов используется `Any` .</span><span class="sxs-lookup"><span data-stu-id="037c1-298">The default is `Any` for both imports and exports.</span></span> <span data-ttu-id="037c1-299">Экспорт, указывающий `Shared` или `NonShared` , будет сопоставлен только с импортом, указывающим то же значение или значение `Any`.</span><span class="sxs-lookup"><span data-stu-id="037c1-299">An export that specifies `Shared` or `NonShared` will only match an import that specifies the same, or that specifies `Any`.</span></span> <span data-ttu-id="037c1-300">Аналогичным образом, импорт, указывающий `Shared` или `NonShared` , будет сопоставлен только с экспортом, указывающим то же значение или значение `Any`.</span><span class="sxs-lookup"><span data-stu-id="037c1-300">Similarly, an import that specifies `Shared` or `NonShared` will only match an export that specifies the same, or that specifies `Any`.</span></span> <span data-ttu-id="037c1-301">Импорты и экспорты с несовместимыми политиками создания соответствием не считаются по аналогии с импортами и экспортами, имеющими разные имена или типы контракта.</span><span class="sxs-lookup"><span data-stu-id="037c1-301">Imports and exports with incompatible creation policies are not considered a match, in the same way as an import and export whose contract name or contract type are not a match.</span></span> <span data-ttu-id="037c1-302">Если как импорт, так и экспорт указывают значение `Any`либо не указывают никакого значения, используя политику создания по умолчанию `Any`, задается общая политика создания.</span><span class="sxs-lookup"><span data-stu-id="037c1-302">If both import and export specify `Any`, or do not specify a creation policy and default to `Any`, the creation policy will default to shared.</span></span>

<span data-ttu-id="037c1-303">В следующем примере показано задание политик создания как импортами, так и экспортами.</span><span class="sxs-lookup"><span data-stu-id="037c1-303">The following example shows both imports and exports specifying creation policies.</span></span> <span data-ttu-id="037c1-304">`PartOne` не задает политику создания, поэтому используется значение по умолчанию `Any`.</span><span class="sxs-lookup"><span data-stu-id="037c1-304">`PartOne` does not specify a creation policy, so the default is `Any`.</span></span> <span data-ttu-id="037c1-305">`PartTwo` не задает политику создания, поэтому используется значение по умолчанию `Any`.</span><span class="sxs-lookup"><span data-stu-id="037c1-305">`PartTwo` does not specify a creation policy, so the default is `Any`.</span></span> <span data-ttu-id="037c1-306">Поскольку как импорт, так и экспорт используют значение по умолчанию `Any`, политика `PartOne` будет общей.</span><span class="sxs-lookup"><span data-stu-id="037c1-306">Since both import and export default to `Any`, `PartOne` will be shared.</span></span> <span data-ttu-id="037c1-307">`PartThree` задает политику создания `Shared` , поэтому `PartTwo` и `PartThree` будут совместно использовать одну копию `PartOne`.</span><span class="sxs-lookup"><span data-stu-id="037c1-307">`PartThree` specifies a `Shared` creation policy, so `PartTwo` and `PartThree` will share the same copy of `PartOne`.</span></span> <span data-ttu-id="037c1-308">`PartFour` задает политику создания `NonShared` , поэтому политика `PartFour` не будет являться общей в `PartFive`.</span><span class="sxs-lookup"><span data-stu-id="037c1-308">`PartFour` specifies a `NonShared` creation policy, so `PartFour` will be non-shared in `PartFive`.</span></span> <span data-ttu-id="037c1-309">`PartSix` задает политику создания `NonShared` .</span><span class="sxs-lookup"><span data-stu-id="037c1-309">`PartSix` specifies a `NonShared` creation policy.</span></span> <span data-ttu-id="037c1-310">`PartFive` и `PartSix` получат отдельные копии `PartFour`.</span><span class="sxs-lookup"><span data-stu-id="037c1-310">`PartFive` and `PartSix` will each receive separate copies of `PartFour`.</span></span> <span data-ttu-id="037c1-311">`PartSeven` задает политику создания `Shared` .</span><span class="sxs-lookup"><span data-stu-id="037c1-311">`PartSeven` specifies a `Shared` creation policy.</span></span> <span data-ttu-id="037c1-312">Поскольку экспортированный `PartFour` с политикой создания `Shared`отсутствует, импорт `PartSeven` не имеет совпадений и не заполняется.</span><span class="sxs-lookup"><span data-stu-id="037c1-312">Because there is no exported `PartFour` with a creation policy of `Shared`, the `PartSeven` import does not match anything and will not be filled.</span></span>

```vb
<Export()>
Public Class PartOne
    'The default creation policy for an export is Any.
End Class

Public Class PartTwo

    <Import()>
    Public Property partOne As PartOne

    'The default creation policy for an import is Any.
    'If both policies are Any, the part will be shared.

End Class

Public Class PartThree

    <Import(RequiredCreationPolicy:=CreationPolicy.Shared)>
    Public Property partOne As PartOne

    'The Shared creation policy is explicitly specified.
    'PartTwo and PartThree will receive references to the
    'SAME copy of PartOne.

End Class

<Export()>
<PartCreationPolicy(CreationPolicy.NonShared)>
Public Class PartFour
    'The NonShared creation policy is explicitly specified.
End Class

Public Class PartFive

    <Import()>
    Public Property partFour As PartFour

    'The default creation policy for an import is Any.
    'Since the export's creation policy was explicitly
    'defined, the creation policy for this property will
    'be non-shared.

End Class

Public Class PartSix

    <Import(RequiredCreationPolicy:=CreationPolicy.NonShared)>
    Public Property partFour As PartFour

    'Both import and export specify matching creation
    'policies.  PartFive and PartSix will each receive
    'SEPARATE copies of PartFour, each with its own
    'internal state.

End Class

Public Class PartSeven

    <Import(RequiredCreationPolicy:=CreationPolicy.Shared)>
    Public Property partFour As PartFour

    'A creation policy mismatch.  Because there is no
    'exported PartFour with a creation policy of Shared,
    'this import does not match anything and will not be
    'filled.

End Class
```

```csharp
[Export]
public class PartOne
{
    //The default creation policy for an export is Any.
}

public class PartTwo
{
    [Import]
    public PartOne partOne { get; set; }

    //The default creation policy for an import is Any.
    //If both policies are Any, the part will be shared.
}

public class PartThree
{
    [Import(RequiredCreationPolicy = CreationPolicy.Shared)]
    public PartOne partOne { get; set; }

    //The Shared creation policy is explicitly specified.
    //PartTwo and PartThree will receive references to the
    //SAME copy of PartOne.
}

[Export]
[PartCreationPolicy(CreationPolicy.NonShared)]
public class PartFour
{
    //The NonShared creation policy is explicitly specified.
}

public class PartFive
{
    [Import]
    public PartFour partFour { get; set; }

    //The default creation policy for an import is Any.
    //Since the export's creation policy was explicitly
    //defined, the creation policy for this property will
    //be non-shared.
}

public class PartSix
{
    [Import(RequiredCreationPolicy = CreationPolicy.NonShared)]
    public PartFour partFour { get; set; }

    //Both import and export specify matching creation
    //policies.  PartFive and PartSix will each receive
    //SEPARATE copies of PartFour, each with its own
    //internal state.
}

public class PartSeven
{
    [Import(RequiredCreationPolicy = CreationPolicy.Shared)]
    public PartFour partFour { get; set; }

    //A creation policy mismatch.  Because there is no
    //exported PartFour with a creation policy of Shared,
    //this import does not match anything and will not be
    //filled.
}
```

<a name="life_cycle_and_disposing"></a>

## <a name="life-cycle-and-disposing"></a><span data-ttu-id="037c1-313">Жизненный цикл и утилизация</span><span class="sxs-lookup"><span data-stu-id="037c1-313">Life Cycle and Disposing</span></span>

<span data-ttu-id="037c1-314">Поскольку части размещаются в контейнере композиции, их жизненный цикл может быть сложнее, чем у обычных объектов.</span><span class="sxs-lookup"><span data-stu-id="037c1-314">Because parts are hosted in the composition container, their life cycle can be more complex than ordinary objects.</span></span> <span data-ttu-id="037c1-315">Части могут реализовать два важных интерфейса, связанных с жизненным циклом: `IDisposable` и `IPartImportsSatisfiedNotification`.</span><span class="sxs-lookup"><span data-stu-id="037c1-315">Parts can implement two important life cycle-related interfaces: `IDisposable` and `IPartImportsSatisfiedNotification`.</span></span>

<span data-ttu-id="037c1-316">Части, которые требуют выполнения операций при завершении работы или освобождают ресурсы, должны реализовать `IDisposable`, как это принято для объектов .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="037c1-316">Parts that require work to be performed at shut down or that need to release resources should implement `IDisposable`, as usual for .NET Framework objects.</span></span> <span data-ttu-id="037c1-317">Однако, поскольку контейнер создает и обслуживает ссылки на части, вызов метода `Dispose` для части должен осуществлять только тот контейнер, которому она принадлежит.</span><span class="sxs-lookup"><span data-stu-id="037c1-317">However, since the container creates and maintains references to parts, only the container that owns a part should call the `Dispose` method on it.</span></span> <span data-ttu-id="037c1-318">Сам контейнер реализует `IDisposable`, а в рамках очистки в `Dispose` он вызывает `Dispose` для всех принадлежащих ему частей.</span><span class="sxs-lookup"><span data-stu-id="037c1-318">The container itself implements `IDisposable`, and as portion of its cleanup in `Dispose` it will call `Dispose` on all the parts that it owns.</span></span> <span data-ttu-id="037c1-319">Поэтому вас следует всегда утилизировать контейнер композиции, когда он и любые принадлежащие ему части больше не нужны.</span><span class="sxs-lookup"><span data-stu-id="037c1-319">For this reason, you should always dispose the composition container when it and any parts it owns are no longer needed.</span></span>

<span data-ttu-id="037c1-320">Для контейнеров композиции с большим временем существования может возникнуть проблема использования памяти, которую вызывают части с политикой создания, не являющейся общей.</span><span class="sxs-lookup"><span data-stu-id="037c1-320">For long-lived composition containers, memory consumption by parts with a creation policy of non-shared can become a problem.</span></span> <span data-ttu-id="037c1-321">Такие не являющиеся общими части могут создаваться несколько раз и не утилизируются до тех пор, пока не будет утилизирован сам контейнер.</span><span class="sxs-lookup"><span data-stu-id="037c1-321">These non-shared parts can be created multiple times and will not be disposed until the container itself is disposed.</span></span> <span data-ttu-id="037c1-322">Для решения данной проблемы контейнер предоставляет метод `ReleaseExport` .</span><span class="sxs-lookup"><span data-stu-id="037c1-322">To deal with this, the container provides the `ReleaseExport` method.</span></span> <span data-ttu-id="037c1-323">Вызов этого метода для не являющегося общим экспорта удаляет данный экспорт из контейнера композиции и утилизирует его.</span><span class="sxs-lookup"><span data-stu-id="037c1-323">Calling this method on a non-shared export removes that export from the composition container and disposes it.</span></span> <span data-ttu-id="037c1-324">Части, используемые только этим удаленным экспортом, и все вложенные элементы также удаляются и утилизируются.</span><span class="sxs-lookup"><span data-stu-id="037c1-324">Parts that are used only by the removed export, and so on down the tree, are also removed and disposed.</span></span> <span data-ttu-id="037c1-325">Это позволяет освободить ресурсы без утилизации всего контейнера композиции.</span><span class="sxs-lookup"><span data-stu-id="037c1-325">In this way, resources can be reclaimed without disposing the composition container itself.</span></span>

<span data-ttu-id="037c1-326">`IPartImportsSatisfiedNotification` содержит один метод с именем `OnImportsSatisfied`.</span><span class="sxs-lookup"><span data-stu-id="037c1-326">`IPartImportsSatisfiedNotification` contains one method named `OnImportsSatisfied`.</span></span> <span data-ttu-id="037c1-327">Этот метод вызывается контейнером композиции для любых частей, реализующих интерфейс, когда композиция уже завершена, а импорты части готовы к использованию.</span><span class="sxs-lookup"><span data-stu-id="037c1-327">This method is called by the composition container on any parts that implement the interface when composition has been completed and the part's imports are ready for use.</span></span> <span data-ttu-id="037c1-328">Части создаются подсистемой композиции для заполнения импортов других частей.</span><span class="sxs-lookup"><span data-stu-id="037c1-328">Parts are created by the composition engine to fill the imports of other parts.</span></span> <span data-ttu-id="037c1-329">До установки импортов части вы не можете выполнять никакую инициализацию, которая основана на импортированных значениях в конструкторе частей или выполняет операции с ними, если только эти значения не были указаны в качестве необходимых условий с помощью атрибута `ImportingConstructor` .</span><span class="sxs-lookup"><span data-stu-id="037c1-329">Before the imports of a part have been set, you cannot perform any initialization that relies on or manipulates imported values in the part constructor unless those values have been specified as prerequisites by using the `ImportingConstructor` attribute.</span></span> <span data-ttu-id="037c1-330">В общем случае этот метод является предпочтительным, но иногда внедрение конструктора может быть недоступно.</span><span class="sxs-lookup"><span data-stu-id="037c1-330">This is normally the preferred method, but in some cases, constructor injection may not be available.</span></span> <span data-ttu-id="037c1-331">В таких ситуациях инициализацию можно выполнить в `OnImportsSatisfied`, при этом часть должна реализовать `IPartImportsSatisfiedNotification`.</span><span class="sxs-lookup"><span data-stu-id="037c1-331">In those cases, initialization can be performed in `OnImportsSatisfied`, and the part should implement `IPartImportsSatisfiedNotification`.</span></span>

## <a name="see-also"></a><span data-ttu-id="037c1-332">См. также</span><span class="sxs-lookup"><span data-stu-id="037c1-332">See also</span></span>

- [<span data-ttu-id="037c1-333">Видео канала 9. Open Up Your Applications with the Managed Extensibility Framework (Раскройте потенциал своих приложений с помощью Managed Extensibility Framework)</span><span class="sxs-lookup"><span data-stu-id="037c1-333">Channel 9 Video: Open Up Your Applications with the Managed Extensibility Framework</span></span>](https://channel9.msdn.com/events/TechEd/NorthAmerica/2009/DTL328)
- [<span data-ttu-id="037c1-334">Видео канала 9. Managed Extensibility Framework (MEF) 2.0</span><span class="sxs-lookup"><span data-stu-id="037c1-334">Channel 9 Video: Managed Extensibility Framework (MEF) 2.0</span></span>](https://channel9.msdn.com/posts/NET-45-Oleg-Lvovitch-and-Kevin-Ransom-Managed-Extensibility-Framework-MEF-20)

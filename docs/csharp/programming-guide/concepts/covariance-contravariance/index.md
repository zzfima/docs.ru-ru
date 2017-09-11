---
title: "Ковариация и контравариантность (C#)"
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
ms.assetid: 066d9a3c-aab7-4ea6-826d-0b1a85399c74
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
ms.openlocfilehash: e1282f84171fa75db9656634a83f7cd5d4b9ac82
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="covariance-and-contravariance-c"></a><span data-ttu-id="7fb81-102">Ковариация и контравариантность (C#)</span><span class="sxs-lookup"><span data-stu-id="7fb81-102">Covariance and Contravariance (C#)</span></span>
<span data-ttu-id="7fb81-103">В C# ковариация и контрвариантность позволяют использовать неявное преобразование ссылок для типов массивов и делегатов, а также для аргументов универсального типа.</span><span class="sxs-lookup"><span data-stu-id="7fb81-103">In C#, covariance and contravariance enable implicit reference conversion for array types, delegate types, and generic type arguments.</span></span> <span data-ttu-id="7fb81-104">Ковариация сохраняет совместимость присваивания, а при контрвариантности присваивание начинает работать противоположным образом.</span><span class="sxs-lookup"><span data-stu-id="7fb81-104">Covariance preserves assignment compatibility and contravariance reverses it.</span></span>  
  
 <span data-ttu-id="7fb81-105">Следующий код показывает разницу между совместимостью присваивания, ковариацией и контрвариантностью.</span><span class="sxs-lookup"><span data-stu-id="7fb81-105">The following code demonstrates the difference between assignment compatibility, covariance, and contravariance.</span></span>  
  
```csharp  
// Assignment compatibility.   
string str = "test";  
// An object of a more derived type is assigned to an object of a less derived type.   
object obj = str;  
  
// Covariance.   
IEnumerable<string> strings = new List<string>();  
// An object that is instantiated with a more derived type argument   
// is assigned to an object instantiated with a less derived type argument.   
// Assignment compatibility is preserved.   
IEnumerable<object> objects = strings;  
  
// Contravariance.             
// Assume that the following method is in the class:   
// static void SetObject(object o) { }   
Action<object> actObject = SetObject;  
// An object that is instantiated with a less derived type argument   
// is assigned to an object instantiated with a more derived type argument.   
// Assignment compatibility is reversed.   
Action<string> actString = actObject;  
```  
  
 <span data-ttu-id="7fb81-106">Ковариация для массивов позволяет неявно преобразовать массив более производного типа в массив менее производного типа.</span><span class="sxs-lookup"><span data-stu-id="7fb81-106">Covariance for arrays enables implicit conversion of an array of a more derived type to an array of a less derived type.</span></span> <span data-ttu-id="7fb81-107">Но эта операция не является типобезопасной, как показано в следующем примере кода.</span><span class="sxs-lookup"><span data-stu-id="7fb81-107">But this operation is not type safe, as shown in the following code example.</span></span>  
  
```csharp  
object[] array = new String[10];  
// The following statement produces a run-time exception.  
// array[0] = 10;  
```  
  
 <span data-ttu-id="7fb81-108">Поддержка ковариации и контрвариантности для групп методов позволяет сопоставить сигнатуры методов с типами делегатов.</span><span class="sxs-lookup"><span data-stu-id="7fb81-108">Covariance and contravariance support for method groups allows for matching method signatures with delegate types.</span></span> <span data-ttu-id="7fb81-109">За счет этого вы можете назначать делегатам не только методы с совпадающими сигнатурами, но и методы, которые возвращают более производные типы (ковариация) или принимают параметры с менее производными типами (контрвариантность), чем задает тип делегата.</span><span class="sxs-lookup"><span data-stu-id="7fb81-109">This enables you to assign to delegates not only methods that have matching signatures, but also methods that return more derived types (covariance) or that accept parameters that have less derived types (contravariance) than that specified by the delegate type.</span></span> <span data-ttu-id="7fb81-110">Дополнительные сведения см. в разделах [Вариативность в делегатах (C#)](../../../../csharp/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md) и [Использование вариативности в делегатах (C#)](../../../../csharp/programming-guide/concepts/covariance-contravariance/using-variance-in-delegates.md).</span><span class="sxs-lookup"><span data-stu-id="7fb81-110">For more information, see [Variance in Delegates (C#)](../../../../csharp/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md) and [Using Variance in Delegates (C#)](../../../../csharp/programming-guide/concepts/covariance-contravariance/using-variance-in-delegates.md).</span></span>  
  
 <span data-ttu-id="7fb81-111">В следующем примере кода демонстрируется поддержка ковариации и контрвариантности для групп методов.</span><span class="sxs-lookup"><span data-stu-id="7fb81-111">The following code example shows covariance and contravariance support for method groups.</span></span>  
  
```csharp  
static object GetObject() { return null; }  
static void SetObject(object obj) { }  
  
static string GetString() { return ""; }  
static void SetString(string str) { }  
  
static void Test()  
{  
    // Covariance. A delegate specifies a return type as object,  
    // but you can assign a method that returns a string.  
    Func<object> del = GetString;  
  
    // Contravariance. A delegate specifies a parameter type as string,  
    // but you can assign a method that takes an object.  
    Action<string> del2 = SetObject;  
}  
```  
  
 <span data-ttu-id="7fb81-112">В .NET Framework 4 и более поздних версиях язык C# поддерживает ковариацию и контрвариантность для универсальных интерфейсов и делегатов, а также позволяет выполнять неявное преобразование параметров универсального типа.</span><span class="sxs-lookup"><span data-stu-id="7fb81-112">In .NET Framework 4 or newer C# supports covariance and contravariance in generic interfaces and delegates and allows for implicit conversion of generic type parameters.</span></span> <span data-ttu-id="7fb81-113">Дополнительные сведения см. в разделах [Вариативность в универсальных интерфейсах (C#)](../../../../csharp/programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md) и [Вариативность в делегатах (C#)](../../../../csharp/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md).</span><span class="sxs-lookup"><span data-stu-id="7fb81-113">For more information, see [Variance in Generic Interfaces (C#)](../../../../csharp/programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md) and [Variance in Delegates (C#)](../../../../csharp/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md).</span></span>  
  
 <span data-ttu-id="7fb81-114">В следующем примере кода показано неявное преобразование ссылок для универсальных интерфейсов.</span><span class="sxs-lookup"><span data-stu-id="7fb81-114">The following code example shows implicit reference conversion for generic interfaces.</span></span>  
  
```csharp  
IEnumerable<String> strings = new List<String>();  
IEnumerable<Object> objects = strings;  
```  
  
 <span data-ttu-id="7fb81-115">Универсальный интерфейс или делегат называется *вариантным*, если его универсальные параметры объявлены ковариантными или контрвариантными.</span><span class="sxs-lookup"><span data-stu-id="7fb81-115">A generic interface or delegate is called *variant* if its generic parameters are declared covariant or contravariant.</span></span> <span data-ttu-id="7fb81-116">C# позволяет вам создавать собственные вариантные интерфейсы и делегаты.</span><span class="sxs-lookup"><span data-stu-id="7fb81-116">C# enables you to create your own variant interfaces and delegates.</span></span> <span data-ttu-id="7fb81-117">Дополнительные сведения см. в разделах [Создание вариантных универсальных интерфейсов (C#)](../../../../csharp/programming-guide/concepts/covariance-contravariance/creating-variant-generic-interfaces.md) и [Вариативность в делегатах (C#)](../../../../csharp/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md).</span><span class="sxs-lookup"><span data-stu-id="7fb81-117">For more information, see [Creating Variant Generic Interfaces (C#)](../../../../csharp/programming-guide/concepts/covariance-contravariance/creating-variant-generic-interfaces.md) and [Variance in Delegates (C#)](../../../../csharp/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md).</span></span>  
  
## <a name="related-topics"></a><span data-ttu-id="7fb81-118">См. также</span><span class="sxs-lookup"><span data-stu-id="7fb81-118">Related Topics</span></span>  
  
|<span data-ttu-id="7fb81-119">Заголовок</span><span class="sxs-lookup"><span data-stu-id="7fb81-119">Title</span></span>|<span data-ttu-id="7fb81-120">Описание</span><span class="sxs-lookup"><span data-stu-id="7fb81-120">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="7fb81-121">Вариативность в универсальных интерфейсах (C#)</span><span class="sxs-lookup"><span data-stu-id="7fb81-121">Variance in Generic Interfaces (C#)</span></span>](../../../../csharp/programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md)|<span data-ttu-id="7fb81-122">В этом разделе описываются ковариация и контрвариация в универсальных интерфейсах, а также представлен список вариативных универсальных интерфейсов платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="7fb81-122">Discusses covariance and contravariance in generic interfaces and provides a list of variant generic interfaces in the .NET Framework.</span></span>|  
|[<span data-ttu-id="7fb81-123">Создание вариантных универсальных интерфейсов (C#)</span><span class="sxs-lookup"><span data-stu-id="7fb81-123">Creating Variant Generic Interfaces (C#)</span></span>](../../../../csharp/programming-guide/concepts/covariance-contravariance/creating-variant-generic-interfaces.md)|<span data-ttu-id="7fb81-124">Узнайте, как создавать ваши собственные вариантные интерфейсы.</span><span class="sxs-lookup"><span data-stu-id="7fb81-124">Shows how to create custom variant interfaces.</span></span>|  
|[<span data-ttu-id="7fb81-125">Использование вариативности в интерфейсах для универсальных коллекций (C#)</span><span class="sxs-lookup"><span data-stu-id="7fb81-125">Using Variance in Interfaces for Generic Collections (C#)</span></span>](../../../../csharp/programming-guide/concepts/covariance-contravariance/using-variance-in-interfaces-for-generic-collections.md)|<span data-ttu-id="7fb81-126">Узнайте, как использовать поддержку ковариации и контрвариантности в интерфейсах <xref:System.Collections.Generic.IEnumerable%601> и <xref:System.IComparable%601> для многократного использования кода.</span><span class="sxs-lookup"><span data-stu-id="7fb81-126">Shows how covariance and contravariance support in the <xref:System.Collections.Generic.IEnumerable%601> and <xref:System.IComparable%601> interfaces can help you reuse code.</span></span>|  
|[<span data-ttu-id="7fb81-127">Вариативность в делегатах (C#)</span><span class="sxs-lookup"><span data-stu-id="7fb81-127">Variance in Delegates (C#)</span></span>](../../../../csharp/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md)|<span data-ttu-id="7fb81-128">Раздел описывает ковариацию и контрвариантность в универсальных и неуниверсальных делегатах, а также приводит список вариантных универсальных делегатов в платформе .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="7fb81-128">Discusses covariance and contravariance in generic and non-generic delegates and provides a list of variant generic delegates in the .NET Framework.</span></span>|  
|[<span data-ttu-id="7fb81-129">Использование вариативности в делегатах (C#)</span><span class="sxs-lookup"><span data-stu-id="7fb81-129">Using Variance in Delegates (C#)</span></span>](../../../../csharp/programming-guide/concepts/covariance-contravariance/using-variance-in-delegates.md)|<span data-ttu-id="7fb81-130">Узнайте, как использовать поддержку ковариации и контрвариантности в неуниверсальных делегатах для сопоставления сигнатур методов с типами делегатов.</span><span class="sxs-lookup"><span data-stu-id="7fb81-130">Shows how to use covariance and contravariance support in non-generic delegates to match method signatures with delegate types.</span></span>|  
|[<span data-ttu-id="7fb81-131">Использование вариативности в универсальных методах-делегатах Func и Action (C#)</span><span class="sxs-lookup"><span data-stu-id="7fb81-131">Using Variance for Func and Action Generic Delegates (C#)</span></span>](../../../../csharp/programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md)|<span data-ttu-id="7fb81-132">Узнайте, как использовать поддержку ковариации и контрвариантности в делегатах `Func` и `Action` для многократного использования кода.</span><span class="sxs-lookup"><span data-stu-id="7fb81-132">Shows how covariance and contravariance support in the `Func` and `Action` delegates can help you reuse code.</span></span>|


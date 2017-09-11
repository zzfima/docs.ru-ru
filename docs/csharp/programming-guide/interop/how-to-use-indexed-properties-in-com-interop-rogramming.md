---
title: "Практическое руководство. Использование индексированных свойств в программировании COM-взаимодействия (Руководство по программированию на C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- indexed properties [C#]
- Office programming [C#], indexed properties
- properties [C#], indexed
ms.assetid: 756bfc1e-7c28-4d4d-b114-ac9288c73882
caps.latest.revision: 20
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
ms.openlocfilehash: 19e620415adefd6190d3896377eaf6a7cf944f28
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-use-indexed-properties-in-com-interop-programming-c-programming-guide"></a><span data-ttu-id="a8ff1-102">Практическое руководство. Использование индексированных свойств в программировании COM-взаимодействия (Руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="a8ff1-102">How to: Use Indexed Properties in COM Interop Programming (C# Programming Guide)</span></span>
<span data-ttu-id="a8ff1-103">*Индексированные свойства* делают использование свойств COM с параметрами при программировании на C# более удобным.</span><span class="sxs-lookup"><span data-stu-id="a8ff1-103">*Indexed properties* improve the way in which COM properties that have parameters are consumed in C# programming.</span></span> <span data-ttu-id="a8ff1-104">Индексированные свойства используются совместно с другими компонентами, представленными в Visual C#, например [именованными и необязательными аргументами](../../../csharp/programming-guide/classes-and-structs/named-and-optional-arguments.md), новым типом ([dynamic](../../../csharp/language-reference/keywords/dynamic.md)) и [внедренными сведениями о типах](../../../csharp/programming-guide/concepts/assemblies-gac/walkthrough-embedding-types-from-managed-assemblies-in-visual-studio.md) для расширения возможностей программирования для Microsoft Office.</span><span class="sxs-lookup"><span data-stu-id="a8ff1-104">Indexed properties work together with other features in Visual C#, such as [named and optional arguments](../../../csharp/programming-guide/classes-and-structs/named-and-optional-arguments.md), a new type ([dynamic](../../../csharp/language-reference/keywords/dynamic.md)), and [embedded type information](../../../csharp/programming-guide/concepts/assemblies-gac/walkthrough-embedding-types-from-managed-assemblies-in-visual-studio.md), to enhance Microsoft Office programming.</span></span>  
  
 <span data-ttu-id="a8ff1-105">В более ранних версиях C# методы доступны как свойства только при условии, что у метода `get` нет параметров, а у метода `set` есть только один параметр значения.</span><span class="sxs-lookup"><span data-stu-id="a8ff1-105">In earlier versions of C#, methods are accessible as properties only if the `get` method has no parameters and the `set` method has one and only one value parameter.</span></span> <span data-ttu-id="a8ff1-106">Однако не все свойства COM удовлетворяют этим ограничениям.</span><span class="sxs-lookup"><span data-stu-id="a8ff1-106">However, not all COM properties meet those restrictions.</span></span> <span data-ttu-id="a8ff1-107">Например, свойство [Range](http://go.microsoft.com/fwlink/?LinkId=166053) Excel имеет метод доступа `get`, которому требуется параметр для имени диапазона.</span><span class="sxs-lookup"><span data-stu-id="a8ff1-107">For example, the Excel [Range](http://go.microsoft.com/fwlink/?LinkId=166053) property has a `get` accessor that requires a parameter for the name of the range.</span></span> <span data-ttu-id="a8ff1-108">Раньше из-за отсутствия возможности прямого обращения к свойству `Range` приходилось использовать вместо этого метод `get_Range`, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="a8ff1-108">In the past, because you could not access the `Range` property directly, you had to use the `get_Range` method instead, as shown in the following example.</span></span>  
  
 <span data-ttu-id="a8ff1-109">[!code-cs[csProgGuideIndexedProperties#1](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-use-indexed-properties-in-com-interop-rogramming_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="a8ff1-109">[!code-cs[csProgGuideIndexedProperties#1](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-use-indexed-properties-in-com-interop-rogramming_1.cs)]</span></span>  
  
 <span data-ttu-id="a8ff1-110">Индексированные свойства позволяют вместо этого использовать следующий код:</span><span class="sxs-lookup"><span data-stu-id="a8ff1-110">Indexed properties enable you to write the following instead:</span></span>  
  
 <span data-ttu-id="a8ff1-111">[!code-cs[csProgGuideIndexedProperties#2](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-use-indexed-properties-in-com-interop-rogramming_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="a8ff1-111">[!code-cs[csProgGuideIndexedProperties#2](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-use-indexed-properties-in-com-interop-rogramming_2.cs)]</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a8ff1-112">В предыдущем примере также используются [необязательные аргументы](../../../csharp/programming-guide/classes-and-structs/named-and-optional-arguments.md), которые позволяют опустить `Type.Missing`.</span><span class="sxs-lookup"><span data-stu-id="a8ff1-112">The previous example also uses the [optional arguments](../../../csharp/programming-guide/classes-and-structs/named-and-optional-arguments.md) feature, which enables you to omit `Type.Missing`.</span></span>  
  
 <span data-ttu-id="a8ff1-113">Аналогичным образом, чтобы задать значение свойства `Value` объекта [Range](https://msdn.microsoft.com/library/microsoft.office.interop.excel.range.aspx) в Visual C# 2008 и более ранних версиях, требуется два аргумента.</span><span class="sxs-lookup"><span data-stu-id="a8ff1-113">Similarly to set the value of the `Value` property of a [Range](https://msdn.microsoft.com/library/microsoft.office.interop.excel.range.aspx) object in Visual C# 2008 and earlier, two arguments are required.</span></span> <span data-ttu-id="a8ff1-114">Один предоставляет аргумент для необязательного параметра, указывающего тип значения диапазона.</span><span class="sxs-lookup"><span data-stu-id="a8ff1-114">One supplies an argument for an optional parameter that specifies the type of the range value.</span></span> <span data-ttu-id="a8ff1-115">Другой предоставляет значение для свойства `Value`.</span><span class="sxs-lookup"><span data-stu-id="a8ff1-115">The other supplies the value for the `Value` property.</span></span> <span data-ttu-id="a8ff1-116">Эти методы показаны в следующих примерах.</span><span class="sxs-lookup"><span data-stu-id="a8ff1-116">The following examples illustrate these techniques.</span></span> <span data-ttu-id="a8ff1-117">В примерах ячейке A1 задается значение `Name`.</span><span class="sxs-lookup"><span data-stu-id="a8ff1-117">Both set the value of the A1 cell to `Name`.</span></span>
  
 <span data-ttu-id="a8ff1-118">[!code-cs[csProgGuideIndexedProperties#3](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-use-indexed-properties-in-com-interop-rogramming_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="a8ff1-118">[!code-cs[csProgGuideIndexedProperties#3](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-use-indexed-properties-in-com-interop-rogramming_3.cs)]</span></span>  
  
 <span data-ttu-id="a8ff1-119">Индексированные свойства позволяют вместо этого использовать следующий код.</span><span class="sxs-lookup"><span data-stu-id="a8ff1-119">Indexed properties enable you to write the following code instead.</span></span>  
  
 <span data-ttu-id="a8ff1-120">[!code-cs[csProgGuideIndexedProperties#4](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-use-indexed-properties-in-com-interop-rogramming_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="a8ff1-120">[!code-cs[csProgGuideIndexedProperties#4](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-use-indexed-properties-in-com-interop-rogramming_4.cs)]</span></span>  
  
 <span data-ttu-id="a8ff1-121">Разработчики не могут создавать собственные индексированные свойства.</span><span class="sxs-lookup"><span data-stu-id="a8ff1-121">You cannot create indexed properties of your own.</span></span> <span data-ttu-id="a8ff1-122">Эта возможность поддерживает только использование имеющихся индексированных свойств.</span><span class="sxs-lookup"><span data-stu-id="a8ff1-122">The feature only supports consumption of existing indexed properties.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a8ff1-123">Пример</span><span class="sxs-lookup"><span data-stu-id="a8ff1-123">Example</span></span>  
 <span data-ttu-id="a8ff1-124">Ниже приведен полный пример кода.</span><span class="sxs-lookup"><span data-stu-id="a8ff1-124">The following code shows a complete example.</span></span> <span data-ttu-id="a8ff1-125">Дополнительные сведения о создании проекта, обращающегося к Office API, см. в разделе [Практическое руководство. Доступ к объектам взаимодействия Office с помощью функций языка Visual C#](../../../csharp/programming-guide/interop/how-to-access-office-onterop-objects.md).</span><span class="sxs-lookup"><span data-stu-id="a8ff1-125">For more information about how to set up a project that accesses the Office API, see [How to: Access Office Interop Objects by Using Visual C# Features](../../../csharp/programming-guide/interop/how-to-access-office-onterop-objects.md).</span></span>  
  
 <span data-ttu-id="a8ff1-126">[!code-cs[csProgGuideIndexedProperties#5](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-use-indexed-properties-in-com-interop-rogramming_5.cs)]</span><span class="sxs-lookup"><span data-stu-id="a8ff1-126">[!code-cs[csProgGuideIndexedProperties#5](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-use-indexed-properties-in-com-interop-rogramming_5.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8ff1-127">См. также</span><span class="sxs-lookup"><span data-stu-id="a8ff1-127">See Also</span></span>  
 <span data-ttu-id="a8ff1-128">[Именованные и необязательные аргументы](../../../csharp/programming-guide/classes-and-structs/named-and-optional-arguments.md) </span><span class="sxs-lookup"><span data-stu-id="a8ff1-128">[Named and Optional Arguments](../../../csharp/programming-guide/classes-and-structs/named-and-optional-arguments.md) </span></span>  
 <span data-ttu-id="a8ff1-129">[Динамический](../../../csharp/language-reference/keywords/dynamic.md) </span><span class="sxs-lookup"><span data-stu-id="a8ff1-129">[dynamic](../../../csharp/language-reference/keywords/dynamic.md) </span></span>  
 <span data-ttu-id="a8ff1-130">[Использование типа dynamic](../../../csharp/programming-guide/types/using-type-dynamic.md) </span><span class="sxs-lookup"><span data-stu-id="a8ff1-130">[Using Type dynamic](../../../csharp/programming-guide/types/using-type-dynamic.md) </span></span>  
 <span data-ttu-id="a8ff1-131">[Практическое руководство. Использование именованных и необязательных аргументов в программировании приложений Office](../../../csharp/programming-guide/classes-and-structs/how-to-use-named-and-optional-arguments-in-office-programming.md) </span><span class="sxs-lookup"><span data-stu-id="a8ff1-131">[How to: Use Named and Optional Arguments in Office Programming](../../../csharp/programming-guide/classes-and-structs/how-to-use-named-and-optional-arguments-in-office-programming.md) </span></span>  
 <span data-ttu-id="a8ff1-132">[Практическое руководство. Доступ к объектам взаимодействия Office с помощью функций языка Visual C#](../../../csharp/programming-guide/interop/how-to-access-office-onterop-objects.md) </span><span class="sxs-lookup"><span data-stu-id="a8ff1-132">[How to: Access Office Interop Objects by Using Visual C# Features](../../../csharp/programming-guide/interop/how-to-access-office-onterop-objects.md) </span></span>  
 <span data-ttu-id="a8ff1-133">[Walkthrough: Office Programming](../../../csharp/programming-guide/interop/walkthrough-office-programming.md) (Пошаговое руководство. Программирование приложений Office)</span><span class="sxs-lookup"><span data-stu-id="a8ff1-133">[Walkthrough: Office Programming](../../../csharp/programming-guide/interop/walkthrough-office-programming.md)</span></span>

